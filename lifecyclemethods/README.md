# Ex.No:1 To create a HelloWorld Activity using all lifecycles methods to display messages.


## AIM:

To create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to print the text “Hello World”.
Developed by:Vineesha S
Registeration Number :212221040180
*/
```

activity_main.xml :

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
        
</androidx.constraintlayout.widget.ConstraintLayout>
```

MainActivity.java :

```
package com.example.exp1;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toast.makeText(this, "onCreate Called", Toast.LENGTH_SHORT).show();
    }

    @Override
    protected void onRestart() {
        Toast.makeText(this, "onRestart Called", Toast.LENGTH_SHORT).show();
        super.onRestart();
    }

    @Override
    protected void onStart() {
        Toast.makeText(this, "onStart Called", Toast.LENGTH_SHORT).show();
        super.onStart();
    }

    @Override
    protected void onResume() {
        Toast.makeText(this, "onResume Called", Toast.LENGTH_SHORT).show();
        super.onResume();
    }

    @Override
    protected void onPause() {
        Toast.makeText(this, "onPause Called", Toast.LENGTH_SHORT).show();
        super.onPause();
    }

    @Override
    protected void onStop() {
        Toast.makeText(this, "onStop Called", Toast.LENGTH_SHORT).show();
        super.onStop();
    }

    @Override
    protected void onDestroy() {
        Toast.makeText(this, "onDestroy Called", Toast.LENGTH_SHORT).show();
        super.onDestroy();
    }
}
```

## OUTPUT:

<img width="545" alt="Screenshot 2023-06-10 102639" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/dbfc1f98-d80b-404e-8cad-6c8d03d9406b">


<img width="547" alt="lab exp 1 0" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/44202194-2229-4fe1-85a3-a81e0acbae24">


<img width="545" alt="lab exp 1 2" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/d45dc5b8-f605-4fd7-af8f-4a5c4fb160df">


<img width="547" alt="lab exp1 4" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/9db30f51-a8a7-4ee4-8c07-5f6d21c3ba1e">


<img width="140" alt="lab exp 1 5" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/07c89148-8700-4459-a1f0-9108d7aaa899">


<img width="137" alt="lab exp 1 6" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/48987942-9d22-4d39-bbc3-02a1a6314004">


## RESULT:

Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
