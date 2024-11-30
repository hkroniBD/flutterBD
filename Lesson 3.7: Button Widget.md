### **Buttons in Flutter**

Buttons in Flutter are used for triggering actions when pressed. Flutter provides several types of buttons, each suited for different use cases.

---

### **Types of Buttons in Flutter**

| Button Type             | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `ElevatedButton`        | A button with a slightly raised appearance, often used for primary actions. |
| `TextButton`            | A flat button with no elevation, typically used for secondary actions.     |
| `OutlinedButton`        | A button with an outlined border, used for secondary actions.              |
| `IconButton`            | A button displaying only an icon, useful for toolbar actions.              |
| `FloatingActionButton`  | A circular button, often used for the main action on a screen.             |

---

### **1. ElevatedButton**

#### **Basic Usage**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('ElevatedButton Example')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            print('ElevatedButton pressed!');
          },
          child: Text('Click Me'),
        ),
      ),
    ),
  ));
}
```

#### **Explanation:**
- **`onPressed`**: Defines the action when the button is tapped.
- **`child`**: Widget displayed inside the button (e.g., text).

---

### **2. TextButton**

#### **Basic Usage**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('TextButton Example')),
      body: Center(
        child: TextButton(
          onPressed: () {
            print('TextButton pressed!');
          },
          child: Text('Press Me'),
        ),
      ),
    ),
  ));
}
```

#### **Key Features:**
- No elevation.
- Typically used for text-only actions like navigation or cancel.

---

### **3. OutlinedButton**

#### **Basic Usage**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('OutlinedButton Example')),
      body: Center(
        child: OutlinedButton(
          onPressed: () {
            print('OutlinedButton pressed!');
          },
          child: Text('Outline'),
        ),
      ),
    ),
  ));
}
```

#### **Key Features:**
- Displays a border around the text.
- Suitable for secondary actions.

---

### **4. IconButton**

#### **Basic Usage**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('IconButton Example')),
      body: Center(
        child: IconButton(
          icon: Icon(Icons.thumb_up),
          onPressed: () {
            print('IconButton pressed!');
          },
        ),
      ),
    ),
  ));
}
```

#### **Key Features:**
- Displays an icon instead of text.
- Often used in toolbars and lists.

---

### **5. FloatingActionButton**

#### **Basic Usage**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('FloatingActionButton Example')),
      body: Center(child: Text('Press the button below')),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          print('FloatingActionButton pressed!');
        },
        child: Icon(Icons.add),
      ),
    ),
  ));
}
```

#### **Key Features:**
- Circular and elevated button.
- Typically used for the primary action on a screen.

---

### **Styling Buttons**

You can customize button appearance using the `style` property. Here's an example with `ElevatedButton`:

```dart
ElevatedButton(
  onPressed: () {
    print('Styled ElevatedButton pressed!');
  },
  child: Text('Styled Button'),
  style: ElevatedButton.styleFrom(
    primary: Colors.blue, // Background color
    onPrimary: Colors.white, // Text color
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(12), // Rounded corners
    ),
    padding: EdgeInsets.symmetric(horizontal: 20, vertical: 15), // Padding
  ),
);
```

---

### **Advanced Example: Multiple Button Types**

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('Multiple Buttons Example')),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          ElevatedButton(
            onPressed: () {},
            child: Text('ElevatedButton'),
          ),
          TextButton(
            onPressed: () {},
            child: Text('TextButton'),
          ),
          OutlinedButton(
            onPressed: () {},
            child: Text('OutlinedButton'),
          ),
          IconButton(
            icon: Icon(Icons.favorite),
            onPressed: () {},
          ),
          FloatingActionButton(
            onPressed: () {},
            child: Icon(Icons.add),
          ),
        ],
      ),
    ),
  ));
}
```

---

### **Quiz**

1. **Which button is typically used for a primary action in Flutter?**
   - a) TextButton
   - b) ElevatedButton
   - c) OutlinedButton

2. **What property is used to specify the action when a button is tapped?**
   - a) `onTap`
   - b) `onPressed`
   - c) `action`

3. **Which button type is circular and elevated?**
   - a) IconButton
   - b) OutlinedButton
   - c) FloatingActionButton

---

### **Quick Task**

- **Task 1**: Create a screen with an `ElevatedButton`, `TextButton`, and `OutlinedButton`, each printing a different message.
- **Task 2**: Add a `FloatingActionButton` to a `Scaffold` and display a `SnackBar` when it is pressed.

---

### **Quiz Solutions**

1. **Correct Answer**: b) ElevatedButton  
   **Explanation**: ElevatedButton is raised and is used for primary actions.

2. **Correct Answer**: b) `onPressed`  
   **Explanation**: The `onPressed` property defines what happens when a button is pressed.

3. **Correct Answer**: c) FloatingActionButton  
   **Explanation**: FloatingActionButton is a circular and elevated button used for primary actions.

---

### **Quick Task Solutions**

#### **Task 1: Multiple Buttons**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('Button Task')),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          ElevatedButton(
            onPressed: () => print('ElevatedButton clicked!'),
            child: Text('ElevatedButton'),
          ),
          TextButton(
            onPressed: () => print('TextButton clicked!'),
            child: Text('TextButton'),
          ),
          OutlinedButton(
            onPressed: () => print('OutlinedButton clicked!'),
            child: Text('OutlinedButton'),
          ),
        ],
      ),
    ),
  ));
}
```

#### **Task 2: FloatingActionButton with SnackBar**
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('FloatingActionButton Task')),
      body: Center(child: Text('Press the button below')),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          print('FloatingActionButton pressed!');
        },
        child: Icon(Icons.add),
      ),
    ),
  ));
}
```
