# API

- Application Programming Interface

- Java API is a dictionary for programmer, which tells us how to use them but you don't have to know how to use it

#### Steps to use it

- package -> the construction method -> member method
- only when the API is in Java.Lang doesn't it need to import



## Scanner

- from `java.util.Scanner`

```java
import java.util.Scanner;

public class PracticeScanner {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
      	float b = sc.nextFloat();
        String str = sc.next();
        System.out.println(a+str);
    }
}
```

- Actually, all variables import from outsides are in the format of "String", but the member method could transform into other types, like `sc.nextInt()`, so the original function(this name may not be appropriate) is `sc.next()`. So when you want to input a "String" type, you should use `sc.next()` rather than `sc.nextString()`, which dosen't existed at all.
- `anonymous` object can be used, but it can used only for once, like the following examples.

```java
import java.util.Scanner;

//illustrate that an object can be used anonymously
public class AnonymousTest {
    public static void main(String[] args) {
        methodParam(new Scanner(System.in));
        Scanner sc = practiceReturm();
        System.out.println("input another number: ");
        System.out.println("the another imputed number is: " + sc.nextInt());
    }

  	//use Scanner as an argument
    public static void methodParam(Scanner sc){
        System.out.println("input a number: ");
        int num = sc.nextInt();
        System.out.println("the inputed number is: "+ num);
    }
		
  	//use Scanner as a return
    public static Scanner practiceReturm(){
        return new Scanner(System.in);
    }
}
```

```
input a number:
1
the inputed number is: 1
input another number: 
12
the another imputed number is: 12
```



## Random

- a objection to generate random numbers
- the random numbers are in the range of the variable's type but won't exceed it.

```java
import java.util.Random;
public class TestRandom {
    public static void main(String[] args) {
        Random r = new Random();
      	
      	//the random numbers are in the range of the 
      	//variable's type but won't exceed it.
        int randon_num = r.nextInt();
      	
      	//range:[0:10)
      	int randon_num_range = r.nextInt(10);
        System.out.println(randon_num);
    }
}
```



## ObjectArray

- when object array just created, the elements are 'null', which is different with crearting single object

```java
Person[] ps = new Person[3];
System.out.println(ps[0]);

Person pps = new Person();
System.out.println(pps);
```

output:

```
null
cn.edu.ustb.demo04.Person@61bbe9ba
```



## ArrayList\<E>
- <E> represents generics: when defining a function, api or class, you don't need to specify the type of it. It will be specified when using it. It can only be `reference type` rather than `basic type`. (the former is in stack, the latter is in heap). ps: E is a set consisting of several addresses of the elements,  so basic types like int, char, short don't fit in this model.
but you can use the package type of these basic types. The following is a table of comparison of basic types to reference types

| Basic Type | Package Type |
| ---------- | ------------ |
| boolean    | Boolean      |
| byte       | Byte         |
| short      | Short        |
| int        | **Integer**  |
| long       | Long         |
| char       | Character    |
| float      | Float        |
| double     | Double       |

[`csdn explained`](https://blog.csdn.net/qing_gee/article/details/101670051?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)   [`zhihu explained`](https://zhuanlan.zhihu.com/p/28654272)

```java
Integer a = 3; //autoboxing
Integer b = 3;
System.out.println("a = " + a);
System.out.println("b = " + b);
System.out.println("a=b? " + (a == b));
System.out.println();

Integer c = new Integer(2);
Integer d = new Integer(2);
System.out.println("c = " + c);
System.out.println("d = " + d);
System.out.println("c=d? " + (c == d));
```

```
a = 3
b = 3
a=b? true

c = 2
d = 2
c=d? false
```



- as for arraylist, you won't get the address of it but content.


### commonly used method
- `public boolean add(E, e)`
- `public E get(int index)`: fetch the element from set, return the gotten element
- `public E remove(int index)`: delete the element from set, return the deleted element
- `public int size()`


```java
package cn.edu.ustb.demo04;

import java.util.ArrayList;
/*
from jdk 1.5, the complier support auto-boxing & auto-unboxing
autoboxing: auto: basic type ----> package type
auto-unboxing: auto: package type ----> basic type
 */

public class ArrayObject {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        System.out.println(list); // []

        // add elements into sets: add
        // remember: adding element into a set will not always be succseeful
        // so you have to check whether it is successfully added, but in this
        // situation, adding into "ArrayList", It will always be successful
        boolean success = list.add("Jesse");
        System.out.println(list);//[Jesse]
        System.out.println("add it successfully? " + success);
      	//add it successfully? true

        //add element
        list.add("Tom");
        list.add("Henry");
        System.out.println(list);//[Jesse, Tom, Henry]

        //get element
        String name2 = list.get(2);
        System.out.println("the name of the third person is: " + name2);
      	//the name of the third person is: Henry

        //delete element
        String name3 = list.remove(1);
        System.out.println("the name of the deleted person is: " + name3);
        System.out.println(list);
      	//the name of the deleted person is: Tom
      	//[Jesse, Henry]

        //show the number of elements
        int num = list.size();
        System.out.println("the number of elements is: " + num);
        System.out.println();
    	  //the number of elements is: 2

        //shortcut: list.fori
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
            System.out.println();
        }
      	//Jesse
				//Henry

        //int? integer?
        ArrayList<Integer> intList = new ArrayList<>();
        intList.add(100);
        intList.add(200);
        intList.add(300);
        System.out.println(intList);
        int i1=intList.get(0);
        int i2=intList.get(1);
        System.out.println("first element of integer list:"+i1);
        System.out.println("second element of integer list:"+i2);
     	 	//[100, 200, 300]
				//first element of integer list:100
				//second element of integer list:200

    }
}

```





