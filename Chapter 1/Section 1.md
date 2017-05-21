# 1.1 Programming Model
Introduces our basic programming model. All of our programs are implemented using a small subset of the Java programming language plus a few of our own libraries for input and output.

### Exercises
[1.1.1](#111) [1.1.2](#112) [1.1.3](#113) [1.1.4](#114) [1.1.5](#115) [1.1.6](#116) [1.1.7](#117) [1.1.8](#118) [1.1.9](#119) [1.1.10](#1110) [1.1.11](#1111) [1.1.12](#1112) [1.1.13](#1113) [1.1.14](#1114)

### 1.1.1
a. `7`

b. `200.0000002`

c. `true`

### 1.1.2
a. Double `1.618`

b. Double `10.0`

c. Boolean `true`

d. String `33`

### 1.1.3
```java
import edu.princeton.cs.algs4.StdOut;
public class Solution {
  public static void main(String[] args) {
    int a = Integer.parseInt(args[0]);
    int b = Integer.parseInt(args[1]);
    int c = Integer.parseInt(args[2]);
    if (a == b && b == c) {
      StdOut.print("equal");
    } else {
      StdOut.print("not equal");
    }
  }
}
```

### 1.1.4
a.
```java
if (a > b) c = 0;
```
b.
```java
if (a > b) { c = 0; }
```
c. Correct.

d.
```java
if (a > b) c = 0; else b = 0;
```

### 1.1.5
```java
StdOut.print(0 < x && x < 1 && 0 < y && y < 1);
```

### 1.1.6
```
0
1
1
2
3
5
8
13
21
34
55
89
144
233
377
610

```

### 1.1.7
a.
```
3.00009

```
b.
```
499500

```
c.
```
10000

```

### 1.1.8
a.
```
b

```
b.
```
197

```
c.
```
?

```
Hint: [Primitive Data Types](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)
> The char data type is a single 16-bit Unicode character. It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive).

### 1.1.9
```java
String s = ""
for (int n = N; n > 0; n /= 2)
  s = (n % 2) + s;
```

### 1.1.10
```java
int[] a = new a[10];
for (int i = 0; i < 10; i++)
  a[i] = i * 1;
```

### 1.1.11
```java
for (int row = 0; row <= b.length - 1; row++)
  for (int col = 0; col <= b[row].length - 1; col++)
    if (b[row][col])
      StdOut.printf("%d %d *\n", row, col);
    else
      StdOut.printf("%d %d  \n", row, col);
```

### 1.1.12
```
0
1
2
3
4
5
6
7
8
9

```

### 1.1.13
```java
// t stands for Transpose
for (int row = 0; row <= M - 1; row++) {
  for (int col = 0; col <= N - 1; col++)
  t[col][row] = a[row][col];
}
for (int row = 0; row <= N - 1; row++) {
  for (int col = 0; col <= M - 1; col++)
    StdOut.print(t[row][col] + " ");
  StdOut.println();
}
```

### 1.1.14
```java
public static int lg(int N) {
  if (N < 1)
    return 0; // It should throw an exception.
  int n = 1;
  int exp = -1;
  while (n <= N) {
    exp++;
    n *= 2;
  }
  return exp;
}
```
