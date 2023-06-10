# Ex.No:3 Develop program to create a text field and a button “Navigate”. When you enter “www.google.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the google page using Android Studio.

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
Program to print the text “Implicitintent”.
Developed by:S.VINEESHA
Registeration Number :212221040180
*/
```

activity_main.xml :

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="44dp"
        android:text="NAVIGATE"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.215"
        tools:ignore="HardcodedText" />

    <EditText
        android:id="@+id/editTextTextPersonName"
        android:layout_width="208dp"
        android:layout_height="52dp"
        android:layout_marginStart="32dp"
        android:ems="10"
        android:inputType="textPersonName"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.218"
        tools:ignore="Autofill,LabelFor,SpeakableTextPresentCheck,TouchTargetSizeCheck" />

    </androidx.constraintlayout.widget.ConstraintLayout>
```
MainActivity.java :

```
package com.example.labexp3;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
    Button button;
    EditText editText;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        button = findViewById(R.id.button);
        editText = findViewById(R.id.editTextTextPersonName);
        button.setOnClickListener(view -> {
            String url=editText.getText().toString();
            Intent intent=new Intent(Intent.ACTION_VIEW, Uri.parse(url));
            startActivity(intent);
        });
    }
}
```

## OUTPUT:

<img width="960" alt="exp4 1" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/19e2dcd6-4a09-48d5-b95b-33f67033b484">


<img width="182" alt="exp3" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/e51c297d-349a-49a8-b88f-8599cead8714">


<img width="182" alt="exp3 0" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/7f616e44-39a6-4ec8-84aa-4ba0bedf5cfe">


## RESULT:

Thus a Simple Android Application create a navigate button using Implicit Intent to display the google page using Android Studio is developed and executed successfully.


