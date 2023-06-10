# Ex.No:9 Develop a simple calculator using android studio.

## AIM:

To develop a program to develop a simple calculator in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to print the text “calculator operation”.
Developed by:S.VINEESHA
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
    <EditText
        android:id="@+id/txt2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:hint="Second Number"
        android:inputType="numberDecimal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.271"
        tools:ignore="Autofill,HardcodedText,SpeakableTextPresentCheck,TouchTargetSizeCheck,VisualLintTextFieldSize" />
    <EditText
        android:id="@+id/txt1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:hint="First Number"
        android:inputType="numberDecimal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.185"
        tools:ignore="Autofill,HardcodedText,SpeakableTextPresentCheck,TouchTargetSizeCheck,VisualLintTextFieldSize" />
    <TextView
        android:id="@+id/result"
        android:layout_width="404dp"
        android:layout_height="24dp"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.366" />
    <Button
        android:id="@+id/btnsubs"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="-"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.359"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.466"
        tools:ignore="HardcodedText" />
    <Button
        android:id="@+id/btndiv"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="/"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.9"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.466"
        tools:ignore="HardcodedText" />
    <Button
        android:id="@+id/btnadd"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="+"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.087"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.466"
        tools:ignore="HardcodedText" />
    <Button
        android:id="@+id/btnmult"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="*"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.628"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.466"
        tools:ignore="HardcodedText" />
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SIMPLE CALCULATOR"
        android:textColor="@color/black"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.073"
        tools:ignore="HardcodedText" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

MainActivity.java :

```
package com.example.labexp9;
import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    Button btnadd,btnsubs,btnmult,btndiv;
    EditText txt1,txt2;
    TextView result;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        btnadd=findViewById(R.id.btnadd);
        btnsubs=findViewById(R.id.btnsubs);
        btndiv=findViewById(R.id.btndiv);
        btnmult=findViewById(R.id.btnmult);
        txt1=findViewById(R.id.txt1);
        txt2=findViewById(R.id.txt2);
        result=findViewById(R.id.result);
        btnadd.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }
                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a + b; // Using Third Variable To Store Output Value
                    result.setText("The Addition Result Is " + c);
                }
            }
        });
        btnsubs.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }
                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a - b; // Using Third Variable To Store Output Value
                    result.setText("The Subtraction Result Is " + c);
                }
            }
        });
        btnmult.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }
                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a*b; // Using Third Variable To Store Output Value
                    result.setText("The Multiplication Result Is " + c);
                } }
        });
        btndiv.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }
                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a/b; // Using Third Variable To Store Output Value
                    result.setText("The Division Result Is " + c);
                }
            }
        });
    }
}
```

## OUTPUT:

<img width="960" alt="workshop-9" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/21422024-958e-4b71-ad9e-b9897ac95327">


<img width="178" alt="labexp 9 2" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/f89b365c-1119-43c2-b9c9-1f8fd815f3ae">


<img width="185" alt="lab exp 9" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/e12d2c25-22b1-40ac-9c24-82d9ab3b968b">


<img width="184" alt="lab 9m" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/3f1302bf-af44-4116-9b8a-efaddd205f8b">


## RESULT:

Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.
