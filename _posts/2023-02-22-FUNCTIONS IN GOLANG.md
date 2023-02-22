Function in Go lang:
Functions are program instructions or statements that permit users to reuse previously written code to save memory usage, speed up processing, and—most importantly—improve readability. A function is a group of statements that complete a particular task and return the outcome to the caller. A function may also carry out a specific activity without producing a result.
Function declaration:
Function declaration refers to the process of creating a function.

Syntax:
func function_name(Parameter-list)(Return_type){
    // function body.....
}

Declaration of a function contains:
func: The Go language uses a keyword called func to build functions.

function_name: The function's name is the function_name Parameter-list: It includes the function arguments' type and name.

Return_type: It is voluntary and contains the many kinds of values that the function can return. Including a return statement on your part is required if you use a return type.

Function calling:
When a user wants to call or invoke a function, this is known as function invocation. To use the function's features, you must call it. We have an area () function with two parameters, as illustrated in the sample below. Now, we use the name of this function, area(12.5, 10), with two parameters to call it in the main function.

Example program:

	package main
	import "fmt"
      	// calculateArea is used to find the
      	// area of a rectangle. It takes two
      	// parameters: length and width, both
     	// of which are floats. It returns a
     	// float value for the area.
	func calculateArea(length, width float64) float64
	{
	area := length * width
	return area
	}
	func main() 
	{
   	// Define the length and width of the rectangle
	length := 12.5
	width := 10.0
  	// Call the calculateArea function and store the result
	area := calculateArea(length, width)
 	// Print the area to the console
	fmt.Printf("The area of the rectangle is: %.2f\n", area)
	}

Output:

  	The area of the rectangle is: 125.00


Function arguments:

The arguments provided to a function in the Go programming language are called actual parameters, whereas the parameters received by a function are called formal parameters.
Note: Go uses the call-by-value method by default for passing arguments to functions.

There are two ways in the Go language to pass arguments to your function:
Call by value:
This method of transferring parameters copies the values of the actual parameters to the function’s formal parameters and stores the two types of parameters in different parts of memory. Hence, modifications made inside such functions do not affect the caller's actual parameters.

Example program:
	package main
	import "fmt"
// swap is a function that takes two integer values and swaps their values.
	func swap(a, b int) 
	{
	temp := a
	a = b
	b = temp
	}
	func main() 
	{
// Declare two integer variables and assign them values.
	x := 5
	y := 10
	// Call the swap function and pass in the two variables.
	swap(x, y)
// Print the values of x and y after the swap function call.
	fmt.Printf("x = %d, y = %d\n", x, y)
	}


Output:
 
 	x = 5, y = 10

Call by reference:
All changes in the function are reflected in the caller's actual parameters because the formal and basic parameters point to exact locations.

Example program:

package main
import "fmt"
    // swap is a function that takes two integer pointers and swaps their values.
func swap(a, b *int) 
{
temp := *a
*a = *b
*b = temp
}
func main() 
{
	// Declare two integer variables and assign them values.
x := 5
y := 10
	// Print the initial values of x and y.
fmt.Printf("Before swap: x = %d, y = %d\n", x, y)
	// Declare two integer pointers and assign them the addresses of x and y.
ptrX := &x
ptrY := &y
	// Call the swap function and pass in the two pointers.
swap(ptrX, ptrY)
	// Print the values of x and y after the swap function call.
fmt.Printf("After swap: x = %d, y = %d\n", x, y)
}

Output:
  Before swap: x = 5, y = 10
  After swap: x = 10, y = 5

Variadic functions:
Variadic functions are those that are invoked with different numbers of arguments. In the variadic function, a user may pass zero or more arguments, to put it another way. fmt.printl. An example of a variable function, which initially required one fixed statement before accepting any number of arguments.
Syntax:
function function_name(para1, para2...type)type {// code...}
Note: The type of the final parameter in the declaration of the variadic function is preceded by an ellipsis, as in (...). It means that any number of parameters of this type may be used to call the function.

Example program:
package main
import "fmt"
// printNumbers is a variadic function that takes a variable number of integers
// and prints them to the console separated by spaces.
func printNumbers(numbers ...int) {
    for _, num := range numbers {
        fmt.Printf("%d ", num)
    }
    fmt.Println()
}
func main() {
    // Call the printNumbers function with different numbers of arguments.
    printNumbers(1, 2, 3)
    printNumbers(4, 5)
    printNumbers(6)
}
Output:
1 2 3 
4 5 
6 

When we use a variadic function:
•	Instead of sending a slice to a function, you can use a variable function.
•	When the number of parameters is unknown, a variable function is utilized.
•	The readability of your program is improved when you utilize a variadic function.
•	Since your function's parameters likely originate from multiple data structures, variadic functions are beneficial (i.e., slice or array, etc.).
•	Using variadic functions in these circumstances prevents the need to create a data structure to send arguments to a function.


Anonymous functions:
An anonymous function is a unique feature offered by the Go programming language. A function without a name is referred to as anonymous. When you wish to develop an inline function, it is helpful. An anonymous function can create closure in the Go language. The term "function literal" can also refer to an anonymous function.

Syntax:
func(parameter_list)(return_type){
// code..

// Use return statement if return_type are given
// if return_type is not given, then do not 
// use return statement
return
}()
Example:
package main
import "fmt"
func main() {
    // Define an anonymous function that takes two integers as arguments
    // and returns their sum.
    add := func(a, b int) int {
        return a + b
    }
    // Call the anonymous function with two integers.
    result := add(3, 4)
    fmt.Println("Result:", result)
}
Output:
Result: 7

NOTES:
•	An anonymous function may be assigned to a variable in the Go programming language. When you assign a function to a variable, the variable's type changes to that of a function, allowing you to call it just like a function call, as demonstrated in the example below.
Example program;
package main
import "fmt"
func main() {
    // Define a slice of integers.
    numbers := []int{1, 2, 3, 4, 5}
    // Use an anonymous function to calculate the sum of the numbers.
    sum := func() int {
        result := 0
        for _, num := range numbers {
            result += num
        }
        return result
    }()
    // Print the sum of the numbers.
    fmt.Println("Sum of the numbers:", sum)
}
Output:

Sum of the numbers: 15






•	Can pass arguments in the anonymous function
Example program:
package main
import "fmt"
func main() {
	// Define an anonymous function that takes two integers
	// as arguments and returns their sum.
	sum := func(a, b int) int {
		return a + b
	}
	// Call the anonymous function with two numbers.
	result := sum(2, 3)
	// Print the result to the console.
	fmt.Println("The sum of 2 and 3 is", result)
}
Output:
The sum of 2 and 3 is 5

•	Can also pass an anonymous function into another function as a parameter.
Example program:
package main
import "fmt"
func main() {
	// Define an anonymous function that takes two integers as arguments
	// and returns their sum.
	sum := func(a, b int) int {
		return a + b
	}

	// Define a function called "calculate" that takes two integers and an
	// anonymous function as arguments. The function should call the anonymous
	// function with the two integers and return the result.
	calculate := func(a, b int, f func(int, int) int) int {
		return f(a, b)
	}
	// Call the "calculate" function with the two numbers 2 and 3, and the
	// anonymous "sum" function as arguments. This should return the sum of
	// 2 and 3 (i.e. 5).
	result := calculate(2, 3, sum)
	// Print the result to the console.
	fmt.Println("The sum of 2 and 3 is", result)
}
Output:
The sum of 2 and 3 is 5




•	Can also return an anonymous function from another function:
Example program:
package main
import "fmt"
// Returning anonymous function
func DM() func(i, j string) string {
	myf := func(i, j string) string {
		return i + j + "DEEKSHITH MATTEPALLY"
	}
	return myf
}
func main() {
	value := DM()
	fmt.Println(value("Welcome ", "to "))
}
OUTPUT:
Welcome to DEEKSHITH MATTEPALLY












