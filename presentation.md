## Types & Variables

- Visualize variables as blocks in memory
- Each block associated with
  - Address
  - Value
- **Size** of variable determined by its type

```c
long L = 2;
const char C = 'A';
int main() {
    int a = 0;
    const char c = 'a';
    char* p = NULL;
}
```

| Name | Address | Value |
| ---- | ------- | ----- |
| L    | 100     | 2     |
| C    | 108     | 'A'   |
| ...  | ...     |       |
| a    | 1024    | 0     |
| c    | 1030    | 'a'   |
| p    | 1031    | 0     |

---

## SizeOf

- Primitive types have their size defined at compile time
- `sizeof` operator returns size of type/variable in bytes

```c
int main() {
      char a = '0';
      printf("%d", sizeof(a));
      printf("%d", sizeof(char));
      printf("%d", sizeof(int));
      printf("%d", sizeof(double));
      printf("%d", sizeof(char*));
      printf("%d", sizeof(long*));
      printf("%d", sizeof(void*));
}
```

---

## Compiling

gcc -Wall -Wextra -Wpedantic -std=c99 -o main main.c gcc

- compile chain here

---

## Debugging Live Demo

hello world with some variables
build on vscode with wsl
configure and run gdb

---

## Operators

```c
int main() {
    int a = 3 + 2; // 5
    int b = 3 - 1; // 2
    int c = a % b; // 3
    c++; //4
    --c; //5
    c = 2, 0; //0
    bool d = a $lt; c;
    if (d) print
    else if (a == c) print
    else print
}
```

---

- Think of each operator a function
  - Takes one/two arguments
  - Returns a value
  - May modify the state of an argument

| Operator | x Type    | Y Type    | Return Type | Detail          |
| -------- | --------- | --------- | ----------- | --------------- |
| x < y    | numerical | numerical | boolean     | x, y share Type |
| x == y   | any       | any       | boolean     | x, y share Type |
| ++x      | integer   |           | integer     | modifies x      |

---

## Precedence & Associativity

- Precedence
  - Which is evaluated first
- Associativity
  - On same precedence, evaluate Left-to-Right or Right-to-Left

```c
int main() {
    int a = 3 * 2 + 1; // Precedence
    int b = 6;
    int c = 5;
    a = b = c = 10; // Associativity Right-to-Left
}
```

## [](https://en.cppreference.com/w/c/language/operator_precedence)

## Scope

- Governs variable visibility
- Increases/Decreases on bracket open/close
  - Other rules can also cause scope change
- Each scope can access the variables of all open upper scopes
- Global scope is accessible by all

```c
const bool c = false;
int main() {
    int a = 1;
    {
        int b = 2;
        {
            int c = 3; // shadowing
              print (a, b, c);
            }
        }
        print b // compiler error
}
```

---

## Enum - Typedef

- Enumerator
  - A type which can hold distinct values
- Typedef
  - Way to alias a type name

```c
      enum Color {
          Red,
          Green,
          Blue,
      };
      typedef enum Color Color;
      int main() {
        // enum Color c = Red;
        print(sizeof(Color));
        Color c = Red;
        if (c == Red) print(Red);
        else if (c == Green) print(Green);
        else if (c == Blue) print(Blue);
        else print(Error);
      }
```

---

## Switch

- if/else syntax for enums/ints

```c
      enum Color {
          Red,
          Green,
          Blue,
      };
      typedef enum Color Color;
      int main() {
          c = Green;
          switch (c) {
              case Red:
                  print(Red);
                  break;
              case Green:
                  print(Green);
                  break;
              case Blue:
                  print(Blue);
                  break;
              default:
                  print(Error);
          }
      }
```

---

## Loops

```c
      int main() {
          const int limit = 10;
          int i = 0;
          while (i $lt; limit) {
              print(i);
              i += 1;
          }
          for (int i = 0; i $lt; limit; ++i) {
              print(i);
          }
          int j = 3;
          bool isDone = false;
          while(!isDone) {
              if (j > 0) {
                  --j;
                  continue;
              }
              isDone = true;
          }
          for(;;) break;
      }
```

---

---

## Functions

- Reusable pieces of code

```c
      bool IsEven(int val) {return val % 2;}
      void PrintEven(int val, bool isEven) {
          if(isEven) printf("%d is Even\n", val, isEven);
      }
      int main() {
        for (int i = 0; i $lt; 10; ++i)
            PrintEven(i, IsEven(i));
      }
```

---

## Call By Value

```c
void Increment(int val) {val += 1;}
int main() {
  int i = 0;
  Increment(i);
  printf("%d\n", i);
}
```

- Output?

Add blocks of memory on the right

---

## Pointers

- Holds an address in memory
- 8 byte size in 64-bit systems
- 4 byte size in 32-bit systems

````c
  int G = 1;
  int* const GPtr = &G;
  int main() {
    print(sizeof(int*))
    print(sizeof(char*))
    *GPtr += 1;
    print(GPtr)
    print(*GPtr)
    char c = '0';
    char* const cPtr = &c;
    print(cPtr)
    print(*cPtr)
    int* p = NULL;
    print(x);
    p = GPtr;
    *p +=1;
    print(x);
    print(*x);
  }
 ```
   ---
 ## Call By Reference trick
   ---
 ## Structs
   ---
 ## C-Arrays
   ---
 ## Dynamic Allocation
   ---
````
