![expressjs](../img/golang.PNG)
## Golang Cheat Sheet for quick learning
---


&nbsp;
<p style="text-align: center">By the end of this page you will get to know the basic of GoLang
</p>

`Thanks for everyone around the world for sharing information and help other to learn and be part of this awesome family` 

[![Linkedin](https://i.stack.imgur.com/gVE0j.png) Follow Me ](https://tn.linkedin.com/in/ahmedbejaoui)
  
 
#### Golang was designed by Google to work on all platforms [ Linux, Mac, Windows ]

# let's start learning

```
Golang Info

when you name your functions start with uppercase letter it can be imported from out side your package 'file' and when using first letter as lowercase then it will work as privet function and can't be imported from out side your package
```
# Data Types  <br> 
 ```go
  
   var x int = 5
   var v bool = true
   var s string = "sky"
   var f float32  = 1.1
   // for date type read structs below
   var BirthDate time.Time // watch this you need to import time package first 

 ```

# Comments

```go

/* 
   multi line comment
*/

// single line comment

```
# Variable  <br> 
 ```go
  
   var x int = 5

   // or
   
   var a , b = 2, 24

   // or

   a := 5
   
   // and like above 
   
   a , b := 2, 24
 
   // but what when we want a constant variable then we use const

   const KEY = "super_key"

   // by this we ensure that the variable will not change
 ```


# Main entry point to golang program and Import & Function

```go

  // before we start coding with go we need to create our main file and import the main package in our code 
  // 1 create file with .go extension

  // 2 let's call it tuto.go
 
  // open the file and type the follow 

  package main // go will execute this package at build 

  import "fmt" // importing package

  // function in go
  func init() {
      fmt.Println("this will run before main()")
  }
  
  // function in go
  func main() {
      fmt.Println("this will run after init()") // this will print on the console
  }


 // to build this file, on the terminal run => go build fileName.go
```
 




# Arithmetic Operatprs
```go
a := 50
z := 5

// Addition
arith := a + z 

// Multiplication
arith := a * z

// Division
arith := a / z

// Subtraction
arith := a - z
```

# If / Else If / Else
```go


   a := 7

   if a < 5 {
       fmt.Println("a is greater than")
   } else if a > 5 {
       fmt.Println("a is less than")
   } else {
       fmt.Println("none of them!")
   }

```
# Switch 
```go 
Cats := "cats"
switch Cats {
  case "dogs":
      fmt.Println("it's dogs")
  case "snake":
      fmt.Println("it's Snake")
  case "cats":
      fmt.Println("yup it's cat")
  default:
     fmt.Println("None")
}
```

# Loop
```go

  for i:=0; i < 10; i++ {
      fmt.Println(i)
  }
  // this will print from 0 to 9

```

# Arrays
```go

 var x[3]int // now we have empty array with length of 3

// add value 
x[0] = 3  // index 0 have value of 3
x[1] = 45 // index 1 have value of 45
x[2] = 15 // index 2 have value of 15

fmt.Println(x) // [3, 45, 15]
fmt.Println(len(x)) // length 3
// or 

var x = [3]int{3, 45, 15}
fmt.Println(x) // [3, 45, 15]
fmt.Println(len(x)) // length 3 
```

# Struct 
```go 

package main

import (
       "fmt"
       "time"
       )

// struct
type User struct {
   name string
   age int
   dateBirth time.Time // when using date type import the time package
}
func main() {
   var user User
    
   user.name = "Elon Musk"
   user.age = 50
   
   fmt.Println( "user.name = ", user.name)
   fmt.Println( "user.age  = ", user.age)
}


// ====================== watch blow

func (m *User) PrintName() string {
  return m.name
}
func (m *User) PrintAge() int {
  return m.age
}

func main() {
  var user User
    
   user.name = "Elon Musk"
   user.age = 50
   fmt.Println( "user.name = ", user.PrintName())
   fmt.Println( "user.age  = ", user.PrintAge())
}

// ======================= magic right
/*
what happen here is we point the function so it will have the power to reach into the User struct and have access to,

by that the two functions has been part of the struct so when you look to the user variable you have access to that function and you can call it like the above

this just for printing name and age but this way is much more power think inside the function you can do anything,

- calculation
- business logic
- ......
*/
```


# Pointers
```go 
/*
 pointer is a way to point to a space in memory and have the ability to change 
 the value in it!
 program life cycle it can change and it must change for some use cases
*/
package main

import "fmt"

func main() {

  var username string
  username = "Elon"
   
  fmt.Println("The name of the space person is ", username)
  //           with & we point to the location in memory 
  changeUsername(&username)
  
  fmt.Println("And for the new space person is ",username)
}

func changeUsername(userN *string) {
  fmt.Println("memory location of variable userN  is ",userN)
 newUser := "John"
 *userN = newUser
}

/*   OUTPUT
The name of the space person is  Elon

memory location of variable userN  is  0xc0000821e0 // this hexadecimal will change every time you run the program

And for the new space person is  Jhon
*/
```

# Slices
```go 
// ================== 1

age = [5]int{23, 18, 78, 56, 81}

var slic1 []int = age[1:4] 
fmt.Println(slic1) // [18, 78, 56]

var slic2 []int = age[:4] 
fmt.Println(slic2) // [23, 18, 78, 56]

// ================== 2

var Num = []int

    Num = append(Num,3)
    Num = append(Num,1)
    Num = append(Num,4)
    Num = append(Num,2)

    fmt.Println(Num) // output = [3 1 4 2]
    sort.Ints(Num) // this will sort the Num
    fmt.Println(Num) // output = [1 2 3 4]
// you need to import sort 
```
# Interfaces

```go
// interface declaration
type geometry interface {
    area() float64
}

// instead, types implicitly satisfy an interface if they implement all required methods
func measure(g geometry) {
    fmt.Println(g)
}
```

---

# `Don't forget to reread it again to stick into your mind`
 
