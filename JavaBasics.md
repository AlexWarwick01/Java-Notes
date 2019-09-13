***BASIC JAVA NOTES START HERE***
*CLARITY NEEDED* basically means i haven't looked it up yet so dunno what the it means.
**Side note** all programs have been compiled using javac hence why there is a .java and a .class file **end**
**Double side note** Using an actual IDE now so that does it for me **end**
**Analysing the Helloworld.java file**
\\filepath ./Java/Basics/TestPrograms/Helloworld/helloworld.java
***JVM STANDS FOR JAVA VIRTUAL MACHINE***
This app consists of 3 main parts
 - On line 1 we declare use *class* to show that a new class is being declared and we assign it the name *Helloworld* this name is used as the identifier. (This is incredibly similar to how classes work in ruby and VB.NET)

 - On line 3 we delcare PSVM(Public Static Void Main) and give it the ability to accept a String as an argument.
 **Breakdown of PSVM**
 - Public allows the method to be executed anywhere from within the JVM. (Private and possibly Protected are others(those will come later))

 - Static means that the main method is going to be called without object(*CLARITY NEEDED*). Public and Static can be written in either order so you can have PSVM or SPVM.

 - Void means that the method isnt going to return anything - it will just output *Hello World* to the console.

 - Main() Name that is configured inside JVM.

- Main shares similarities with C/++, fortunately i don't need to know that.
**BREAKDOWN OVER**

- Finally, on line 5, we output Hello world to the console using the *System.out.println* command.

- System is a pre-defined class that provides access to the system.
- Out is a varaible of Output Stream.

**COMMENTS**
- single line is //
- multiline is /* to start and */* to end

**COMPILER**
- Now that we have created the code, we can use JAVAC to create a file that contains the byte code.
This code can then be executed by using java and then the class name. For example, i can execute the Helloworld bytecode by using java Helloworld rather than executing the file by using java helloworld.java.
**ANALYSIS OVER**

***TAKING IN USER INPUT***
Firstly, you will need to Import the scanner class using the following code(*import java.unil.scanner*)

Inorder to create an instance of this you will do (*Scanner myObj = new Scanner(System.in);*)
Then inorder to assign the user input to a variable you can do something like this(*String name = myObj.nextline()*).
 This reads the user input and will assign it to the variable name with type String. nextLine() will read a string value from the user.

You then just use System.out.println(name) to display the name the user has inputted.
***END***

**INPUT TYPES**
- nextBoolean() reads a boolean value from the user
- nextByte() reads a byte value from the user
- nextDouble() reads a double value from the user
- nextFloat() reads a float value from the user
- nextInt() reads an int value from the user
- nextLong() reads a long(*CLARITY NEEDED*) value from the user
- nextShort() reads a short(*CLARITY NEEDED*) value from the user
- nextLine() reads a string - i really should have written this down sooner.
**END**

**IF(STATEMENTS){**
They are actually identical to Javascript If statements.
The syntax is as follows:
If(CONDITION){
  \\CODE GOES HERE;
}

if(CONDITION){
  \\CODE GOES HERE;
}else if(CONDITION){

}

Code Example:
If(5 > 4){
  System.out.println("Yes, thats how math works...");
} else{
  System.out.println("what?");

}
This here is an if else statement, It will check a condition(is 5 bigger than 4 in this case) and will execute the first bit of code if its true(which it always should be in this context). If the condition fails, it will execute the else code.
**}**

***ANALYSING CALCULATOR APP***
\\filepath ./Java/TestPrograms/Basics/Calculator/calculator.java
Starts by importing the java.util.Scanner utility so i can read user inputs.
Declare the Calculator class
Declares the PSVM with String[] args(This is actually completely needed)
Line 6 i declare a new Scanner and give it the identifier myObj(as this is what i had seen in examples)
Lines 7, 9 and 11 are purely there for User benefit so they know what to do(Simply use the System.out.println)
Line 8 i declare a new int called num1, due to how nextInt() works, in order to actually get the user input into this variable without breaking everything later, i had to use Integer.parseInt(myObj.nextLine()). If i didn't do this then when i came to assign an operand it would skip the line of code entirely and crash. This is explained later.
Same happens on line 10 but this time with num2
Line 12 i declare the operand String and set it equal to the myObj.nextLine().
Line 14 i call the private method that contains the calculator logic and i pass it the 3 variables of (int num1, int num2, String operand).

Line 18 starts the If Else statement. This will compare the value in operand to each of the 4 basic mathematical operators(+,-,/,x).
if (operand.equals("+")){
  output = num1 + num2;
This is the first part of the statement, it checks if operand equals +, if it does it will set output equal to the result of adding num1 and num2, if it doesn't it will move on to the next part of the statement.
If the entire statement is completed with none of the requirements being met, an Else is used that displays "Invalid Operand" and then ends.
***ANALYSIS OVER***

**LOOPS IN JAVA**
There are 3 main types of loop
 - For loop(Used for the FizzBuzz app)
 - While loop
 - Do While loop
***FOR LOOPS***
The For loop is a control flow statement that will iterate a part of the program multiple times.
They should be used when the number of iterations of the loop is fixed.
The syntax for the for loop is as follows:
for(initialize;condition;+/-)
In code this will be written as
for(int i = 1;i <= 100; i++){
  System.out.println(i);
}
This is defining a new int i and setting it to = 1, the condition is i <= 100 meaning this loop will run provided i is less than or equal to 100 and the i++ means it will increment(i-- will decrement however you will then be stuck in an infinite loop of hell and doom)
HOWEVER!!
if you actaully want an loop to go almost infinitely, firstly don't use a for and secondly:
for(;;){
  \\code
}
should work.
***END***

***WHILE LOOPS***
In java, a while loop is a control flow statement that executes a part of the program repeatedly based on a given boolean(true/false) condition.
They should be used when the number of iterations if not fixed(when you don't know how many times your code needs to loop.) They can also be used when you do know how many times your code will run but a for loop is better for that.
The syntax for this is as follows:
while(condition){
  \\code goes here
}
In code, this could look like:
int i = 1;
while(i<=100){
  System.out.println(i);
  i++;
}
Just like the for loop above, this will run through numbers 1-100 and print it out into the console.
If you want an infinite loop for some weird reason, you can use:
int i = 1
while(true){
  System.out.println(i);
  i++;
}
This will infinitely loop and display the numbers between 1 and getting bored and turning the program off.
***END***

***DO WHILE LOOPS***
In java, a do while loop is a control flow statement that will execute part of the program at least once. Further execution is determined by a boolean condition.
These are used when the number of iterations is not fixed but the code inside the loop must be ran at least once.
The syntax for this is as follows:
do{
  \\here be code(or pirates)
}while(condition);
In code, this could look like:
int i=1;
do{
  System.out.println(i);
  i++;
}while(i<=100);
Exactly the same output as the other 2 loops, it will run the code at least once, outputting 1 and then check the condition and run while i <= 100.
You can probably figure out how to make this loop infinitely.
***END***
**LOOPS DONE, THANK YOU FOR COMING TO MY TED TALK**

***ANALYSIS OF FIZZBUZZ***
\\filepath ./Java/Basics/TestPrograms/FizzBuzz/FizzBuzz.java
No need to start with any imports as this program takes no user input and just spits out a load of numbers and assorted fizzes and buzzes at them.
As usual, i start with declaring class FizzBuzz.
Declare PSVM with String[] args.
Line 5 i declare the for loop. inside this i declare int i and set it to 0, then, the condition of the loop is set(it will keep looping until i <= 100) and finally i state that it is going to increment i each time.
Line 7 i start the If iteration that is going to check if i/3 and i/5 both give a remainder of 0
If they do, FizzBuzz is outputted and the loop restarts, else it moves on.
Line 9 i start the If iteration that is going to check if i/3 gives a remainder of 0
If it does, Fizz is outputted and the loop restarts, else it moves on.
Line 11 i start the If iteration that is going to check if i/5 gives a remainder of 0
If it does, Buzz is outputted and the loop restarts, else it moves on.
Finally, if none of these conditions are met, the code simply outputs i and then restarts the loop.
***END***

**WHAT PARSE INT ACTUALLY DOES**
Integer.parseInt()
