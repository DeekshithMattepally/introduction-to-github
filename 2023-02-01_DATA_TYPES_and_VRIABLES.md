DATA TYPES IN GOLANG: In GOLANG, data types are divided into four categories. They are 

BASIC TYPE: numbers, strings, and Boolean 
AGGREGATE TYPE: arrays and structs
REFERENCE TYPE: pointers, slices, maps, functions, and channel
INTERFACE TYPE

Here, in BASIC TYPE, numbers are categorized into three subcategories, which are 
Integers -  In the Go language, both signed and unsigned integers are available in four different sizes.
Floating-point numbers - In the Go language, floating-point numbers are divided into two categories.
Complex numbers - Complex numbers are divided into two parts. 

Example programs for numbers:

           // Go program to illustrate
           // the use of integers
           package main
           import "fmt"
           func main()

        {
           
           // Using 8-bit unsigned int
           var X uint8 = 225
           fmt.Println(X, X-3)
           
           // Using 16-bit signed int
           var Y int16 = 32767
           fmt.Println(Y+2, Y-2)
        }

Output: 
        225 222
       -32767 32765

Example program for Boolean:

          // Go program to illustrate
          // the use of booleans
          package main
          import "fmt"
          func main() 
        {
          
          // variables
           
            str1 := "SOFTWAREENGINEERING"
            str2:= "softwareengineering"
            str3:= "SOFTWAREENGINEERING"
            
            result1:= str1 == str2
            result2:= str1 == str3
            
            // Display the result
            
            fmt.Println( result1)
            fmt.Println( result2)
            
            // Display the type of
            // result1 and result2
            
            fmt.Printf("The type of result1 is %T and "+"the type of result2 is %T", result1, result2)
         }

OUTPUT: 

         false
         true
         The type of result1 is bool and the type of result2 is bool
 
 Example program for strings: 

              // Go program to illustrate
             // the use of strings
      package main
      import "fmt"
      func main()
      {

             // str variable which stores strings
             
              str := "DEEKSHITH"
              
             // Display the length of the string
             
              fmt.Printf("Length of the string is:%d",
                                       len(str))
             // Display the string
             
              fmt.Printf("\nString is: %s", str)
              
             // Display the type of str variable
             
              fmt.Printf("\nType of str is: %T", str)
       }


OUTPUT:

        Length of the string is: 9
        String is: DEEKSHITH
        Type of str is: string
        
	
VARIABLES IN GO:
A typical program employs a variety of values, some of which could change as it runs. As an illustration, consider a program that manipulates user-entered values. It is possible for values entered by one user and another user to be different. As a result, using variables is important because a different user might not utilize the same values. When a user enters a new value, the computer's Random Access Memory can store it temporarily. Because the values in this area of memory change as the operation is carried out, a new term for this phenomenon called variables emerged. A variable is a reference for data that can be altered in real-time.

There are specific rules for naming variables in GO LANG, and they are.

Variables must begin with a letter or an underscore (_) but not with a numerical one.
Variable names are case-sensitive.
Keywords are not allowed to use as a variable.

In GO LANG, variables are declared in two ways, they are.

Using var keyword
          Syntax: variable_name type = expression
          
Type or the = expression can be omitted in the syntax above, but not both.
The default value for the variable's type will be used if the = expression is absent. Typically, the default value is 0.
The value-initialize in the expression determines the type of variable if the type is removed.

Using the short variable declaration
          Syntax: variable_name:= expression
          
In the expression above, the type of the expression defines the type of the variable.

Example program for using the var keyword

          package main
          import "fmt"
          func main() {
	
	var name string = "Deekshith Mattepally"
	var age int = 26
	var height float64 = 5.7

	fmt.Println("Name:", name)
	fmt.Println("Age:", age)
	fmt.Println("Height:", height) }


OUTPUT:
	
	
	Name: Deekshith Mattepally
	
	Age: 26
	
	Height: 5.7

Example program for using the short variable declaration:

          package main
          import "fmt"
          func main() {
    // Short variable declaration
    age := 24
    name := "DEEKSHITH"
    cgpa:= 4.0
    
    fmt.Println(age)
    fmt.Println(name)
    fmt.Println(cgpa)
    fmt.Printf("The type of age is %T\n", age)
    fmt.Printf("The type of name is %T\n", name)
    fmt.Printf("The type of cgpa is %T\n", cgpa) }



OUTPUT:

        24
	
	DEEKSHITH
	
	4
	
	The type of a is int
	
	The type of b is string
	
	The type of c is float64
