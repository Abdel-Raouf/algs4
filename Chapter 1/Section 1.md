# 1.1 Programming Model
Introduces our basic programming model. All of our programs are implemented using a small subset of the Java programming language plus a few of our own libraries for input and output.

### Exercises
[1.1.1](#111) [1.1.2](#112) [1.1.3](#113) [1.1.4](#114) [1.1.5](#115) [1.1.6](#116) [1.1.7](#117) [1.1.8](#118) [1.1.9](#119) [1.1.10](#1110) [1.1.11](#1111) [1.1.12](#1112) [1.1.13](#1113) [1.1.14](#1114) [1.1.15](#1115) [1.1.16](#1116) [1.1.17](#1117) [1.1.18](#1118) [1.1.19](#1119) [1.1.20](#1120)

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
public class Solution {
  public static void main(String[] args) {
    int a = Integer.parseInt(args[0]);
    int b = Integer.parseInt(args[1]);
    int c = Integer.parseInt(args[2]);
    if (a == b && b == c) StdOut.print("equal");
    else StdOut.print("not equal");
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

### 1.1.9
There is a solution in textbook.

### 1.1.10
There is a solution in textbook.

### 1.1.11
```java
for (int row = 0; row <= b.length - 1; row++)
  for (int col = 0; col <= b[row].length - 1; col++)
    if (b[row][col]) StdOut.printf("%d %d *\n", row, col);
    else StdOut.printf("%d %d  \n", row, col);
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
  int n = 1;
  int exp = -1;
  while (n <= N) {
    exp++;
    n *= 2;
  }
  return exp;
}
```

### 1.1.15
```java
public static int[] histogram(int a[], int M) {
  int b[] = new int[M];
  for (int i = 0; i < M; i++) {
    for (int j = 0; j < a.length; j++) {
      if (i == a[j]) b[i]++;
    }
  }
  return b;
}
```

### 1.1.16
`311361142246`

### 1.1.17
There is a solution in textbook.

### 1.1.18
- Before replacement

`mystery(2, 25)` returns `50`, `mystery(3, 11)` returns `33`, `mystery(a, b)` returns a×b.

- After replacement

`mystery(2, 25)` returns `33554432`, `mystery(3, 11)` returns `177147`, `mystery(a, b)` returns a^b.

### 1.1.19
The N it can reach depends on computer's performance. Since `F(93)` is bigger than 2^63-1, maximum value of `long` type, the N it can acturally reach is `92`. Check [First 100 Fibonacci Numbers](http://www.miniwebtool.com/list-of-fibonacci-numbers/?number=100). 

One of the improvements of `F(N)`: 
```java
public class Fibonacci {
  public static long[] F(int N) {
    long[] f = new long[N + 1];
    if (N == 0) return f;
    f[1] = 1;
    if (N == 1) return f;
    for (int i = 2; i <= N; i++)
      f[i] = f[i - 1] + f[i - 2];
    return f;
  }
  public static void main(String[] args) {
    long[] f = F(99);
    for (int N = 0; N < f.length; N++)
      StdOut.println(N + " " + f[N]);
  }
}
```

### 1.1.20
```java
public static double lnf(int N) {
  if (N == 1) return 0;
  return Math.log(N) + lnf(N - 1);
}
```
