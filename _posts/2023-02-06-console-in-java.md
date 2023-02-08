---
layout: post
title: "Console in Java"
category: java
---

Writing to console in Java is very simple, but reading is more complex.

## Write

Using the ``java.lang.System.out`` print stream, writing is very simple.

Example 1:

```java
public class ConsoleInJava {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
        // Output: Hello, World!
    }
}
```

Example 2:

```java
public class ConsoleInJava {
    public static void main(String[] args) {
        System.out.println("Output1");
        System.out.println("Output2");
        // Output: Output1
        //         Output2
    }
}
```

Example 3:

```java
public class ConsoleInJava {
    public static void main(String[] args) {
        System.out.print("Hello, World!");
        // Output: Hello, World!
    }
}
```

Example 4:

```java
public class ConsoleInJava {
    public static void main(String[] args) {
        System.out.print("Output1");
        System.out.print("Output2");
        // Output: Output1Output2
    }
}
```

CONCLUSION: ``System.out.println()`` prints a line break after your string.

TIP: If you pass another value, for example a ``java.io.File``, ``System.out.println()`` and ``System.out.print()`` prints
the return value of the ``toString()`` method.

## Read

Reading from console is in Java more complex, you must be use the ``java.util.Scanner`` class.

Example 1:

```java
import java.util.Scanner;

public class ConsoleInJava {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Your name: ");
        String input = scanner.next();
        System.out.println("Hello, " + input + "!");
    }
}
```

Example 1:

```java
import java.util.Scanner;

public class ConsoleInJava {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Whats your name? ");
        String name = scanner.next();
        System.out.print("How old are you? ");
        int age = scanner.nextInt();
        System.out.println("Hello " + name + ", you are " + age + " years old!");
    }
}
```
