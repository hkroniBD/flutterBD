### **Routing Between Two Pages Using Navigator.pushNamed**

In Flutter, you can navigate between pages (routes) using named routes, which provide a cleaner and more organized way to manage navigation.

---

### **1. Setting Up Named Routes**
Named routes allow you to define all your app's routes in one place and refer to them using string identifiers.

---

### **2. Create the Pages**
You will create two pages: **Page 1** and **Page 2**.

#### **Page 1:**
Create a Dart file called `page_one.dart`:
```dart
import 'package:flutter/material.dart';

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
            // Navigate to Page Two using named route
            Navigator.pushNamed(context, '/pageTwo');
          },
          child: Text("Go to Page Two"),
        ),
      ),
    );
  }
}
```

---

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
            // Go back to Page One
            Navigator.pop(context);
          },
          child: Text("Go Back to Page One"),
        ),
      ),
    );
  }
}
```

---

### **3. Define Routes in Main File**
Set up the named routes in `MaterialApp`.

**main.dart**:
```dart
import 'package:flutter/material.dart';
import 'page_one.dart';
import 'page_two.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Named Routes Demo',
      theme: ThemeData(primarySwatch: Colors.blue),
      // Define named routes
      routes: {
        '/': (context) => PageOne(), // Default route
        '/pageTwo': (context) => PageTwo(),
      },
      initialRoute: '/', // Specify the initial route
    );
  }
}
```

---

### **4. How It Works**
1. **`/`** is the default route, leading to `PageOne`.
2. The button on `PageOne` calls:
   ```dart
   Navigator.pushNamed(context, '/pageTwo');
   ```
   This navigates to `PageTwo`.
3. The button on `PageTwo` calls:
   ```dart
   Navigator.pop(context);
   ```
   This returns to `PageOne`.

---

### **5. Running the App**
1. Run the app with `flutter run`.
2. On **Page One**, tap the button to navigate to **Page Two**.
3. On **Page Two**, tap the button to navigate back to **Page One**.

---

### **Quiz**

1. What function is used for named navigation to a new page?
   - a) `Navigator.push`
   - b) `Navigator.pushNamed`
   - c) `Navigator.navigateNamed`

2. How do you define named routes in `MaterialApp`?
   - a) Using `routes` property
   - b) Using `navigator` property
   - c) Using `routeNamed` property

3. What happens when `Navigator.pop(context)` is called?
   - a) It closes the app.
   - b) It goes back to the previous page.
   - c) It resets the navigation stack.

---

### **Quick Task**
1. Add a third page (`PageThree`) and define its named route as `/pageThree`.
2. Navigate from **Page Two** to **Page Three** using:
   ```dart
   Navigator.pushNamed(context, '/pageThree');
   ```
3. Add a "Back to Home" button on **Page Three** to navigate to **Page One**.

---

### **Quiz Solutions**
1. **Answer**: b) `Navigator.pushNamed`  
2. **Answer**: a) Using `routes` property  
3. **Answer**: b) It goes back to the previous page  

---

### **Summary**
- Named routes help in managing navigation in a more structured way.
- Define all routes in the `MaterialApp.routes` property.
- Use `Navigator.pushNamed` to navigate and `Navigator.pop` to return.

This approach is ideal for apps with multiple pages, ensuring a cleaner navigation setup.
