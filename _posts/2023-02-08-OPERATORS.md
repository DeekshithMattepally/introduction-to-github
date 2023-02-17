OPERATORS IN GO LANG

Any programming language's core is its set of operators. As a result, the Go programming language is only sufficient with the use of operators. Operands can be subjected to a variety of procedures thanks to operators. According to their various functionalities, Go operators can be divided into the following categories:

Arithmetic Operators
Relational Operators
Logical Operators
Bitwise Operators
Assignment Operators
Misc Operators

ARITHMETIC OPERATORS:

They are used to perform mathematical operands.

+, -, *, /, %

	Example:
          
	  package main
          import "fmt"
          func main() {
          
	p := 34
	q := 20

		result := [4]int{p + q, p - q, p * q, p / q}
	fmt.Printf("Result of p + q = %d\n", result[0])
	fmt.Printf("Result of p - q = %d\n", result[1])
	fmt.Printf("Result of p * q = %d\n", result[2])
	fmt.Printf("Result of p / q = %d\n", result[3]) }



Output:


Result of p + q = 54

Result of p - q = 14

Result of p * q = 680

Result of p / q = 1




RELATIONAL OPERATORS: They are used to compare two values
''=='', ''!'', ''>'', ''<'', ''>='', ''<=''

  	
	Example: 
		  // Go program to illustrate the
		  // use of relational operators
                    package main
                    import "fmt"
                    func main() {

                    p:= 34
                    q:= 20
	
		// '=='(Equal To)
	result1:= p == q
	fmt.Println(result1)
		// '!='(Not Equal To)
	result2:= p != q
	fmt.Println(result2)
		// '<'(Less Than)
	result3:= p < q
	fmt.Println(result3)
		// '>'(Greater Than)
	result4:= p > q
	fmt.Println(result4)
		// '>='(Greater Than Equal To)
	result5:= p >= q
	fmt.Println(result5)
		// '<='(Less Than Equal To)
	result6:= p <= q
	fmt.Println(result6) }


Output: 
	
	false
	
	true
	
	false
	
	true
	
	true
	
	false

LOGICAL OPERATORS: They are utilized to complement the evaluation of the initial condition under consideration or to integrate two or more conditions or limitations.

Logical AND, logical OR, logical NOT

          Example:
	// Go program to illustrate the
	// use of logical operators
		package main
		import "fmt"
		func main() {
		var p int = 23
		var q int = 60
		if(p!=q && p<=q){
			fmt.Println("True")
			}
			if(p!=q || p<=q){
			fmt.Println("True")
			}
			if(!(p==q)){
			fmt.Println("True")
			} }	

Output: 
	
	True
	
	True
	
	True
	
BITWISE OPERATORS: these are used to perform bit-by-bit operations.
 & (bitwise AND), | (bitwise OR), ^ (bitwise XOR), << (left shift), >>(right shift), &^ (AND NOT)
 
	Example: 
		// Go program to illustrate the
		// use of bitwise operators
		
		package main
		import "fmt"
		func main() {
	p:= 33
	q:= 58
			
			
			// & (bitwise AND)
			result1:= p & q
			fmt.Printf("Result of p & q = %d", result1)
			// | (bitwise OR)
			result2:= p | q
			fmt.Printf("\nResult of p | q = %d", result2)
			// ^ (bitwise XOR)
			result3:= p ^ q
			fmt.Printf("\nResult of p ^ q = %d", result3)
			// << (left shift)
			result4:= p << 1
			fmt.Printf("\nResult of p << 1 = %d", result4)
			// >> (right shift)
			result5:= p >> 1
			fmt.Printf("\nResult of p >> 1 = %d", result5)
			// &^ (AND NOT)
			result6:= p &^ q
			fmt.Printf("\nResult of p &^ q = %d", result6) }

Output: 
		
		Result of p & q = 32
		
		Result of p | q = 59
		
		Result of p ^ q = 27
		
		Result of p << 1 = 66
		
		Result of p >> 1 = 16
		
		Result of p &^ q = 1

ASSIGNMENT OPERATORS: To give a variable a value, assignment operators are utilized. The assignment operator has a variable as its left-side operand and a value as its right-side operand. The variable's data type must match the value on the right side for the compiler not to produce an error.

"=" (Simple Assignment)
"+=" (Add Assignment)
"-=" (Subtract Assignment)
"*=" (Multiply Assignment)
"/=" (Division Assignment) 
"%=" (Modulus Assignment)
"&=" (Bitwise AND Assignment)
"^=" (Bitwise Exclusive OR)
"|=" (Bitwise Inclusive OR)
"<<=" (Left shift AND Assignment operator)
">>="(Right shift AND assignment operator)
	

		Example:
			// Go program to illustrate the
			// use of assignment operators
			
		  package main
		  import "fmt"	
		  func main() {
		  
	var p int = 85
	var q int = 60
			
			// "="(Simple Assignment)
		p = q
		fmt.Println(p)
			// "+="(Add Assignment)
		p += q
		fmt.Println(p)
			// "-="(Subtract Assignment)
		p -= q
		fmt.Println(p)
			// "*="(Multiply Assignment)
		p *= q
		fmt.Println(p)
			// "/="(Division Assignment)
		p /= q
		fmt.Println(p)
			// "%="(Modulus Assignment)
		p %= q
		fmt.Println(p) }


Output: 
	
	60
	
	120
	
	60
	
	3600
	
	60
	
	0

MISC OPERATORS:
"&": This operator returns the variable's address.
"*": This operator gives a pointer to a variable.
"<"-: This operator is known as receive. A value is obtained from the channel using it.

	Example:
		// Go program to illustrate the
		// use of Misc Operators

		package main
		import "fmt"
		fund main() {
	a := 6
		// Using address of operator(&) and
		// pointer indirection(*) operator
		b := &a
		fmt.Println(*b)
		*b = 9
		fmt.Println(a) }
	
Output: 
	
	
	6
	
	9
