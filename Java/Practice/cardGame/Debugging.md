
**Incompatible operand types Scanner and String**

Added 
```java
String myVar = scanner.nextLine();
```
Needed to assign the scanner input as a string before use

**scanner cannot be resolved**

Correction
```java
Scanner playOrNo= new Scanner(System.in);
		System.out.println("Do you want to play 'between the two red queens'? Yes/No");
		String playOrNoString = playOrNo.nextLine();
		if(playOrNoString == "Yes"){
```

Needed to have two var names, playOrNo and playOrNoString. playOrNo is used for the scanner and is then converted into a string where it needs to have a different var name, in this case playOrNoString
