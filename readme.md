# NotProguard

## 说明

[![](https://img.shields.io/badge/platform-Android-yellow.svg)](https://www.android.com)
[![](https://jitpack.io/v/kingsollyu/NotProguard.svg)](https://jitpack.io/#kingsollyu/NotProguard)
[![](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)
[![](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg?style=flat-square)](https://www.apache.org/licenses/LICENSE-2.0.html)

NotProguard 是个编译时注解，不会对运行时性能有任何影响。可修饰类、方法、构造函数、属性。

## 配置

### 添加仓库

```
repositories {
    maven { url 'https://jitpack.io' }
}
```

### 添加引用
```
dependencies {
    compile 'com.github.kingsollyu:NotProguard:1.0.0'
}
```

在 proguard-rules.pro 配置文件中过滤被这个注解修饰的元素

```pro
# keep annotated by NotProguard  - by sollyu
-keep @com.sollyu.android.not.proguard.NotProguard class * {*;}
-keep,allowobfuscation @interface com.sollyu.android.not.proguard.NotProguard
-keepclassmembers class * { @com.sollyu.android.not.proguard.NotProguard *;}
```

## 使用

### 整个类不混淆

```java
@NotProguard
public class User {}
```

### 单个属性不混淆

```java
@NotProguard
public int id;
```

### 单个方法不混淆

```java
@NotProguard
public void callButton1(Activity activity) {}
```

## License

```
Copyright 2017 Sollyu

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```