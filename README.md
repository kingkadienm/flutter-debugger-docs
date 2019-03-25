# Flutter Debugger

![](.gitbook/assets/icon.png)

## 简介

Flutter Debugger 这是一个用于调试 [Flutter](https://flutter.dev) 应用的独立应用程序，基于 [Flipper](https://github.com/facebook/flipper)（可扩展的移动应用调试器）并提供更多功能。

### 特性

* 网络检查
* 状态检查
* 数据库浏览

## 快速开始

### 安装

要安装该应用，您可以从[发布页面](https://github.com/blankapp/flutter-debugger/releases)下载预构建的二进制文件。

### 集成

添加以下内容到包的 pubspec.yaml 文件中：

```yaml
dependencies:
  flutter_flipperkit: ^0.0.7
```

> 这是官方维护的一些流行库的支持插件，请查看 [https://github.com/blankapp/flutter\_flipperkit\_plugins](https://github.com/blankapp/flutter_flipperkit_plugins)。

根据示例更改项目的 ios/Podfile 文件：

```diff
+source 'https://github.com/facebook/flipper.git'
+source 'https://github.com/CocoaPods/Specs'
# Uncomment this line to define a global platform for your project
-# platform :ios, '9.0'
+platform :ios, '9.0'
```

根据示例更改项目文件：

`android/app/build.gradle`:

```diff
android {
-    compileSdkVersion 27
+    compileSdkVersion 28

    defaultConfig {
-        targetSdkVersion 27
+        targetSdkVersion 28
    }
}
```

`android/app/gradle.properties`

```diff
+android.useAndroidX=true
+android.enableJetifier=true
```

您可以通过命令行安装软件包：

```bash
$ flutter packages get
```

#### 用法

```dart
import 'package:flutter_flipperkit/flutter_flipperkit.dart';

void main() {
  FlipperClient flipperClient = FlipperClient.getDefault();

  flipperClient.addPlugin(new FlipperNetworkPlugin());
  flipperClient.addPlugin(new FlipperReduxInspectorPlugin());
  flipperClient.addPlugin(new FlipperSharedPreferencesPlugin());
  flipperClient.start();

  runApp(MyApp());
}

...
```

> 请参考 [flutter-debugger-examples](https://github.com/blankapp/flutter-debugger-examples) 项目，将各插件集成到你的项目。

#### 运行程序

```bash
$ flutter run
```

## 相关链接

* [https://github.com/blankapp/flutter\_flipperkit](https://github.com/blankapp/flutter_flipperkit)
* [https://github.com/blankapp/flutter\_flipperkit\_plugins](https://github.com/blankapp/flutter_flipperkit_plugins)
* [https://github.com/blankapp/flutter-debugger](https://github.com/blankapp/flutter-debugger)
* [https://github.com/blankapp/flutter-debugger-docs](https://github.com/blankapp/flutter-debugger-docs)
* [https://github.com/blankapp/flutter-debugger-examples](https://github.com/blankapp/flutter-debugger-examples)
* [https://github.com/blankapp/flipper-plugin-dbbrowser](https://github.com/blankapp/flipper-plugin-dbbrowser)
* [https://github.com/blankapp/flipper-plugin-reduxinspector](https://github.com/blankapp/flipper-plugin-reduxinspector)

## 探讨

如果您对此项目有任何建议或疑问，可以通过 [Telegram Group](https://t.me/flutterdebugger) 或我的微信进行讨论。

![](.gitbook/assets/wechat_qrcode.png)

## 许可证

```text
MIT License

Copyright (c) 2019 JianyingLi <lijy91@foxmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

