### **Lesson Plan: Building a Simple Flutter App**

#### **Goal:** 
To help students understand the fundamental components of a basic Flutter app, including using the `SafeArea`, `Scaffold`, and `build` method in a custom widget class.

---

### **Step 1: Basic Flutter App**

We start with a simple app that displays the text "Hello there" in amber color.

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MaterialApp(
  home: Text(
    'Hello there',
    style: TextStyle(color: Colors.amber),
  ),
));
```

**Explanation:**
- `runApp`: This function takes the given widget and makes it the root widget of the app.
- `MaterialApp`: A convenience widget that wraps several widgets related to Material Design.
- `Text`: Displays the text "Hello there" in amber color.
- `TextStyle`: Used to style the text.

---

### **Step 2: Add SafeArea**

In this step, we will add the `SafeArea` widget. The `SafeArea` ensures that the child widget is not obstructed by system UI elements like the notch or status bar, ensuring the content is always visible within the screen's safe area.

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MaterialApp(
  home: SafeArea(
    child: Text(
      'Hello there',
      style: TextStyle(color: Colors.amber),
    ),
  ),
));
```

**Explanation:**
- `SafeArea`: Ensures the text is displayed in a way that avoids overlap with system UI elements.

---

### **Step 3: Add Scaffold and Basic Text**

Next, we'll wrap the `Text` widget inside a `Scaffold`. The `Scaffold` provides a framework for implementing the basic visual structure of the app, including an app bar, body, floating action buttons, and more.

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MaterialApp(
  home: Scaffold(
    appBar: AppBar(
      title: const Text('Simple App'),
    ),
    body: SafeArea(
      child: Center(
        child: Text(
          'Hello there',
          style: TextStyle(color: Colors.amber),
        ),
      ),
    ),
  ),
));
```

**Explanation:**
- `Scaffold`: A layout structure that gives us a consistent visual design.
- `AppBar`: A material design app bar that displays the app's title.
- `Center`: A widget that centers its child within its available space.
- `SafeArea`: To prevent overlap with system UI elements.

---

### **Step 4: Implement `build` Method with Class**

Now, we will move the code into a custom widget class that uses the `build` method. This is how Flutter recommends structuring larger apps.

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Simple App'),
        ),
        body: SafeArea(
          child: Center(
            child: Text(
              'Hello there',
              style: TextStyle(color: Colors.amber),
            ),
          ),
        ),
      ),
    );
  }
}
```

**Explanation:**
- `MyApp`: This is a custom widget class extending `StatelessWidget`, which means the widget does not have any mutable state.
- `build` method: The method that returns a widget tree. It is called when the widget is first created or rebuilt.
- `const` keyword: Used to mark the `MyApp` widget as a constant constructor, optimizing performance.

---

### **Quiz & Quick Task**

#### **Quiz:**
1. **What is the role of the `SafeArea` widget in Flutter?**
   - a) To make the app more secure.
   - b) To prevent widgets from overlapping with system UI elements (like the status bar or notch).
   - c) To add padding to the widget.
   
2. **What does the `Scaffold` widget provide in a Flutter app?**
   - a) A simple layout with a header.
   - b) A framework for implementing common material design visual elements (e.g., app bar, drawer, floating action button).
   - c) A container for holding images.

3. **What is the purpose of the `build` method in a Flutter widget?**
   - a) To initialize the widget state.
   - b) To construct and return the widget tree.
   - c) To set the visual properties of the widget.

#### **Quick Task:**
- Create a Flutter app that displays the text "Welcome to Flutter" in blue color inside a centered `SafeArea`. Use a `Scaffold` to add an `AppBar` with the title "Home" and ensure that the text is visible even on devices with a notch.

--- 

This lesson gradually introduces the key building blocks of a Flutter app, ensuring students understand each part before moving to the next step.
