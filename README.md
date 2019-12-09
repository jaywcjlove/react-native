# react-native

<details>
<summary>修改 App 在手机上展示的名称</summary>

### Android

修改 `android/app/src/main/res/values/strings.xml` 配置

```xml
<resources>
  <string name="app_name">这里填写名称</string>
</resources>
```

### iOS

修改 `ios/AneConfigure/Info.plist` 配置

```xml
<key>CFBundleDisplayName</key>
<string>这里填写名称</string>
```

</details>

<details>
<summary>修改 App 在手机上展示的图标</summary>

### Android

修改替换 `android/app/src/main/res/mipmap-(*)` 下面的图标

图标分为 方形图标(`ic_launcher.png`) 和 圆形图标(`ic_launcher_round.png`)

### iOS

修改 `ios/AneConfigure/Images.xcassets/AppIcon.appiconset/Contents.json` 配置，及修改配置目录 `ios/AneConfigure/Images.xcassets/AppIcon.appiconset` 下的图标文件。

通过 xcode 下图拖拽更换图标更方便。

![image](https://user-images.githubusercontent.com/1680273/70401053-f8b8c100-1a68-11ea-845b-e28e22d5cf10.png)

</details>

<details>
<summary>Android: Gradle project sync failed.</summary>

在 Android Gradle 同步失败，导致项目无法启动，只需重新同步 Gradle 即可(可能需要翻墙)，方法如下图。

![image](https://user-images.githubusercontent.com/1680273/70401827-2ce1b100-1a6c-11ea-9ec0-7fe3e203ce48.png)

</details>

<details>
<summary>判断 Release/Debug 用于调试</summary>

### Android

修改 `android/app/src/main/res/values/strings.xml` 配置

```java
// 在Android Studio项目中
if(BuildConfig.DEBUG){
  // debug模式
}else{
  // release模式
}
```

### iOS

```objective-c
#ifdef DEBUG
   // debug模式
#else
    //release 模式
#endif
```

### React Native

```js
if (__DEV__) {
  // debug 模式
} else {
  // release 模式
}
```

</details>
