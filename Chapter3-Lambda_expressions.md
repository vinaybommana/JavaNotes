#Lambda Expressions
* Lambda expressions are introduced in Java 8.
* Lambda expression facilitates functional programming and simplifies the development.

A Lambda expression is characterised by the following syntax-\

`parameter -> expression body`

###Example

```java
interface Addable {
    int add(int a, int b);
}

public class AdditionDemo {
    public static void main(String[] args) {
        //Multiple parameters in lambda expressions
        Addable ad1 = (a, b) -> (a + b);
        System.out.println(ad1.add(10, 20));
        
        //Multiple parameters with datatypes 
        Addable ad2 = (int a, int b) -> (a + b);
        System.out.println(ad2.add(100, 200));
    }
}
```

* Here the `interface Addable` is called `functional interface`.

###Simple implementation of for each loop

```java
import java.util.*;
public class ForEachExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<String>();
        list.add("a");
        list.add("b");
        list.add("c");

        list.forEach(
            (n) -> System.out.println(n);
        );
    }
}
```
###Java Lambda Expression : single parameter
```java
@FunctionalInterface
interface Sayable {
    public String say(String name);
}

public class SingleParameterExample {
    public static void main(String[] args) {
        Sayable s1 = (name) -> {
            return "Hello, " + name;
        }

        System.out.println(s1.say("jon"));
    }
}
```
###Java Lambda Expression : Comparator
```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Product {
    int id;
    String name;

    public Product(int id, String name) {
        super(); // called implicitly anyway
        this.id = id;
        this.name = name;
    }
}

public class ComparatorExample {
    public static void main(String[] args) {
        List<Product> list = new ArrayList<Product>();
        list.add(new Product(1, "Ice"));
        list.add(new Product(2, "Long Claw"));
        list.add(new Product(3, "Dawn"));

        System.out.println("Sorting according to name");
        //lambda expression implementation
        Collections.sort(list, (p1, p2) -> {
            return p1.name.compareTo(p2.name);
        });

        //printing the sorted list
        for(Product p: list) {
            System.out.println(p.id + " " + p.name);
        }
    }
}
```
