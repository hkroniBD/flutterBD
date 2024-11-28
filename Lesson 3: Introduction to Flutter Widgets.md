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

### **Understanding the Scaffold Widget in Flutter (Step-by-Step)**

The **Scaffold** widget in Flutter is the backbone of most Flutter apps. It provides a high-level structure for building a screen with a default visual layout, such as an **app bar**, **floating action button**, **drawer**, **bottom navigation bar**, and more.

---

### **1. Basic Scaffold Structure**

The `Scaffold` widget is typically used as the root widget in a screen.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('Basic Scaffold'),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
)
```

- **Effect**: 
  - Displays an app bar with the title "Basic Scaffold".
  - Centers the text "Hello, Flutter!" in the body.

---

### **2. Adding an App Bar**

The `appBar` property allows you to add a top bar with titles, icons, and actions.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('AppBar Example'),
    backgroundColor: Colors.teal,
  ),
  body: Center(child: Text('App Bar added!')),
)
```

- **Effect**:
  - Adds an app bar with a teal background and title.

---

### **3. Adding a Floating Action Button**

The `floatingActionButton` property is used to add a circular button, often for primary actions.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('Floating Action Button')),
  body: Center(child: Text('Click the button!')),
  floatingActionButton: FloatingActionButton(
    onPressed: () {
      print('Button pressed!');
    },
    child: Icon(Icons.add),
  ),
)
```

- **Effect**:
  - A floating action button with a "+" icon appears at the bottom-right of the screen.

---

### **4. Adding a Drawer**

The `drawer` property allows you to add a navigation drawer that slides in from the left.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('Drawer Example')),
  body: Center(child: Text('Swipe from the left or click the menu!')),
  drawer: Drawer(
    child: ListView(
      children: [
        DrawerHeader(
          child: Text('Header'),
          decoration: BoxDecoration(color: Colors.blue),
        ),
        ListTile(
          title: Text('Item 1'),
          onTap: () {
            print('Item 1 clicked');
          },
        ),
        ListTile(
          title: Text('Item 2'),
          onTap: () {
            print('Item 2 clicked');
          },
        ),
      ],
    ),
  ),
)
```

- **Effect**:
  - A navigation drawer with two items slides out from the left.

---

### **5. Adding a Bottom Navigation Bar**

The `bottomNavigationBar` property is used to add a navigation bar at the bottom of the screen.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('Bottom Navigation Bar')),
  body: Center(child: Text('Navigate using the bottom bar!')),
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
      BottomNavigationBarItem(icon: Icon(Icons.search), label: 'Search'),
    ],
  ),
)
```

- **Effect**:
  - A bottom navigation bar with two items: Home and Search.

---

### **6. Adding a SnackBar**

The `ScaffoldMessenger` widget is used to show snack bars with `Scaffold`.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('SnackBar Example')),
  body: Center(
    child: ElevatedButton(
      onPressed: () {
        ScaffoldMessenger.of(context).showSnackBar(
          SnackBar(content: Text('Hello from SnackBar!')),
        );
      },
      child: Text('Show SnackBar'),
    ),
  ),
)
```

- **Effect**:
  - Clicking the button shows a SnackBar at the bottom of the screen.

---

### **7. Persistent Footer Buttons**

The `persistentFooterButtons` property allows you to add buttons that stick to the bottom of the screen.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('Footer Buttons Example')),
  body: Center(child: Text('Scroll to see footer buttons!')),
  persistentFooterButtons: [
    ElevatedButton(
      onPressed: () {},
      child: Text('Button 1'),
    ),
    ElevatedButton(
      onPressed: () {},
      child: Text('Button 2'),
    ),
  ],
)
```

- **Effect**:
  - Two buttons remain at the bottom of the screen.

---

### **8. Handling Multiple Widgets with Body**

The `body` property can hold complex widgets like `Column` or `Row` for advanced layouts.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(title: Text('Complex Layout Example')),
  body: Column(
    children: [
      Text('First Widget'),
      Expanded(
        child: Center(
          child: Text('Second Widget in Center'),
        ),
      ),
      Text('Third Widget'),
    ],
  ),
)
```

- **Effect**:
  - Displays a column with three widgets: the middle widget is centered and expanded.

---

### **9. Combining Widgets in Scaffold**

Here’s a comprehensive example that combines multiple Scaffold properties.

#### **Example**:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('Full Scaffold Example'),
  ),
  drawer: Drawer(
    child: ListView(
      children: [ListTile(title: Text('Home')), ListTile(title: Text('Settings'))],
    ),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  floatingActionButton: FloatingActionButton(
    onPressed: () {},
    child: Icon(Icons.add),
  ),
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
      BottomNavigationBarItem(icon: Icon(Icons.settings), label: 'Settings'),
    ],
  ),
)
```

- **Effect**:
  - A full Scaffold layout with an app bar, drawer, body, floating action button, and bottom navigation bar.

---

### **10. Key Properties of Scaffold**

| **Property**              | **Description**                                                                |
|---------------------------|--------------------------------------------------------------------------------|
| `appBar`                  | Adds a top app bar with optional title and actions.                           |
| `body`                    | Defines the main content of the screen.                                       |
| `floatingActionButton`    | Adds a floating action button for primary actions.                            |
| `drawer`                  | Adds a navigation drawer.                                                     |
| `bottomNavigationBar`     | Adds a navigation bar at the bottom of the screen.                            |
| `persistentFooterButtons` | Adds persistent buttons at the bottom of the screen.                          |

---

### **Assignment**

1. Create a Flutter app with:
   - An app bar titled "My Scaffold App".
   - A body containing centered text.
   - A floating action button that logs "FAB Clicked!" when pressed.
   - A bottom navigation bar with two items: Home and Profile.
   
2. Modify the app to include:
   - A drawer with navigation options: Home, About, and Logout.
   - Add an elevated button in the body that displays a SnackBar when clicked.
---

### **Understanding the Container Widget in Flutter (Step-by-Step)**

The **`Container`** widget is one of the most versatile widgets in Flutter. It is used for creating and decorating a rectangular box that can contain a single child widget. Here's a detailed, step-by-step breakdown of its features and how to use them.

---

### **1. Basic Usage**

A `Container` is used to wrap or contain other widgets, providing padding, alignment, margins, borders, and more.

#### **Example**:
```dart
Container(
  child: Text('Hello, Container!'),
)
```

This creates a rectangular box containing the text widget. By default, the container takes the smallest size required to fit its child.

---

### **2. Adding Styling and Customization**

#### **Step 1: Adding Padding**
Padding is the space **inside** the container, between its edges and its child.

```dart
Container(
  padding: EdgeInsets.all(20.0),
  color: Colors.blue,
  child: Text('Hello with Padding!'),
)
```

- **Key Property**: `padding`  
- **Effect**: Adds 20 pixels of padding on all sides.

#### **Step 2: Adding Margins**
Margins are the space **outside** the container, separating it from neighboring widgets.

```dart
Container(
  margin: EdgeInsets.all(10.0),
  color: Colors.green,
  child: Text('Hello with Margin!'),
)
```

- **Key Property**: `margin`  
- **Effect**: Adds 10 pixels of margin on all sides.

---

### **3. Controlling Size**

You can explicitly define the width and height of the container using the `width` and `height` properties.

#### **Example**:
```dart
Container(
  width: 150.0,
  height: 100.0,
  color: Colors.red,
  child: Center(child: Text('Fixed Size')),
)
```

- **Key Properties**: `width`, `height`  
- **Effect**: Creates a container of fixed dimensions.

#### **Example with Constraints**:
Alternatively, you can use the `constraints` property to specify flexible size requirements.

```dart
Container(
  constraints: BoxConstraints(
    minWidth: 100.0,
    maxWidth: 200.0,
    minHeight: 50.0,
    maxHeight: 100.0,
  ),
  color: Colors.orange,
  child: Text('Constrained Size'),
)
```

---

### **4. Adding Borders, Shadows, and Rounded Corners**

The `decoration` property allows you to style the container with advanced features like borders, shadows, and rounded corners.

#### **Step 1: Adding Borders**
```dart
Container(
  decoration: BoxDecoration(
    border: Border.all(color: Colors.black, width: 2.0),
  ),
  child: Text('With Border'),
)
```

- **Effect**: Draws a black border of 2 pixels around the container.

#### **Step 2: Rounded Corners**
```dart
Container(
  decoration: BoxDecoration(
    color: Colors.purple,
    borderRadius: BorderRadius.circular(15.0),
  ),
  child: Text('Rounded Corners'),
)
```

- **Key Property**: `borderRadius`  
- **Effect**: Gives the container rounded corners with a 15-pixel radius.

#### **Step 3: Adding Shadows**
```dart
Container(
  decoration: BoxDecoration(
    color: Colors.yellow,
    boxShadow: [
      BoxShadow(
        color: Colors.grey,
        blurRadius: 5.0,
        offset: Offset(2.0, 2.0),
      ),
    ],
  ),
  child: Text('With Shadow'),
)
```

- **Key Property**: `boxShadow`  
- **Effect**: Creates a shadow with a blur radius of 5 pixels.

---

### **5. Aligning Content**

The `alignment` property allows you to position the child widget within the container.

#### **Example**:
```dart
Container(
  alignment: Alignment.center,
  color: Colors.lightBlue,
  child: Text('Centered Content'),
)
```

- **Key Property**: `alignment`  
- **Effect**: Aligns the child widget at the center of the container.

#### **Other Alignments**:
```dart
alignment: Alignment.topLeft
alignment: Alignment.bottomRight
```

---

### **6. Using Gradients**

You can apply a gradient background using the `BoxDecoration` class.

#### **Example**:
```dart
Container(
  decoration: BoxDecoration(
    gradient: LinearGradient(
      colors: [Colors.red, Colors.blue],
      begin: Alignment.topLeft,
      end: Alignment.bottomRight,
    ),
  ),
  child: Text('Gradient Background'),
)
```

- **Effect**: Creates a linear gradient from red (top-left) to blue (bottom-right).

---

### **7. Combining Properties**

You can combine multiple features for advanced designs.

#### **Example**:
```dart
Container(
  width: 200,
  height: 100,
  padding: EdgeInsets.all(10.0),
  margin: EdgeInsets.all(20.0),
  alignment: Alignment.center,
  decoration: BoxDecoration(
    color: Colors.lightGreen,
    borderRadius: BorderRadius.circular(10.0),
    border: Border.all(color: Colors.black, width: 2.0),
    boxShadow: [
      BoxShadow(
        color: Colors.grey,
        blurRadius: 5.0,
        offset: Offset(2.0, 2.0),
      ),
    ],
  ),
  child: Text('Combined Properties'),
)
```

---

### **8. Handling Interaction**

The `Container` widget itself does not support interaction, but it can wrap interactive widgets like `GestureDetector`.

#### **Example**:
```dart
GestureDetector(
  onTap: () {
    print('Container Tapped!');
  },
  child: Container(
    color: Colors.cyan,
    child: Text('Tap Me!'),
  ),
)
```

- **Effect**: Logs a message when the container is tapped.

---

### **Summary of Key Properties**
| **Property**     | **Purpose**                                                     |
|-------------------|-----------------------------------------------------------------|
| `child`           | Contains a single widget inside the container.                 |
| `padding`         | Adds space inside the container.                               |
| `margin`          | Adds space outside the container.                              |
| `width`, `height` | Sets fixed dimensions for the container.                       |
| `alignment`       | Aligns the child widget within the container.                  |
| `decoration`      | Adds styling like color, border, shadow, and rounded corners.  |
| `constraints`     | Sets minimum and maximum size limits.                          |

---

### **Practice Task**
Create a Flutter app with a container:
- Apply a gradient background.
- Add rounded corners and a shadow.
- Align the text "Flutter Container" in the center.  

---

This step-by-step breakdown provides a clear understanding of the `Container` widget and its features, helping you design beautiful and flexible layouts.

---

### **Understanding the Row and Column Widgets in Flutter (Step-by-Step)**

The **Row** and **Column** widgets are fundamental layout widgets in Flutter. They arrange child widgets in a horizontal (Row) or vertical (Column) direction. Here is a detailed step-by-step explanation of these widgets.

---

### **1. Basic Usage**

#### **Row Widget**:  
Arranges its children **horizontally** in a single line.

#### **Column Widget**:  
Arranges its children **vertically** in a single column.

---

#### **Example: Basic Row**
```dart
Row(
  children: [
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

#### **Example: Basic Column**
```dart
Column(
  children: [
    Text('Item A'),
    Text('Item B'),
    Text('Item C'),
  ],
)
```

- **Output for Row**: Displays the text items side-by-side.
- **Output for Column**: Displays the text items one below the other.

---

### **2. Key Properties**

#### **Step 1: Arranging Children Along the Main Axis**
- **Row**: The main axis is horizontal.  
- **Column**: The main axis is vertical.  

- **Key Property**: `mainAxisAlignment`  
  Aligns children along the main axis.

  **Options**:  
  - `MainAxisAlignment.start` (default): Aligns children to the start.  
  - `MainAxisAlignment.center`: Aligns children in the center.  
  - `MainAxisAlignment.end`: Aligns children to the end.  
  - `MainAxisAlignment.spaceAround`: Distributes children with equal space around them.  
  - `MainAxisAlignment.spaceBetween`: Distributes children with space only between them.  
  - `MainAxisAlignment.spaceEvenly`: Distributes children with equal space between and around them.

#### **Example**:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Icon(Icons.star),
    Icon(Icons.favorite),
    Icon(Icons.share),
  ],
)
```

---

#### **Step 2: Aligning Children Along the Cross Axis**
- **Row**: The cross axis is vertical.  
- **Column**: The cross axis is horizontal.  

- **Key Property**: `crossAxisAlignment`  
  Aligns children along the cross axis.

  **Options**:  
  - `CrossAxisAlignment.start`: Aligns children to the start.  
  - `CrossAxisAlignment.center` (default): Aligns children to the center.  
  - `CrossAxisAlignment.end`: Aligns children to the end.  
  - `CrossAxisAlignment.stretch`: Stretches children to fill the cross axis.

#### **Example**:
```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.stretch,
  children: [
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

- **Effect**: Stretches the text widgets to fill the width of the screen.

---

#### **Step 3: Adding Spacing Between Children**
The `mainAxisSize` property controls whether the Row or Column widget occupies only as much space as its children need, or stretches to fill the available space.

- **Options**:  
  - `MainAxisSize.min`: Shrinks to fit the children.  
  - `MainAxisSize.max` (default): Expands to fill the available space.

#### **Example**:
```dart
Row(
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('Item 1'),
    SizedBox(width: 10.0),
    Text('Item 2'),
  ],
)
```

---

### **3. Nesting Rows and Columns**

Rows and Columns can be nested to create more complex layouts.

#### **Example**:
```dart
Column(
  children: [
    Row(
      mainAxisAlignment: MainAxisAlignment.spaceAround,
      children: [
        Icon(Icons.star),
        Icon(Icons.favorite),
        Icon(Icons.share),
      ],
    ),
    Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('Nested Row 1'),
        SizedBox(width: 20.0),
        Text('Nested Row 2'),
      ],
    ),
  ],
)
```

- **Effect**: Combines Rows within a Column to create hierarchical layouts.

---

### **4. Adding Flexibility**

#### **Step 1: Flexible Widget**
The `Flexible` widget allows a child to take up a proportional amount of space.

#### **Example**:
```dart
Row(
  children: [
    Flexible(
      flex: 2,
      child: Container(color: Colors.blue, height: 50),
    ),
    Flexible(
      flex: 1,
      child: Container(color: Colors.red, height: 50),
    ),
  ],
)
```

- **Effect**: The blue container takes up twice the space of the red container.

---

#### **Step 2: Expanded Widget**
The `Expanded` widget stretches a child to fill the remaining space.

#### **Example**:
```dart
Row(
  children: [
    Text('Item 1'),
    Expanded(
      child: Container(color: Colors.green, height: 50),
    ),
  ],
)
```

- **Effect**: The green container stretches to fill the remaining horizontal space.

---

### **5. Combining Row and Column in Real-World Layouts**

#### **Example: Profile Card**
```dart
Column(
  children: [
    Row(
      children: [
        CircleAvatar(
          backgroundImage: NetworkImage('https://example.com/avatar.jpg'),
          radius: 40,
        ),
        SizedBox(width: 10.0),
        Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('John Doe', style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            Text('Flutter Developer'),
          ],
        ),
      ],
    ),
    SizedBox(height: 20.0),
    Row(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        Icon(Icons.phone, size: 30),
        Icon(Icons.email, size: 30),
        Icon(Icons.location_on, size: 30),
      ],
    ),
  ],
)
```

- **Effect**: Creates a user profile card with an avatar, user details, and contact icons.

---

### **Summary of Key Properties**
| **Property**             | **Row/Column**  | **Purpose**                                                                 |
|---------------------------|-----------------|-----------------------------------------------------------------------------|
| `mainAxisAlignment`       | Both            | Aligns children along the main axis (start, center, end, space options).    |
| `crossAxisAlignment`      | Both            | Aligns children along the cross axis (start, center, end, stretch).         |
| `mainAxisSize`            | Both            | Determines whether the widget shrinks (`min`) or stretches (`max`).         |
| `children`                | Both            | Contains the list of child widgets to be arranged.                          |
| `Flexible` and `Expanded` | Both            | Allows children to expand or share space proportionally.                    |

---

### **Practice Task**
1. Create a layout with:
   - A **Row** containing three icons (`Row` widget).
   - A **Column** below the row displaying three buttons (`Column` widget).
   - Use spacing (`SizedBox`) to separate the widgets.

2. Experiment with `mainAxisAlignment` and `crossAxisAlignment` properties to see how the layout changes.

---

This detailed explanation equips you to use the Row and Column widgets effectively, enabling the creation of clean, organized, and flexible layouts in Flutter.
---

### **Understanding the Text Widget in Flutter (Step-by-Step)**

The **Text** widget in Flutter is used to display a string of text in your application. It is one of the most commonly used widgets and offers various customization options for styling, alignment, and interaction.

---

### **1. Basic Usage**

To display simple text in Flutter, use the `Text` widget with a string.

#### **Example**:
```dart
Text('Hello, Flutter!')
```

- **Effect**: Displays the text *Hello, Flutter!* in the default style.

---

### **2. Styling Text**

#### **Step 1: Changing Text Color**
You can use the `style` property with a `TextStyle` object to change the color of the text.

```dart
Text(
  'Hello, Flutter!',
  style: TextStyle(color: Colors.blue),
)
```

---

#### **Step 2: Changing Font Size**
You can adjust the size of the text using the `fontSize` property.

```dart
Text(
  'Large Text Example',
  style: TextStyle(fontSize: 24),
)
```

---

#### **Step 3: Making Text Bold or Italic**
You can change the weight and style of the text using `fontWeight` and `fontStyle`.

```dart
Text(
  'Bold Text',
  style: TextStyle(fontWeight: FontWeight.bold),
)

Text(
  'Italic Text',
  style: TextStyle(fontStyle: FontStyle.italic),
)
```

---

#### **Step 4: Underlining or Adding Decoration**
The `decoration` property adds effects like underlining, overlining, or strikethrough.

```dart
Text(
  'Underlined Text',
  style: TextStyle(decoration: TextDecoration.underline),
)

Text(
  'Strikethrough Text',
  style: TextStyle(decoration: TextDecoration.lineThrough),
)
```

---

#### **Step 5: Customizing Font Family**
You can change the font family to use custom or preloaded fonts.

```dart
Text(
  'Custom Font Example',
  style: TextStyle(fontFamily: 'Roboto'),
)
```

---

### **3. Aligning Text**

#### **Step 1: Aligning Text Horizontally**
Use the `textAlign` property to align the text horizontally.

```dart
Text(
  'Center Aligned Text',
  textAlign: TextAlign.center,
)
```

- **Options**:  
  - `TextAlign.start`: Aligns to the start (left for LTR, right for RTL).  
  - `TextAlign.end`: Aligns to the end.  
  - `TextAlign.center`: Aligns to the center.  
  - `TextAlign.justify`: Stretches the text to align with both edges.

---

#### **Step 2: Aligning Text Vertically**
To align text vertically, wrap the `Text` widget in a `Container` or `Center` widget and adjust its alignment.

```dart
Container(
  alignment: Alignment.center,
  child: Text('Vertically Centered Text'),
)
```

---

### **4. Wrapping and Overflow Handling**

#### **Step 1: Controlling Text Overflow**
If the text exceeds the available space, you can control how it behaves using the `overflow` property.

```dart
Text(
  'This is a very long line of text that might overflow.',
  overflow: TextOverflow.ellipsis, // Adds "..."
)
```

- **Options**:  
  - `TextOverflow.clip`: Clips the text.  
  - `TextOverflow.ellipsis`: Adds "..." at the end.  
  - `TextOverflow.fade`: Gradually fades out the text.

---

#### **Step 2: Handling Multiple Lines**
The `maxLines` property restricts the text to a certain number of lines.

```dart
Text(
  'This is a long piece of text that will wrap into multiple lines.',
  maxLines: 2, // Limits to 2 lines
  overflow: TextOverflow.ellipsis, // Adds "..." if it exceeds 2 lines
)
```

---

### **5. Adding Shadows and Advanced Styling**

You can add shadows to text using the `shadows` property.

```dart
Text(
  'Text with Shadow',
  style: TextStyle(
    color: Colors.black,
    fontSize: 24,
    shadows: [
      Shadow(
        blurRadius: 5.0,
        color: Colors.grey,
        offset: Offset(2.0, 2.0),
      ),
    ],
  ),
)
```

---

### **6. Rich Text (Multiple Styles in a Single Text)**

For text with multiple styles in a single line, use the `RichText` widget.

#### **Example**:
```dart
RichText(
  text: TextSpan(
    text: 'Hello, ',
    style: TextStyle(color: Colors.black, fontSize: 18),
    children: [
      TextSpan(
        text: 'Flutter!',
        style: TextStyle(color: Colors.blue, fontWeight: FontWeight.bold),
      ),
    ],
  ),
)
```

- **Effect**: Displays *Hello,* in black and *Flutter!* in bold blue.

---

### **7. Interactable Text**

The `GestureDetector` widget can make text clickable.

```dart
GestureDetector(
  onTap: () {
    print('Text clicked!');
  },
  child: Text(
    'Click Me!',
    style: TextStyle(color: Colors.blue, decoration: TextDecoration.underline),
  ),
)
```

- **Effect**: Logs a message when the text is tapped.

---

### **8. Combining Properties**

You can combine multiple properties for advanced text designs.

#### **Example**:
```dart
Text(
  'Styled and Centered Text',
  textAlign: TextAlign.center,
  style: TextStyle(
    color: Colors.deepPurple,
    fontSize: 20,
    fontWeight: FontWeight.bold,
    fontStyle: FontStyle.italic,
    decoration: TextDecoration.underline,
    decorationColor: Colors.deepPurpleAccent,
    shadows: [
      Shadow(
        blurRadius: 3.0,
        color: Colors.deepPurple.withOpacity(0.5),
        offset: Offset(2.0, 2.0),
      ),
    ],
  ),
)
```

---

### **9. Key Properties Summary**
| **Property**     | **Purpose**                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| `data`           | The text string to display.                                                |
| `style`          | Customizes the text appearance (color, size, font weight, etc.).           |
| `textAlign`      | Aligns the text horizontally.                                              |
| `overflow`       | Handles text that overflows its container.                                 |
| `maxLines`       | Restricts the text to a certain number of lines.                           |
| `shadows`        | Adds shadows for decorative effects.                                       |

---

### **Practice Task**
Create a Flutter app with a `Text` widget:
- Style the text with a custom font, size 20, bold, and italic.
- Align the text to the center.
- Add a shadow effect.

--- 

This step-by-step breakdown covers all the important aspects of the `Text` widget and helps you design attractive and functional text displays in Flutter.

---

### **Understanding the SizedBox Widget in Flutter (Step-by-Step)**

The **SizedBox** widget in Flutter is a versatile widget used to create empty space or define fixed dimensions for a child widget. It’s simple yet powerful and is often used to adjust spacing in layouts or constrain widget sizes.

---

### **1. Basic Usage of SizedBox**

The simplest use of a `SizedBox` is to define empty space with specified dimensions.

#### **Example**:
```dart
SizedBox(
  width: 100,
  height: 50,
)
```

- **Effect**: Creates an invisible box with a width of 100 and a height of 50.

---

### **2. Adding Space Between Widgets**

You can use `SizedBox` to add vertical or horizontal space between widgets.

#### **Example**:
```dart
Column(
  children: [
    Text('First Text'),
    SizedBox(height: 20), // Adds vertical space of 20 pixels
    Text('Second Text'),
  ],
)
```

- **Effect**: Adds a vertical gap of 20 pixels between the two `Text` widgets.

---

### **3. Constraining Widget Size**

You can use `SizedBox` to define specific dimensions for a child widget.

#### **Example**:
```dart
SizedBox(
  width: 150,
  height: 100,
  child: Container(
    color: Colors.blue,
  ),
)
```

- **Effect**: The `Container` is constrained to a width of 150 and a height of 100.

---

### **4. Creating a Square or Rectangle**

To create fixed-size shapes, you can use a `SizedBox` without a child.

#### **Example**:
```dart
SizedBox.square(
  dimension: 100, // Creates a square box with 100px width and height
)
```

- **Effect**: Creates an invisible square box with equal width and height.

For a rectangle:
```dart
SizedBox(
  width: 200,
  height: 50,
)
```

---

### **5. Placeholder for Dynamic Layouts**

`SizedBox` is useful as a placeholder when designing layouts where space might be dynamically filled later.

#### **Example**:
```dart
Row(
  children: [
    Text('Before'),
    SizedBox(width: 50), // Placeholder for future use
    Text('After'),
  ],
)
```

- **Effect**: Leaves 50 pixels of horizontal space between the two `Text` widgets.

---

### **6. Zero-Dimension SizedBox**

A `SizedBox.shrink()` creates a zero-size widget, which can be used for conditional rendering.

#### **Example**:
```dart
SizedBox.shrink()
```

- **Effect**: Creates an invisible widget with zero width and height.

---

### **7. Expanding Space Dynamically**

A `SizedBox.expand()` fills all available space in its parent widget.

#### **Example**:
```dart
SizedBox.expand(
  child: Container(
    color: Colors.green,
  ),
)
```

- **Effect**: The `Container` expands to fill the entire available space.

---

### **8. Combining with Flexible/Expanded**

To create responsive layouts, you can use `SizedBox` with `Flexible` or `Expanded`.

#### **Example**:
```dart
Row(
  children: [
    Flexible(
      child: SizedBox(width: 100, height: 100, child: Container(color: Colors.red)),
    ),
    Flexible(
      child: SizedBox(width: 150, height: 100, child: Container(color: Colors.blue)),
    ),
  ],
)
```

- **Effect**: The `SizedBox` widgets adjust their dimensions flexibly within the `Row`.

---

### **9. Nesting Widgets**

You can nest widgets inside a `SizedBox` to control their size and alignment.

#### **Example**:
```dart
SizedBox(
  width: 200,
  height: 100,
  child: Center(
    child: Text(
      'Hello!',
      style: TextStyle(fontSize: 20, color: Colors.white),
    ),
  ),
)
```

- **Effect**: A box with a width of 200 and height of 100 containing centered text.

---

### **10. Key Properties of SizedBox**

| **Property**   | **Purpose**                                    |
|----------------|------------------------------------------------|
| `width`        | Sets the width of the box.                    |
| `height`       | Sets the height of the box.                   |
| `child`        | Defines the widget to be constrained by the box. |
| `.shrink()`    | Creates a box with zero width and height.      |
| `.expand()`    | Expands the box to fill available space.       |
| `.square()`    | Creates a square box with equal dimensions.    |

---

### **11. Practical Example: Spacing and Sizing**

Create a Flutter app using `SizedBox` for spacing and size constraints.

#### **Example**:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('SizedBox Demo')),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Text('Widget 1'),
              SizedBox(height: 20), // Space between widgets
              Text('Widget 2'),
              SizedBox(
                width: 150,
                height: 50,
                child: Container(
                  color: Colors.blue,
                  child: Center(child: Text('SizedBox')),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

---

### **Assignment**
- Create a layout where:
  1. A `SizedBox` adds vertical space between three `Text` widgets.
  2. Another `SizedBox` constrains a `Container` to a size of 200x100.
  3. Use `SizedBox.expand()` to fill available space with a `Container`.

--- 

The `SizedBox` widget is an essential building block in Flutter for managing spacing and size constraints, making it a versatile tool for developers.

---

### **Understanding the Center Widget in Flutter (Step-by-Step)**

The **Center** widget in Flutter is used to align a child widget to the center of its parent container or layout. It is a simple but powerful widget, especially useful for layouts that require centering elements horizontally and vertically.

---

### **1. Basic Usage**

The `Center` widget wraps a child and places it in the middle of its parent.

#### **Example**:
```dart
Center(
  child: Text('Hello, Flutter!'),
)
```

- **Effect**: The text "Hello, Flutter!" is displayed at the center of the screen.

---

### **2. Centering Multiple Widgets**

If you want to center multiple widgets, wrap them in a layout widget like `Column` or `Row` inside the `Center`.

#### **Example**:
```dart
Center(
  child: Column(
    mainAxisSize: MainAxisSize.min,
    children: [
      Text('Widget 1'),
      Text('Widget 2'),
    ],
  ),
)
```

- **Effect**: Both text widgets are centered vertically and stacked in a column.

---

### **3. Centering with Containers**

You can center a `Container` widget or other visual widgets.

#### **Example**:
```dart
Center(
  child: Container(
    width: 100,
    height: 100,
    color: Colors.blue,
  ),
)
```

- **Effect**: A blue square container appears at the center of the screen.

---

### **4. Combining Center with Padding**

You can combine `Center` with `Padding` to control spacing around the centered widget.

#### **Example**:
```dart
Center(
  child: Padding(
    padding: EdgeInsets.all(20.0),
    child: Text('Padded Centered Text'),
  ),
)
```

- **Effect**: The text is centered with padding around it.

---

### **5. Center with Nested Widgets**

You can use nested widgets inside `Center` to create complex layouts.

#### **Example**:
```dart
Center(
  child: Container(
    width: 150,
    height: 150,
    color: Colors.green,
    child: Center(
      child: Text(
        'Nested Center',
        style: TextStyle(color: Colors.white),
      ),
    ),
  ),
)
```

- **Effect**: A green container is centered on the screen, with text centered inside the container.

---

### **6. Centering Images**

The `Center` widget is frequently used to center images.

#### **Example**:
```dart
Center(
  child: Image.network('https://flutter.dev/images/flutter-logo-sharing.png'),
)
```

- **Effect**: The Flutter logo is centered on the screen.

---

### **7. Flexible Centering in Columns and Rows**

When used inside a `Column` or `Row`, the `Center` widget ensures its child is aligned in the middle of the available space.

#### **Example**:
```dart
Column(
  children: [
    Center(
      child: Text('Centered in Column'),
    ),
    Spacer(), // Adds space below the centered widget
  ],
)
```

- **Effect**: Text is centered horizontally, and the `Spacer` ensures dynamic spacing in the column.

---

### **8. Center and Expand with Containers**

Combine the `Center` widget with an `Expanded` or `Flexible` widget for responsive layouts.

#### **Example**:
```dart
Center(
  child: Container(
    constraints: BoxConstraints.expand(height: 200, width: 200),
    color: Colors.orange,
    child: Center(
      child: Text('Expanded Center'),
    ),
  ),
)
```

- **Effect**: A container of fixed size is centered on the screen, with text inside it also centered.

---

### **9. Key Properties of Center Widget**

| **Property** | **Purpose**                                     |
|--------------|-------------------------------------------------|
| `child`      | Defines the widget to be centered.              |

---

### **10. Practical Example: Centering Widgets**

Create a Flutter app where different widgets are centered using the `Center` widget.

#### **Example**:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Center Widget Demo')),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Text(
                'Centered Text',
                style: TextStyle(fontSize: 20, color: Colors.blue),
              ),
              SizedBox(height: 20), // Adds space between widgets
              Container(
                width: 100,
                height: 100,
                color: Colors.green,
                child: Center(
                  child: Text(
                    'Centered Container',
                    style: TextStyle(color: Colors.white),
                    textAlign: TextAlign.center,
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

---

### **11. Assignment**

1. Create a Flutter app that displays:
   - A centered `Text` widget with a font size of 24.
   - A `Container` with a fixed size of 150x150 pixels, centered and containing text inside.
   - Add padding of 10 pixels around the centered `Container`.

2. Modify the app to dynamically center widgets within a `Column` layout based on screen size.

---

The **Center** widget is a straightforward but vital component for creating elegant and responsive layouts in Flutter. It helps focus attention on important UI elements by placing them prominently in the center of their containers.

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
