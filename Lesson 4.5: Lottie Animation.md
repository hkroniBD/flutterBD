### **Using Lottie Animations in Flutter**

Lottie is a library for parsing Adobe After Effects animations exported as JSON with the Bodymovin plugin. It allows smooth and scalable animations in Flutter apps with minimal effort.

---

### **Step 1: Add Lottie Package to Your Project**

1. Open your `pubspec.yaml` file.
2. Add the `lottie` dependency:
   ```yaml
   dependencies:
     lottie: ^2.3.2
   ```
3. Run the following command to install the package:
   ```bash
   flutter pub get
   ```

---

### **Step 2: Import the Lottie Package**
In your Dart file, import the Lottie package:
```dart
import 'package:lottie/lottie.dart';
```

---

### **Step 3: Use Lottie in Your App**

#### **Display a Local Lottie Animation**
1. Add your Lottie JSON file to the `assets` directory in your project (e.g., `assets/animation.json`).
2. Update the `pubspec.yaml` file to include the asset:
   ```yaml
   flutter:
     assets:
       - assets/animation.json
   ```
3. Load and display the animation:
   ```dart
   import 'package:flutter/material.dart';
   import 'package:lottie/lottie.dart';

   void main() => runApp(MyApp());

   class MyApp extends StatelessWidget {
     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(title: Text("Lottie Animation Example")),
           body: Center(
             child: Lottie.asset('assets/animation.json'),
           ),
         ),
       );
     }
   }
   ```

---

#### **Display a Lottie Animation from a URL**
You can also load animations directly from a URL:
```dart
Center(
  child: Lottie.network(
    'https://assets2.lottiefiles.com/packages/lf20_kqvbmksn.json',
  ),
),
```

---

### **Step 4: Customize Lottie Animations**
Lottie allows customization for better control:
- **Loop Animation**: 
  ```dart
  Lottie.asset('assets/animation.json', repeat: true),
  ```
- **Play Animation Once**: 
  ```dart
  Lottie.asset('assets/animation.json', repeat: false),
  ```
- **Control Speed**: 
  ```dart
  Lottie.asset('assets/animation.json', animate: true, repeat: true, reverse: true),
  ```

---

### **Common Use Cases**

#### **1. Loading Animations**
Use Lottie for displaying a loading animation.
```dart
Center(
  child: Lottie.asset('assets/loading.json'),
),
```

#### **2. Success or Error Feedback**
Use different animations to display success or error feedback.
```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    Text("Operation Successful!", style: TextStyle(fontSize: 18)),
    SizedBox(height: 20),
    Lottie.asset('assets/success.json'),
  ],
),
```

---

### **Quiz**

1. **Which file format does Lottie use for animations?**
   - a) GIF
   - b) MP4
   - c) JSON

2. **Which method is used to load Lottie animations from a file?**
   - a) `Lottie.load`
   - b) `Lottie.asset`
   - c) `Lottie.network`

3. **What should you do after adding a new asset file to your project?**
   - a) Restart your Flutter project.
   - b) Add the file to the `pubspec.yaml` under `assets`.
   - c) Both a and b.

---

### **Quick Task**
1. Add a Lottie animation to your app showing a "thumbs-up" animation after clicking a button.
2. Use a Lottie animation from the web as a loading indicator.

---

### **Quiz Solutions**

1. **Correct Answer**: c) JSON  
2. **Correct Answer**: b) `Lottie.asset`  
3. **Correct Answer**: c) Both a and b.
