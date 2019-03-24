# Scala

Scala was first published in 2003 by Martin Odersky - who previously wrote a lot of the Java compiler `javac`.

- It's staticly typed
- It supports object-oriented and functional features
- It allows for imperitive programming but encourages a functional approach
- It compiles to JVM bytecode or to Javascript
- It has a syntax that has evolved from Java but is now a lot more concise and powerful
- The Scala community is good, and there are some very good open-source libraries in the ecosystem

## Functional Programming

Functional programming has been around in academic and limited commercial contexts for ages, but is now becoming a lot more mainstream.

The key idea is to make code comprised of functions that take in inputs and produce outputs that only depend on the inputs. Thus the developer no longer needs to think about the state of the program (such as property/variable values) to know how a function will behave. This reduces the number of things a developer has to think about at any one time, and makes it much easier not to miss things!

Functional programming also helps with code reuse, meaningful error handling, writing good quality tests and making code much easier for new developers to understand.

Parrallelism and threading are often pain points for applications. Functional programming handles parrallelism a lot better.

The book "Functional Programming in Scala" (available in Safari Books) is a bit of a bible in this field which is also approachable to anyone with a little coding experience. The first couple of chapters illustrate really nicely some of the benefits of a functional approach.

Functional Programming is not magic: it's a strategy for building low-bug, maintainable and expandable software. It's viewed by some as the logical conclusion of "clean code" and OOP practices.

## Scala in the Real World

Scala is probably the most widely commercially used functional programming language - because it provides an easy on-ramp from Java for organisations and developers. There is decent support for Scala in Eclipse and IntelliJ IDEA, and in Vim, Emacs, Sublime, VSCode and Atom via ENSIME.

Scala is the language that Apache Spark was written in. The R&D team at Quantexa work almost exclusively with it. It's in use at Apple, LinkedIn and Twitter.