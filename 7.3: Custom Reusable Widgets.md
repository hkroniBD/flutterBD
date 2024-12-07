Creating custom reusable styles and widgets is a best practice in Flutter development, as it helps maintain consistency and improves code reusability. Below is a guide to creating custom reusable **text styles**, **icon styles**, **container styles**, and **commonly used widgets**.

---

### **Step 1: Create a Reusable Text Style**
We define a class for text styles to reuse across the app.

```dart
import 'package:flutter/material.dart';

class AppTextStyles {
  static const TextStyle heading = TextStyle(
    fontSize: 24,
    fontWeight: FontWeight.bold,
    color: Colors.black,
  );

  static const TextStyle subtitle = TextStyle(
    fontSize: 18,
    fontWeight: FontWeight.w500,
    color: Colors.grey,
  );

  static const TextStyle body = TextStyle(
    fontSize: 16,
    fontWeight: FontWeight.normal,
    color: Colors.black87,
  );
}
```

#### **Usage Example:**
```dart
Text(
  'Hello, Flutter!',
  style: AppTextStyles.heading,
);
```

---

### **Step 2: Create a Reusable Icon Style**
We can create custom reusable **icon styles** using a widget.

```dart
class AppIcons {
  static Widget primaryIcon(IconData icon) {
    return Icon(
      icon,
      color: Colors.teal,
      size: 30,
    );
  }

  static Widget secondaryIcon(IconData icon) {
    return Icon(
      icon,
      color: Colors.grey,
      size: 24,
    );
  }
}
```

#### **Usage Example:**
```dart
AppIcons.primaryIcon(Icons.favorite),
AppIcons.secondaryIcon(Icons.settings),
```

---

### **Step 3: Create a Reusable Container Style**
Define a reusable container style for common layouts.

```dart
class AppContainers {
  static Widget cardContainer({required Widget child}) {
    return Container(
      padding: EdgeInsets.all(16),
      margin: EdgeInsets.symmetric(vertical: 8, horizontal: 16),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(12),
        boxShadow: [
          BoxShadow(
            color: Colors.black12,
            offset: Offset(0, 4),
            blurRadius: 6,
          ),
        ],
      ),
      child: child,
    );
  }

  static Widget gradientContainer({required Widget child}) {
    return Container(
      padding: EdgeInsets.all(16),
      decoration: BoxDecoration(
        gradient: LinearGradient(
          colors: [Colors.teal, Colors.blue],
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
        ),
        borderRadius: BorderRadius.circular(12),
      ),
      child: child,
    );
  }
}
```

#### **Usage Example:**
```dart
AppContainers.cardContainer(
  child: Text('Reusable Card Container', style: AppTextStyles.body),
),
AppContainers.gradientContainer(
  child: Text('Reusable Gradient Container', style: AppTextStyles.body),
),
```

---

### **Step 4: Create a Reusable Common Widget**
Encapsulate frequently used UI components like buttons, cards, or text + icons.

#### **Custom Reusable Button:**
```dart
class AppButton extends StatelessWidget {
  final String label;
  final VoidCallback onPressed;
  final Color color;

  const AppButton({
    required this.label,
    required this.onPressed,
    this.color = Colors.teal,
  });

  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: onPressed,
      style: ElevatedButton.styleFrom(
        primary: color,
        padding: EdgeInsets.symmetric(horizontal: 20, vertical: 12),
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
      ),
      child: Text(
        label,
        style: AppTextStyles.body.copyWith(color: Colors.white),
      ),
    );
  }
}
```

#### **Custom Reusable Text with Icon:**
```dart
class AppTextWithIcon extends StatelessWidget {
  final String text;
  final IconData icon;

  const AppTextWithIcon({required this.text, required this.icon});

  @override
  Widget build(BuildContext context) {
    return Row(
      children: [
        AppIcons.primaryIcon(icon),
        SizedBox(width: 8),
        Text(text, style: AppTextStyles.body),
      ],
    );
  }
}
```

#### **Usage Example:**
```dart
AppButton(
  label: 'Click Me',
  onPressed: () {
    print('Button Pressed');
  },
),

AppTextWithIcon(
  text: 'Flutter Dev',
  icon: Icons.code,
),
```

---

### **Step 5: Create a Global Theme for Most Used Widgets**
Instead of individually styling widgets, create a **ThemeData** for app-wide consistency.

```dart
class AppTheme {
  static ThemeData themeData = ThemeData(
    primaryColor: Colors.teal,
    textTheme: TextTheme(
      headline1: AppTextStyles.heading,
      subtitle1: AppTextStyles.subtitle,
      bodyText1: AppTextStyles.body,
    ),
    iconTheme: IconThemeData(color: Colors.teal, size: 24),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        primary: Colors.teal,
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
      ),
    ),
  );
}
```

#### **Usage Example:**
```dart
MaterialApp(
  theme: AppTheme.themeData,
  home: Scaffold(
    appBar: AppBar(title: Text('Reusable Components')),
    body: Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          AppButton(
            label: 'Submit',
            onPressed: () => print('Submitted!'),
          ),
          SizedBox(height: 20),
          AppContainers.cardContainer(
            child: Text('This is a reusable card container.', style: AppTextStyles.body),
          ),
        ],
      ),
    ),
  ),
),
```

---

### **Quiz**

1. **What is the benefit of reusable widgets in Flutter?**
   - a) Consistency in UI
   - b) Faster development
   - c) Both a and b

2. **Which class is used to define custom text styles?**
   - a) `Text`
   - b) `TextStyle`
   - c) `Container`

3. **How can you apply a gradient to a container?**
   - a) Use `BoxDecoration` with `gradient`
   - b) Use `padding`
   - c) Add `LinearGradient` directly to the `Container`

---

### **Quick Task**
1. Create a reusable `MyCard` widget that accepts a title and subtitle as parameters.
2. Use the `AppButton` to create a submit button with custom colors.

---

### **Quiz Solutions**
1. **Correct Answer**: c) Both a and b  
2. **Correct Answer**: b) TextStyle  
3. **Correct Answer**: a) Use `BoxDecoration` with `gradient`
