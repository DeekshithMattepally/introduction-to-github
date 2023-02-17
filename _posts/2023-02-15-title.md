Control statements:
Making decisions in programming is equivalent to making decisions in everyday life. When the predetermined circumstance is met, the decision-making code is run. Golang employs control statements to regulate the program's execution based on specific circumstances. These are also known as the control flow statements at times. These are used to direct the flow of execution to advance and diverge in response to changes in a program's state.

DECISION-MAKING STATEMENTS IN GOLANG ARE:

IF STATEMENT:

The most straightforward decision-making statement is this one. It is used to decide whether to execute a specific word or block of statements, i.e., if a particular condition is proper, the union of statements is executed. Otherwise, not.

Syntax: 

if condition

{
// Statements to execute
if
// condition is true	
}

Example program:

	// Go program to illustrate the
	// use of if statement
		package main
		import "fmt"
		func main() 
		{
	// taking a local variable
	var v int = 700
	// using if statement for// checking the condition
	if v < 1000 
	{
	// print the following if
	// condition evaluates to true
	fmt.Printf("v is less than 1000\n")
	}
fmt.Printf("Value of v is : %d\n", v)
	}
	

Output:
	
	v is less than 1000

	value of v is: 700

IF-ELSE STATEMENT:

A block of statements will be executed if a condition is true, and if it is false, they won't be, according to the if statement alone. But what if the condition is false, and we want to take another action? The else statement is now made. If the condition is false, we can combine the else statement with if statement to run a code block.

Syntax:
	if condition 
	{
		// Executes this block if
		// condition is true
	}
	else 
	{
		// Executes this block if
		// condition is false
	}

Example program:
	
		// Go program to illustrate the
		// use of if...else statement
	package main
	import "fmt"
	func main()
	{
		// taking a local variable
	var v int = 1200
		// using if statement for
		// checking the condition
	if v < 1000
	{	
		// print the following if
		// condition evaluates to true
	fmt.Printf("v is less than 1000\n")	
	}
	else 
	{	
		// print the following if
		// condition evaluates to true
	fmt.Printf("v is greater than 1000\n")}	
	}


Output:
	
		v is greater than 1000

NESTED IF statement:

A nested if in the Go programming language is an if statement that is the object of another if or else. If statements can be nested by placing another if statement inside of them. Yes, we may nest if statements inside other if statements in Golang. Hence, we can nest one if statement inside another.

Syntax:
if condition1 
	{
	 // Executes when condition1 is true
	    if condition2
    	{
 	// Executes when condition2 is true
  	 }
	 }

Example program:

	package main
	import "fmt"
	func main() 
	{
	   x:=10
	   y:=20
	if x > 5
	{
        fmt.Println("x is greater than 5")
        if y > 15 
	{
        fmt.Println("y is greater than 15")
        } 
	else 
	{
        fmt.Println("y is not greater than 15")
        }
    	} 
    	else 
    	{
        fmt.Print
	ln("x is not greater than 5")
    	}
	}


Output:
	
	x is greater than 5
	
	y is greater than 15


If else If statement:

A user can choose from a variety of alternatives here. The if statements are carried out bottom-up. When one of the conditions governing the if is satisfied, the statement connected to that if is carried out, and the remainder of the ladder is skipped. The final else statement will be carried out if none of the conditions are met.

Syntax:
if condition_1 
{
	     // this block will execute 
	     // when condition_1 is true

} 
else if condition_2 {

	    // this block will execute 
	    // when condition2 is true
}
.
.
. 
else 
{

	    // this block will execute when none
	    // of the condition is true
}

Example program:

	package main
	import "fmt"
	func main() 
	{
   	 x := 10
	 if x < 5 
	 {
    	fmt.Println("x is less than 5")
    	 } 
        else if x < 15 
    	 {
       	fmt.Println("x is between 5 and 15")
   	 } 
	else 
	 {
        fmt.Println("x is greater than or equal to 15")
   	 }
	 }

	

Output:

	x is between 5 and 15

LOOPS IN GO LANG :

The only loop in the Go programming language is a for-loop. The repetition control structure known as a "for loop" enables us to create a loop that runs a certain number of times. This for loop has several uses in the Go programming language. They are:

FOR loop: 
It is identical to what we use in C, C++, Java, C#, and other programming languages.
Syntax: 
for initialization; condition; post{
       // statements....
}

Example:

		// Go program to illustrate the
		// use of simple for loop
	package main
	import "fmt"
		// Main function
	func main() 
	{
		// for loop
		// This loop starts when i = 0
		// executes till i<4 condition is true
		// post statement is i++
	for i := 0; i < 4; i++
	{
	fmt.Printf("DEEKSHITH MATTEPALLY\n")
	}
	}
	

Output: 

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

FOR loop as infinite loop:

By deleting all three expressions from the for loop, one may also use it as an infinite loop. if the condition statement is true and the loop enters an infinite loop if the user does not include a condition statement in the for loop.

Syntax:
for{
     //statement...
}

EXAMPLE PROGRAM:

		// Go program to illustrate the
		// use of an infinite loop
	package main
	import "fmt"
		// Main function
	func main() 
	{
		// Infinite loop
	for 
	{
	fmt.Printf("DEEKSHITH MATTEPALLY\n")
	}
	}


OUTPUT:

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	DEEKSHITH MATTEPALLY

	………………………………………………….


FOR loop as WHILE loop:
While loops can be used in place of for loops. The supplied condition must be true for this loop to continue. The loop terminates when the value of the specified condition is false.

Syntax:
for condition{
    //statement..
}

Example program:

		// Go program to illustrate the
		// the for loop as while Loop
	package main
	import "fmt"
		// Main function
	func main() 
	{
		// while loop
		// for loop executes till
		// i < 3 condition is true
	i:= 0
	for i < 3 
	{
	i += 2
	}
	fmt.Println(i)
	}
	

Output: 
	
	4

SIMPLE range in for Loop:
We can use range in for loop.

Syntax:
for i, j:= range rvariable{
   //statement..
}

Example program:

	package main
	import "fmt"
	func main()
	{
	nums:= []int{2, 4, 6, 8, 10}
	for index, value:= range nums 
	{
	fmt.Printf("Index: %d, Value: %d\n", index, value)
   	}
	}


OUTPUT:

	Index: 0, Value: 2

	Index: 1, Value: 4

	Index: 2, Value: 6

	Index: 3, Value: 8

	Index: 4, Value: 10


Using FOR loops for STRINGS:
The Unicode code point for a string can be iterated over using a for loop.

SYNTAX:
for index, chr:= range str{
     //statement..
}

EXAMPLE PROGRAM:

	package main
	import "fmt"
	func main() 
	{
    str := "Hello, World!"
    for i := 0; i < len(str); i++ 
   	 {
    fmt.Printf("Character at index %d is %c\n", i, str[i])
	 }
	 }



OUTPUT:
	
	Character at index 0 is H

	Character at index 1 is e

	Character at index 2 is l

	Character at index 3 is l

	Character at index 4 is o

	Character at index 5 is ,

	Character at index 6 is  

	Character at index 7 is W

	Character at index 8 is o

	Character at index 9 is r

	Character at index 10 is l

	Character at index 11 is d

	Character at index 12 is !

FOR maps:
The key and value pairs in the map can be iterated over in a for loop.

Syntax:
for key, value := range map { 
     //statement.. 
}

Example program:

		// Go program to illustrate the
		// use for loop using maps
	package main
	import "fmt"
		// Main function
	func main() 
	{
		// using maps
	mmap := map[int]string{
		22:"ABC",
		33:"PHANTOM",
		44:"DEEKSHITH MATTEPALLY",
	}
	for key, value:= range mmap 
	{
	fmt.Println(key, value)
	}
	}


Output:

	22 ABC

	33 PHANTONM

	44 DEEKSHITH MATTEPALLY

FOR Channel:
The channel's consecutive values can be iterated over in a for loop until the channel closes.

Syntax:
for item := range Chnl { 
     // statements..
}

Example program:

	// Go program to illustrate the
	// use for loop using channel
	package main
	import "fmt"
	// Main function
	func main() 
	{
	// using channel
	chnl := make(chan int)
	go func()
	{
	chnl <- 100
	chnl <- 1000
	chnl <- 10000
	chnl <- 100000
	close(chnl)
	}
	()
	for i:= range chnl 
	{
	fmt.Println(i)
	}	
	}
	

Output:

	100

	1000

	10000

	100000

SWITCH STATEMENT IN GO:
A multiway branch statement is a switch statement. Based on the value (also known as case) of the expression, it offers an effective approach to move execution to various areas of a code. The Go language supports both switch statement types, theyre:

EXPRESSION SWITCH:
Similar to the switch statement in the C, C++, and Java languages is the expression switch. It offers a simple method for allocating execution to various sections of code according on the expression's value.

Syntax:
switch optstatement; optexpression{
case expression1: Statement..
case expression2: Statement..
...
default: Statement..
}


Important notes on switch statement:
•	Opstatement and Opexpression are optional statements in the expression switch.
•	If there is an optstatement and an optexpression, a semicolon (;) must be placed between them.
•	The compiler assumes that the expression is true if the switch has no expression.
•	Simple statements like variable declarations, increment or assignment statements, function calls, etc. are included in the optional statement, also known as optstatement.
•	A variable's scope is restricted to the switch statement if it appears in the optional statement.
•	There is no break statement in the case and default statement of a switch statement. However , you may utilize the break and fallthrough statements if your application calls for itts.
•	In a switch statement, the default statement is optional.
•	If a case has numerous values that are separated by commas (,).
•	The compiler assumes that an expression is true if a case contains no expressions.

Example program:

		// Go program to illustrate the
		// concept of Expression switch
		// statement
	package main
	import "fmt"
	func main() 
	{
	
		// Switch statement with both
		// optional statement, i.e, day:=4
		// and expression, i.e, day
	switch day:=4; day
	{
	case 1:
	fmt.Println("Monday")
	case 2:
	fmt.Println("Tuesday")
	case 3:
	fmt.Println("Wednesday")
	case 4:
	fmt.Println("Thursday")
	case 5:
	fmt.Println("Friday")
	case 6:
	fmt.Println("Saturday")
	case 7:
	fmt.Println("Sunday")
	default:
	fmt.Println("Invalid")
	}
	}



Output: 

	Thursday

Example program without default block and optional statement block:

	package main
	import "fmt"
	func main() 
		// Switch statement without default statement
		// Switch statement without an optional statement
	{
    name := "John"
    switch name 
    	{
    case "Alice":
        fmt.Println("Hello, Alice!")
    case "Bob":
        fmt.Println("Hello, Bob!")
    case "John":
        fmt.Println("Hello, John!")
   	}
	}




Output:

	Hello, John!

Type switch:
A type switch is utilized when comparing kinds. The type that will be compared with the type in the switch expression is contained in the case of this switch.

Syntax:
switch optstatement; typeswitchexpression{
case typelist 1: Statement..
case typelist 2: Statement..
...
default: Statement..
}

Important points on type switch statement:
•	The opt statement, or optional statement, is comparable to the switch expression.
•	Whenever a case allows for the possibility of several values and these values are separated by commas (,).
•	There is no break statement in the case or default statement of a switch statement. If your software requires it, though, you may utilize the break and fallthrough statements.
•	In type switch statements, the default statement is not required.
•	The typeswitch is an expression with a type as the outcome.
•	The type of that variable depends on the type present in the case clause if an expression is assigned in a typeswitchexpression using the:= operator. When there are two or more types in the case clause, the variable's type is determined by the type in which it was created in the typeswitchexpression.

Example program:
	
	package main
	import "fmt"

	func printType(v interface{})
	{
	switch v.(type) 
    	{
		case int:
		    fmt.Println("v is an integer")
		case string:
		    fmt.Println("v is a string")

	default:
	 	fmt.Println("v is of an unknown type")
	}
	}

	func main() 
	
	{
		printType(42)
		printType("hello")
		printType(true)
	
	}
	

Output:

	v is an integer

	v is a string

	v is of an unknown type


