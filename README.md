
# Rapport

Ändringar i activity_main.xml:

En EditText widget med id "nyNewEdt" lades till och positionerades längst upp. 
Styling, så som textstorlek, font, och padding lades till.
```
    <EditText
        android:id="@+id/myNewEdt"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-condensed-light"
        android:hint="@string/write_something"
        android:inputType="text"
        android:paddingLeft="20dp"
        android:paddingRight="20dp"
        android:soundEffectsEnabled="true"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0"
        tools:layout_editor_absoluteX="0dp" />
```

ImageView elementet lades till med vidd och höjd på 300dp. Positionerades i förhållande till EditText elementet.
```
    <ImageView
        android:id="@+id/imageView"
        android:layout_width="300dp"
        android:layout_height="300dp"
        android:contentDescription="@string/happy_corgi"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/myNewEdt"
        app:srcCompat="@drawable/corgi" />
```
Bilden är en drawable som skapades i Adobe Illustrator och importerades till mappen "drawable".
[Länk till drawable](app/src/main/res/drawable-mdpi/corgi.png)

Button elementet lades till med id "myButton".
Styling som färg och padding lades till och elementet positionerades i förhållande till ImageView elementet.
```
<Button
        android:id="@+id/myButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/the_button"
        android:layout_margin="10dp"
        android:background="@color/colorAccent"
        android:padding="15dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />
```
För att göra knappen funktionell kopplades den ihop via findViewById och funktionen onClick initierades i MainActivity.java.
När man klickar på knappen skrivs texten "You clicked the button!" i Logcat.
```
@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

        Button b = findViewById(R.id.myButton);

        b.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Log.d("==>","You clicked the button!");
            }
        });
    }}
```

Screenshot av appen med alla widgets; EditText, ImageView och Button.
[Länk till screenshot av app](screenshots/widgetapp.png)

Ändringar i values:
Färgerna i colors.xml ändrades.
```
<resources>
    <color name="colorPrimary">#FF9800</color>
    <color name="colorPrimaryDark">#FF5722</color>
    <color name="colorAccent">#FFEB3B</color>
</resources>
```

Strings lades till i strings.xml för att undvika hårdkodad text.
```
<resources>
    <string name="app_name">Happy Corgi Widgets</string>
    <string name="write_something">Write something nice here..</string>
    <string name="happy_corgi">happy corgi</string>
    <string name="the_button">The button</string>
</resources>
```