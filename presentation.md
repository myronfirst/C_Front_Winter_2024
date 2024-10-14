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

gcc -Wall -Wextra -std=c99 -o main main.c gcc compile chain here

---

## Debugging Live Demo

---

## Operators

```c
int main() {
    int a = 3 + 2;
    int b = 3 - 1;
    int c = a % b;
    c++;
    --c;
    c = 2, 0;
    bool d = a $lt; c;
    if (d) print
    else if (a == c) print
    else print
}
```

---

## table - operator - arguments - return type - comment

---

## operator precedence associativity table

---

## Scope

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
        print b //error
        static int s = 3;
}
```

---

## Internal External linkage

    ```c
          extern const int External;
          const int External = false;
          static const int Internal = false;
              int main() {}
    ```
    ---
    ## Enum Switch
    ```c
          enum Color {
              Red,
              Green,
              Blue,
          };
          typedef enum Color Color;
          int main() {
              Color c = Red;
              if (c == Red) print(Red);
              else if (c == Green) print(Green);
              else if (c == Blue) print(Blue);
              else print(Error);
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

## Implicit - Explicit type conversions

    ---
    ## Functions
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
          int Increment(int val) {val += 1;}
          int main() {
            int i = 0;
            Increment(i);
            print(i);
          }
    ```
    ---
      ## Pointers

````c
                int G = 1;
                int* const GPtr = &G;
                int main() {
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
