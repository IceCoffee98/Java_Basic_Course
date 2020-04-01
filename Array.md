## Variables

- the first letters of all `variables` are `lowercase`
- the first letters of all `Classes` are `uppercase`

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