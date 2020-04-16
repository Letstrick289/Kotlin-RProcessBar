[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Round%20Corner%20Progress%20Bar-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1375) [![Build Status](https://travis-ci.org/akexorcist/Android-RoundCornerProgressBar.svg?branch=master)](https://travis-ci.org/akexorcist/Android-RoundCornerProgressBar) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.akexorcist/RoundCornerProgressBar/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.akexorcist/RoundCornerProgressBar)

Android-RoundCornerProgressBar
==============================

![Round Corner Progress Bar Sample](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/header.jpg)

Round Corner Progress Bar Library for Android

Colorful progress bar with round corner on progress which you can customized a color and corner radius


What's new in version 2.0
===========================
* New code structure, Easy for further development


Demo
===========================
[![Round Corner Progress Bar Demo (Google Play)](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/google_play.jpg)](https://play.google.com/store/apps/details?id=com.akexorcist.roundcornerprogressbar)


Overview
===============================
Round Corner Progress Bar
-------------------------------

A simple round corner progress bar with color and corner radius configuration supported

![Round Corner Progress Bar Sample](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/screenshot_01.jpg)

Icon Round Corner Progress Bar
-------------------------------

A round corner progress bar with icon

![Icon Round Corner Progress Bar Sample](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/screenshot_02.jpg)


Installation
===============================

### Maven ###
```
<dependency>
  <groupId>com.akexorcist</groupId>
  <artifactId>RoundCornerProgressBar</artifactId>
  <version>2.0.3</version>
</dependency>
```

### Gradle ###
```
implementation 'com.akexorcist:RoundCornerProgressBar:2.0.3'
```


Feature
===========================
* Progress's background color, corner radius and padding customize-able
* Primary and secondary progress supported 


Usage
===========================
For using custom attribute of progress bar, define 'app' namespace as root view attribute in your layout 

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
```

RoundCornerProgressBar
-------------------------------
### Layout XML ######
```xml
<com.akexorcist.roundcornerprogressbar.RoundCornerProgressBar
        app:rcProgress="float"
        app:rcSecondaryProgress="float"
        app:rcMax="float"
        app:rcRadius="dimension"
        app:rcBackgroundPadding="dimension"
        app:rcReverse="boolean"
        app:rcProgressColor="color"
        app:rcSecondaryProgressColor="color"
        app:rcBackgroundColor="color" />
```

![Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/usage_01.jpg)

### Public Methods ######
```java
int getRadius()
void setRadius(int radius)
int getPadding()
void setPadding(int padding)
float getMax()
void setMax(float max)

float getProgress()
void setProgress(float progress)
float getSecondaryProgressWidth()
float getSecondaryProgress()
void setSecondaryProgress(float secondaryProgress)

int getProgressBackgroundColor()
void setProgressBackgroundColor(int colorBackground)
int getProgressColor()
void setProgressColor(int colorProgress)
int getSecondaryProgressColor()
void setSecondaryProgressColor(int colorSecondaryProgress)

boolean isReverse()
void setReverse(boolean isReverse)

void setOnProgressChangedListener(OnProgressChangedListener listener)
float getLayoutWidth()
void invalidate()
```

IconRoundCornerProgressBar
-------------------------------
### Layout XML ######
```xml
<com.akexorcist.roundcornerprogressbar.IconRoundCornerProgressBar
        app:rcProgress="float"
        app:rcSecondaryProgress="float"
        app:rcMax="float"
        app:rcRadius="dimension"
        app:rcBackgroundPadding="dimension"
        app:rcReverse="boolean"
        app:rcProgressColor="color"
        app:rcSecondaryProgressColor="color"
        app:rcBackgroundColor="color"
        app:rcIconSrc="integer"
        app:rcIconSize="dimension"
        app:rcIconWidth="dimension"
        app:rcIconHeight="dimension"
        app:rcIconPadding="dimension"
        app:rcIconPaddingLeft="dimension"
        app:rcIconPaddingRight="dimension"
        app:rcIconPaddingTop="dimension"
        app:rcIconPaddingBottom="dimension"
        app:rcIconBackgroundColor="color" />
```

![Icon Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/usage_02.jpg)

### Public method on IconRoundCornerProgressBar ###
```java
int getIconImageResource()
void setIconImageResource(int resId)
Bitmap getIconImageBitmap()
void setIconImageBitmap(Bitmap bitmap)
Drawable getIconImageDrawable()
void setIconImageDrawable(Drawable drawable)

int getIconSize()
void setIconSize(int size)

int getIconPadding()
void setIconPadding(int padding)
int getIconPaddingLeft()
void setIconPaddingLeft(int padding)
int getIconPaddingRight()
void setIconPaddingRight(int padding)
int getIconPaddingTop()
void setIconPaddingTop(int padding)
int getIconPaddingBottom()
void setIconPaddingBottom(int padding)

int getColorIconBackground()
void setIconBackgroundColor(int color)

void setOnIconClickListener(OnIconClickListener listener)
```

### Icon Size & Padding ###
![Icon Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/usage_03.jpg)

Progress Bar Reversing
-------------------------------
![Icon Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/usage_04.jpg)

Recommendation for progress bar's height
-------------------------------
* `android:layout_height` for RoundCornerProgressBar's height 
* `app:rcIconSize` for IconRoundCornerProgressBar's height


Example
===========================
```xml
<com.akexorcist.roundcornerprogressbar.RoundCornerProgressBar
    android:layout_width="320dp" 
    android:layout_height="40dp" 
    app:rcBackgroundPadding="5dp" />

<com.akexorcist.roundcornerprogressbar.IconRoundCornerProgressBar
    android:layout_width="320dp" 
    android:layout_height="wrap_content"
    app:rcBackgroundPadding="10dp"
    app:rcIconSize="50dp" 
    app:rcIconPadding="5dp" />
```
![Icon Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/example_01.jpg)

![Icon Round Corner Progress Bar Usage](https://raw.githubusercontent.com/akexorcist/Android-RoundCornerProgressBar/master/image/example_02.jpg)

```java
RoundCornerProgressBar progress1 = ...;
progress1.setProgressColor(Color.parseColor("#ed3b27"));
progress1.setProgressBackgroundColor(Color.parseColor("#808080"));
progress1.setMax(70);
progress1.setProgress(15);

int progressColor1 = progress1.getProgressColor();
int backgroundColor1 = progress1.getProgressBackgroundColor();
int max1 = progress1.getMax();
int progress1 = progress1.getProgress();


IconRoundCornerProgressBar progress2 = ...;
progress2.setProgressColor(Color.parseColor("#56d2c2"));
progress2.setProgressBackgroundColor(Color.parseColor("#757575"));
progress2.setIconBackgroundColor(Color.parseColor("#38c0ae"));
progress2.setMax(550);
progress2.setProgress(147);
progress2.setIconImageResource(imageResource);

int progressColor2 = progress2.getProgressColor();
int backgroundColor2 = progress2.getProgressBackgroundColor();
int headerColor2 = progress2.getColorIconBackground();
int max2 = progress2.getMax();
int progress2 = progress2.getProgress();
```


Documentation
===========================
Thai Language : [Round Corner Progress Bar สำหรับคนบ้าขอบมน](http://www.akexorcist.com/2015/01/round-corner-progress-bar-library.html)


Special Thanks
===========================
Artit Kuiwilai @first087


What's Next
===========================
• Add Text Round Corner Progress Bar (Under-construction)

*TextRoundCornerProgressBar*
Additional attribute for TextRoundCornerProgressBar
```
rcTextProgressColor
rcTextProgressSize
rcTextProgressMargin
rcTextProgress
```

Additional method for TextRoundCornerProgressBar
```
String getProgressText()
void setProgressText(String text)
void setProgress(float progress)
int getTextProgressColor()
void setTextProgressColor(int color)
int getTextProgressSize()
void setTextProgressSize(int size)
int getTextProgressMargin()
void setTextProgressMargin(int margin)
``` 

Licence
===========================
Copyright 2020 Akexorcist

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License in the LICENSE file, or at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
