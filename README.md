# Golang Practice
* The starting line of the program should be a package.
* The package main is a special package which contains special function main.
* Main function acts as entry point for the executable programs. No need to call the main function explicitly.

# Static typed language
* Compiler throws an error when data types are used incorrectly. we need to mention the data type. Eg: Java, C++. int a, int b
* Advantages:
* Better performance
* Bugs can often be caught by a compiler
* Better data integrity

# Dynamic typed language
* Compiler does not enforce the type system. Eg: Python, JavaScript.
* Advantages:
* Faster to write code
* less rigid
* shorter learning curve

* Go has a concept of types that is either explicitly declared by a programmer or is inferred by the compiler.
* Go is a statically typed compiled language, that feels like dynamically typed interpreted language.

# Data types
* golang supports different data types such as string, number, boolean, array, slice, map.
  * Number
      * Number includes both integers and float
      * Integers are 2 types. 1. uint (unsigned integers) -> >=0 2. int (signed integers) -> both positive and negative numbers
      * float is of two types. float32 and float64.
   * string occupies 16 bytes.
   * bool takes values true and false. It occupies 1 byte of memory.
 * Syntax for variable declaration:
 * var <variable name> <data type> = <value>
 * var s string = "Hello world!"
 * var i int = 100
 * var b bool = false
 * var f float64 = 77.90

 * Types of print statements in golang:
 ```
   package main
   import "fmt"
   func main() {
     fmt.Println("Hello")  //this will print Hello and moves to new line
   }
```
```
   package main
   import "fmt"
   func main() {
     fmt.Print("Hello")  //this will print Hello and the cursor is in the same line
     fmt.Print("World")
   }
```
```
   package main
   import "fmt"
   func main() {
     fmt.Print("Hello", "\n")  //Here \n means new line. Prints Hello and moves to new line
     fmt.Print("Jeevan")
   }
```
```
   package main
   import "fmt"
   func main() {
     var user string = "Jeevan"
     fmt.Print("Hello ", user)
   }
```
```
   package main
   import "fmt"
   func main() {
     var user string = "Jeevan"
     fmt.Printf("Hello %s", Object arg(s))  //note: If you are using format specifiers then we should use Printf
   }
```

# Format specifiers
* format specifiers start with "%" symbol
* %v -> formats the value in default format
* %T -> type of the value
* %d -> integers
* %f -> floating numbers
* %.2f -> floating numbers upto 2 decimal points
* %t -> true or false
* %c -> character
* %q -> quoted characters/string




# Variable declaration

* var name string = "admin"
* var name,email string = "admin","admin@gmail.com"
```
* var(name string = "admin
  phone int = 999999999)
```
* name := "admin"

# Local and global variables
* The inner blocks can access the variables declared in the outer blocks.
* The outer blocks cannot access the variables declared in the inner blocks.

# Default values 
* string = ""
* bool = false
* float = 0.00

# Taking user input
* To take the input from the user 
