# 1.2 Data Abstraction
Emphasizes data abstraction, where we define abstract data types (ADTs). We specify an applications programming interface (API) and then use the Java class mechanism to develop an implementation for use in client code.

### Exercises
[1.2.1](#121)
### 1.2.1
``` java
public static void main(String[] args) {
  int N = Integer.parseInt(args[0]);
  Point2D[] p = new Point2D[N];
  double min = 1.0;
  for (int t = 0; t < N; t++) {
    double x = Math.random();
    double y = Math.random();
    p[t] = new Point2D(x, y);
    p[t].draw();
    if (t > 0)
      for (int i = 0; i < t; i++)
        if (p[t].distanceTo(p[i]) < min)
          min = p[t].distanceTo(p[i]);
  }
  StdOut.println(min);
}
```
