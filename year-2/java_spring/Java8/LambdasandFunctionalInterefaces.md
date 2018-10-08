# Lambda Expressions and Functional Interfaces

[Source](https://medium.freecodecamp.org/learn-these-4-things-and-working-with-lambda-expressions-b0ab36e0fffc)

## What is a functional interface?

**An interface that contains one and only one abstract method**

If you take a look at the definition of the Java standard Runnable interface, you will notice how it falls into the definition of functional interface because it only defines one method: run().

In the code sample below, the method computeName is implicitly abstract and is the only method defined, making MyName a functional interface.
```
interface MyName{
  String computeName(String str);
}
```

## What does the arrow mean?

Lambda expressions introduce the new arrow operator -> into Java. It divides the lambda expressions in two parts:
```(n) -> n*n```

It might be helpful to think about this operator as “becomes”. For example, “n becomes n*n”, or “n becomes n squared”.


## What are single expression lambdas?

With functional interface and arrow operator concepts in mind, you can put together a simple lambda expression.

Example 1:
```Java
interface NumericTest {
	boolean computeTest(int n); 
}

public static void main(String args[]) {
	NumericTest isEven = (n) -> (n % 2) == 0;
	NumericTest isNegative = (n) -> (n < 0);

	// Output: false
	System.out.println(isEven.computeTest(5));

	// Output: true
	System.out.println(isNegative.computeTest(-5));
}
```

Example 2:
```Java
interface MyGreeting {
	String processName(String str);
}

public static void main(String args[]) {
	MyGreeting morningGreeting = (str) -> "Good Morning " + str + "!";
	MyGreeting eveningGreeting = (str) -> "Good Evening " + str + "!";
  
  	// Output: Good Morning Luis! 
	System.out.println(morningGreeting.processName("Luis"));
	
	// Output: Good Evening Jessica!
	System.out.println(eveningGreeting.processName("Jessica"));	
}
```

## What are block lambda expressions?

There is another type of expression used when the code on the right side of the arrow operator contains more than one statement known as block lambdas:
```Java
interface MyString {
	String myStringFunction(String str);
}

public static void main (String args[]) {
	// Block lambda to reverse string
	MyString reverseStr = (str) -> {
		String result = "";
		
		for(int i = str.length()-1; i >= 0; i--)
			result += str.charAt(i);
		
		return result;
	};

	// Output: omeD adbmaL
	System.out.println(reverseStr.myStringFunction("Lambda Demo")); 
}
```

## How do generics work with lambdas?

A lambda expression cannot be generic. But the functional interface associated with a lambda expression can. It is possible to write one generic interface and handle different return types like this:
```
interface MyGeneric<T> {
	T compute(T t);
}

public static void main(String args[]){

	// String version of MyGenericInteface
	MyGeneric<String> reverse = (str) -> {
		String result = "";
		
		for(int i = str.length()-1; i >= 0; i--)
			result += str.charAt(i);
		
		return result;
	};

	// Integer version of MyGeneric
	MyGeneric<Integer> factorial = (Integer n) -> {
		int result = 1;
		
		for(int i=1; i <= n; i++)
			result = i * result;
		
		return result;
	};

	// Output: omeD adbmaL
	System.out.println(reverse.compute("Lambda Demo")); 

	// Output: 120
	System.out.println(factorial.compute(5)); 

}
```

## How can lambda expressions be used as arguements?

One common use of lambdas is to pass them as arguments.

They can be used in any piece of code that provides a target type. I find this exciting, as it lets me pass executable code as arguments to methods.

To pass lambda expressions as parameters, just make sure the functional interface type is compatible with the required parameter.

```Java
interface MyString {
	String myStringFunction(String str);
}

public static String reverseStr(MyString reverse, String str){
  return reverse.myStringFunction(str);
}

public static void main (String args[]) {
	// Block lambda to reverse string
	MyString reverse = (str) -> {
		String result = "";
		
		for(int i = str.length()-1; i >= 0; i--)
			result += str.charAt(i);
		
		return result;
	};

	// Output: omeD adbmaL
	System.out.println(reverseStr(reverse, "Lambda Demo")); 
}
```

