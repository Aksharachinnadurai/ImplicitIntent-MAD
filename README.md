# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: AKSHARA C
Registeration Number : 212223220004
*/
```

# Main_Activity.java:
```
package com.example.implicit;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import com.example.implicit.R;

public class MainActivity extends AppCompatActivity {

    EditText urlInput;
    Button navigateBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        urlInput = findViewById(R.id.urlInput);
        navigateBtn = findViewById(R.id.navigateBtn);

        navigateBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = urlInput.getText().toString().trim();

                if (url.isEmpty()) {
                    Toast.makeText(MainActivity.this, "Please enter a URL", Toast.LENGTH_SHORT).show();
                } else {
                    // Add http if missing
                    if (!url.startsWith("http://") && !url.startsWith("https://")) {
                        url = "http://" + url;
                    }

                    // Create implicit intent
                    Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));

                    // Start browser
                    try {
                        startActivity(intent);
                    } catch (Exception e) {
                        Toast.makeText(MainActivity.this, "No app found to handle this request", Toast.LENGTH_SHORT).show();
                    }
                }
            }
        });
    }
}

```
# activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/urlInput"
        android:hint="Enter website (e.g. www.gmail.com)"
        android:inputType="textUri"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/navigateBtn"
        android:text="Navigate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"/>
</LinearLayout>

```

## OUTPUT

<img width="1913" height="1024" alt="image" src="https://github.com/user-attachments/assets/89fa3fbe-35b9-492c-84fd-d7026c9a4f9b" />

<img width="1917" height="1019" alt="Screenshot 2025-09-22 224008" src="https://github.com/user-attachments/assets/15a8ab22-5929-473d-aa21-0511c7e75211" />

<img width="1916" height="1028" alt="image" src="https://github.com/user-attachments/assets/24edf104-0e6c-4b6d-be2f-c86db8279a78" />



## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


