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
 * var <variable_name> <data_type> = <value>
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
* name := "admin"  -> short hand variable declaration

# Local and global variables
* The inner blocks can access the variables declared in the outer blocks.
* The outer blocks cannot access the variables declared in the inner blocks.

# Default values 
* string = ""
* bool = false
* float = 0.00

# Taking user input
* To take the input from the user we use scanf.
```
package main
import "fmt"
func main() {
  var name string
  var age int
  fmt.Print("Enter name and age")
  fmt.Scanf("%s %d", &name, &age)
  fmt.Println("name is ", name)
  fmt.Println("age is ", age)
}
```
```
package main
import "fmt"
func main() {
  var name string
  var age int
  fmt.Print("Enter Name and age")
  count,err := fmt.Scanf("%s %d", &name, &age)
  fmt.Println("count: ", count)  //Here count has the number of correct input variables set.
  fmt.Println("error: ", err)  //if there is an error it will be stored in err variable.
  fmt.Println("name is ", name)
  fmt.Println("age is ", age)
}
```
```
package main
import (
"fmt"
"reflect"
)
func main() {
  var name string := "Dhruva"
  fmt.Printf("Type: %v \n", reflect.TypeOf(1000)) //reflect package gives the type of variable, literal or constant
  fmt.Printf("Type: %T \n", name)
}
```

# Converting between data types (Type casting)
*The process of converting one data to another is called Type casting.
* converting int to float
```
  package main
  import "fmt"
  func main() {
    var i int = 50
    var f float64 = float64(i)
    fmt.Printf(%v is converted to %T type", i, f)
}
```

* To convert string to integer and vice-versa, strconv package is used
```
  package main
  import (
    "fmt"
    "strconv"
  )
  func main() {
    var i int = 50
    var s string = strconv.Itoa(i) //converts integer to string
    fmt.Printf("%v \n",s)
    fmt.Printf("%T \n",s)
    var name string = "200"
    num, err := strconv.Atoi(name) //converts string to integer. This returns 2 values.
    fmt.Printf("%v \n", num)
    fmt.Printf("%T \n", num)
    fmt.Printf("%v \n", err)
  }
```

# Constants
* variable should be given a value while declaration. variable value can't be modified once declared.
* short hand declaration (:=) should not be used while declaring constant.
* const <variable_name> <data_type> = <value> . Data_type is optional.
* There are 2 types. 1.Typed 2.Untyped
### untyped
* data_type is not explicitly defined. More flexible
* Eg: const age = 20
* Eg: const name,age = "Dhruva", 20
### typed
* data_type is explicitly defined.
* Eg: const name string = "Dhruva"

# Operators and Operands
### Operators
* Types of Operators:
 * Comparision operators
 * Assignment operators
 * Arithmatic operators
 * Bitwise operators
 * Logical operators

### Comparision operator:
 * compares two operands of same data type and yields a boolean value (true/false). If two operands of different data types are compared will result in error.
 * (==) equal
 * (!=) not equal
 * (>) greater than
 * (>=) greater than or equal to
 * (<) less than
 * (<=) less than or equal to

### Arithmatic operator:
 * common arithmatic operations such as addition, subtraction, multiplication, division etc.
 * (+) addition
    * when addition operator is used on int type, it will result in sum of those numbers. If used on strings, then it will concat the strings. If used between int and 
      float or int and string it will result in error.
 * (-) subtraction
 * (*) multiplication
 * (/) division -> returns the quotient
 * (%) modulus -> returns the remainder
 * (++) increment
 * (--) decrement
