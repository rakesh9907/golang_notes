# Variables

- Go automatically maps int to int32 or int64 based on the value
    - var a int = 10

- Define String
    - var str string = "hello"

- Here define float variable according to value length two type of float type float32 and float64
    - var b float32 = 10.3

- Here define boolean variable
    - var isActive bool = false

- Integer Types
    - int, int8, int16, int32, int64 -> Signed integers
    - uint, uint8, uint16, uint32, uint64 -> Unsigned integers

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
    ```
        // define struct 
        type Person struct {
            name string
            age int
        }
        
        var p Person
        fmt.Println(unsafe.Sizeof(p))   // o/p 24bytes 

    ```

## Const Variable
    ```
        const PI = 3.4159
        const GREETING = "Good morning"
    ```


## Default Value
    ```
        var i int
        var f float64
        var b bool
        var s string

        // if no value assing by default it will assing this values
        fmt.Println(i, f, b, s)  // o/p  0 0 false ""
    ```

## Alias
    ```
        check it work for other data types also please check it

        var r rune = 'A'  // rune is an alias for int32
        var b byte = 'B'  // byte is an alias for uint8
        
        // to store the character value in that case we should declare the variable as rune
        // char is not a data type in go
        // char can be stored in rune / byte
        // rune use for  -> unicode, char, emojis, foreign scripts
        // byte use for -> ASCII code
        // in r and b have ascii value hold 


        fmt.Println(r, string(r), b, string(b)) // 65 A 66 B    ascii values of A and B

    ```

##  Feature const vs. `iota` Summary
| Feature | `const` | `iota` |
|---------|---------|--------|
| Type | Immutable fixed values | Auto-incrementing constants |
| Defalut Behavior | Must assign manually | Starts at 0, increments per line |
| Scope | works for all types | primarilly for integers |
| Flexibility | fixed values only | Allows auto-numbering, bit-shifting |
| Best use case | PI value, fixed settings | Enums, bit flags, custom sequences |

```
    const (
        A = iota
        B
        c
        D
    )

    fmt.Println(A, B, C, D) // o/p 0 1 2 3

    const (
            A = iota
            B = 500
            c = iota
            D = iota
        )

        fmt.Println(A, B, C, D) // o/p 0 500 2 3
    
    const (
            A = iota
            B = 500
            c = iota
            D
        )

    fmt.Println(A, B, C, D) // o/p 0 500 2 3

    const (
        A = iota
        B = 500
        c
        D
    )

    fmt.Println(A, B, C, D) // o/p 0 500 500 500

    const (
        A = iota +200
        B
        c
        D
    )

    fmt.Println(A, B, C, D) // o/p 200 201 202 203


    const (
        A = 200 + (iota * 10)
        B
        c
        D
    )

    fmt.Println(A, B, C, D) // o/p 201 211 221 231


    const (
        A = 200 + (iota * 10) // 0
        B                       // 1
        c = 500 + (iota * 10) // here iota value 2
        D                     // 3
    )

    fmt.Println(A, B, C, D) // o/p 201 211 520 530

    const (
        _ = iota
        A
        B
        C
        _  = iota // skip iota 4 value
        D
    )

    // skip 0 value
    fmt.Println(A, B, C, D) // o/p 1 2 3 5
```



