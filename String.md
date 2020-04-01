## String

- all strings in Java are objects of String Class, even if they are not created by "new"

### Characteristic
1. content can't be altered
2. string can be shared (because it can never be altered)
3. the result of string is equivalent to `Char[]`, but the underlying principle is `byte[]`

### 4 ways to create String

- 3 construct methods & 1 direct creation (common)

```java
public class String(); //create a blank string without any content
public class String(char[] array); //creation based on content of char[]
public class String(byte[] array);//creation based on content of byte[]
String str = "Hello"; //jvm will "new" it
```
- eg:
```java
String str1 = new String();
System.out.println("str1 = " + str1);

char[] chars = {'A', 'B', 'C'};
String str2 = new String(chars);
System.out.println("str2 = " + str2);

byte[] bytes = {97, 98, 99};
String str3 = new String(bytes);
System.out.println("str3 = " + str3);
```
output:
```
str1 = 
str2 = ABC
str3 = abc
```

### String Pool

- all character strings created by `String str = "Hello"` are in `String Pool`, those created by `String str1 = new String()`are not. 
- if you create 2 Strings with the ***same value*** like:

```java
String str1 = "Hello";
String str2 = "Hello";
system.out.println(str1 == str2);//true
```
- but if you create with ***new***, which are not in String pool, the output will be false.

```java
String str1 = "abc";
String str2 = "abc";
char[] str = {'a', 'b', 'c'};
String str3 = new String(str);
System.out.println(str1 == str2); //true
System.out.println(str1 == str3); //false
System.out.println(str2 == str3); //false
System.out.println(str1.equals(str3)); //true
System.out.println(str2.equals(str3)); //true
```


