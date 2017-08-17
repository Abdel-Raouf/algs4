# 1.2 Data Abstraction
Emphasizes data abstraction, where we define abstract data types (ADTs). We specify an applications programming interface (API) and then use the Java class mechanism to develop an implementation for use in client code.

## Index
- [Exercises](#exercises)

[1.2.1](#121) [1.2.2](#122) [1.2.3](#123) [1.2.4](#124) [1.2.5](#125) [1.2.6](#126) [1.2.7](#127) [1.2.8](#128) [1.2.9](#129) [1.2.10](#1210) [1.2.11](#1211) [1.2.12](#1212) [1.2.13](#1213) [1.2.14](#1214)
- [Creative Problems](#creative-problems)

[1.2.15](#1215) [1.2.16](#1216) [1.2.17](#1217)
## Exercises
### 1.2.1
```java
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  Point2D[] p = new Point2D[N];
  double min = 1.0;
  for (int t = 0; t < N; t++) {
    double x = Math.random(); double y = Math.random();
    p[t] = new Point2D(x, y); p[t].draw();
    if (t > 0) for (int i = 0; i < t; i++)
        if (p[t].distanceTo(p[i]) < min)
          min = p[t].distanceTo(p[i]);
  }
  StdOut.println(min);
}
```
### 1.2.2
```java
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  double[] x = new double[N]; double[] y = new double[N];
  Interval1D[] interval = new Interval1D[N];
  for (int i = 0; i < N; i++)
    if (!StdIn.isEmpty()) {
      x[i] = StdIn.readDouble(); y[i] = StdIn.readDouble();
      interval[i] = new Interval1D(Math.min(x[i], y[i]), Math.max(x[i], y[i]));
    }
  for (int i = 1; i < N; i++) for (int j = 0; j < i; j++)
    if (interval[j].intersects(interval[i]))
      StdOut.printf("[%f, %f], [%f, %f]\n", Math.min(x[j], y[j]), Math.max(x[j], y[j]), Math.min(x[i], y[i]), Math.max(x[i], y[i]));
}
```
### 1.2.3
```java
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  double min = Double.parseDouble(args[1]);
  double max = Double.parseDouble(args[2]);
  Point2D[] a = new Point2D[N]; Point2D[] b = new Point2D[N];
  Interval2D[] box = new Interval2D[N];
  int intersect = 0, contain = 0;
  StdDraw.setXscale(min, max); StdDraw.setYscale(min, max);
  for (int i = 0; i < N; i++) {
    double x1 = StdRandom.uniform(min, max); double x2 = StdRandom.uniform(min, max);
    double y1 = StdRandom.uniform(min, max); double y2 = StdRandom.uniform(min, max);
    a[i] = new Point2D(Math.min(x1, y1), Math.max(x1, y1));
    b[i] = new Point2D(Math.min(x2, y2), Math.max(x2, y2));
    Interval1D xinterval = new Interval1D(Math.min(x1, x2), Math.max(x1, x2));
    Interval1D yinterval = new Interval1D(Math.min(y1, y2), Math.max(y1, y2));
    box[i] = new Interval2D(xinterval, yinterval); box[i].draw();
    if (i > 0) for (int j = 0; j < i; j++) {
      if (box[i].intersects(box[j])) intersect++;
      if (box[i].contains(a[j]) && box[i].contains(b[j])) contain++;
    }
  }
  StdOut.println(intersect); StdOut.print(contain);
}
```
### 1.2.4
```
world
hello

```
### 1.2.5
There's a solution in textbook. Formatted output is:
```
Hello World

```
### 1.2.6
```java
public static boolean isCircular(String s, String t) {
  if (s.length() == t.length() && s.concat(s).indexOf(t) >= 0)
    return true;
  else return false;
}
```
### 1.2.7
Reverse of the string.
### 1.2.8
There's a solution in textbook.
### 1.2.9
```java
import java.util.Arrays;
public class BinarySearch {
  public static int rank(int key, int[] a, Counter counter) {
    int lo = 0;
    int hi = a.length - 1;
    while (lo <= hi) {
      counter.increment();
      int mid = lo + (hi - lo) / 2;
      if (key < a[mid]) hi = mid - 1;
      else if (key > a[mid]) lo = mid + 1;
      else return mid;
    }
    return -1;
  }
  public static void main(String[] args) {
    int[] whitelist = In.readInts(args[0]);
    Counter counter = new Counter("counter");
    Arrays.sort(whitelist);
    while (!StdIn.isEmpty()) {
      int key = StdIn.readInt();
      if (rank(key, whitelist, counter) < 0) StdOut.println(key);
    }
    StdOut.println(counter);
  }
}
```
### 1.2.10
```java
public class VisualCounter {
  private int N, max, count = 0, op = 0;
  public VisualCounter(int N, int max) {
    this.N = N; this.max = max;
    StdDraw.setXscale(0, N);
    StdDraw.setYscale(-max, max);
  }
  public void increment() {
    if (op + 1 <= N && count + 1 <= max) {
      count++; op++; StdDraw.point(op, count);
    }
  }
  public void decrement() {
    if (op + 1 <= N && count - 1 >= -max) {
      count--; op++; StdDraw.point(op, count);
    }
  }
}
```
### 1.2.11
See [Data.java](http://algs4.cs.princeton.edu/12oop/Date.java).
### 1.2.12
```java
private static final String[] DAYSOFTHEWEEK = { "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday" };
public String dayOfTheWeek() {
  int tmpMonth = month, tmpYaer = year;
  if (tmpMonth < 3) { tmpMonth += 12; tmpYaer -= 1; }
  return DAYSOFTHEWEEK[((day + (((tmpMonth + 1) * 26) / 10) + tmpYaer % 100 + (tmpYaer % 100 / 4) + (tmpYaer / 400)) + (tmpYaer / 20) - 1) % 7];
}
```
### 1.2.13
See [Transaction.java](http://algs4.cs.princeton.edu/12oop/Transaction.java).
### 1.2.14
See [Transaction.java](http://algs4.cs.princeton.edu/12oop/Transaction.java).
## Creative Problems
### 1.2.15
There's a solution in textbook.
### 1.2.16
See [Rational.java](http://algs4.cs.princeton.edu/12oop/Rational.java).
### 1.2.17
```java
// From Rational.java
// Some codes...
private static int MAX = 2147483647;
private static int MIN = -2147483647;
// Some codes...
public Rational times(Rational that) {
  assert isTimesOverflow(this.num, that.num) : "overflow";
  assert isTimesOverflow(this.den, that.den) : "overflow";
  // Some codes...
}
// Some codes...
public Rational plus(Rational that) {
  assert isPlusOverflow(this.num * that.den, that.num * this.den) : "overflow";
  assert isTimesOverflow(this.den, that.den) : "overflow";
  // Some codes...
}
// Some codes...
private boolean isPlusOverflow(int a, int b) {
  return a >= 0 ? a + b < MAX : a + b > MIN;
}
private boolean isTimesOverflow(int a, int b) {
  if (a < 0) a = -a;
  if (b < 0) b = -b;
  if (a == 0 || b == 0) return false;
  else return a * b < MAX;
}
// Some codes...
```
