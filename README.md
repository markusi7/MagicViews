MagicViews
==========
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.ivankocijan/MagicViews/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.ivankocijan/MagicViews)

Provides a simple way to set custom font in Android application.

![Screenshots](https://raw.github.com/ikocijan/MagicViews/master/screenshot.jpg)![Screenshots](https://raw.github.com/ikocijan/MagicViews/master/screenshoot_2.png)

## Adding to your project

1) Add the library as a dependency to your ```build.gradle```

```groovy
compile 'com.ivankocijan:MagicViews:version@aar'
```

2) Specify path to fonts folder in onCreate method of your Application class (See example app). 

```java
   public class MyApplication extends Application {
   
        @Override
        public void onCreate() {
            super.onCreate();
            
             MagicViews.setFontFolderPath(this, "fontFolderPath");
        
        }
   
   }
   
   ```

## Usage from layout

1) Add your application namespace to the root element in the XML
    <code>xmlns:app="http://schemas.android.com/apk/res-auto"</code> 

2) Instead of TextView use <code>com.ivankocijan.magicviews.views.MagicTextView</code>

```xml
    <com.ivankocijan.magicviews.views.MagicTextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:typeFace="cha_chicle.otf"/>
```

For a complete list of features and how to use them see [wiki page](https://github.com/ikocijan/MagicViews/wiki).

## Supported views
* TextView
* EditText
* Button
* CheckBox
* CheckedTextView
* RadioButton
* AutoCompleteTextView
* MultiAutoCompleteTextView
* PreferenceGroup
* Preference
* CheckboxPreference
* SwitchPreference
* EditTextPreference
* Span

## Supported Android versions
* 2.3 or higher

## Change log

V3.1.0

* New MagicFontSpan - See example [here](https://github.com/ikocijan/MagicViews/blob/development/TestApp%2Fsrc%2Fmain%2Fjava%2Fcom%2Fivankocijan%2FTestApp%2Factivites%2FMagicFontSpanExampleActivity.java)
* Layout preview no longer shows exception when MagicView is added to custom view - [See example] (https://github.com/ikocijan/MagicViews/blob/development/TestApp%2Fsrc%2Fmain%2Fjava%2Fcom%2Fivankocijan%2FTestApp%2Factivites%2FCustomViewActivity.java) 

V3.0.1

* New letter spacing attribute which lets you add horizonatal spacing between characters
* TabLayout support - you can now set custom font on TabLayout

See [wiki](https://github.com/ikocijan/MagicViews/wiki) for more info. 

You might encounter this issue after updating: /build/intermediates/exploded-aar/com.android.support/appcompat-v7/23.0.1/res/values-v23/values-v23.xml

There are two options to fix that:

Exclude appcompact-v7 from MagicViews library:

```groovy
    compile (compile 'com.ivankocijan:MagicViews:3.0.1@aar) {
        exclude group: 'com.android.support', module: 'appcompat-v7'
    }
```

or Compile your app with Android SDK 23:
```groovy
   android {
      compileSdkVersion 23
   }
```

V3.0

* Library now uses new AppCompat views which backport some cool stuff to pre-lollipop devices. See [Android developer blogspot](http://android-developers.blogspot.com/2015/04/android-support-library-221.html) for more info
* Added new views: RadioButton, AutoCompleteTextView and MultiAutoCompleteTextView
* Font can now be set from code by calling setFont(String fontName) method
* Example app is updated with new features
* Bugfixes

## Contributing

Feedback and code contributions are very much welcomed. Just make a pull request with a short description of your changes. By making contributions to this project you give permission for your code to be used under the same [license](LICENSE).
    
