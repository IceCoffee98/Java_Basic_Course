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

<img src="https://github.com/IceCoffee98/Java_Basic_Course/blob/master/img/image-20200327220724529.png" style="zoom:30%;" align='left'/>

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