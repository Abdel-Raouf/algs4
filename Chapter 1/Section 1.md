# 1.1 Programming Model
Introduces our basic programming model. All of our programs are implemented using a small subset of the Java programming language plus a few of our own libraries for input and output.
### Exercises
[1.1.1](#111) [1.1.2](#112) [1.1.3](#113) [1.1.4](#114) [1.1.5](#115) [1.1.6](#116) [1.1.7](#117) [1.1.8](#118) [1.1.9](#119) [1.1.10](#1110) [1.1.11](#1111) [1.1.12](#1112) [1.1.13](#1113) [1.1.14](#1114) [1.1.15](#1115) [1.1.16](#1116) [1.1.17](#1117) [1.1.18](#1118) [1.1.19](#1119) [1.1.20](#1120) [1.1.21](#1121) [1.1.22](#1122) [1.1.23](#1123) [1.1.24](#1124) [1.1.25](#1125) [1.1.26](#1126)
### 1.1.1
<ol type="a">
<li><code>7</code></li>
<li><code>200.0000002</code></li>
<li><code>true</code></li>
</ol>

### 1.1.2
<ol type="a">
<li>Double <code>1.618</code></li>
<li>Double <code>10.0</code></li>
<li>Boolean <code>true</code></li>
<li>String <code>33</code></li>
</ol>

### 1.1.3
```java
public static void main(String[] args) {
  int a = Integer.parseInt(args[0]);
  int b = Integer.parseInt(args[1]);
  int c = Integer.parseInt(args[2]);
  if (a == b && b == c) StdOut.print("equal");
  else StdOut.print("not equal");
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

`mystery(2, 25)` returns `50`, `mystery(3, 11)` returns `33`, `mystery(a, b)` returns a × b.

- After replacement

`mystery(2, 25)` returns `33554432`, `mystery(3, 11)` returns `177147`, `mystery(a, b)` returns a<sup>b</sup>.
### 1.1.19
The N it can reach depends on computer's performance. Since `F(93)` is bigger than 2^63-1, maximum value of `long` type, the N it can acturally reach is `92`. Check [First 100 Fibonacci Numbers](http://www.miniwebtool.com/list-of-fibonacci-numbers/?number=100). 

One of the better implementations of `F(N)` that saves computed values in an array: 
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
### 1.1.21
```java
public static void main(String[] args) {
  String[] in = new String[0];
  int i = 0;
  while (!StdIn.isEmpty()) {
    String[] in_tmp = new String[in.length + 1];
    System.arraycopy(in, 0, in_tmp, 0, in.length);
    in = in_tmp;
    in[i] = StdIn.readLine();
    i++;
  }
  int len = in.length;
  for (i = 0; i < len; i++) {
    String[] p = in[i].split(" ");
    String s = p[0];
    int x = Integer.parseInt(p[1]);
    int y = Integer.parseInt(p[2]);
    StdOut.printf("%s\t%d\t%d\t%.3f\n", s, x, y, (double) x / (double) y);
  }
}
```
### 1.1.22
One of the solutions:
```java
public static int rank(int key, int[] a) {
  return rank(key, a, 0, a.length - 1, 0);
}
public static int rank(int key, int[] a, int lo, int hi, int indent) {
  StdOut.printf("%s%-4d%d\n", repeat(4 * indent, ' '), lo, hi);
  if (lo > hi) return -1;
  int mid = lo + (hi - lo) / 2;
  if (key < a[mid]) return rank(key, a, lo, mid - 1, indent + 1);
  else if (key > a[mid]) return rank(key, a, mid + 1, hi, indent + 1);
  else return mid;
}
public static String repeat(int n, char c) {
  String s = "";
  for (int i = 0; i < n; i++) s += c;
  return s;
}
```
### 1.1.23
```java
public static void main(String[] args) {
  In in = new In(args[0]);
  char flag = args[1].charAt(0);
  int[] whitelist = in.readAllInts();
  Arrays.sort(whitelist);
  if (flag == '-') while (!StdIn.isEmpty()) {
    int key = StdIn.readInt();
    if (BinarySearch.indexOf(whitelist, key) != -1) StdOut.println(key);
  } else while (!StdIn.isEmpty()) {
    int key = StdIn.readInt();
    if (BinarySearch.indexOf(whitelist, key) == -1) StdOut.println(key);
  }
}
```
### 1.1.24
1. p=105 q=24
2. p=24 q=9
3. p=9 q=6
4. p=6 q=3
5. p=3 q=0
```java
public class Eculid {
  public static void main(String[] args) {
    int p = Integer.parseInt(args[0]);
    int q = Integer.parseInt(args[1]);
    StdOut.print(gcd(p, q));
  }
  public static int gcd(int p, int q) {
    StdOut.printf("%d %d\n", p, q);
    if (q == 0) return p;
    int r = p % q;
    return gcd(q, r);
  }
}
```
`java Eculid 1111111 1234567` outputs
```
1111111 1234567
1234567 1111111
1111111 123456
123456 7
7 4
4 3
3 1
1 0
1
```
### 1.1.25
See [Euclidean algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm#Proof_of_validity).
### 1.1.26
```java
if (a > b) { t = a; a = b; b = t; } // Make sure that the bigger one between a or b moves to right.
if (a > c) { t = a; a = c; c = t; } // Make sure that the biggest one moves to rightmost.
if (b > c) { t = b; b = c; c = t; } // Make sure that the smallest one moves to left most.
```
### 1.1.27
The number of recursive calls is 2<sup>100</sup> + 2<sup>50</sup>.

You can try using the code below to get the number of recursive calls (it would spend a lot of time, then overflow...): 
```java
public static void main(String[] args) {
  Counter c = new Counter("");
  double b = binomial(100, 50, 0.25, c);
  StdOut.println(b);
}
public static double binomial(int N, int k, double p, Counter c) {
  if (N == 0 && k == 0) return 1.0;
  if (N < 0 || k < 0) return 0.0;
  c.increment();
  StdOut.println(c);
  return (1.0 - p) * binomial(N - 1, k, p, c) + p * binomial(N - 1, k - 1, p, c);
}
```
One of the better implementations that is based on saving computed values in an array: 
```java
public static void main(String[] args) {
  double b = binomial(100, 50, 0.25);
  StdOut.println(b);
}
public static double binomial(int n, int k, double p) {
  double[][] v = new double[n + 1][k + 1];
  for (int i = 0; i <= n; i++)
    for (int j = 0; j <= k; j++)
      v[i][j] = -1;
  return binomial(v, n, k, p);
}
public static double binomial(double[][] v, int n, int k, double p) {
  if (n == 0 && k == 0) return 1.0;
  if (n < 0 || k < 0) return 0.0;
  if (v[n][k] == -1) v[n][k] = (1.0 - p) * binomial(v, n - 1, k, p) + p * binomial(v, n - 1, k - 1, p);
  return v[n][k];
}
```
