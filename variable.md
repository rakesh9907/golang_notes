# Variables

- Go automatically maps int to int32 or int64 based on the value
    - var a int = 10

- Define String
    - var str string = "hello"

- Here define float variable according to value length two type of float type float32 and float64
    - var b float32 = 10.3

- Here define boolean variable
    - var isActive bool = false

## Short hand declaration ( this called inferred )
- Here short hand declartion
    - a := 10  int
    - str := "hello"  string

    - A float declared using short-hand syntax (:=) is automatically inferred as float64.
        - b := 10.5  float64
    - isActive := false  boolean


- Use Type Inference When:
    - The Type is obvious from the assignment.
    - You want cleaner and more concise code.
    - You're working with short-lived variables inside functions.

- List of format specifiers (placeholders) used in Go
    - %d  decimal integer
    - %f  Decimal floating point
    - %s  String
    - %t  Boolean
    - %T  type of variable
    - %p  pointer address

- fmt.Printf("a=%d, b=%d, c=%d \n", unsafe.Sizeof(a), unsafe.Sizeof(b), unsafe.Sizeof(c))
    - unsafe is package and Sizeof function which return size of perticulare allocation

- check size of Struct
    ``` type Person struct {
        name string
        age int
    }
    
    var p Person
    fmt.Println(unsafe.Sizeof(p))   // o/p 24
    ```

    