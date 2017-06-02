# 1.1 Programming Model
Introduces our basic programming model. All of our programs are implemented using a small subset of the Java programming language plus a few of our own libraries for input and output.
### Exercises
[1.1.1](#111) [1.1.2](#112) [1.1.3](#113) [1.1.4](#114) [1.1.5](#115) [1.1.6](#116) [1.1.7](#117) [1.1.8](#118) [1.1.9](#119) [1.1.10](#1110) [1.1.11](#1111) [1.1.12](#1112) [1.1.13](#1113) [1.1.14](#1114) [1.1.15](#1115) [1.1.16](#1116) [1.1.17](#1117) [1.1.18](#1118) [1.1.19](#1119) [1.1.20](#1120) [1.1.21](#1121) [1.1.22](#1122) [1.1.23](#1123) [1.1.24](#1124) [1.1.25](#1125) [1.1.26](#1126) [1.1.27](#1127) [1.1.28](#1128) [1.1.29](#1129) [1.1.30](#1130) [1.1.31](#1131) [1.1.32](#1132) [1.1.33](#1133) [1.1.34](#1134) [1.1.35](#1135) [1.1.36](#1136) [1.1.37](#1137)
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
There's an answer in textbook.
### 1.1.10
There's an answer in textbook.
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
for (int row = 0; row <= M - 1; row++)
  for (int col = 0; col <= N - 1; col++)
    t[col][row] = a[row][col];
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
  for (int i = 0; i < M; i++)
    for (int j = 0; j < a.length; j++)
      if (i == a[j]) b[i]++;
  return b;
}
```
### 1.1.16
`311361142246`
### 1.1.17
There's an answer in textbook.
### 1.1.18
- Before replacement

`mystery(2, 25)` returns `50`, `mystery(3, 11)` returns `33`, `mystery(a, b)` returns a × b.

- After replacement

`mystery(2, 25)` returns `33554432`, `mystery(3, 11)` returns `177147`, `mystery(a, b)` returns a<sup>b</sup>.
### 1.1.19
The _N_ it can reach depends on computer's performance. Since `F(93)` is bigger than 2^63-1, maximum value of `long` type, the _N_ it can acturally reach is `92`. Check [First 100 Fibonacci Numbers](http://www.miniwebtool.com/list-of-fibonacci-numbers/?number=100). 

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
One of the versions:
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
if (a > b) { t = a; a = b; b = t; } // make sure that the bigger one between a or b moves to right.
if (a > c) { t = a; a = c; c = t; } // make sure that the biggest one moves to rightmost.
if (b > c) { t = b; b = c; c = t; } // make sure that the smallest one moves to left most.
```
### 1.1.27
The number of recursive calls is 2<sup>100</sup> + 2<sup>50</sup>.

A implementation that is based on saving computed values in an array (official version, see [Binomial.java](http://algs4.cs.princeton.edu/11model/Binomial.java.html)): 
```java
public static double binomial2(int N, int k, double p) {
  double[][] b = new double[N + 1][k + 1];
  for (int i = 0; i <= N; i++)
    b[i][0] = Math.pow(1.0 - p, i);
  b[0][0] = 1.0;
  for (int i = 1; i <= N; i++)
    for (int j = 1; j <= k; j++)
      b[i][j] = p * b[i - 1][j - 1] + (1.0 - p) * b[i - 1][j];
    return b[N][k];
}
```
### 1.1.28
```java
public static void main(String[] args) {
  In in = new In(args[0]);
  int[] whitelist = in.readAllInts();
  Arrays.sort(whitelist);
  
  // remove duplicates
  int len = whitelist.length;
  for (int i = 0; i < whitelist.length - 1; i++)
    if (whitelist[i] == whitelist[i + 1]) len--;
  int[] tmp = new int[len]; int pos = 0;
  for (int i = 0; i < whitelist.length - 1; i++) {
    if (whitelist[i] != whitelist[i + 1]) {
      tmp[pos] = whitelist[i]; pos++;
      if (i == whitelist.length - 2) tmp[pos] = whitelist[i + 1];
    }
  }
  whitelist = tmp;
  
  while (!StdIn.isEmpty()) {
    int key = StdIn.readInt();
    if (Test.indexOf(whitelist, key) == -1) StdOut.println(key);
  }
}
```
### 1.1.29
For `rank(key, a)`: 
```java
public static int rank(int key, int[] a) {
  int lo = 0;
  int hi = a.length - 1;
  int mid = 0;
  while (lo <= hi) {
    mid = lo + (hi - lo) / 2;
    if (key < a[mid]) hi = mid - 1;
    else if (key > a[mid]) lo = mid + 1;
    else {
      while (--mid >= 0 && a[mid] == key) ;
      return mid + 1;
    }
  }
  while (++hi < a.length && a[hi] < key) ;
  return hi - 1;
}
```
For `count(key, a)`: 
```java
public static int count(int key, int[] a) {
  int lo = 0;
  int hi = a.length - 1;
  while (lo <= hi) {
    int mid = lo + (hi - lo) / 2;
    if (key < a[mid]) hi = mid - 1;
    else if (key > a[mid]) lo = mid + 1;
    else {
      int tmp = mid;
      while (--tmp >= 0 && a[tmp] == key) ;
      while (++mid < a.length && a[mid] == key) ;
      return mid - tmp - 1;
    }
  }
  return 0;
}
```
### 1.1.30
```java
boolean[][] a = new boolean[N][N];
for (int i = 0; i < a.length; i++)
  for (int j = 0; j < a[i].length; j++)
    if (gcd(i, j) == 1) a[i][j] = true;
```
### 1.1.31
```java
// using default scale.
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  double p = Double.parseDouble(args[1]);
  double[] x = new double[N];
  double[] y = new double[N];
  StdDraw.setPenRadius(.05);
  for (int i = 0; i < N; i++) {
    x[i] = Math.cos(2 * Math.PI * i / N);
    y[i] = Math.sin(2 * Math.PI * i / N);
    StdDraw.point(x[i], y[i]);
  }
  StdDraw.setPenRadius();
  StdDraw.setPenColor(StdDraw.GRAY);
  for (int i = 0; i < N - 1; i++)
    for (int j = i + 1; j < N; j++)
      if (StdRandom.bernoulli(p))
        StdDraw.line(x[i], y[i], x[j], y[j]);
}
```
### 1.1.32
```java
// using default scale.
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  double l = Double.parseDouble(args[1]);
  double r = Double.parseDouble(args[2]);
  double[] e = new double[N + 1];
  for (int i = 0; i <= N; i++)
    e[i] = (r - l) * i / N + l;
  int[] c = new int[N];
  while (!StdIn.isEmpty()) {
    double n = StdIn.readDouble();
    for (int i = 0; i < N; i++)
      if (e[i] < n && n < e[i + 1]) c[i]++;
  }
  for (int i = 0; i < N; i++) {
    double x = 1.0 * i / N;
    double y = c[i] / 2.0;
    double rw = 0.5 / N;
    double rh = c[i] / 2.0;
    StdDraw.filledRectangle(x, y, rw, rh);
  }
}
```
### 1.1.33
```java
public class Matrix {
  public static double dot(double[] x, double[] y) {
    int N = x.length;
    double z = 0;
    for (int i = 0; i < N; i++) z += x[i] * y[i];
    return z;
  }
  public static double[][] mult(double[][] a, double[][] b) {
    int M = a.length;
    int N = b[0].length;
    double[][] c = new double[M][N];
    for (int i = 0; i < M; i++)
      for (int j = 0; j < N; j++)
        for (int k = 0; k < a[i].length; k++)
          c[i][j] += a[i][k] * b[k][j];
    return c;
  }
  public static double[][] transpose(double[][] a) {
    int M = a.length;
    int N = a[0].length;
    double[][] t = new double[N][M];
    for (int i = 0; i < N; i++)
      for (int j = 0; j < M; j++)
        t[i][j] = a[j][i];
    return t;
  }
  public static double[] mult(double[][] a, double[] x) {
    int N = a.length;
    double[] b = new double[N];
    for (int i = 0; i < N; i++)
      for (int j = 0; j < a[i].length; j++)
        b[i] += a[i][j] * x[j];
    return b;
  }
  public static double[] mult(double[] y, double[][] a) {
    int M = y.length;
    int N = a[0].length;
    double[] b = new double[N];
    for (int i = 0; i < M; i++)
      for (int k = 0; k < a[i].length; k++)
        b[i] += y[k] * a[k][i];
    return b;
  }
  public static void main(String[] args) {
    int aM = StdIn.readInt();
    int aN = StdIn.readInt();
    double[][] a = new double[aM][aN];
    for (int i = 0; i < aM; i++)
      for (int j = 0; j < aN; j++)
        a[i][j] = StdIn.readDouble();
    double[][] t = transpose(a);
    int bM = StdIn.readInt();
    int bN = StdIn.readInt();
    double[][] b = new double[bM][bN];
    for (int i = 0; i < bM; i++)
      for (int j = 0; j < bN; j++)
        b[i][j] = StdIn.readDouble();
    double[][] ab = mult(a, b);
    int xN = StdIn.readInt();
    double[] x = new double[xN];
    for (int i = 0; i < xN; i++) x[i] = StdIn.readDouble();
    double[] ax = mult(a, x);
    int yN = StdIn.readInt();
    double[] y = new double[yN];
    for (int i = 0; i < xN; i++) y[i] = StdIn.readDouble();
    double xy = dot(x, y);
    double[] ya = mult(y, a);
    if (StdIn.isEmpty()) {
      StdOut.println("dot(x, y): ");
      StdOut.println(xy);
      StdOut.println("mult(a, b): ");
      for (double[] row : ab) {
        for (double col : row) StdOut.print(col + "\t");
        StdOut.println();
      }
      StdOut.println("transpose(a): ");
      for (double[] row : t) {
        for (double col : row) StdOut.print(col + "\t");
        StdOut.println();
      }
      StdOut.println("mult(a, x): ");
      for (double e : ax) StdOut.print(e + "\t");
      StdOut.println();
      StdOut.println("mult(y, a): ");
      for (double e : ya) StdOut.print(e + "\t");
      StdOut.println();
    }
  }
}
```
Input stream format: 
```
a's row's length
a's column's length
a's elements' values form left to right, from top to bottom
b's row's length
b's column's length
b's elements' values form left to right, from top to bottom
x's row's (or column's) length
x's elements' values from left to right (or from top to bottom)
y's row's (or column's) length
y's elements' values from left to right (or from top to bottom)
```
Input: 
```
2
2
1
2
3
4
2
2
5
6
7
8
2
9
10
2
11
12

```
Output: 
```
dot(x, y): 
219.0
mult(a, b): 
19.0	22.0	
43.0	50.0	
transpose(a): 
1.0	3.0	
2.0	4.0	
mult(a, x): 
29.0	67.0	
mult(y, a): 
47.0	70.0	

```
### 1.1.34
Require saving all the values from standard input: 
- Print the median of the numbers.
- Print the percentage of numbers greater than the average.
- Print the _N_ numbers in increasing order.
- Print the _N_ numbers in random order.

Could be implemented as a filter using only a fixed number of variables and arrays of fixed size: 
- Print the maximum and minimum numbers.
- Print the <em>k</em>th smallest value, for _k_ less than 100.
- Print the sum of the squares of the numbers.
- Print the average of the _N_ numbers.
### 1.1.35
One of the experiments: 
```java
int SIDES = 6, dice1, dice2;
int[] time = new int[2 * SIDES + 1];
double[] dist = new double[2 * SIDES + 1];
for (int i = 0; i < N; i++) {
  dice1 = StdRandom.uniform(1, 7);
  dice2 = StdRandom.uniform(1, 7);
  time[dice1 + dice2]++;
}
for(int j = 2; j <= 2 * SIDES; j++)
  dist[j] = (double) time[j] / N;
```
_N_ should at least reach 10<sup>6</sup> to match the exact results to three decimal places.
### 1.1.36
```java
public class ShuffleTest {
  public static void main(String[] args) {
    int M = Integer.parseInt(args[0]);
    int N = Integer.parseInt(args[1]);
    int[] a = new int[M];
    int[][] time = new int[M][M];
    for (int i = 0; i < N; i++) {
      for (int j = 0; j < M; j++) a[j] = j;
      StdRandom.shuffle(a); // Test here.
      for (int j = 0; j < M; j++) time[j][a[j]]++;
    }
    for (int i = 0; i < M; i++) {
      for (int j = 0; j < M; j++)
        StdOut.printf("%d\t", time[i][j]);
      StdOut.println();
    }
  }
}
```
### 1.1.37
```java
public class ShuffleTest {
  public static void shuffle(int[] a) {
    int N = a.length;
    for (int i = 0; i < N; i++) {
      int r = StdRandom.uniform(N); // Change here.
      int temp = a[i];
      a[i] = a[r];
      a[r] = temp;
    }
  }
  public static void main(String[] args) {
    int M = Integer.parseInt(args[0]);
    int N = Integer.parseInt(args[1]);
    int[] a = new int[M];
    int[][] time = new int[M][M];
    for (int i = 0; i < N; i++) {
      for (int j = 0; j < M; j++) a[j] = j;
      shuffle(a); // Test here.
      for (int j = 0; j < M; j++) time[j][a[j]]++;
    }
    for (int i = 0; i < M; i++) {
      for (int j = 0; j < M; j++)
        StdOut.printf("%d\t", time[i][j]);
      StdOut.println();
    }
  }
}
```
