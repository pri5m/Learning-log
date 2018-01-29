
[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4534176-dt-content-rid-9331524_2/courses/1718-CM6121/IntroJava%281%29.pdf)

**What is java?**


• Compiled	/	interpreted

• Concurrent

• Object	orientated	

• Class	based

**Files**

• .java
    The	code	file	
• .class
    The	bytecode
• .jar	
    Java	archive	files
    
**Memory**


• Heap

  • Thread	local	areas	for	small	objects
  
    • Non	synchronized
    
  • Large	objects	directly	on	the	heap.	
  
• Thread	stacks

  • Said	Java	is	a	concurrent	language
  
    • Stack	same	as	the	call	stack	in	JS
    
  • But	for	each	thread
  
Garbage colection is activated when the heap becomes full

Every time you create a new var/object Memory is assigned

When the object is no longer in use it is deleted by the garbage collector

**JS vs Java**

- Java is an OOP programming language while Java Script is an OOP scripting language.

- Java creates applications that run in a virtual machine or browser while JavaScript code is run on a browser only.

- Java code needs to be compiled while JavaScript code are all in text.

**Python vs Java**

A Key Difference: Duck Typing.

The biggest difference between the two languages is that Java is a statically typed and Python is a dynamically typed. Python is strongly but dynamically typed. This means names in code are bound to strongly typed objects at runtime.

**Message.java**
```java
public class Message {//The beginning of a class

  private String message; //field object

  public Message(String aMessage){ //this is the constructor
    this.message=aMessage
  }
  public void printMessage(){ //Method object
    System.out.println(message);
  }
}
```

**FirstExercise.java**
```java
public class FirstExercise{
  //'public'- Access modifier, 'FirstExercise'- Same name as the file
  public static void main (String args[]){
    Message hw = new Meassage("Hi Hol");
    //Message- the object, hw- the var that contains the object message
    //'new'- Operator makes a message object and the object in the var hw
    hw.printMessage();
    // Use of method printMessage on the instance of the class message
  }
}
```
To run:

Command prompt

• javac FirstExercise.java

• java	FirstExercise

```
Hi Hol
```

Both files are compiled when one is complied the other is automatically compiled with 'main' in it.

Compile the file with 'main'in it first and the others will auto compile if in the same directory.

**SecondExercise.java**
```java
public class SecondExercise{
  public static void main(String[] args){
    Message mess1 = new Message("Hello world");
    Message mess2 = new Message("I'm writing my first Java program");
    Message mess3 = new Message("It's fun (ish)");
    mess1.printMessage();
    mess2.printMessage();
    mess3.printMessage();
  }
}

```

**Output**
```
Hello world
I'm writing my first Java program
It's fun (ish)
```

**Types: primative**

*Integer	types*

• byte:	8	bit	

• short:	16	bit

• int:	32	bit

• long:	64	bit

*Real	types*

• float:	32	bit

• double:	64	bit

*Other*

• char:	16-bit	Unicode	character

• boolean:	true and false

**Cat.java**
```java
public class Cat{
  private String name;
  private String food;

  public Cat(String aName, String someFood){
    this.name = aName;
    this.food = someFood;
  }

  public void eat(){
    System.out.println(food+" is tasty!");
  }
  public void sayHello(){
    System.out.println("My name is "+name+" Mmmrrrooowww");
  }
}

```

**ThirdExercise.java**
```java
public class ThirdExercise{

  public static void main (String args[]){
    Cat felix = new Cat("Felix", "Tuna");
    felix.eat();
    felix.sayHello();
    Cat tom = new Cat("Tom", "Milk");
    tom.eat();
    tom.sayHello();
  }
}
```
