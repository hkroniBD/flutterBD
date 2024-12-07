### **Generating Different Shapes with `Container` in Flutter**

The `Container` widget in Flutter is highly versatile and can be styled with the `BoxDecoration` property to create various shapes like squares, rectangles, circles, and more. Below are step-by-step examples for generating different shapes.

---

### **1. Square**

```dart
Container(
  height: 100,
  width: 100,
  color: Colors.blue,
),
```

- **Explanation**:
  - A square is formed when height and width are equal.

---

### **2. Rectangle**

```dart
Container(
  height: 100,
  width: 200,
  color: Colors.green,
),
```

- **Explanation**:
  - A rectangle is formed when height and width are different.

---

### **3. Circle**

```dart
Container(
  height: 100,
  width: 100,
  decoration: BoxDecoration(
    color: Colors.red,
    shape: BoxShape.circle,
  ),
),
```

- **Key Property**:
  - `shape: BoxShape.circle` ensures the `Container` is a perfect circle when height and width are equal.

---

### **4. Oval**

```dart
Container(
  height: 100,
  width: 200,
  decoration: BoxDecoration(
    color: Colors.purple,
    borderRadius: BorderRadius.circular(50),
  ),
),
```

- **Explanation**:
  - The `borderRadius` makes the corners round, forming an oval.

---

### **5. Rounded Rectangle**

```dart
Container(
  height: 100,
  width: 200,
  decoration: BoxDecoration(
    color: Colors.orange,
    borderRadius: BorderRadius.circular(20),
  ),
),
```

- **Key Property**:
  - `borderRadius`: Defines the roundness of the rectangle's corners.

---

### **6. Triangle**

The `Container` widget alone cannot create a triangle, but you can use `ClipPath` for this:

```dart
ClipPath(
  clipper: TriangleClipper(),
  child: Container(
    height: 100,
    width: 100,
    color: Colors.yellow,
  ),
),
```

Define the custom clipper:
```dart
class TriangleClipper extends CustomClipper<Path> {
  @override
  Path getClip(Size size) {
    final path = Path();
    path.moveTo(size.width / 2, 0);
    path.lineTo(size.width, size.height);
    path.lineTo(0, size.height);
    path.close();
    return path;
  }

  @override
  bool shouldReclip(CustomClipper<Path> oldClipper) => false;
}
```

---

### **7. Hexagon**

Similarly, use `ClipPath` for creating a hexagon:
```dart
ClipPath(
  clipper: HexagonClipper(),
  child: Container(
    height: 100,
    width: 100,
    color: Colors.teal,
  ),
),
```

Define the custom clipper:
```dart
class HexagonClipper extends CustomClipper<Path> {
  @override
  Path getClip(Size size) {
    final width = size.width;
    final height = size.height;

    return Path()
      ..moveTo(width * 0.5, 0)
      ..lineTo(width, height * 0.25)
      ..lineTo(width, height * 0.75)
      ..lineTo(width * 0.5, height)
      ..lineTo(0, height * 0.75)
      ..lineTo(0, height * 0.25)
      ..close();
  }

  @override
  bool shouldReclip(CustomClipper<Path> oldClipper) => false;
}
```

---

### **8. Heart**

The heart shape can also be created using `CustomPaint` or `ClipPath`:
```dart
ClipPath(
  clipper: HeartClipper(),
  child: Container(
    height: 200,
    width: 200,
    color: Colors.pink,
  ),
),
```

Define the custom clipper:
```dart
class HeartClipper extends CustomClipper<Path> {
  @override
  Path getClip(Size size) {
    final path = Path();
    path.moveTo(size.width / 2, size.height * 0.35);
    path.cubicTo(size.width * 0.85, size.height * -0.3, size.width * 1.4,
        size.height * 0.8, size.width / 2, size.height);
    path.cubicTo(size.width * -0.4, size.height * 0.8, size.width * 0.15,
        size.height * -0.3, size.width / 2, size.height * 0.35);
    path.close();
    return path;
  }

  @override
  bool shouldReclip(CustomClipper<Path> oldClipper) => false;
}
```

---

### **Quiz**

1. **Which property of `BoxDecoration` is used to make a container circular?**
   - a) `shape`
   - b) `borderRadius`
   - c) `clipBehavior`

2. **How do you create a triangle shape in Flutter?**
   - a) `shape: BoxShape.triangle`
   - b) Using `CustomClipper` with `ClipPath`
   - c) `borderRadius: BorderRadius.circular(0)`

3. **What is required for creating a hexagon shape?**
   - a) `BoxShape.circle`
   - b) `ClipPath` with a custom clipper
   - c) `BoxDecoration`

---

### **Quick Task**
1. Create a Flutter app that displays all the shapes discussed.
2. Add a button to change the color of each shape dynamically when clicked.

---

### **Quiz Solutions**

1. **Correct Answer**: a) `shape`  
2. **Correct Answer**: b) Using `CustomClipper` with `ClipPath`  
3. **Correct Answer**: b) `ClipPath` with a custom clipper



### **Generating Different Shapes in Flutter**

Flutter allows the creation of various shapes using widgets like `Container`, `ClipRRect`, `ClipOval`, `CustomPaint`, and more. Below is a step-by-step guide to generating different shapes.

---

### **Step 9: Circle with `ClipOval`**

```dart
ClipOval(
  child: Container(
    height: 100,
    width: 100,
    color: Colors.red,
  ),
),
```

- **Key Property**:
  - Clips the child widget into a circular or elliptical shape.

---

### **Step 10: Rounded Rectangle with `ClipRRect`**

```dart
ClipRRect(
  borderRadius: BorderRadius.circular(20),
  child: Container(
    height: 100,
    width: 100,
    color: Colors.green,
  ),
),
```

- **Key Property**:
  - `borderRadius`: Creates rounded corners.

---

### **Step 11: Triangle with `CustomPaint`**

```dart
CustomPaint(
  size: Size(100, 100),
  painter: TrianglePainter(),
),
```

Define a custom painter for the triangle:
```dart
class TrianglePainter extends CustomPainter {
  @override
  void paint(Canvas canvas, Size size) {
    final paint = Paint()..color = Colors.orange;
    final path = Path()
      ..moveTo(size.width / 2, 0)
      ..lineTo(size.width, size.height)
      ..lineTo(0, size.height)
      ..close();

    canvas.drawPath(path, paint);
  }

  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) => false;
}
```

---

### **Step 12: Oval with `Container` and `BoxDecoration`**

```dart
Container(
  height: 100,
  width: 200,
  decoration: BoxDecoration(
    color: Colors.purple,
    shape: BoxShape.rectangle,
    borderRadius: BorderRadius.circular(50),
  ),
),
```

- **Key Property**:
  - Adjust the `borderRadius` to make the corners circular, forming an oval.

---

### **Step 13: Hexagon with `ClipPath`**

```dart
ClipPath(
  clipper: HexagonClipper(),
  child: Container(
    height: 100,
    width: 100,
    color: Colors.teal,
  ),
),
```

Define a custom clipper for the hexagon:
```dart
class HexagonClipper extends CustomClipper<Path> {
  @override
  Path getClip(Size size) {
    final path = Path();
    final width = size.width;
    final height = size.height;

    path.moveTo(width * 0.5, 0);
    path.lineTo(width, height * 0.25);
    path.lineTo(width, height * 0.75);
    path.lineTo(width * 0.5, height);
    path.lineTo(0, height * 0.75);
    path.lineTo(0, height * 0.25);
    path.close();

    return path;
  }

  @override
  bool shouldReclip(CustomClipper<Path> oldClipper) => false;
}
```

---

### **Step 14: Heart Shape with `CustomPaint`**

```dart
CustomPaint(
  size: Size(100, 100),
  painter: HeartPainter(),
),
```

Define a custom painter for the heart shape:
```dart
class HeartPainter extends CustomPainter {
  @override
  void paint(Canvas canvas, Size size) {
    final paint = Paint()..color = Colors.pink;
    final path = Path();

    path.moveTo(size.width / 2, size.height / 4);
    path.cubicTo(size.width * 3 / 4, size.height / 8, size.width, size.height / 2,
        size.width / 2, size.height);
    path.cubicTo(0, size.height / 2, size.width / 4, size.height / 8,
        size.width / 2, size.height / 4);

    canvas.drawPath(path, paint);
  }

  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) => false;
}
```

---

### **Quiz**
1. **Which widget is used to create rounded rectangles?**
   - a) `ClipOval`
   - b) `ClipRRect`
   - c) `Container`

2. **What is the role of `CustomPainter` in Flutter?**
   - a) Add text to widgets.
   - b) Draw custom shapes on the screen.
   - c) Modify the `Container`.

3. **Which property is used to make a `Container` circular?**
   - a) `shape: BoxShape.circle`
   - b) `radius`
   - c) `borderRadius`

---

### **Quick Task**
1. Create an app where the user can select and view different shapes (square, circle, triangle, and hexagon).
2. Add a button to change the color of the displayed shape dynamically.

---

### **Quiz Solutions**
1. **Correct Answer**: b) `ClipRRect`  
2. **Correct Answer**: b) Draw custom shapes on the screen.  
3. **Correct Answer**: a) `shape: BoxShape.circle`.
