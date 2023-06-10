# Ex.No: 2 To develop an application that uses GUI Components with Fonts and Colors. 
Note: Create button for colors and fonts while clicking color or font button should change 


## AIM:

To create an application that uses GUI Components with Fonts and Colors using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to print the text “GUIcomponent”.
Developed by:S.VINEESHA
Registeration Number :212221040180
*/
```

activity_main.xml:

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <TextView
            android:id="@+id/textView"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="30dp"
            android:layout_marginTop="296dp"
            android:gravity="center"
            android:text="Hello Vineesha!"
            android:textSize="25sp"
            android:textStyle="bold"
            app:layout_constraintBottom_toTopOf="@+id/button1"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="0.266"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            tools:ignore="HardcodedText,MissingConstraints" />
    <Button
            android:id="@+id/button1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="20dp"
            android:layout_marginBottom="48dp"
            android:gravity="center"
            android:text="Change font size"
            android:textSize="25sp"
            app:layout_constraintBottom_toTopOf="@+id/button2"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="0.25"
            app:layout_constraintStart_toStartOf="parent"
            tools:ignore="HardcodedText,MissingConstraints,VisualLintButtonSize" />
    <Button
            android:id="@+id/button2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="20dp"
            android:gravity="center"
            android:text="Change color"
            android:textSize="25sp"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintHorizontal_bias="0.4"
            app:layout_constraintStart_toStartOf="parent"
            tools:ignore="HardcodedText,MissingConstraints,VisualLintButtonSize" />
    </androidx.constraintlayout.widget.ConstraintLayout>
```    
MainActivity.java : 

```
package com.example.labexp2;

import androidx.appcompat.app.AppCompatActivity;
import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
public class MainActivity extends AppCompatActivity {
    int ch=1;
    float font=30;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        final TextView t= (TextView) findViewById(R.id.textView);
        Button b1= (Button) findViewById(R.id.button1);
        b1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                t.setTextSize(font);
                font = font + 5;
                if (font == 50)
                    font = 30;
            }
        });
        Button b2= (Button) findViewById(R.id.button2);
        b2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                switch (ch) {
                    case 1:
                        t.setTextColor(Color.RED);
                        break;
                    case 2:
                        t.setTextColor(Color.GREEN);
                        break;
                    case 3:
                        t.setTextColor(Color.BLUE);
                        break;
                    case 4:
                        t.setTextColor(Color.CYAN);
                        break;
                    case 5:
                        t.setTextColor(Color.YELLOW);
                        break;
                    case 6:
                        t.setTextColor(Color.MAGENTA);
                        break;
                }
                ch++;
if  (ch == 7)
                ch = 1;
            }
        });
    }
}
```

## OUTPUT:

<img width="960" alt="Screenshot 2023-05-31 140741" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/69ed5791-a756-4442-a07e-fd56699b3bf3">


<img width="182" alt="lab exp-2" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/d49b39f8-0082-4c38-8b27-0cea80324210">


## RESULT:

Thus a Simple Android Application that uses GUI Components with Fonts and Colors using Android Studio is developed and executed successfully.


