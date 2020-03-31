

## Development Environment of Java

--------

### JVM - Java Virtual Machine

All of the code run in JVM(Like a translator)

#### Cross-platform

- All of the programs runs in JVM and all the JVMs run on the OS
- JVMs of different OS are different, JVM is not cross-platform

### JRE(Java Runtime Environment) 
- the environment Jave code runs on, which includes `JVM` and `Esential Class Lib` for running

### JDK(Java Development Kit)

- including `JRE` & tools developers need

If you want to run a existing Java program, only `JRE` is needed

If you want to develop a new Java program, you must install `JDK`

<img src="https://github.com/IceCoffee98/Java_Basic_Course/blob/master/img/image-20200327203832387.png" alt="image-20200327203832387" style="zoom:50%;" />

------

## Optimization of Compliers

for byte/short/char these 3 kinds of types,:

- if the values on the right side doesn't exceed the range of the left side, the complier - Javac - will automatically add (byte)(short)(short)
- if it dosen't exceed, the complier will report "error"
- When assigning a value to a variable, Javac will directly use the result of the expression as its value if the right side is all parameters  

```java
short a=5;
short b=8;
short result=5+8; //right
short result=a+b; //wrong
```

if there are variables on the right side, the optimization won't work.

```java
short result=5+a+8; //wrong
```

----

## Structure of IDEA

<img src="https://github.com/IceCoffee98/Java_Basic_Course/blob/master/img/image-20200327203832387.png" style="zoom:30%;" align='left'/>

### PS:

- the name of packages should be lower case



## Common Shortcut of IDEA

| Shortcut               | Function                 |
| ---------------------- | :----------------------- |
| `Ctrl+x`               | Eliminate the line       |
| `Opt+Enter`            | Importing jar package    |
| `Ctrl+d`               | Duplicate the line       |
| `Opt+cmd+L`            | Importing jar package    |
| `Cmd+/`                | Annotation selected area |
| `Cmd+Shift+/`          | Annotation selected area |
| `Cmd+Shift+Arrow keys` | Move the line            |
| `"num.fori"`           | loop(i)                  |
| `"array.fori"`         | loop(array)              |



## Import Models

> File
>
> > Project Structure
> >
> > > Modules




## Method

“5.fori表示五次循环，idea自动填写”

#### Define format:

```java
public static void methodName(){
    method body
}
```

#### Call format:

- The sequency is unnecessary
- Nesting method is not allowed
- Method can't implement itself: I you want it to implement, you need call the method

### Method Overloading

- the same `method name` to be used with different `argument` types
- the sequence/type can be different.
- nothing to do with the name of parameters / type of return / public? / static

```java
public class MethodOverload{
    public static void main(String[] args){
      System.out.println(sum(10,20));
      System.out.println(sum(10,20,30));
      System.out.println(sum(10,20,30,40));
    }
  	public static int sum(double a,double b){
      return (int)(a+b);
    }
   	public static int sum(int a,double b){
      return (int)(a+b);
    }
    public static int sum(double a,int b){
      return (int)(a+b);
    }
  	public static int sum(int a,int b,int c){
      return a+b+c;
    }
  	public static int sum(int a,int b,int c,int d){
      return a+b+c+d;
    }
  	//the following methods are wrong
  	public static int sum(int x,double y){
      return (int)(x+y);
    }
    public static double sum(double a,double b){
      return a+b+0.0;
    }
}
```

Actually, `System.out.println("Hello World");` is a kind of overload of various types.



## Variables

### Basic variables

| Types   | Size /Byte(s) |
| ------- | ------------- |
| byte    | 1             |
| short   | 2             |
| int     | 4             |
| long    | 8             |
| float   | 7             |
| double  | 8             |
| char    | 2             |
| boolean | 1             |

### Reference variables

All the reference variables can be assigned "null", representing there's nothing in it.



## Array

### Initialise

#### 1.Dynamic initialization(specify length)

- basic format

```java
datatype[] name = new datatype[length]
```

- eg:

```java
int[] arrayA = new int[300];
String[] arrayC = new String[5];
```

#### 2.Static initialization(specify value)

- basic format

```java
// elements can also be variables, not only parameters
datatype[] name = new datatype[]{element1, element1, .....}
datatype[] name = {element1, element1, .....} //omit format
```

- eg

```java
int[] arrayA = new int[]{5, 15, 20};
int[] arrayB = /* new int[] */ {5, 15, 20}; // "new int[]" have been omitted
String[] arrayC = new String[]{"Hello", "World", "Java"};
```

#### 3.Attention

- Static initialization still has its length, which will be automatically calculated
- Static and Dynamic initialization can be divided into 2 parts

```java
// Static initialization
int[] arrayA;
arrayA = new int[] {5, 15, 20};

// Dynamic initialization
int[] arrayB;
arrayA = new int[5];

// !!!!! The Following isn't supported by compliers
int[] arrayC;
arrayC = {5, 15, 20};
```

- ==All arrays need to be initialized before using(new)==

### Reference

```java
datatype[] arrayA = new int[3];
datatype[] arrayB = arrayA;
```

`arrayA` will be refered by `arrayB`, both of them have the same starting address.

### Null Pointer Exception of Array

- incorrect eg:

```java
int[] array = null;
System.out.println(array[0]);
// Exception in thread "main" xx.NullPointerException
```

- correct eg:

```java
int[] array = null;
array = new int[3];
System.out.println(array[0]);
```

### Use Arrays as Arguments of Method

- the transmitted arguments are the starting address of the `array`

```java
public static void main(String[] args) {
    int[] arrayA = new int[] {10, 200, 30};
    printArray(arrayA);
}
public static void printArray(int[] array){
    for (int i = 0; i < array.length; i++) {
        System.out.print(array[i]+" ");
    }
    System.out.println();
}
```

### Use Array as a Return of a Method

- the returned `array` is also the starting address

```java
//return array
public static int[] returnArray(int a[]){
  	...
 		int[] array = {...};
    return array;
}
```



## Class & Objects

### Class

- a set of related `attributes` & `behavior`
- like a template of a thing describeb by `attributes` & `behavior`

#### Attributes

- the statues of a thing

#### Behaviors 

- what this thing can do

eg:

```
class: a cat
attributes: name, weight, age, color
behaviors: walk, run
```

<img src="https://github.com/IceCoffee98/Java_Basic_Course/blob/master/img/image-20200327220724529.png" style="zoom:67%;" />

### Object

`Class` is the description of a type of thing, which is ==abstract==.

`Object` is an example of a type of thing, which is ==specific==.

`Class` is the templet of `Object`, `Object` is the entity of `Class`

#### Attention

- common method should include keyword: `static`, but in the method of a member, it is not allowed.
- member's variables are defined outside of methods of the class 
- different examples of the same class share the same starting address of behavior method
- the example of a class can be refered
- when an object is transmitted into a method, the actual transitted is the address of the object
- when the tpye of a variable is "boolean", "Getter Function" should be written as "isXxx".
- you can add Class with another Class in different package
- when a **local variable** and a **member variable** in the same Class have the same name in a method, the method will use the **closet variable as priority**. And you can use **`this.`** to represent member variables. **`this`** is called by the the particular object by Class.

```java
// Class Declaration  
public class Dog { 
    // Instance Variables 
  	// behaviors
    String name; 
    String breed; 
    int age; 
    String color; 
  
    // Constructor Declaration of Class 
    public Dog(String name, String breed, int age, String color){ 
        this.name = name; 
        this.breed = breed; 
        this.age = age; 
        this.color = color; 
    } 
  	
  	// Attributes
    // method 1 
    public String getName(){ 
        return name; 
    } 
  
    // method 2 
    public String getBreed(){ 
        return breed; 
    } 
  
    // method 3 
    public int getAge(){ 
        return age; 
    } 
  
    // method 4 
    public String getColor(){ 
        return color; 
    } 
  
    @Override
    public String toString(){ 
        return("Hi my name is "+ this.getName()+ 
               ".\nMy breed,age and color are " + 
               this.getBreed()+"," + this.getAge()+ 
               ","+ this.getColor()); 
    } 
  
    public static void main(String[] args){ 
        Dog tuffy = new Dog("tuffy","papillon", 5, "white"); 
        System.out.println(tuffy.toString()); 
    } 
} 
```

### Construction Method

- the name of a construction method should be completely the same as the Class, even the case.
- construction method don't need `return` and `void`
- if you don't write a construction method manually, the complier will create one automatically. Once you write it, the complier won't create another any more. But you can write more than one construction method with different argument list --  overload of construction.

### A Standard Class Consists of Following 4 Parts: (Java Bean)

1. all member variables are modified by `private`
2. all member variables need a pair of `Getter`&`Setter`
3. a construction method without `arguments`
4. a construction method with full `arguments`

