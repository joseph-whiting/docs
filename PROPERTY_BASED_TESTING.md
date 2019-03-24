# Property Based Testing

Property based testing is a testing philosophy. It can be applied to unit tests or integration tests. It aims for produce more meaningful and thorough tests, which have to be changed less when implementations change. There are several libraries that help with it.

## Ramble

Testing is good because it forces us to consume our own APIs (dog-fooding). It also allows us to prove to ourselves (and others) that the code does what we think it does.

In a functional context "does what we think it does" isn't really what we mean - we don't care about the implementation, but we do care about certain things being true for the output given certain things about the input. We call these things __properties__.

Taking sorting a list of object by a given key (ascending) as an example, we can think of several properties that should be satisfied by the output:

- it should have the same number of objects as the input
- it should have the same elements as the input, notice this implied the above
- the key of any element should be less than or equal to that of the element after it (if it exists), and more than or equal to that of the element before it (if it exists)

If any of the above weren't satisfied, we wouldn't consider the list sorted! Conversely, they are the sorts of properties anyone consuming the output (using thr API) would assume.

A traditional approach to testing a sort function might be to make a load of lists, and make sorted versions of them, and then compare the expected to the output of the code. That's pretty good, but property based testing can do better.

Another property that is sometimes relevent in such sorting algorithms is __stability__. Such an algorithm is stable if it will always leave two objects with the same key value in the same order as they were in the input. Some sorting algorithms are not stable (such as quicksort). Suppose we don't really care about stability. If we happen to use a naive stable sorting implementation to begin with (eg. shell sort) then the expected lists we write will assume that stability.

Suppose we then change the implementation to quicksort for efficiency. Quicksort is unstable, so we might get failing tests despite the fact we didn't break anything we cared about!

In property based testing we could again have a big list of input lists, but instead of having expected results - we would just write code to check that the properties we care about hold (preserving the elements, correct ordering of keys). Then when the implementation changes to become unstable, nothing will fail - because the things we care about are still true!

This approach also means that we could build up a enourmous collection of input lists for testing, and we would expect the properties to hold for all the outputs produced from them. Most property based testing frameworks have support for this built in - we can ask for lists of objects of a given shape and they will give us loads of automatically generated test cases. In general they are inclined to produce plenty of the edge cases - null values, empty lists, MaxInt etc. This means we don't have to waste our own time constructing boring test cases - the computer can do a much more thorough job! Despite making our tests in a sense looser, we will often catch more bugs by trying a lot more cases.

Property based testing __is__ possible in a non-functional context, it's just usually a little bit more tricky. There are libraries for it in .NET, Scala, Javascript and Haskell.