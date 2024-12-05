### **Routing and Navigation Between Two Pages in Flutter**

This guide explains the basics of navigation between two pages in Flutter without passing any data.

---

### **1. Setting Up the Flutter Project**
Create a new Flutter project:
```bash
flutter create navigation_example
cd navigation_example
```

---

### **2. Create the Pages**
You need two pages: **Page 1** and **Page 2**.  

#### **Page 1:**
Create a Dart file called `page_one.dart`:
```dart
import 'package:flutter/material.dart';
import 'page_two.dart'; // Import the second page

class PageOne extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Page One"),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => PageTwo()),
            );
          },
          child: Text("Go to Page Two"),
        ),
      ),
    );
  }
}
```

#### **Page 2:**
Create a Dart file called `page_two.dart`:
```dart
import 'package:flutter/material.dart';

class PageTwo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Page Two"),
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pop(context); // Go back to the previous page
          },
          child: Text("Go Back to Page One"),
        ),
      ),
    );
  }
}
```

---

### **3. Set up Main File**
Modify `main.dart` to point to **PageOne** as the home page.

```dart
import 'package:flutter/material.dart';
import 'page_one.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Navigation Example',
      theme: ThemeData(primarySwatch: Colors.blue),
      home: PageOne(), // Starting point of the app
    );
  }
}
```

---

### **4. Running the App**
1. Run the app using `flutter run`.
2. Tap the button on **Page One** to navigate to **Page Two**.
3. Tap the "Go Back" button on **Page Two** to return to **Page One**.

---

### **Key Navigation Functions**
- **`Navigator.push`**: Pushes a new route onto the navigation stack.
- **`Navigator.pop`**: Removes the current route from the navigation stack, returning to the previous route.

---

### **Quiz**
1. What function is used to navigate to a new page?
   - a) `Navigator.navigate`
   - b) `Navigator.push`
   - c) `Navigator.addRoute`

2. What function returns to the previous page?
   - a) `Navigator.return`
   - b) `Navigator.pop`
   - c) `Navigator.back`

3. Which method is used to define the destination page in `Navigator.push`?
   - a) `MaterialApp`
   - b) `Scaffold`
   - c) `MaterialPageRoute`

---

### **Quick Task**
1. Add a third page and create navigation from Page 2 to Page 3.
2. Add a "Home" button on Page 3 to navigate back to Page 1.

---

### **Quiz Solutions**
1. **Answer**: b) `Navigator.push`  
2. **Answer**: b) `Navigator.pop`  
3. **Answer**: c) `MaterialPageRoute`

---

This setup demonstrates simple navigation between two pages using `Navigator`. It provides the foundation for creating more complex navigation flows in your Flutter applications.
