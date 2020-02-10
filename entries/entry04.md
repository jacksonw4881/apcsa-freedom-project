# Entry 4
##### 2/10/20

## Engineering Design Process
Currently, I am on step 5 on the Engineering Design Process, which is creating a prototype. I have created multiple buttons that the user can choose to click on based on what the user wants to see, and when the user clicks on the button, it will open to a new screen with different texts or different buttons that the user can click on. I have learned how to do this with the [Android Developer Guide](https://developer.android.com/guide/topics/ui/controls/button) and some help on [Stack Overflow](https://stackoverflow.com/questions/24610527/how-do-i-get-a-button-to-open-another-activity). This interaction is a big component of my app since my app will have many buttons that the user can click on to see what tip the user wants to see.

## Knowledge
To create a button, we have to drag a button from the palette to the design layout. This is the code on the text editor of activity_main.xml when we add the button onto the screen of the design editor.

```
<Button
        android:id="@+id/gunguide"
        android:layout_width="418dp"
        android:layout_height="92dp"
        android:text="Gun Guide"
        tools:layout_editor_absoluteX="-8dp"
        tools:layout_editor_absoluteY="-3dp" />
```

The only main takeaway of this is that the name of the button is called Gun Guide and the id of the button is gunguide. Similar to CSS, Buttons have ids that we can use when we want to select a specific button.

Next, we need to create a private variable button in the MainActivity class. The name of the private variable button must be the same as the button id in order for it to work.

```private Button gunguide;```

We then have to reference it by creating an object of a button type within the ```protected void onCreate(Bundle savedInstanceState)``` method, which is similar to the main method in Java.

```gunguide = (Button) findViewById(R.id.gunguide);```

The ```findViewById``` method goes through the resources of the id to find the gunguide id button and returns it. We cast it as a Button type to have the properties of a Button.

Then, we want something to happen when the user clicks on the button. We can do this by assigning an ```setOnClickListener``` method onto the button.

```
gunguide.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        openGunGuide();
    }
});
```

Essentially, when the Gun Guide button is clicked, the ```onClick``` method will be called, which will call the ```openGunGuide``` method.

Lastly, we need to create the ```openGunGuide``` method and create an ```Intent``` object for our button in order for it to open to another screen. We then call the ```Intent``` object with the ```startActivity``` method.

```
public void openGunGuide() {
    Intent intent = new Intent(this, GunGuide.class);
    startActivity(intent);
    }
```

This will open GunGuide.java from MainActivity.java when the user clicks on the Gun Guide button.

The process of learning how to make buttons responsive is very important in my project because my guide has subtopics within topics of pubg, which means that when the user clicks on a button for some topics, there will be another button about a similar topic of the button name that has even more text when the user clicks on that button.

## Skill

A skill that I have developed when building the app is **time management**. I have realized that although I would like to include some more content that might be helpful for the user, I have realized it is better in the long run to actually start coding the app on Android Studio to fulfill the Minimum Viable Product, as it is better to have an app that works with some content rather than have an app that does not work with a bunch of extra content. I have prioritized making the app work like how it is suppose to before focusing on things that are not as significant, like adding extra content or making the app look better.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)