Main() and init() function in go lang:
The main() and init() methods are two that the Go programming language reserves for specific purposes.

Main() function:
The main package in the Go programming language is a unique package used with executable programs and contains the main() function. The entry point of executable programs is a unique function called main(). It neither accepts nor returns any arguments. Every executable program must contain a single main package and the main() function because go automatically calls the main() function, negating the need for explicit main() function calls.
Example program:

		package main
		import "fmt"
		func main() 
		{
		fmt.Println("Hello, my name is Deekshith Mattepally")
		}

Output:

  	Hello, my name is Deekshith Mattepally

•	The main() function, which is the program's entry point, is defined in this program. This indicates that the main() function will be called first when the program is executed.
•	The main() function generally includes much more code in a real program, including variable declarations, function calls, and other statements that specify the program's behavior.
 In this example, the main() method uses the fmt.Println() function to print "Hello, my name is Deekshith Mattepally" to the console. 
•	It is important to remember that Go always looks for the main package when running a program, where the main() function must always be specified. You will encounter errors if you try to define main() in a different package.

Init() function:
When a package is imported into memory in Go, a particular function called init() is called automatically. Any initialization operations that must be completed before the package can be used are usually carried out using the init() function defined in a package.
Wherever in the program we like, we can create an init() function, which is called in lexical file name order (Alphabetical Order). Moreover, statements may be included if the init() function is called, but always keep in mind that the init() method runs before the call to the main() function, therefore it is independent of the main() function. Initializing global variables that cannot be initialized in the global context is the primary goal of the init() function.

Example program:

		// Declaration of the main package
		
		package main

		// Importing package
		
		import "fmt"

		// Multiple init() function
		
		func init() {
		fmt.Println("Welcome to init() function")
		}
		func init() {
		fmt.Println("Hello! init() function")
		}

		// Main function
		
		func main() {
		fmt.Println("Welcome to main() function")
		}
Output:

		Welcome to init() function
		Hello! init() function
		Welcome to main() function

•	The Go program in the preceding example demonstrates the init() function's concept. We define two init() functions in this program, and when they are called, they each output a message to the terminal. Additionally, we define the main() method, which serves as the program's starting point and merely outputs another message on the console.
•	As we can see, the two init() functions are called before the main() function when the application launches automatically. The two init() functions are performed in the order they were defined because we defined two of them.
•	As long as they are all written in the same package, creating several init() functions in a Go program is OK. Several init() functions should be more advised, though, as they might make the program more challenging to comprehend and maintain. Generally speaking, it is better to define one init() function per package, using that method to carry out any initialization duties required.

Blank identifier(underscore) in go lang:

The underscore (_) is referred to as the "anonymous variable" or the "blank identifier" in Go. It is a unique identifier that can be used to ignore an expression's value or to denote the absence of a variable.
The main application of Blank Identifier is when a function returns a large number of items, but we only require a small subset of those values and wish to toss the rest. It instructs the compiler to ignore this variable without raising any errors because it is not required. It makes the program understandable and conceals the values of the variables. Hence, if you give Blank Identifier a value, it is rendered useless.

The blank Identifier in Go is frequently used in the following scenarios:

1.	Ignoring an expression's value:

		package main
		import "fmt"
		func main() {
		sum, _ := calculateSumAndProduct(2, 3)
		fmt.Println("Sum:", sum)
		}
		func calculateSumAndProduct(x, y int) (int, int) {
		return x+y, x*y
		}

Output:

		Sum: 5


•	In this example, the second return result from the calculateSumAndProduct() function is discarded using the blank Identifier. We utilize the blank Identifier to say that we are not interested in the result of the same numbers because we only care about the sum of two numbers.

2.	demonstrating the absence of a variable:
         
	package main
	import "fmt"
	func main()
	{
	numbers :=[]int{1,2,3,4,5}
	for _ , num :=range numbers
	{
	fmt.println(num)
	}
	}

	
OUTPUT:

		1
		2
		3
		4
		5

•	To indicate that we are not interested in the index of the elements in the numbers slice in this example, we use the blank Identifier. We use the blank Identifier to ignore the index because we are just interested in the values of the items.
•	It should be noted that the blank Identifier can be applied everywhere a variable is needed, but its value is not. The blank Identifier should only be used when it benefits the code. Overusing the blank Identifier is generally discouraged because it might make the code more difficult to read and maintain.

Defer keyword:
The defer keyword in Go is used to plan the execution of a function call to happen right before the function around it returns. No of how the function terminates, the defer statement is frequently used to guarantee that resources are released correctly.



Syntax:edd
	// Function
	
	defer func func_name(parameter_list Type)return_type{
	
	// Code
	
	}
	
	// Method
	
	defer func (receiver Type) method_name(parameter_list){
	
	// Code
	
	}
	
	defer func (parameter_list)(return_type){
	
	// code
	
	}()

Example program:

		package main
		import "fmt"
		func main() {
		defer fmt.Println("Second")
		defer fmt.Println("First")
		fmt.println("Hello")
		}

Output:

		Hello
		First
		Second

•	Several defer statements are permitted in a single Go program and carried out in LIFO (Last-In, First-Out).
•	The arguments in the defer statements are assessed during the execution of the defer statement, not during invocation.
•	Defer statements are frequently used to ensure that files are closed after they no longer need to be open, to end a channel, or to stop program panics.
