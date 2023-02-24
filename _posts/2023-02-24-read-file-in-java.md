---
layout: post
title: Read file in Java
category: java
---

There are a lot of methods to read a file in Java, you can use the ``java.nio.file.Files`` class,
a ``java.util.Scanner`` instance, a ``java.io.InputStream``, a ``java.io.BufferedReader`` and other.

Example for ``java.nio.file.Files``:

```java
import java.io.File;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;

class ReadFileWithFiles {
    public static void main(String[] args) throws IOException {
        System.out.println("From string:");
        System.out.println(fromPath("FOLDER/myFile.txt"));
        System.out.println("\n\nFrom file:");
        System.out.println(fromFile(new File("myFile.txt")));
    }

    private static String fromFile(File file) throws IOException {
        // Convert File to Path using File.toPath()
        return Files.readString(file.toPath());
    }

    private static String fromPath(String path) throws IOException {
        // Create path from string, using Path.of()
        return Files.readString(Path.of(path));
    }
}
```

Example for ``java.util.Scanner``:

```java
import java.util.Scanner;

class ReadFileWithScanner {
    public static void main(String[] args) {
        // You can use a String a File, a Path, a InputStream, a Readable or a ReadableByteChannel.
        Scanner scanner = new Scanner("myFile.txt");
        StringBuilder fileContent = new StringBuilder();
        while (scanner.hasNext()) {
            fileContent.append(scanner.nextLine());
        }
        System.out.println("Content:\n\n" + fileContent);
    }
}
```

Example for ``java.io.InputStream``:

```java
import java.io.FileInputStream;
import java.io.IOException;

class ReadFileWithInputStream {
    public static void main(String[] args) {
        try (FileInputStream fis = new FileInputStream("myFile.txt")) {
            System.out.println(new String(fis.readAllBytes()));
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

Example for ``java.io.BufferedReader``:

```java
import java.io.*;

class ReadFileWithBufferedReader {
    public static void main(String[] args) throws IOException {
        // Constructing stream/readers
        FileInputStream fis = new FileInputStream("");
        InputStreamReader isr = new InputStreamReader(fis);
        BufferedReader reader = new BufferedReader(isr);
        // Reading
        String line;
        while ((line = reader.readLine()) != null) {
            System.out.println(line);
        }
        // Close streams
        reader.close();
        isr.close();
        fis.close();
    }
}
```
