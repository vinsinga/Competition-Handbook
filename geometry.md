# Geometry

## Object Declarations

### Circle

```
struct Circle {
    Vector2D origin;
    double radius;
}
```

### Line

```
struct Line {
    Vector2D origin;
    Vector2D extent;
}
```

### Square

```
struct Square {
    Vector2D origin;
    Vector2D extent;
}
```

### Vector2D

```
struct Vector2D {
    double x;
    double y;
}
```

### Vector3D

```
struct Vector3D {
    double x;
    double y;
    double z;
}
```

## Formulas

### Distance

#### Doubles
```
static double distance(double x1, double y1, double x2, double y2){
    return Math.hypot(x2 - x1, y2 - y1);
}
```
#### Vector2D
```
static double distance(Vector2D v1, Vector2D v2){
    return Math.hypot(v2.x - v1.x, v2.y - v1.y);
}
```

### Point Intersections

#### Circle

```
static bool circleIntersection(Circle c, Vector2D v) {
    return distance(v, c.origin) <= c.radius;
}
```

#### Square

```
static bool squareIntersection(Square s, Vector2D v) {
    return s.origin.x >= v.x && s.origin.y >= v.y && v.x <= s.extent.x && v.y <= s.extent.y;
}
```

#### Line

```
// TODO: insert point-on-line intersection function.
```

