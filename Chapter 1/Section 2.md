# 1.2 Data Abstraction
Emphasizes data abstraction, where we define abstract data types (ADTs). We specify an applications programming interface (API) and then use the Java class mechanism to develop an implementation for use in client code.

### Exercises
[1.2.1](#121) [1.2.2](#122) [1.2.3](#123)
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
