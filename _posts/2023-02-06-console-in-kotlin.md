---
layout: post
title: "Console in Kotlin"
category: kotlin
---

Write and read from/to the console in Kotlin is very simple, using the following methods: ``println()``, ``print()`` and ``readln()``.

## Write

To write any value to the console use the ``print()`` or the ``println()`` method, defined in ``kotlin.io``.

Example 1:

```kotlin
fun main() {
    println("Hello, World!")
    // Output: Hello, World!
}
```

Example 2:

````kotlin
fun main() {
    println("Output 1")
    println("Output 2")
    // Output: Output1
    //         Output2
}
````

Example 3:

```kotlin
fun main() {
    print("Hello, World!")
    // Output: Hello, World!
}
```

Example 4:

```kotlin
fun main() {
    print("Output 1")
    print("Output 2")
    // Output: Output1Output2
}
```

CONCLUSION: ``println()`` prints a line break after your string.

TIP: If you pass another value, for example a ``java.io.File``, ``println()`` and ``print()`` prints
the return value of the ``toString()`` method.

INFO: ``println()``/``print()`` only call the ``System.out.println()``/``System.out.print()`` method.

## Read

To read any string, use the ``readln()`` method, defined in ``kotlin.io``.

Example 1:

```kotlin
fun main() {
    print("Your name: ")
    val input = readln()
    println("Hello, $input!")
}
```

Example 2:

```kotlin
fun main() {
    print("Whats your name? ")
    val name = readln()
    print("How old are you? ")
    val age = readln()
    println("Hello $name, you are $age years old!")
}
```

-