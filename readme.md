# NotProguard

## 说明

[![](https://jitpack.io/v/kingsollyu/NotProguard.svg)](https://jitpack.io/#kingsollyu/NotProguard)

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
-keep class * { @com.sollyu.android.not.proguard.NotProguard <fields>;  }
-keepclassmembers class * {@com.sollyu.android.not.proguard.NotProguard <methods>;  }
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