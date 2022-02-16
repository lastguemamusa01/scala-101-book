# scala-101-book


Scala is unique. It is a multi-paradigm programming language that combines both functional and object-oriented languages

## part 1 - Scala: the basics

If you have existing Java applications and are looking for a language that will improve your productivity and at the same time reuse your existing Java codebase, you’ll like Scala’s Java integration and the fact that Scala runs on the JVM platform.

To understand and benefit from Scala collections, you need to know two concepts: type parameterization and higher-order functions. Type parameterization allows you to create types that take another type as a parameter (similar to Java generics). Higher-order functions let you create functions that take other functions as parame- ters. These two concepts allow you to create generic and reusable components, like Scala collections.

A recent addition to the collection library is parallel collections. Scala par- allel collections allow you to solve data parallelism problems in Scala with ease.

### Why Scala?

Scala is a general-purpose programming language that runs on Java Virtual Machine (JVM) and .NET platforms.

Among the heap of programming languages like Groovy, Ruby, Clojure, Erlang, and F#, why should you learn Scala?

Scala is. It’s a feature-rich language that’s used in various types of applications, starting with building a large messaging layer for social networking sites such as Twitter to creating an application build tool like SBT(Simple Build Tool). Because of this scala-bility, the name of the language is Scala.

Scala is one of those rare languages that successfully integrates both object-oriented and functional lan- guage features. This makes Scala powerful because it gives you more in your toolbox to solve programming problems.

#### What’s Scala?

Scala is a general-purpose programming language designed to express common pro- gramming patterns in a concise, elegant, and type-safe way. It smoothly integrates fea- tures of object-oriented and functional programming languages, enabling programmers to be more productive. Martin Odersky (the creator of Scala) and his team started development on Scala in 2001 in the programming methods laboratory at EPFL (École Polytechnique Fédérale de Lausanne). Scala made its public debut in January 2004 on the JVM platform and a few months later on the .NET platform.

scala on .net has some support issues, that need convert java  to .net library.

#### Scala as an object-oriented language

Think of objects as data structures that consist of fields and methods. Object orientation helps to provide structure to your application using classes and objects. It also facilitates composition so you can create large applications from smaller building blocks.

What makes a language purely object-oriented? Although the exact definition of the term depends on whom you ask, most will agree a pure object-oriented language should have the following characteristics:

* Encapsulation/information hiding.
* Inheritance.
* Polymorphism/dynamic binding.
* All predefined types are objects.
* All operations are performed by sending messages to objects.
* All user-defined types are objects.

Scala supports all these qualities and uses a pure object-oriented model similar to that of Smalltalk (a pure object-oriented language created by Alan Kay around 1980), where every value is an object, and every operation is a message send.

1+2

In Scala this expression is interpreted as 1.+(2) by the Scala compiler. That means you’re invoking a + operation on an integer object (in this case, 1) by passing 2 as a parameter.

Scala treats operator names like ordinary identifiers. An identifier in Scala is either a sequence of letters and digits starting with a letter or a sequence of operator characters. In addition to +, it’s possible to define methods like <=, -, or *.

Along with the pure object-oriented features, Scala has made some innovations on OOP space:

* Modular mixin composition — This feature of Scala has traits in common with both Java interfaces and abstract classes. You can define contracts using one or more traits and provide implementations for some or all of the methods.
* Self-type — A mixin doesn’t depend on any methods or fields of the class that it’s mixed into, but sometimes it’s useful to use fields or methods of the class it’s mixed into, and this feature of Scala is called self-type.
* Type abstraction — There are two principle forms of abstraction in programming languages: parameterization and abstract members. Scala supports both forms of abstraction uniformly for types and values.

DEFINITION A mixin is a class that provides certain functionality to be inher- ited by a subclass and isn’t meant for instantiation by itself. A mixin could also be viewed as an interface with implemented methods.

#### Scala as a functional language

Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids state and mutable data.

Mutable vs. immutable data

An object is called mutable when you can alter the contents of the object if you have a reference to it. In the case of an immutable object, the contents of the object can’t be altered if you have a reference to it.

It’s easy to create a mutable object; all you have to do is provide access to the muta- ble state of the object. The disadvantage of mutable objects is keeping track of the changes. In a multithreaded environment you need lock/synchronization techniques to avoid concurrent access. For immutable objects, you don’t have to worry about these situations.

Functional programming takes more of a mathematical view of the world, where pro- grams are composed of functions that take certain input and produce values and pos- sibly other functions. The building blocks of functional programming are neither objects nor procedures (C programming style) but functions. The simple definition of functional programming is programming with functions.

It’s important to understand what is meant by function here. A function relates every value of the domain (the input) to exactly one value of the codomain (the out- put). 

Another aspect of functional program- ming is that it doesn’t have side effects or mutability. The benefits of not having mutability and side effects in functional programs are that the programs are much easier to understand (it has no side effects), reason about, and test because the activity of the function is completely local and it has no external effects. Another huge benefit of functional programming is ease of concurrent programming. Concur- rency becomes a nonissue because there’s no change (immutability) to coordinate between processes or threads.


Functional programming languages that support this style of programming provide at least some of the following features:

* Higher-order functions (chapter 4)
* Lexical closures (chapter 3)
* Pattern matching (chapters 2 and 3)
* Single assignment (chapter 2)
* Lazy evaluation (chapter 2)
* Type inference (chapter 2)
* Tail call optimization (chapter 5)
* List comprehensions (chapters 2 and 4)
* Mondadic effects (chapter 5)

The function associates each element in the domain with exactly one element in the codomain. For example, f(x) = y could be interpreted as 

x has a relationship f with y or x maps to y via f

Let’s see this in a programming context. Say you have the following function that takes two input parameters and produces the sum of them:
```scala
def addFunction(a: Int, b: Int) = a + b
```
For a given input set (2, 3) this function always returns 5, but the following function
currentTime doesn’t fit the definition: 
```scala
def currentTime(timezone: TimeZone) = Calendar.getInstance(timezone).getTime
```
For the given timezone GMT, it returns different results based on the time of day.

One other interesting property of a mathematical function is referential transparency, which means that an expression can be replaced with its result. In the case of add- Function, we could replace all the calls made to it with the output value, and the behavior of the program wouldn’t change.

Side effects

A function or expression is said to have a side effect if, in addition to pro- ducing a value, it modifies some state or has an observable interaction with calling functions or the outside world. A func- tion might modify a global or a static variable, modify one of its arguments, raise an exception, write data to a display or file, read data, or call other functions having side effects. In the presence of side effects, a program’s behavior depends on its history of execution.

Scala, put simply, is not a pure functional language. In a pure functional language modifications are excluded, and variables are used in a mathematical sense, with identifiers referring to immutable and persistent values. An example of a pure func- tional language is Haskell.


Scala supports both types of variables: single-assignment variables (also called val- ues) that don’t change their value throughout their lifetime and variables that point to a mutable state or could be reassigned to other objects. Even though you should use immutable objects whenever possible, Scala as a language doesn’t provide any restrictions. The restriction is purely conventional. A good rule of thumb is to always default to val and use variables when it’s absolutely necessary.


Scala supports most of them, but to keep it simple Scala is a functional language in the sense that functions are first-class values. That means that in Scala, every function is a value (like some integer value 1 or some string value "foo"), and like any values, you can pass them as parameters and return them from other functions. In Scala you can assign a function (x: Int) => x + 1 to a val inc and use that to invoke that function:
```scala
val inc = (x : Int) => x + 1
inc(1)
```
Here val represents a single assignment variable (like Java final variables) with a value that can’t be changed after the assignment. The output of the function call is 2.

In the following example you’ll see how to pass functions as parameters to another function and get the result:
```scala
List(1, 2, 3).map((x: Int) => x + 1)
```
In this case you’re passing an increment function to another function called map, and the output produced by the invocation of the map function will be List(2, 3, 4). Based on the output you can see that map is invoking the given function for each ele- ment in the list. Don’t worry about the syntax right now; you’ll learn about it in detail in later chapters.

#### Scala as a multi-paradigm language

Scala is a multi-paradigm language because it supports both functional and OOP pro- gramming. Scala is the first to unify functional programming and OOP in a statically typed language for the JVM. 

The goal of multi-paradigm computing is to provide a number of problem-solving styles so a programmer can select the solution that best matches the characteristics of the problem to be solved. This provides a framework where you can work in a variety of styles and mix the constructs from different ones. Functional programming makes it easy to build interesting things from simple parts (functions), and OOP makes it easy to adopt and extend complex systems using inheritance, classes, and so on.

Research results from the psychology of programming indicate that expertise in programming is far more strongly related to the number of different programming styles understood by an individual than it is the number of years of experience in programming.”


In Scala, functions are treated as objects.

FUNCTIONS AS OBJECTS

Scala, being a functional language, treats functions as values, and you saw one example of assigning a function to a variable. Because all values in Scala are objects.
```scala
List(1, 2, 3).map((x: Int) => x + 1)
```
You’re passing the function (x:Int) => x + 1 to the method map as a parameter. When the compiler encounters such a call, it replaces the function parameter with an object, as in the following:

```scala
List(1, 2, 3).map(new Function1[Int, Int]{ def apply(x:Int): Int = x + 1})
```

when the Scala compiler encounters functions with one parameter, it replaces that call with an instance of class scala.Function1, which implements a method called apply. 

#### Scala as a scalable and extensible language


cala stands for scalable language.7 One of the design goals of Scala is to create a lan- guage that will grow and scale with your demand. Scala is suitable for use as a scripting language, as well as for large enterprise applications. Scala’s component abstraction, succinct syntax, and support for both object-oriented and functional programming make the language scalable.

Scala also provides a unique combination of language mechanisms that makes it easy to add new language constructs in the form of libraries. You could use any method as an infix or postfix operator, and closures in Scala can be passed as “pass by name” arguments to other functions (see the next listing). These features make it eas- ier for developers to define new constructs.

Let’s create a new looping construct called loopTill, which is similar to the while loop in the following listing.

```scala

def loopTill(cond: => Boolean)(body: => Unit): Unit = {
 if (cond) {
    body
    loopTill(cond)(body)
 }
}

var i = 10

loopTill (i > 0) {
    println(i)
    i -= 1 
}

```

In this code you’re creating a new loopTill construct by declaring a method called loopTill that takes two parameters. The first parameter is the condition (i > 0) and the second parameter is a closure. As long as the condition evaluates to true, the loopTill function will execute the given closure.

Closure is a first-class function with free variables that are bound in the lexical environment. In the loopTill example, the free variable is i. Even though it’s defined outside the closure, you could still use it inside. The second parameter in the loopTill example is a closure, and in Scala that’s represented as an object of type scala.Function0.

Extending a language with a library is much easier than extending the language itself because you don’t have to worry about backward compatibility. For example, Scala actor implementation (defined in section 1.2.2) is provided as a library and isn’t part of the Scala language. When the first actor implementation didn’t scale that well, another actor implementation was added to Scala without breaking anything.

#### Scala runs on the JVM

he best thing about Java is not the language but the JVM. A JVM is a fine piece of machinery, and the Hotspot team has done a good job in improving its performance over the years. Being a JVM language, Scala integrates well with Java and its ecosystem, including tools, libraries, and IDEs. Now most of the IDEs ship with the Scala plug-in so that you can build, run, and test Scala applications inside the IDE. To use Scala you don’t have to get rid of all the investments you’ve made in Java so far. Instead you can reuse them and keep your ROI coming.

cala compiles to Java byte code, and at the byte-code level you can’t distinguish between Java code and Scala code. They’re the same. You could use the Java class file disassembler javap to disassemble Scala byte code (chapter 11 looks into this in more detail) as you could for Java classes.

why Scala?

The current crisis

An interesting phenomenon known as “Andy giveth, and Bill taketh away” comes from the fact that no matter how fast processors become, we software people find a way to use up that speed. 

End of Moore’s law

According to Moore’s law, the number of transistors per square inch on a chip will double every 18 months. Unfortunately, Intel and other CPU manufacturers are finally hitting the wall8 with Moore’s law and instead are taking the route of multicore pro- cessors. The good news is that processors are going to continue to become more pow- erful, but the bad news is that our current applications and programming environments need to change to take advantage of multicore CPUs.

Programming for multicores

Concurrency. Concurrency will be, if it isn’t already, the way we can write software to solve our large, distributed, complex enterprise problems if we want to exploit the CPU throughputs. Who doesn’t want efficient and good performance from their appli-
cations? We all do.

A few people have been doing parallel and concurrent programming for a long
time, but it still isn’t mainstream or common among enterprise developers. One rea- son is that concurrent programming has its own set of challenges. In the traditional thread-based concurrency model, the execution of the program is split into multiple concurrently running tasks (threads), and each operates on shared memory. This leads to hard-to-find race conditions and deadlock issues that can take weeks and months to isolate, reproduce, and fix. It’s not the threads but the shared memory that’s the root of all the concurrency problems. The current concurrency model is too hard for developers to grok, and we need a better concurrent programming model that will help developers easily write and maintain concurrent programs.

Scala takes a totally different approach to concurrency: the Actor model. An actor9 is a mathematical model of concurrent computation that encapsulates data, code, and its own thread of control and communicates asynchronously using immutable (no side effects) message-passing techniques. The basic Actor architecture relies on a shared-nothing policy and is lightweight in nature. It’s not analogous to a Java thread; it’s more like an event object that gets scheduled and executed by a thread. The Scala Actor model is a better way to handle concurrency issues. Its shared-nothing architec- ture and asynchronous message-passing techniques make it an easy alternative to existing thread-based solutions.

History of the Actor model

The Actor model was first proposed by Carl Hewitt in 1973 in his paper “A Universal Modular ACTOR Formalism for Artificial Intelligence” and was later on improved by Gul Agha (“ACTORS: A Model of Concurrent Computation in Distributed Systems”).
Erlang was the first programming language to implement the Actor model. Erlang is a general-purpose concurrent programming language with dynamic typing. After the success of the Erlang Actor model at Ericsson, Facebook, and Yahoo!, it became a good alternative for handling concurrency problems, and Scala inherited it. In Scala, actors are implemented as a library that allows developers to have their own imple- mentation. In chapters 7 and 12 you’ll look into various Scala actor implementations.

Traditionally, programming multicore processors is more complex than programming uniprocessors and it requires platform-specific knowledge. It’s also harder to maintain and manage these codebases. To make parallel programming easier, Scala provides higher abstractions in the form of a parallel collections library that hides parallel algo- rithms. For example, to square up each element of a List in parallel, you can use par- allel collections like the following:

```scala
List(1, 2, 3).par.map(x => x * x)
```

In this case the .par transforms the List into a parallel collection that implements the map method using a parallel algorithm. Behind the scenes a parallel collections library will fork threads necessary to execute the map method using all the cores available in a given host machine. The parallel collections library is a new addition to Scala and provides parallel versions of most collection types. 

Transitioning from Java to Scala

When Java, released in May 1995 by Sun Microsystems, arrived on the programming language scene, it brought some good ideas, such as a platform-independent pro- gramming environment (write once, run anywhere), automated garbage collection, and OOP. Java made object-oriented programming easier for developers, compared with C/C++, and was quickly adopted into the industry.

Over the years Java has become bloated. Every new feature added to the language brings with it more boilerplate code for the programmer; even small programs can become bloated with annotations, templates, and type information. 

Scala improves productivity

Adding libraries and tools to solve the productivity problem sometimes backfires, add- ing complexity to applications and reducing productivity. I’m not saying that you shouldn’t rely on libraries; you should whenever it makes sense. But what if you had a language built from the ground up from ideas like flexibility, extensibility, scalabil- ity—a language that grows with you?

If you’re from Java, then Scala is that language. It will make you productive, and it will allow you to do more with less code and without the boilerplate code.

Scala does more with less code

To see the succinctness of Scala, you have to dive into the code. The next two listings provide a simple example of finding an uppercase character in a given string, compar- ing Scala and Java code.


Finding an uppercase character in a string using Java

```java
boolean hasUpperCase = false;
for(int i = 0; i < name.length(); i++) {
    if(Character.isUpperCase(name.charAt(i))) {
        hasUpperCase = true;
        break;
    }
}
```

Finding an uppercase character in a string using scala

```scala
val hasUpperCase = name.exists(_.isUpper)
```

In Scala you can solve this problem with one line of code. Even though it’s doing the same amount of work, most of the boilerplate code is taken out of the programmer’s hands. In this case you’re calling a function called exists on name, which is a string, by passing a predicate that checks whether the character is true, and that character is represented by _. This demonstrates the brevity of the Scala language and its read- ability. 

Now let’s look at the following listing, where you create a class called Program- mer with the properties name, language, and favDrink.

programmer class in java

```java
public class Programmer {
    private String name;
    private String language;
    private String favDrink;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getLanguage() {
        return language;
    }
    public void setLanguage(String language) {
        this.language = language;
    }
    public String getFavDrink() {
        return favDrink;
    }
    public void setFavDrink(String favDrink) {
        this.favDrink = favDrink;
    }
}
```

This is a simple POJO (plain old Java object) with three properties—nothing much to it. In Scala you could create a similar class in one line, as in the following listing.

programmer class in scala

```scala
class Programmer(var name:String,var language:String,var favDrink:String)
```

In this example you’re creating a similar class called Programmer in Scala but with something called a primary constructor (similar to a default constructor in Java) that takes three arguments. Yes, you can define a constructor along with the class declaration— another example of succinctness in Scala. The var prefix to each parameter makes the Scala compiler generate a getter and setter for each field in the class


You could argue that the IDE will automatically generate some of this boilerplate code, and that’s not a problem. But I’d argue that you’d still have to maintain the generated code. Scala’s succinctness will be more apparent when you look into much more involved examples. In Java and Scala code comparisons, the same feature requires 3 to 10 times more lines in Java than Scala.

Coming from a dynamic language

It’s hard to find developers these days who haven’t heard of or played with Ruby, Groovy, or Python. The biggest complaint from the dynamic language camp about statically typed languages is that they don’t help the productivity of the programmer and they reduce productivity by forcing programmers to write boilerplate code. And when dynamically typed languages are compared with Java, obvious things like clo- sures and extensibility of the language are cited everywhere.

Before going into the issue of static versus dynamically typed languages, let’s look into Scala’s support for closures and mixin. The following listing shows how to count the number of lines in a given file in Ruby.

Counting the number of lines in a file in Ruby

```ruby
count = 0
File.open "someFile.txt" do |file|
    file.each { |line| count += 1 }
end
```

Counting the number of lines in a file in Scala

```scala
val src = scala.io.Source.fromFile(“someFile.txt”) 
val count = src.getLines().map(x => 1).sum
```

The Scala code looks similar to the Ruby code. You could solve this in many ways in Scala; here you’re using the map method to return 1 for each line, then using the sum method to calculate the total count.

Scala supports mixin composition with something called traits, which are similar to an abstract class with partial implementation. For example, you can create a new type of collection which allows users to access file contents as iterable, by mixing the Scala Iterable trait. The only contract is to implement an iterator method:

```scala
class FileAsIterable {
    def iterator = scala.io.Source.fromFile("someFile.txt").getLines()
}
```

Now if you mix in the Scala Iterable, your new FileAsIterable will become a Scala Iterable and will start supporting all the Iterable methods:

```scala
val newIterator = new FileAsIterable with Iterable[String]
newIterator.foreach { line => println(line) }
```

In this case you’re using the foreach method defined in the Iterable trait and print- ing each line in the file.

Scala version 2.10 adds support for a Dynamic10 type. Using this feature you can dynamically add methods and fields to a type at runtime. This is very similar to the method_missing feature of Ruby and is quite useful if you’re building a domain-specific language (DSL).

Scala map is a collection of key value pairs and if you want to access the value associated with a key you can do something like the following:

```scala
val someMap = Map("foo" -> 1, "bar" -> 2)
someMap.get("foo")
```

Here someMap is a collection of two key value pairs and someMap.get("foo") will return 1. Using Dynamic we can easily change that so that we can access the keys as if they were part of a type:

```scala
class MyMap extends Dynamic {
  ...
  def selectDynamic(fieldName: String) = map.get(fieldName)
  private val map = Map("foo" -> "1", "bar" -> 2)
}
val someMap = new MyMap
someMap.foo
someMap.bar
```

The magic ingredient in this case is the selectDynamic method. (Scala methods are defined using the def keyword.) When the Scala compiler checks that foo is not part of the type it doesn’t give up immediately. If the type is a subtype of Dynamic it looks for the selectDynamic method and invokes it. If the method is not provided, you will get a compilation error.

Scala also supports something called implicit conversion, which is similar to Ruby open classes but scoped and compile time checked.

Case for static typing, the right way

Static typing is a typing system where the values and the variables have types. A number variable can’t hold anything other than a number. Types are determined and enforced at compile time or declaration time.

Dynamic typing is a typing system where values have types but the variables don’t. It’s possible to successively put a number and a string inside the same variable.

The size and the complexity of the software you’re building are growing every day, and having a compiler do the type checking for you is great. It reduces the time you need to spend fixing and debugging type errors. In a statically typed language like Scala, if you try to invoke a length method on a number field, the Scala compiler will give you a compilation error. In a dynamically typed language you’ll get a runtime error.

Another benefit of a statically typed language is that it allows you to have powerful tools like refactoring and IDEs. Having an IDE might not interest you because of pow- erful editing tools like Emacs and TextMate, but having refactoring support is great when working on large codebases.

All these benefits do come with a price. Statically typed languages are more con- straining than dynamically typed languages, and some force you to provide additional type information when you declare or call a function. But having constraints is useful when building a large application because they allow you to enforce a certain set of rules across the codebase. Scala, being a type-inferred language, takes care of most of the boilerplate code for the programmer (that’s what compilers are good for, right?) and takes you close to a dynamically typed language, but with all the benefits of a stat- ically typed language.

Type inference is a technique by which the compiler determines the type of a variable or function without the help of a programmer. The compiler can deduce that the variable s in s="Hello" will have the type string because "hello" is a string. The type inference ensures the absence of any runtime type errors without putting a declaration burden on the programmer.

To demonstrate how type inference works, create an array of maps in Scala:
```scala
val computers = Array(
                   Map("name" -> "Macbook", "color" -> "white"),
                   Map("name" -> "HP Pavillion", "color" -> "black")
               )
```

If you run this Scala code in the Scala REPL, you’ll see the following output:

```console
computers: Array[scala.collection.immutable.Map[java.lang.String,java.lang.String]] = Array(Map(name -> Macbook, color -> white), Map(name -> HP Pavillion, color -> black))
```

Even though you only specified an array of maps with key and value, the Scala com- piler was smart enough to deduce the type of the array and the map. And the best part is that now if you try to assign the value of name to some integer type variable some- where in your codebase, the compiler will complain about the type mismatch, saying that you can’t assign String to an integer-type variable.


For the programming language enthusiast

Scala inherits lots of ideas from various programming languages of the past and present. To start with, Scala adopts its syntax from Java/C# and supports both JVM and Common Language Runtime (CLR). Some would argue that Scala’s syntax is more dis- similar than similar to that of Java/C#. You saw some Scala code in previous sections, so you can be the judge of that. In Scala every value is an object, and every operation is a method call. Smalltalk influences this pure object-oriented model. Scala also sup- ports universal nesting and uniform access principles (see the following listing), and these are borrowed from Algol/Simula and Eiffel, respectively. In Scala variables and functions without parameters are accessed the same way.

Universal access principles in Scala
```scala
class UAPExample {
  val someField = "hi"
  def someMethod = "there"
}
val o = new UAPExample
o.someField
o.someMethod
```

Here you’re accessing a field and a method of the instance of the UAPExample class, and to the caller of the class it’s transparent.

Scala’s functional programming constructs are similar to those of the metalan- guage (ML) family of languages, and Scala’s Actor library is influenced by Erlang’s Actor model.

The Scala 2.10 release adds experimental support for compile-time macros.11 This allows programmers to write macro defs: func- tions that are transparently loaded by the compiler and executed during com- pilation. This realizes the notion of compile-time metaprogramming for Scala.

### Summary

Its multi-paradigm model provides programmers with the power of abstractions from both functional and OOP models. Functional programming and actors will make your concurrent program- ming easy and maintainable. Scala’s type inference takes care of the pain of boiler- plate code so that you can focus on solving problems.

## 2 Getting Started






