# 一行代码实现加载对话框



![Example Image1][1]

===========

开始
===
在project的build.gradle添加如下代码(如下图)
```groovy
allprojects {
    repositories {
        jcenter()
        maven { url "https://jitpack.io" }
    }
}
```
![image](jitpack.png)
 
在build.gradle添加依赖
```groovy
     compile 'com.github.open-android:Loading:1.0'
```

For example: 
```java
AlertDialog dialog = new SpotsDialog(context);
dialog.show();
...
dialog.dismiss();
```
===========



**For example:**

默认是白色，想修改样式直接修改style，代码如下：
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="Custom" parent="android:Theme.DeviceDefault.Dialog">
        <item name="DialogTitleAppearance">@android:style/TextAppearance.Medium</item>
        <item name="DialogTitleText">Updating…</item>
        <item name="DialogSpotColor">@android:color/holo_orange_dark</item>
        <item name="DialogSpotCount">4</item>
    </style>
</resources>
```

如果自定义样式代码如下:
```java
new SpotsDialog(context, R.style.Custom).show();
```

Result:

![Example Image1][2]

如果想改变加载的文字，代码如下，默认是loading，英文的，想改成中文，代码如下:
```java
new SpotsDialog(context, "Завантаження").show();
```


**Note:**
On the pre-lollipop devices _DialogSpotColor_ item won't work. As workaround just override color in your resources.
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="spots_dialog_color">@color/your_color_value</color>
</resources>
```


