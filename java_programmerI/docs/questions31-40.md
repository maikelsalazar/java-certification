## Question 31

Which two describe reasons to modularize the JDK?

1. Improves application robustness
2. Improves security and maintainability
3. Easier to exposes implementation details
4. Easier to understand the Java language
5. Easier to build a custom runtime linking application modules and JDK modules

## Question 32

```java
package a;

public abstract class Animal {

    protected abstract void walk();
}

```


```java

package b;

import a.Animal;

public abstract class Human extends Animal {
    
}

```

Which two lines inserted in line 1 will allow this code to compile?

1. private void walk(){}
2. protected void walk(){}
3. void walk(){}
4. abstract void walk();
5. public abstract void walk();

> Answer is 2 and 5

## Question 33

Given:


```java
public class Person {
    private String name;

    public void setName(String name) {
        String title = "Dr. ";
        name = title + name;
    }

    public String toString() {
        return name;
    }
}

```

```java
public class Test {
    public static void main(String[] args) {
        Person p = new Person();
        p.setName("Who");
        System.out.println(p);
    }
}

```

What is the result?
1. null
2. Dr. Null
3. Dr. Who
4. An exception is thrown at runtime

> The answer is 1

## Question 34

Given

```java
public interface ExampleInterface {}
```

Which two statements are valid to be written in this interface?

1.

```java
final void methodG(){
	System.out.println("G");
}
```

2. public int x;

3. 

```java
public void methodF(){
	System.out.println("F");
}
```

4. public abstract void methodB();
5. final void methodE();
6. private abstract void methodC();
7. public String methodD();

> invalids are 1, 3, 5, 6. The answer is 4 and 6. Although in jdk 11 you can declarate variables in interfaces. By the way, in 4 abstract is redundant

try this with jdk 11:

```java
package question34;

public interface ExampleInterface {

    public int x = 10;
    public abstract void methodB();
    public String methodD();
}
```

```java
package question34;

public class Impl implements ExampleInterface {

    @Override
    public void methodB() {
        System.out.println("methodB");
    }

    @Override
    public String methodD() {
        return "methodD";
    }


    public static void main(String[] args){

        ExampleInterface i = new Impl();

        i.methodB();
        System.out.println(i.methodD());
        System.out.println(i.x);
    }
}
```

output:

```
methodB
methodD
10
```

