<img width="1916" height="653" alt="Screenshot 2026-09-07 091646" src="https://github.com/user-attachments/assets/803bcd59-f681-4983-aceb-9504ee0646aa" /># Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Design xml files for all operations such as blink, rotate, move, slide, zoom, fade.

Step 6: Display the button operations in MainActivity file.

Step 7: Save and run the application


## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Rajamanikandan R
Registeration Number : 212223220082
*/
```

### MainActivity.java:
````
package com.example.animation_in_android;



import android.os.Bundle;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private ImageView imageView;

    private Button moveButton;
    private Button blinkButton;
    private Button fadeButton;
    private Button clockwiseButton;
    private Button zoomButton;
    private Button slideButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);


        setContentView(R.layout.activity_main);


        imageView = findViewById(R.id.imageView);

        moveButton = findViewById(R.id.moveButton);
        blinkButton = findViewById(R.id.blinkButton);
        fadeButton = findViewById(R.id.fadeButton);
        clockwiseButton = findViewById(R.id.clockwiseButton);
        zoomButton = findViewById(R.id.zoomButton);
        slideButton = findViewById(R.id.slideButton);

        moveButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.move);

            imageView.startAnimation(animation);
        });

        blinkButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.blink);

            imageView.startAnimation(animation);
        });

        fadeButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.fade);

            imageView.startAnimation(animation);
        });

        clockwiseButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.clockwise);

            imageView.startAnimation(animation);
        });


        zoomButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.zoom);

            imageView.startAnimation(animation);
        });

        slideButton.setOnClickListener(v -> {
            Animation animation =
                    AnimationUtils.loadAnimation(MainActivity.this, R.anim.slide);

            imageView.startAnimation(animation);
        });
    }
}

````

### activity_main.xml:
````
<?xml version="1.0" encoding="utf-8"?>

<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fillViewport="true">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center"
        android:padding="20dp">

        <ImageView
            android:id="@+id/imageView"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:layout_marginBottom="20dp"
            android:src="@drawable/ic_bright_star"
            android:contentDescription="Image"/>

        <Button
            android:id="@+id/moveButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Move"/>

        <Button
            android:id="@+id/blinkButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Blink"/>

        <Button
            android:id="@+id/fadeButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Fade"/>

        <Button
            android:id="@+id/clockwiseButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Clockwise"/>

        <Button
            android:id="@+id/zoomButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Zoom"/>

        <Button
            android:id="@+id/slideButton"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:text="Slide"/>

    </LinearLayout>
</ScrollView>


````

### Move.xml:
```
<?xml version="1.0" encoding="utf-8"?>

<translate
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="300"
    android:duration="1000" />
```

### Blink.xml:
````
<?xml version="1.0" encoding="utf-8"?>

<alpha
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="500"
    android:repeatCount="3"
    android:repeatMode="reverse" />

````

### Fade.xml:
````
<?xml version="1.0" encoding="utf-8"?>

<alpha
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="1000"
    android:repeatCount="1"
    android:repeatMode="reverse" />

````

### Clockwise.xml:
````
<?xml version="1.0" encoding="utf-8"?>

<rotate
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />

````
### Zoom.xml:
```
<?xml version="1.0" encoding="utf-8"?>

<scale
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="2.0"
    android:fromYScale="1.0"
    android:toYScale="2.0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatCount="1"
    android:repeatMode="reverse" />

```

### slide.xml:
```
<?xml version="1.0" encoding="utf-8"?>

<translate
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-300"
    android:toXDelta="0"
    android:duration="1000" />

```





















## OUTPUT
#### Move
<img width="1917" height="1012" alt="Screenshot 2026-09-07 091541" src="https://github.com/user-attachments/assets/70e0912f-2d04-4c12-a0ab-6d4cd2232d36" />

#### Blink
<img width="1917" height="650" alt="Screenshot 2026-09-07 091556" src="https://github.com/user-attachments/assets/90e87f34-b148-4732-8a1c-0381cdbb8370" />

#### Fade
<img width="1917" height="658" alt="Screenshot 2026-09-07 091613" src="https://github.com/user-attachments/assets/283e9e2d-d0cc-484c-9037-3f57d326e23d" />

#### ClockWise:

<img width="1902" height="657" alt="Screenshot 2026-09-07 091628" src="https://github.com/user-attachments/assets/ccdc738a-e5f2-489d-9f97-aac6f90e7fcb" />

#### Zoom:

<img width="1916" height="653" alt="Screenshot 2026-09-07 091646" src="https://github.com/user-attachments/assets/261dbed9-9ea4-4ee5-a924-3912915c55d5" />

#### Slide
<img width="1917" height="647" alt="Screenshot 2026-09-07 091711" src="https://github.com/user-attachments/assets/58bb5174-ce74-468f-a99a-327a6322fed5" />


## RESULT

Thus a Simple Android Application to add animations: Move,blink,fade,clockwise,zoom,slide operations using Android Studio is developed and executed successfully.








## RESULT
