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
 * var <variable_name> <data_type> = value
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
    fmt.Printf("%v is converted to %T type", i, f)
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

### Logical operator:
 * logical AND (&&)
 * logical OR (||)
 * logical NOT (!)

### Assignment operator:
 * assign (=)
 * add and assign (+=) x += y => x = x + y
 * subtract and assign (-=) x -= y => x = x - y
 * multiply and assign (*=) x *= y => x = x * y
 * divide and assign (/=) x /= y => x = x/y
 * modulus and assign (%=) x %= y => x = x % y

### Bitwise operator
 * bitwise AND (&): Takes two numbers as operands and does AND on every bit of the two numbers.
 * Eg: 12 in binary is 00001100. 25 in binary is 00011001. If we do 12 & 25 then we get 00001000.
```
   00001100 => 12(decimal)
 & 00011001 => 25(decimal)
-------------
   00001000 => 8(decimal)
-------------
```
```
package main
import "fmt"
func main(){
  var x,y int = 12,25
  z := x & y
  fmt.Println(z)
}
```
 * bitwise OR (|): Takes two numbers as operands and does OR on every bit of the two numbers.
 * Eg: 12 in binary is 00001100. 25 in binary is 00011001. If we do 12 | 25 then we get 00011101.
```
   00001100 => 12(decimal)
 | 00011001 => 25(decimal)
-------------
   00011101 => 29(decimal)
-------------
```
```
package main
import "fmt"
func main(){
  var x,y int = 12,25
  z := x | y
  fmt.Println(z)
}
```
 * bitwise XOR (^): Takes two numbers as operands and does XOR on every bit of the two numbers.
 * The result of XOR is 1 only when both the bits are opposite.
 * Eg: 12 in binary is 00001100. 25 in binary is 00010101. If we do 12 | 25 then we get 00010101.
```
   00001100 => 12(decimal)
 ^ 00011001 => 25(decimal)
-------------
   00010101 => 21(decimal)
-------------
```
```
package main
import "fmt"
func main(){
  var x,y int = 12,25
  z := x ^ y
  fmt.Println(z)
}
```
 * Left shift (<<): Shifts all bits towards left by a certain number of specified bits.
 * The bit positions that have been vacated by the left shift operator are filled by 0.
 * Eg: 212 = 11010100 (binary)
 * 212 << 1 = 110101000 (424)
 ```
package main
import "fmt"
func main(){
  var x int = 212
  z := x << 1
  fmt.Println(z)
}
```
 * Right shift (>>): Shifts all bits towards right by a certain number of specified bits.
 * The bit positions that have been vacated by the right shift operator are filled by 0.
 * Eg: 212 = 11010100 (binary)
 * 212 >> 2 = 00110101 (53)
  ```
package main
import "fmt"
func main(){
  var x int = 212
  z := x >> 2
  fmt.Println(z)
}
```

# Control flow
* we can write "If" block independently without else if or else block
### if-else
```
  if (condition) {
    // block to be executed if the condition is met
  } else {
    // block to be executed if condition is not met
  }
```
* Valid syntax:
```
  if (condition) {
    // block to be executed if the condition is met
} else if (condition) {
    // block to be executed if the condition is met
} else {
    // block to be executed if none of the condition is met
}
```
* Invalid syntax:
```
  if (condition) {
    // block to be executed if the condition is met
  }
  else {
    // block to be executed if condition is not met
  }
```
Note: The else block or else if block must start just after the completion of previous block.
```
 package main
 import "fmt"
 func main() {
   var fruit string
   fmt.Print("Enter the fruit: ")
   fmt.Scanf("%v", &fruit)
   if fruit == "grapes" {
      fmt.Println("Fruit is a grape")
   } else if fruit == "orange" {
      fmt.Println("Fruit is an orange")
   } else {
      fmt.Println("Fruit does not match")
   }
}
```
# Switch statement:
```
package main
import "fmt"
func main() {
  var i int = 20
  switch i {
    case 10:
      fmt.Println("The value is 10")
    case 20,30:
      fmt.Println("The value is either 20 or 30)
    default:
      fmt.Println("The value is neither 10,20 nor 30)
}
}
output: The value is either 20 or 30.
```
* fallthrough is a keyword used in switch block. If fallthrough is used then the successive blocks will also get executed.
```
package main
import "fmt"
func main() {
  var i int = 20
  switch i {
    case 10:
      fmt.Println("The value is 10")
    case 20,30:
      fmt.Println("The value is either 20 or 30)
      fallthrough
    default:
      fmt.Println("The value is neither 10,20 nor 30)
}
}
output: The value is either 20 or 30.
The value is neither 10,20 nor 30.
```
```
package main
import "fmt"
func main() {
  var i int = 20
  var j int = 10
  switch {
    case a+b == 30:
      fmt.Println("The value is 30")
    case a+b >= 30:
      fmt.Println("The value is greater than or equal to 30)
    default:
      fmt.Println("The value is neither 10,20 nor 30)
}
}
output: The value is 30.
```
Note: When using switch with conditionals - we don't specify expression after switch.
Note: In go the switch case statement has an internal break statement.

### Looping
* for loop
```
 for initialization; condition; post{
     // statement
 }
```
```
  for i:=1;i<=5;i++ {
     fmt.Println(i)
  }
```
```
  i := 1
  for i<=5 {
     fmt.Println(i)
     i++
  }
```
* Break statement will come out of the loop.
* Continue statement will move to the next iteration.

### Arrays
Arrays are elements containing similar data type.
* Declaring an array:
* var <array_name> [array_length] <array_datatype> = [arrya_length] <array_datatype> <elements>
* Eg: var grades [5] int = [5] int{50,60,80,90,20}
* The elements in the array can be less than or equal to the length of the array but should not exceed the length.
* In arrays, the length and the capacity are equal.
* If we give more elements than the length of the array then it will throw an error.
* Eg: grades := [5] int{50,60,80,90,20} -> short hand declaration
* To retrieve the elements in the array, grades[1].
```
  package main
  import "fmt"
  func main() {
    var grades [5] int = [5] int{50,60,80,90,20}
    var l int = len(grades)
    for i:=0;i<l;i++{
        fmt.Println(grades[i])
    }
  }
```
```
  package main
  import "fmt"
  func main() {
    grades := [5] int{50,60,80,70,90}
    for index,elements := range grades {       //here range is the keyword used in the arrays
        fmt.Println(index," => ",elements)
    }
  }
```
* 2D-Array
```
package main
import "fmt"
func main() {
  grades := [3][2] int{{30,40},{60,70},{80,90}}
  var l int = len(grades)
    for i:=0;i<l;i++{
        for j:=0;j<=1;j++{
        fmt.Println(grades[i][j])
        }
    }
}
```
### slicing of an Array
* arr := [5]int{1,2,3,4,5}
* slice := arr[start_index:end_index]
* slice := []<datatype>{<values>}  //no need to specify the length of the slice
* slice := make([]<datatype>, length, capacity)  //used to create an empty slice
* len function will give the length and cap function gives the capacity.
* The slice taken from the array will reference to the array. It means, if we change the value of one of the index of a slice then the value from the main array will also be replaced.
* append function is used to append values to the slice. We can also append one slice to another slice.
* slice_1 := arr[2:5]
* slice_2 := arr[1]
* slice_3 := append(slice_1, slice_2...)  //the 3 dots after slice_2 are mandatory.
* If we want to append some values to slice then slice_4 = append(slice_1, value_1, value_2)
* num := copy(dest_slice, src_slice)
* The data type of both src and dest slice should be same inorder to copy.

### Maps
* Unordered collection of key/value pairs.
* Provide efficient add, get and delete operations.
* var <map_name> map[key_data_type]<value_data_type> -> If we initialize the map using this then we cannot add elements to the map.
* <map_name> := make(map[key_data_type]<value_data_type>,<initial_capacity>)
* <map_name> := map[key_data_type]<value_data_type>{key/value pairs}
* Eg: map := map[string]string{"en":"English", "hi":"Hindi", "Te":"Telugu"}
* value,found := <map_name>["en"]. The value will give the value associated with the key "en". The found will give the bool value. If "en" key is there then the found value is true.
* <map_name>["it"] = "Italian". By this we can add key/value pairs to the map.
* <map_name>["en"] = "English Language". By this we can update the existing key/value pairs.
* delete(<map_name>,<key_name>). By this we can delete the key and the corresponding value.
```
for key, value := range map {
    fmt.Println(key," => ",value)
}
```

# Functions
* function syntax:
  ```
   func <function_name>(function_parameters) <return_type> {
        // function body
  }
  ```
  ```
  package main
  import "fmt"
  func addNumbers(a int, b int) int {
     sum := a + b
     return sum
  }
  func main(){
   output := addNumbers(10, 20)
   fmt.Println("The sum of the numbers is: ",output)
  }
  ```
  * Note: Function names should not start with numbers and should not contain spaces.

* If a functions returns multiple values then we can declare function in the following way:
  ```
  func <function_name>(function_parameters) <return_types> {
     // function body
  }
  ```
  ```
  func arithmeticOperations(a int, b int) (sum int, diff int) {
     sum = a + b     // as sum and diff are already initialized, no need to use shorthand notation(:=)
     diff = a - b
     return
  }
  ```
  ```
    func arithmeticOperations(a int, b int) (int, int) {
     sum := a + b     // as sum and diff are not initialized, we should use shorthand notation(:=)
     diff := a - b
     return sum, diff
  }
  ```
  ### Variadic functions
  * Variadic functions are the functions that takes arbitary number of arguments of the defined datatype.
  ```
    package main
    import "fmt"
    func arithmeticOperations(a int, b ...int) int {
       sum := 0
       for _,n := range b {
           sum += n
       }
       output := sum + a
       return output
    }

    func main(){
        fmt.Println(arithmeticOperations(1))   // output is 1
        fmt.Println(arithmeticOperations(1,2))  // output is 3
        fmt.Println(arithmeticOperations(1,2,3))  // output is 6
    }
  ```

  ### Recursive functions
  * Recursion is a concept where a function calls itself by direct or indirect means.
  * The function keeps calling itself until it reaches a base condition.
  ```
  package main
  import "fmt"
  func factorial(n int) int {
      if n == 1 {
         return 1
      }
      return n * factorial(n-1)
  }
  func main(){
      output := factorial(5)
      fmt.Println("The factorial of 5 is",output)
  }
  ```
  
  ### Anonymous functions
  * An anonymous function is a function that is declared without any named identifier to refer to it.
  * They can be used for containing functionality that need not be named and possibly for short-term use.
  ```
  package main
  import "fmt"
  func main() {
      x := func(l int, b int) int{
      return l*b
      }
  fmt.Printf("%T \n", x)  //x is of type func(int, int) int
  fmt.Println(x(20, 30)) // It will give 600 as output
  ```
  ```
  package main
  import "fmt"
  func main() {
      x := func(l int, b int) int{
      return l*b
      }(20, 30)
  fmt.Printf("%T \n", x)  //x is of type int, since the x is storing the output.
  fmt.Println(x) // It will give 600 as output
  ```

  ### Higher order functions
  * Higher order function is a function that receives a function as an argument or returns a function as output.
  ```
  package main
  import "fmt"

  func calcArea(r float64) float64 {
      return 3.14 * r * r
  }
  func calcPerimeter(r float64) float64 {
      return 2 * 3.14 * r
  }
  func calcDiameter(r float64) float64 {
      return 2 * r
  }

  func getFunction(query int) func(r float64) float64 {   // returning function as output
      query_to_func := map[int]func(r float64) float64 {
          1: calcArea,
          2: calcPerimeter,
          3: calcDiameter,
      }
      return query_to_func[query]
  }

  func printResult(radius float64, calcFunction func(r float64) float64){   // taking function as parameter
      result := calcFunction(radius)
      fmt.Println("Result: ",result)
      fmt.Println("Thank you!")
  }

  func main() {
      var query int
      var radius float64
      fmt.Print("Enter the radius of the circle: ")
      fmt.Scanf("%f", &radius)
      fmt.Printf("Enter \n 1. area \n 2. perimeter \n 3. diameter: ")
      fmt.Scanf("%d", &query)
      printResult(radius, getFunction(query))
  }
  ```

### Defer statement
* A defer statement delays the execution of a function until the surrounding function returns.
* The deffered call's arguments are evaluated immediately, but the function call is not executed until the surrounding function returns.
```
 package main
 import "fmt"
 func printName(name string) {
    fmt.Println(name)
 }
 func printRollNo(roll int) {
    fmt.Println(roll)
 }
 func printAddress(address string) {
    fmt.Println(address)
 }

 func main() {
    printName("Dhruva")
    defer printRollNo(21)
    printAddress("street-21")
}

output:
Dhruva
street-21
21
```
* The printRollNo function will get executed after the surrounding function is returned as defer keyword is used.

# Pointers
* A pointer is a variable that holds memory address of another variable.
* They point where the memory is allocated and provide ways to find or even change the value located at the memory location.
* & operator: The address of a variable can be obtained by preceding the name of the variable with an ampersand(&) sign, known as address-of operator.
* * operator: It is known as dereference operator. When placed before an address, it returns the value at that address.
```
package main
import "fmt"
func main() {
    i := 10
    fmt.Printf("%T %v \n", &i, &i)
    fmt.Printf("%T %v \n", *(&i), *(&i))
}
output:
    *int 0xc00018c008
    int 10
```
### Declaring and initializing Pointers
* var <pointer_name> *<data_type> = & variable
* var <pointer_name> = & variable
* <pointer_name> := & variable
```
package main
import "fmt"
func main() {
    s := "hello"
    var b *string = &s
    fmt.Println(b)
    var c = &s
    fmt.Println(c)
    a := &s
    fmt.Println(a)
output:
0xc000010230
0xc000010230
0xc000010230
```
* Dereferencing a pointer
```
package main
import "fmt"

func main() {
    s := "hello"
    fmt.Printf("%T %v", s, s)
    ps := &s
    *ps = "world"
    fmt.Printf("%T %v", s, s)
}
output:
string hello
string world
```
* Function can be called in two ways.
1. Call by value
2. Call by reference
* Note: By default, arrays, slices, maps are passed by reference.
* If a function is called by value then the original parameter value will not be changed.
* If a function is called by reference then the original parameter value will be changed.

### Structs
* Struct is a user defined data type.
* A structure that groups together data elements.
* Provides a way to reference a series of grouped values through a single variable name.
* Used when it makes sense to group or associate two or more data variables.

# Declaring and initializing a Struct
* Declaring a struct
```
type <struct_name> struct {
    //fields
}
```
* Eg:
```
type <struct_name> struct {
    x float64
    y float64
}
```
```
type Student struct {
    name string
    rollno int
    marks []int
    grades map[string]int
}
```
* Initializing a struct
* var <variable_name> <struct_name>
* var s Student
* variable = new(<struct_name>)  // this is not commonly used. This will give pointer as output
```
  <variable> := <struct_name> {
       <field_name>: <value>,
       <field_name>: <value>,
  }
```
```
package main
import "fmt"
type Student struct {
    name string
    rollNo int
}
func main() {
st := Student {                    st := Student("Dhruva", 21)
    name: "Dhruva",       or    
    rollNo: 21,
}
fmt.Printf("%+v", st)
}    
```
* Accessing fields
* variable_name.<field_name>
```
package main
import "fmt"
type Circle struct {
    radius int
}
func main(){
    var c Circle
    c.radius = 5
    fmt.Printf("%+v", c)
}
```
* If we try to access the field that is not defined, it will throw an error.
* Passing structs to functions.
```
package main
import "fmt"
type Circle struct {
   x int
   y int
   radius float64
   area float64
}
func calcArea(*c Circle){
    const PI float64 = 3.14
    area = (PI * c.radius * c.radius)
}
func main() {
   c := Circle {
    x: 5,
    y: 5,
    radius: 7,
    area: 0
}
   calcArea(&c)
   fmt.Printf("%+v \n", c)
```
* Comparing Structs
* Structs of the same type can be compared using Go's equality operators.
```
package main
import "fmt"
type s1 struct {
    x int
}
func main() {
c := s1{x: 5}
c1 := s1{x: 6}
c2 := s1{x: 5}
if c != c1 {
    fmt.Println("c and c1 are not equal")
}
if c == c2 {
    fmt.Println("c and c2 are equal")
}
}
```
* Methods:
* A method augments a function by adding an extra parameter section immediately after the 'func' keyword that accepts a single argument. This argument is called a receiver.
```
func (<receiver>) <method_name>(<parameters>) <return_parameters> {
    // code
}
```
```
func (c Circle) area() float64{
    // code
}

func (c *Circle) area() float64{
    // code
}
```
```
package main
import "fmt"
type Circle struct {
    radius float64
    area float64
}
func (c *Circle) calcArea(){
    c.area = 3.14 * c.radius * c.radius
}
func main(){
    c := Circle{radius: 5}
    c.calcArea()
    fmt.Printf("%+v", c)
}
```
