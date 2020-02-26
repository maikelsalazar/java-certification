## Question 21

Given Hello.java

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

Which two sets of commands, independently, print Hello World?

1.
```shell
javac Hello.java
java Hello
```
2.
```shell
javac Hello.java
java Hello.class
```

3.
```shell
java Hello
```

4.
```shell
java Hello.java
```

5.
```shell
java Hello.class
```

> The answer is 1 and 5. 5 is valid because is a single source file

## 22

Given
```java
public class Test {
    public static void main(String[] args) {
        int prime = 21;
        Integer wrapint = Integer.valueOf(21);
        System.out.println("prme==wrapint in " + (prime == wrapint));
    }
}
```

Which is correct?

1. The code compiles and prints prime==wrapint is true
2. The code compiles but throws an exception at runtime
3. The code compiles and prints prime==wrapint is false
4. The code does not compile successfully

> The answer is 1.

## Question 23

Given:

```java
package question23;

public class Tester {
    public static void main(String[] args) {
        byte x = 7, y = 6;
        // line 1
        System.out.println(z);
    }
}
```

Which expression when added at line 1 will produce the output 1.17? 

1. float z = Math.round((float)x/y*100)/(float)100;
2. float z = Math.round((int) (x/y),2);
3. (float)(Math.round((float)x/y*100)/100);
4. float z = Math.round((float)x/y,2);

> The answer is: 1.
>
> Math.round accepts only one argument.
>
> cant' be 3, because z wouldn't exists

## Question 24

Given
```java
import java.util.Collection;

public class Foo {

    public <T> Collection<T> foo(Collection<T> arg) {
        
        return null;
    }
}
```

```java
public class Bar extends Foo {
    // ...
}

```

Which two statements are true if the method is added to Bar?

1. public Collection<String> foo(Collection<String> arg) { ... } overrides Foo.foo
2. public <T> Collection<T> foo(Collection<T> arg) { ... } overloads Foo.foo
3. public <T> Collection<T> foo(Stream<T> arg) { ... } overloads Foo.foo
4. public <T> Collection<T> bar(Collection<T> arg) { ... } overloads Foo.foo
5. public <T> Iterable<T> foo(Collection<T> arg) { ... } overrides Foo.foo
6. public <T> List<T> foo(Collection<T> arg) { ... } overrides Foo.foo

> The answer is 2 and 6.
>
> List is a subclass of Collection, so it is allowed. 
> Collection is a subclass of Iterable, so it is not allowed on overriden.

## Question 25

```java
public class DNASynth {
    int aCount;
    int tCount;
    int cCount;
    int gCount;

    void setACount(int cCount) {
        cCount = cCount;
    }

    void setTCount() {
        this.tCount = tCount;
    }

    int setCCount() {
        return cCount;
    }

    int setGCount(int g) {
        gCount = g;
        return gCount;
    }

    void setAllCounts(int x) {
        aCount = tCount = this.cCount = setGCount(x);
    }
}
```

Which two methods modify field values?
1. setGCount
2. setCCount
3. setAllCounts
4. setACount
5. setTCount

> The answer is 1 and 3.

## Question 26

Given:

```java
package question26;

public class TestArray {
    public static void main(String[] args) {
        String[][] arr = {
                {"Red", "White"},
                {"Black"},
                {"Blue", "Yellow", "Green", "Violet"}
        };
        for (int row = 0; row < arr.length; row++) {
            int column = 0;
            for (; column < arr[row].length; column++) {
                System.out.println("[" + row + "," + column + "] = " + arr[row][column]);
            }
        }
    }
}
```

Whats is the result?

1.
```
[0,0] = Red
[0,1] = White
[1,0] = Black
[2,0] = Blue
[2,1] = Yellow
[2,2] = Green
[2,3] = Violet
```

2. java.lang.ArrayIndexOutOfBoundsException thrown

3.
```
[0,0] = Red
[0,1] = White
[1,0] = Black
[1,1] = Blue
[2,0] = Yellow
[2,1] = Green
[3,0] = Violet
```

4.
```
[0,0] = Red
[1,0] = Black
[2,0] = Blue
```

> The answer is 1.

## Question 27

```java
interface Pastry {
    void getIngredients();
}
abstract class Cookie implements Pastry {}

class ChocolateCookie implements Cookie {
    public void getIngredients() {}
}
class CoconutChocolateCookie extends ChocolateCookie {
    void getIngredients(int x) {}
}
```

Which is true?

1. The compilation fails due to an error in line 10
2. The compilation fails due to an error in line 2
3. The compilation fails due to an error in line 6
4. The compilation fails due to an error in line 7
4. The compilation fails due to an error in line 4
6. The compilation fails due to an error in line 9
7. The compilation succeeds

> The answer is 3. Cookie is a class, not an interface. So ChocolateCookie has to extend it.

## Question 28

Given:

```java
public interface Builder {
    public A build(String str);
}

public class BuilderImpl implements Builder {
    @Override
    public B build(String str) {
        return new B(str);
    }
}
```

Assuming that this code compiles correctly, which three statements are true?

1. B is a subtype of A
2. B cannot be abstract
3. A cannot be final
4. B cannot be final 
5. A cannot be abstract
6. A is a subtype of B

> The answer is 1, 2 and 3.

## Question 29

Which two statements are correct about modules in Java?

1. module-info.java cannot be empty
2. A module must be declared in module-info.java
3. module-info.java can be placed in any folder inside module-path
4. java.base exports all of the Java platforms core packages
5. By default, modules can access each other as long as they run in the same folder

> 1 and 2 are correct

### 30

Given the formula to calculate a monthly mortgage payment:

And these declarations:

```java
double m; //monthly payment d
ouble r = 0.05/12; //monthly interest rate
int p = 100_000; //principal
int n = 180; //number of payment
```

How can you code the formula?

1.

```java
m=p*(r*Math.pow(1+r,n)/ /(Math.pow(1+r,n)-1));
```
2.

```java
m=p*((r*Math.pow(1+r,n)/ /(Math.pow(1+r,n))-1));
```

3.

```java
m=p*(r*Math.pow(1+r,n)/ /Math.pow(1+r,n)-1);
```

4.

```java
m=p*r*Math.pow(1+r,n)/ /Math.pow(1+r,n)-1;
```

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

