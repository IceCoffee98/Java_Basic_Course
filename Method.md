## Method

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