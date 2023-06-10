
# Ex.No:5 Create Your Own Content Providers to get Contacts details.


## AIM:

To create your own content providers to get contacts details using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “contentprovider″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to print the text create your own content providers to get contacts details.
Developed by:S.VINEESHA
Registeration Number :212221040180
*/
```

AndroidManifest.xml :

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools">
 <uses-permission android:name="android.permission.READ_CONTACTS"></uses-permission>
 <uses-permission android:name="android.permission.WRITE_CONTACTS"></uses-permission>
 <application
 android:allowBackup="true"
 android:dataExtractionRules="@xml/data_extraction_rules"
 android:fullBackupContent="@xml/backup_rules"
 android:icon="@mipmap/ic_launcher"
 android:label="@string/app_name"
 android:supportsRtl="true"
 android:theme="@style/Theme.ContentProviderForContacts"
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
<android.support.constraint.ConstraintLayout 
xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <Button
 android:id="@+id/button"
 android:layout_width="120dp"
 android:layout_height="54dp"
 android:background="#3F57DC"
 android:text="Get Contacts"
 android:onClick="btnGetContactPressed"
 android:textColor="#FAF1F1"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintHorizontal_bias="0.498"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
app:layout_constraintVertical_bias="0.77" />
</android.support.constraint.ConstraintLayout>
```

MainActivity.java :

```
package com.example.contentproviderforcontacts;
import android.Manifest;
import android.content.ContentResolver;
import android.content.pm.PackageManager;
import android.database.Cursor;
import android.provider.ContactsContract;
import android.support.v4.app.ActivityCompat;
import android.support.v4.content.ContextCompat;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.net.Uri;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 }
 public void btnGetContactPressed(View v){
 getPhoneContacts();
 }
 private void getPhoneContacts(){
 if (ContextCompat.checkSelfPermission(this, Manifest.permission.READ_CONTACTS)
 != PackageManager.PERMISSION_GRANTED) {
 ActivityCompat.requestPermissions(this, new String[] 
{Manifest.permission.READ_CONTACTS},0);
 }
 ContentResolver contentResolver = getContentResolver();
 Uri uri = ContactsContract.CommonDataKinds.Phone.CONTENT_URI;
 Cursor cursor = contentResolver.query(uri, null,null,null,null);
 Log.i("CONTACT_PROVIDER_DEMO","TOTAL # of Contacts ::: " + 
Integer.toString(cursor.getCount()));
 if (cursor.getCount() > 0){
 while (cursor.moveToNext()) {
 String contactName = 
cursor.getString(cursor.getColumnIndex(ContactsContract.CommonDataKinds.Phone.DISPLAY_NAME
));
 String contactNumber = 
cursor.getString(cursor.getColumnIndex(ContactsContract.CommonDataKinds.Phone.NUMBER));
 Log.i("CONTACT_PROVIDER_DEMO","Contact Name ::: " + " Ph # ::: " + contactNumber);
 }
 }
 }
}
```

## OUTPUT:

<img width="488" alt="labexp-5" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/bfa6101b-f085-4279-a90a-17c399fa7949">


<img width="183" alt="labexp-5 1" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/23e1fbdf-81de-46f3-897d-2438129e3bb4">


<img width="488" alt="lab exp 56" src="https://github.com/Vineesha29031970/Mobile-Application-Development/assets/133136880/77bbb090-8bbe-4854-afa0-81507cb62450">


## RESULT:

Thus a Simple Android Application create your own content providers to get contacts details using Android Studio is developed and executed successfully.
