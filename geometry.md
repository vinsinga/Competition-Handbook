# Geometry

## Object Declarations
**If supported by the language, replace `class` with `struct` to reduce memory usage.**

### Circle

``` Java
class Circle {
    Vector2 origin;
    double radius;
}
```

### Line

``` Java
class Line {
    Vector2 origin;
    Vector2 extent;
}
```

### Square

``` Java
class Square {
    Vector2 origin;
    Vector2 extent;
}
```

### Vector2

``` Java
class Vector2 {
    double x;
    double y;
}
```

### Vector3

``` Java
class Vector3 {
    double x;
    double y;
    double z;
}
```

## Formulas

### Distance

#### Doubles
``` Java
static double distance(double x1, double y1, double x2, double y2) {
    return Math.hypot(x2 - x1, y2 - y1);
}
```
#### Vector2
``` Java
static double distance(Vector2 v1, Vector2 v2) {
    return Math.hypot(v2.x - v1.x, v2.y - v1.y);
}
```

### Midpoint

``` Java
static Vector2 midpoint(Vector2 v1, Vector2 v2) {
    double x = (v1.x + v2.x) / 2;
    double y = (v1.y + v2.y) / 2;
    return new Vector2(x, y);
}
```

### Point Intersections

#### Circle

``` Java
static bool circleIntersection(Circle c, Vector2 v) {
    return distance(v, c.origin) <= c.radius;
}
```

#### Square

``` Java
static bool squareIntersection(Square s, Vector2 v) {
    return s.origin.x >= v.x && s.origin.y >= v.y && v.x <= s.extent.x && v.y <= s.extent.y;
}
```

#### Line

``` Java
// TODO: insert point-on-line intersection function.
```
