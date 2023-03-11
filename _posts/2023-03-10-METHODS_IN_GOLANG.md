**METHODS IN GO LANG:**

Go language assistance techniques. With one exception—the method's inclusion of a receiver argument—Go methods and Go functions are comparable. The method can access the receiver's properties by using the receiver parameter. The receiver, in this case, can be either struct- or non-struct-type. The receiver and receiver type must be present in the same package when we create a method in our code. Also, we are not permitted to write a method whose receiver type is an already existing inbuilt type (such as an int, string, etc.) declared in another package. The compiler will give us an error if we attempt to do so.

Syntax:
func(reciver_name Type) method_name(parameter_list)(return_type){
// Code
}

**METHOD WITH “STRUCT” TYPE INSTRUCTOR:**

We are permitted to define a method in the Go language whose receiver is a struct type. This receiver is reachable within the method, as demonstrated in the example below:

Example:

            package main
            import "fmt"
            type Person struct {
            Name string
            Age  int
            }
            func (p Person) Greet() {
            fmt.Printf("Hello, my name is %s and I'm %d years old.\n", p.Name, p.Age)
            }
            func main() {
            p := Person{Name: "Deekshith", Age: 24}
            p.Greet()
            }

Output: 

  Hello, my name is Deekshith and I'm 24 years old.


•In this example, we define a Person struct with two fields: Name and Age. We then define a method called Greet on the Person struct, which uses a Person receiver to access the Name and Age fields of the struct and print a greeting message.

•Finally, in the main function, we create a new Person struct with the name "Deekshith" and age 24, and call the Greet method on it to print the greeting message.

**Method with “non-struct” type receiver:**

As long as the type definition and the method definition are present in the same package, we are permitted to write a Go method with a non-struct type receiver. If they are defined in distinct packages, such as int, string, etc., the compiler will report an error.

Example:

    package main
    import "fmt"
    type MyInt int
    func (m MyInt) Double() MyInt {
    return m * 2
    }
    func main() {
    m := MyInt(10)
    fmt.Println(m.Double())
    }

Output:

  20

•In this example, we define a new type MyInt as an alias for the built-in int type using the type keyword. We then define a method Double on the MyInt type, which uses a MyInt receiver to access the integer value and return its double.

•Finally, in the main function, we create a new MyInt value with the value of 10, and call the Double method on it to print the result of doubling the value (which is 20).

**Method with “POINTER” receiver:**

We can write a method in the Go language with a pointer receiver. A modification made to the method will be reflected in the caller with the aid of a pointer receiver, which is not possible with methods that use value receivers.

Example:

      package main
      import "fmt"
      type Counter struct {
      count int
      }
      func (c *Counter) Increment() {
      c.count++
      }
      func main() {
      c := Counter{count: 0}
      c.Increment()
      fmt.Println(c.count)

      // Increment counter using pointer

      cp := &c
      cp.Increment()
      fmt.Println(c.count)
      }


Output:

  1
  
  
  2



•In this example, we build a Counter struct with one field, count, and a function, Increment, that accesses and modifies the count field via a pointer recipient (*Counter).

•In the main function, a new Counter instance c is created with a starting count of 0, and the count is increased by 1 by calling the Increment method on it. The current count value is then printed.

•We then use the & operator to construct a pointer cp to the c instance, and we call the Increment method on the pointer cp to increase the count by 1 more. Then, after printing the current count value once more, we can see that it has increased twice. Note that we can use either the pointer or the receiver to call the pointer receiver method using either the pointer or the value, as demonstrated in the program.


**Method can accept both “POINTER and VALUE”:	
**

As is generally known, functions in Go that take a value argument will only accept the values of the parameter; attempting to give a pointer to a value function will result in an error. So regardless of whether a Go method is defined with a pointer or value receiver, it can accept both values and pointers.

Example:

        package main
        import "fmt"
        type Person struct {
        Name string
        Age  int
        }
        func (p Person) Greet() {
        fmt.Printf("Hello, my name is %s and I'm %d years old.\n", p.Name, p.Age)
        }
        func (p *Person) SetAge(age int) {
        p.Age = age
        }
        func main() {
          
        // Using a value receiver method
          
        p1 := Person{Name: "Deekshith", Age: 24}
        p1.Greet()

        // Using a pointer receiver method
        
        p2 := &Person{Name: "Deepak", Age: 22}
        p2.SetAge(30)
        p2.Greet()

        // Using a value receiver method on a pointer
        
        p3 := &Person{Name: "RamaKrishna", Age: 47}
        (*p3).Greet()

        // Using a pointer receiver method on a value
        
        p4 := Person{Name: "Srilatha", Age: 40}
        (&p4).SetAge(40)
        p4.Greet()
        }
        
Output:

      
      Hello, my name is Deekshith and I'm 24 years old.
      
      Hello, my name is Deepak and I'm 30 years old.
      
      Hello, my name is RamaKrishna and I'm 47 years old.
      
      Hello, my name is Srilatha and I'm 40 years old.


•In this example, a Person struct is defined using the attributes Name and Age. Then, we define two methods: Greet, which prints a greeting message using a value receiver, and SetAge, which sets the person's age using a pointer receiver.

•We employ these techniques in the main function to show how they work. By utilizing the value receiver method Greet and the pointer receiver methods SetAge and Greet, we create two instances of the Person class: p1 and p2, respectively.

•We also show how to perform a pointer receiver method SetAge on a value p4 of the Person type before invoking a value receiver method Greet on a pointer p3 to a Person instance.

•As you can see, using value receivers and pointer receivers with methods is very flexible in Go.


**Differences between method and function:
**

In Go, a function is a standalone piece of code that performs a specific task, while a method is a function connected to a method. particular type and can access and modify the data within that type. Here are some key differences between methods and functions:


•Associated with a type: Methods are associated with a type and can access and modify the data within that type, while functions are standalone and do not have access to any data that is not explicitly passed to them as arguments.

•Syntax: Methods are defined using the func keyword, followed by the receiver type and a method name, while functions are defined using the func keyword and a function name.

•Functionality: Methods are usually used to encapsulate behavior that is specific to a particular type, while functions are more general-purpose and can be used in a wider range of contexts.

•Call Syntax: To call a method, you need to have an instance of the type to which the method belongs and call it using the dot notation. In contrast, to call a function, you just need to call it by its name.

**Structures in go lang:**

A struct is a type of object that can be used to represent any real-world object with a collection of properties or fields. In Golang, a structure or struct is a user-defined type that enables the grouping or combining of things of potentially diverse types into one type. This idea is frequently likened to object-oriented programming classes. It can be referred to as a lightweight class that enables composition but not inheritance.
An address, for instance, consists of a name, street, city, state, and pincode. As seen below, these three properties should be combined into a single structure address.

Declaring a structure:
type Address struct {
      name string 
      street string
      city string
      state string
      Pincode int
}

The type keyword in the example above defines a new type. To demonstrate that we are defining a struct, the word is followed by the name of the type (Address) and the keyword struct. The curly braces of the struct hold a list of several fields. There are names and types for each field.
type Address struct {
    name, street, city, state string
    Pincode int
}

To define a structure the syntax is:
var a Address

The code above generates an Address type variable with a default value of zero. Zero indicates that all of the fields in a struct are set to their corresponding zero values. Name, Street, City, and State are set to "" and Pincode is set to 0 as a result.
Moreover, a struct literal can be used to initialize a struct type variable. Such as,
var a = Address{"Deekshith", "SRNagar", "Warangal", "Telangana", 506001}


example:

          // Golang program to show how to
          // declare and define the struct

          package main
          import "fmt"
          
          // Defining a struct type
          
          type Address struct {
          Name    string
          city    string
          Pincode int
          }

          func main() {

          // Declaring a variable of a `struct` type
          // All the struct fields are initialized
          // with their zero value
           
          var a Address
          fmt.Println(a)

          // Declaring and initializing a
          // struct using a struct literal
         
         a1 := Address{"Deekshith", "Warangal", 506001}

         fmt.Println("Address1: ", a1)

         // Naming fields while
         // initializing a struct
         a2 := Address{Name: "Deepak", city: "hanamkonda",
         Pincode: 506001}

         fmt.Println("Address2: ", a2)

         // Uninitialized fields are set to
         // their corresponding zero-value
            
         a3 := Address{Name: "Telangana"}
         fmt.Println("Address3: ", a3)
         }


Output:

  {  0}
  Address1:  {Deekshith Warangal 506001}
  Address2:  {Deepak hanamkonda 506001}
  Address3:  {Telangana  0}

**Pointers to a struct:**

Pointers are variables used to store the memory address of other variables in the Go programming language or Golang.

Example:

          package main
          import "fmt"
          type Person struct {
          Name string
          Age  int
          }
          func main() {
          
          // Create a new person
          
          p1 := Person{Name: "Deekshith", Age: 24}
          
          // Create a pointer to the person
          
          p2 := &p1

          // Print the values of the person and the pointer
          
          fmt.Println("Person:", p1.Name, p1.Age)
          fmt.Println("Pointer:", p2.Name, p2.Age)

          // Update the age of the person using the pointer
          
          p2.Age = 35

          // Print the updated values of the person and the pointer
          
          fmt.Println("Person:", p1.Name, p1.Age)
          fmt.Println("Pointer:", p2.Name, p2.Age)
          }


Output:

        
        Person: Deekshith 24
        
        Pointer: Deekshith 24
        
        Person: Deekshith 35
        
        Pointer: Deekshith 35


•We define a Person struct with two fields in this program: Name and Age. The & operator is then used to generate the new person p1 and a pointer to the person p2.

•Using fmt.Println, we print the values for the person and the pointer. Next, we use the pointer p2 to update the person's age. Given that p1 and p2 both refer to the same underlying data, this also changes p1's age.

•To ensure that the age has been updated for both the person and the pointer, we print the revised values for both again. As you can see, we can change the basic data of a struct using pointers rather than having to construct a new instance of the struct.


**Challenges faced by me while learning Methods in go lang are:**

•Syntax: The syntax for defining methods in Go is different from that of regular functions. It can take some time to get used to the syntax for defining receiver types and method names.

•Understanding receivers: I find it challenging to understand the concept of receivers in Go. It's essential to understand that a receiver is just a parameter that allows us to access and modify the data within a struct.

•Pointer receivers: Methods can have pointer receivers, which was a bit confusing for me. I struggle to understand the difference between pointer and value receivers and when to use each one.

•Naming conventions: Go has some naming conventions for methods that can be challenging to remember at first. For example, method names that start with a capital letter are exported and can be accessed from other packages.

•Interacting with other packages: I struggled with using methods from other packages and understanding how they work. It's essential to learn how to use packages and their methods effectively.

