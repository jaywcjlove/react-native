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

<img src="https://user-images.githubusercontent.com/1680273/70401053-f8b8c100-1a68-11ea-845b-e28e22d5cf10.png" width="600" />

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

<details>
<summary>打包修改 APP 版本号</summary>

### Android

修改 `android/app/build.gradle` 配置

```java
android {
  .....
  defaultConfig {
    ....
    versionName "2.1.1"
  }
}
```

### iOS

修改 `ios/<应用名称>/Info.plist` 配置

```xml
<key>CFBundleShortVersionString</key>
<string>1.2.0</string>
```

</details>

### 常见错误

<details>
<summary>应用反应缓慢，出现卡顿问题</summary>

> 可能存在的问题

- 查看是否 console 日志打印过度造成。
- React Native Debugger 页面放到最前面，浏览器窗口不要放到选项卡里面。

</details>

<details>
<summary>Android: Gradle project sync failed.</summary>

在 Android Gradle 同步失败，导致项目无法启动，只需重新同步 Gradle 即可(可能需要翻墙)，方法如下图。

<img src="https://user-images.githubusercontent.com/1680273/70401827-2ce1b100-1a6c-11ea-9ec0-7fe3e203ce48.png" width="600" />

</details>

<details>
<summary>iOS: library not found for -lDoubleConversion.</summary>

Xcode 打卡工程文件错误，使用 `*.xcodeproj` 打开工程会报这个错误。

> 请打开 `*.xcworkspace` 的工程文件，错误将得到解决。

</details>

<details>
<summary>iOS: symbol(s) not found for architecture i386.</summary>

可能使用的某个包，不支持 i386 模拟器，使用 x86 模拟器或真机。

> 设置 `Build Configuration` 为 `Debug` 模式下可能会解决问题。  
> `Xcode` => `Product` => `Scheme` => `Edit Scheme...` => `Run` => `Info` => `Build Configuration`  

<img src="https://user-images.githubusercontent.com/1680273/70960642-8a07e300-20ba-11ea-83ac-d4e824727323.png" width="600" />

</details>
