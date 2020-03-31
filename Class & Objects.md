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

<img src="https://github.com/IceCoffee98/Java_Basic_Course/blob/master/img/image-20200328111204621.png" style="zoom:67%;" />

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

