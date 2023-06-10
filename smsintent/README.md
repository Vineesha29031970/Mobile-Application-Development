
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to create and design an android application Send SMS using Intent.
Developed by:S.VINEESHA
Registeration Number :212221040180
*/
```

AndroidManifest.xml :

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <uses-feature
        android:name="android.hardware.telephony"
        android:required="false" />
    <uses-permission android:name="android.permission.SEND_SMS"/>
    <uses-permission android:name="android.permission.RECEIVE_SMS"/>
    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
        android:theme="@style/Theme.LabExp6"
    tools:targetApi="31">
    <activity
        android:name=".MainActivity"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
    </activity>
</application>
</manifest>
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
        android:id="@+id/number"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="180dp"
        android:ems="10"
        android:inputType="phone"
        android:text="Phone Number"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="Autofill,HardcodedText,LabelFor,TouchTargetSizeCheck" />

    <EditText
        android:id="@+id/message"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="24dp"
        android:ems="10"
        android:inputType="text"
        android:text="Type Message"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/number"
        tools:ignore="Autofill,HardcodedText,LabelFor,TouchTargetSizeCheck" />
    <Button
        android:id="@+id/send"
        android:layout_width="100dp"
        android:layout_height="57dp"
        android:layout_marginBottom="316dp"
        android:text="SEND"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/message"
        app:layout_constraintVertical_bias="0.452"
        tools:ignore="HardcodedText" />
    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SEND SMS"
        android:textColor="@color/black"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.161"
        tools:ignore="HardcodedText" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

MainActivity.java :

```
package com.example.labexp6;
import androidx.appcompat.app.AppCompatActivity;
import android.Manifest;
import android.content.pm.PackageManager;
import android.os.Build;
import android.os.Bundle;
import android.telephony.SmsManager;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    private EditText number,message;
    private Button send;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        number = findViewById(R.id.number);
        message = findViewById(R.id.message);
        send = findViewById(R.id.send);
        send.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if (Build.VERSION.SDK_INT>=Build.VERSION_CODES.M){
                    if (checkSelfPermission(Manifest.permission.SEND_SMS) ==
                            PackageManager.PERMISSION_GRANTED){
                        sendSMS();
                    }else {
                        requestPermissions(new String[]{Manifest.permission.SEND_SMS},1);
                    } } } });
    }
    private void sendSMS(){
        String phoneNo = number.getText().toString().trim();
        String SMS = message.getText().toString().trim();
        try{
            SmsManager smsManager = SmsManager.getDefault();
            smsManager.sendTextMessage(phoneNo,null,SMS,null,null);
            Toast.makeText(this,"Message is sent",Toast.LENGTH_SHORT).show();
        } catch (Exception e){
            e.printStackTrace();
            Toast.makeText(this,"Failed to send message",Toast.LENGTH_SHORT).show();
        } } }
 ```

## OUTPUT:

<img width="960" alt="Screenshot 2023-06-03 212610" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/966c2fea-88f4-495f-b879-47a8ae0895db">


<img width="960" alt="Screenshot 2023-06-03 212744" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/44c2d84b-342b-4f9b-8951-f72a2bddc3e3">


<img width="178" alt="bjvgkjk6work" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/0b1afa52-272d-410f-a941-10fc36bc3a30">


<img width="184" alt="dyjuworkshop6" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/f033d99e-5151-4092-9c5f-120dc28e9615">

## RESULT:

Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
