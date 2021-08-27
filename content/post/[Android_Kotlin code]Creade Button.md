---
title : "[Android_Kotlin code]Creade Button"
date : "2021-08-26"
tags : [CodeDictionary,Button,Android,Kotlin]
topics : [CodeDictionary]
---

## Steps
1. create button in layout/activity_main.xml
2. create strings on button in values/strings.xml
3. connect button and set event in MainActivity.kt

### padding and margin
![](https://raw.githubusercontent.com/eunhanlee/img/main/0053.jpg)

### 1. create button in layout/activity_main.xml
```xml

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:padding="10dp"
        android:text="@string/btn"
        android:textColor="@color/black"
        app:backgroundTint="@color/white" />
```

### 2. create strings on button in values/strings.xml
```xml

<string name="btn">Button</string>
```

### 3. connect button and set event in MainActivity.kt
```kotlin

import android.widget.Button

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
        // set id from activity_main.xml
        val button = findViewById<Button>(R.id.button)

        // button event
        button?.setOnClickListener()
        {
            // set event
            //Toast.makeText(this@MainActivity, "button test", Toast.LENGTH_LONG).show()
        }
    }

}
```