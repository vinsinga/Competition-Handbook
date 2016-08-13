# Geometry

## Object Declarations

### Circle

```
struct Circle {
    Vector2D origin;
    double radius;
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
// TODO: insert point-in-square intersection function.
```

#### Line

```
// TODO: insert point-on-line intersection function.
```

