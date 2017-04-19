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
![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/jitpack.png)
 
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
设置颜色代码如下.
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="spots_dialog_color">@color/your_color_value</color>
</resources>
```

* 欢迎关注微信公众号、长期为您推荐优秀博文、开源项目、视频

![](http://upload-images.jianshu.io/upload_images/4037105-8f737b5104dd0b5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
