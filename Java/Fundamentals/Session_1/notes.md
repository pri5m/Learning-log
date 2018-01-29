
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
public class Message {
  private String message; //class var/field

  public Message(String aMessage){
    this.message=aMessage
  }
  public void printMessage(){
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

• javac FirstExercise.java

• java	FirstExercise

```
Hi Hol
```