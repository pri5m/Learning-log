30/1/18

[slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4536022-dt-content-rid-9366132_2/courses/1718-CM6121/ObjectOrientedJava_2.pdf)

**Constructors**

- Constructor	initialise	the	instance	variables	of	an	object

• Constructors	have	no	return	type	(not	even	void).

• Constructor	ARE	NOT	Methods	even	if	it’s	similar

• Constructor	is	use	to	construct	an	object,	so	to	be	used	with	“new”

• Name	of	the	constructor	is	always	the	same	as	the	name	of	the	class	
(Case	sensitive)

**ifelse**
```
If	(condition){	
do	this	stuff
}	else	{	
do	this	other	stuff
}
```


```java
import java.util.Scanner;
public class IfElse{
	public static void main (String args[]){
		System.out.println("What language do you want ?");
		Scanner in = new Scanner(System.in);
		String language = in.nextLine();
		if (language.equalsIgnoreCase("english")){
			System.out.println("This is an english version");
		}else{
			System.out.println("This is not an english version");
		}
	}
}
```

```
if	(condition	1)	{
….
}	else	if	(condition	2)	{
…..
}	else	if	(condition	3)	{
….
}	else	{
…..
}
```

```java
System.out.println("type	yes	or	something	else");
String	input	=	scanner.nextLine();
if	(input.equals("yes")	)		{
System.out.println("oh	yes");
}	else	if	(input.equals("no")	){
System.out.println("oh	no");
}	else{
System.out.println("what???!?!?!?");
}	
```

**Cat.java**

- Changed file name fron cat.java to Cat.java

- matxhed up cat instances
```java
public class Cat{
    private String name;
    private String typeOfFood;
    private String voice;
    private int dateOfBirth;

    public Cat(String aName){
    this.name=aName;
    }

    public Cat(String name, String typeOfFood, String voice, int dateOfBirth){
        this.name=name;
        this.typeOfFood=typeOfFood;
        this.voice=voice;
        this.dateOfBirth=dateOfBirth;
    }
    public String getName(){
        return name;
    }
		public String getTypeOfFood(){
    	return typeOfFood;
		}
    public void sayHello(){
    	System.out.println(voice);
    }
    public void printName(){
        System.out.println("I am "+name);
    }
    public double calculAge(){
        return (double)2018-dateOfBirth;
    }
    public double calculHumanAge() {
        return calculAge() * 7.5;
    }

		public void catAge(){
			System.out.println("How old is your cat?");
			if(calculHumanAge()>= 120.0){
				System.out.println("Are you sure your cat is still alive?");
			}else if (calculHumanAge()>= 80.0){
				System.out.println("Your cat is really old");
			}else if (calculHumanAge()>= 45.0){
				System.out.println("Your cat is still young");
			} else if (calculHumanAge()>= 15.0){
				System.out.println("Your cat is young");
			} else if (calculHumanAge()>= 7.6){
				System.out.println("Your cat is just born");
			} else{
				System.out.println("Your cat is not born yet");
			}
		}
}
```

**Exercise1.java**

```java
public class Exercise1{

  public static void main(String[] args){
    Cat cat1 = new Cat("Tom","Tuna", "mrrawww", 12);
    cat1.getName();
    cat1.catAge();
  }
}

```
