### **Lesson 3: Introduction to Flutter Widgets**

---

#### **1. What is a Widget?**

- **Definition**:  
  Widgets are the core building blocks of a Flutter application. Everything in Flutter, from layout structures to UI elements, is a widget.

- **Key Characteristics**:
  - **Composable**: Widgets can be nested to build complex UIs.  
  - **Immutable**: Once created, widgets cannot be modified. Changes require rebuilding the widget tree.  
  - **Hierarchical**: Widgets form a tree structure, enabling parent-child relationships.  

- **Types of Widgets**:
  1. **Stateless Widgets**: For static UI elements that don’t change.  
  2. **Stateful Widgets**: For dynamic UI components that update during runtime.

- **Example**:  
  ```dart
  Widget build(BuildContext context) {
    return Text('Hello, Widgets!');
  }
  ```

---

#### **2. Basic Widgets in Flutter**

Below are some fundamental widgets to understand and start building Flutter UIs:

---

##### **2.1 Scaffold Widget**
- **Purpose**: Provides the basic structure for an app, including the app bar, body, floating action button, and more.  
- **Key Properties**:
  - `appBar`: Displays a navigation bar at the top.  
  - `body`: Holds the main content of the screen.  
  - `floatingActionButton`: Adds a floating button.  

- **Example**:  
  ```dart
  Scaffold(
    appBar: AppBar(title: Text('Scaffold Example')),
    body: Center(child: Text('Hello Scaffold!')),
    floatingActionButton: FloatingActionButton(
      onPressed: () {},
      child: Icon(Icons.add),
    ),
  );
  ```

---

##### **2.2 Container Widget**
- **Purpose**: A versatile widget used for layout and styling purposes.  
- **Key Properties**:
  - `padding`, `margin`: Adds spacing inside or around the container.  
  - `decoration`: Customizes appearance (e.g., color, borders).  
  - `alignment`: Aligns child widgets.  

- **Example**:  
  ```dart
  Container(
    padding: EdgeInsets.all(16.0),
    color: Colors.blue,
    child: Text('This is a Container!'),
  );
  ```

---

##### **2.3 Row and Column Widgets**
- **Purpose**:  
  - **Row**: Arranges child widgets horizontally.  
  - **Column**: Arranges child widgets vertically.  

- **Key Properties**:
  - `mainAxisAlignment`: Aligns children along the main axis.  
  - `crossAxisAlignment`: Aligns children along the cross axis.

- **Example (Row)**:  
  ```dart
  Row(
    mainAxisAlignment: MainAxisAlignment.spaceAround,
    children: [
      Icon(Icons.star),
      Icon(Icons.favorite),
      Icon(Icons.share),
    ],
  );
  ```

- **Example (Column)**:  
  ```dart
  Column(
    crossAxisAlignment: CrossAxisAlignment.start,
    children: [
      Text('Column 1'),
      Text('Column 2'),
      Text('Column 3'),
    ],
  );
  ```

---

##### **2.4 Text Widget**
- **Purpose**: Displays textual content in the app.  
- **Key Properties**:
  - `style`: Customizes font size, weight, color, etc.  
  - `textAlign`: Aligns the text.  

- **Example**:  
  ```dart
  Text(
    'Hello, Flutter!',
    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold, color: Colors.blue),
  );
  ```

---

##### **2.5 SizedBox Widget**
- **Purpose**: Adds spacing between widgets or constrains a widget's size.  
- **Key Properties**:
  - `height`, `width`: Defines the size.  

- **Example**:  
  ```dart
  SizedBox(height: 20.0),
  ```

---

##### **2.6 Center Widget**
- **Purpose**: Aligns its child widget at the center of the available space.  

- **Example**:  
  ```dart
  Center(
    child: Text('Centered Widget!'),
  );
  ```

---

### **Quiz with Expandable Solutions**

#### **Quiz 1: Fill in the Blanks**
1. The ______ widget provides the basic structure of a Flutter app.  
   <details>
   <summary>See solution</summary>
   **Solution**: Scaffold  
   </details>  

2. The ______ widget is used to align its child in the middle of the available space.  
   <details>
   <summary>See solution</summary>
   **Solution**: Center  
   </details>  

---

#### **Quiz 2: True/False**
1. The `Row` widget arranges its children vertically.  
   <details>
   <summary>See solution</summary>
   **Solution**: False (it arranges children horizontally).  
   </details>  

2. The `Container` widget can have both padding and margins.  
   <details>
   <summary>See solution</summary>
   **Solution**: True.  
   </details>  

---

#### **Quiz 3: Multiple Choice**
1. **Which property is used to define the space inside a `Container`?**  
   a) `margin`  
   b) `padding`  
   c) `alignment`  
   d) `decoration`  
   <details>
   <summary>See solution</summary>
   **Solution**: b) `padding`  
   </details>  

---

### **Assignments and Homework**

1. **Assignment: Design a Simple Layout**
   - Create a Flutter app with the following layout:
     - Use a `Scaffold` widget.  
     - Add a title in the `AppBar`.  
     - Use a `Column` widget to display:
       - A `Text` widget for a welcome message.  
       - An image (use any online image URL with the `Image.network` widget).  
       - A row of three icons (`Row` widget).  

   - Submit the source code and screenshots.

2. **Challenge Task**:
   - Create a Flutter app where:
     - A button is added to the `Scaffold`.
     - Clicking the button displays a centered message using the `Center` widget.

3. **Reflection Exercise**:
   - Write a 300-word reflection comparing the `Row` and `Column` widgets. Include examples of where each can be used effectively.

---

### **Relevant Weblinks for Further Learning**

1. **Flutter Widgets Overview**:  
   [https://flutter.dev/docs/development/ui/widgets](https://flutter.dev/docs/development/ui/widgets)

2. **Scaffold Widget Documentation**:  
   [https://api.flutter.dev/flutter/material/Scaffold-class.html](https://api.flutter.dev/flutter/material/Scaffold-class.html)

3. **Row and Column Widgets**:  
   [https://flutter.dev/docs/cookbook/layout/rows-columns](https://flutter.dev/docs/cookbook/layout/rows-columns)

4. **Text Styling in Flutter**:  
   [https://flutter.dev/docs/cookbook/design/text-styles](https://flutter.dev/docs/cookbook/design/text-styles)

---

### **Key Takeaways**
- Widgets are the building blocks of Flutter apps.  
- Understanding basic widgets like `Scaffold`, `Container`, and `Row/Column` helps you create structured layouts.  
- Widgets are highly composable, allowing flexible UI designs.

---

This lesson plan combines practical examples, interactive quizzes, and assignments, ensuring students gain both theoretical and hands-on experience with Flutter widgets.
