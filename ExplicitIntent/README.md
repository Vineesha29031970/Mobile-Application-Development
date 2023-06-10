# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


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
Program to print the text “ExplicitIntent”.
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
 <TextView
 android:id="@+id/maintxt"
 android:layout_width="317dp"
 android:layout_height="38dp"
 android:layout_marginTop="36dp"
android:text="FACTORIAL CALCULATOR"
 android:textAlignment="center"
 android:textColor="@color/purple_700"
 android:textSize="25sp"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
 <TextView
 android:id="@+id/text1"
 android:layout_width="156dp"
 android:layout_height="32dp"
 android:layout_marginStart="76dp"
 android:layout_marginTop="240dp"
 android:text="Enter a Number"
 android:textColor="@color/black"
 android:textSize="20sp"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
 <EditText
 android:id="@+id/n1"
 android:layout_width="50dp"
 android:layout_height="50dp"
 android:layout_alignRight="@+id/text1"
 android:layout_marginTop="224dp"
 android:layout_marginEnd="120dp"
 android:textColor="#EA80FC"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
 <Button
 android:id="@+id/btn1"
 android:layout_width="108dp"
 android:layout_height="45dp"
 android:layout_marginBottom="360dp"
 android:background="#2C34CF"
 android:text="Calculate"
 android:textColor="@color/white"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.498"
 app:layout_constraintStart_toStartOf="parent" />
 <TextView
 android:id="@+id/resum"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:layout_marginLeft="150dp" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

MainActivity.java :

```
package com.example.factorialcalculator;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
public class MainActivity extends AppCompatActivity {
public static String Send_Result;
EditText num1;
 TextView txtrslt;
 Button btn;
 double n,i=1,fact=1;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 num1 = (EditText) findViewById(R.id.n1);
 txtrslt = (TextView) findViewById(R.id.resum);
 btn = (Button) findViewById(R.id.btn1);
 btn.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 n = Double.parseDouble(num1.getText().toString());
 while (i<=n)
 {
 fact=fact*i;
 i++;
 }
 String message = Double.toString(fact);
 Intent myIntent = new Intent(MainActivity.this, MainActivity2.class);
 myIntent.putExtra(Send_Result, message);
 startActivity(myIntent);
 }
 });
 }
}
```

activity_main2.xml :

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity2">
 <TextView
 android:id="@+id/textView"
 android:layout_width="137dp"
 android:layout_height="47dp"
 android:text="RESULT : "
 android:textColor="@color/black"
 android:textSize="34sp"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.167"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 app:layout_constraintVertical_bias="0.425" />
 <TextView
 android:id="@+id/reslt"
 android:layout_width="198dp"
 android:layout_height="59dp"
 android:text="00.00"
 android:textColor="#EA80FC"
 android:textSize="38sp"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.924"
 app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
 app:layout_constraintVertical_bias="0.433" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

MainActivity2.java :

```
package com.example.factorialcalculator;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main2);
 Intent intent = getIntent();
 String message = intent.getStringExtra(MainActivity.Send_Result);
 TextView textView = findViewById(R.id.reslt);
 textView.setText(message);
 }
}
```

## OUTPUT:

<img width="960" alt="lab exp-4" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/b9bb49a4-49f5-48d6-8e83-b032de1f0971">


<img width="182" alt="lab exp 4" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/6607585c-9401-434c-9224-73afc21d677a">


## RESULT:

Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


