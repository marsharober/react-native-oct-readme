#### 如何将RN项目集成到Flutter项目中

* 复制以下文件到Flutter项目目录

```bash
package.json // 集成一下第三方库等
metro.config.js
index.js
Gemfile
babel.config.js
app.json
```

复制成功以后执行 `yarn install` 命令

#### Flutter项目Podfile配置

- 目前适配Podfile的文件只提供一份，主要添加的代码有如下3个部分

    ![图片说明](../../../images/image_11.png)

#### 报错处理

在执行 `pod install` 可能会报错，可能出现的错误如下：

- 错误1

```bash

error Failed to build the app: No package name found. Found errors in /Users/xxx.../easy_record/android/app/src/main/AndroidManifest.xml.

[!] Invalid `Podfile` file: 809: unexpected token at 'info Run CLI with --verbose flag for more details.
'.

 #  from /Users/zack/001_M/01Month/04_easy_record/easy_record/ios/Podfile:27
 #  -------------------------------------------
 #  target 'Runner' do
 >    config = use_native_modules!
 #  
 #  -------------------------------------------

```

解决方式，找到对应的 `android` 目录，然后在 `AndroidManifest.xml` 修改对应的代码

```xml

<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.YourPackageName">

```