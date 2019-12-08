# Android访问SD卡的问题



## 一、SD卡访问权限问题

​	1.在AndroidManifest.xml添加了以下权限配置信息

```java
	<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
	<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
```
​	2.在MainActivity中加入动态权限申请，具体如下：

```java
	int permission = ActivityCompat.checkSelfPermission(this,
    				Manifest.permission.WRITE_EXTERNAL_STORAGE);

    if (permission != PackageManager.PERMISSION_GRANTED) {
        // 请求权限
        ActivityCompat.requestPermissions(this, new String[]
                {Manifest.permission.WRITE_EXTERNAL_STORAGE},
                EXTERNAL_STORAGE_REQ_CODE);
    }
```
> 参考资料：https://blog.csdn.net/NYH19961125/article/details/85255224



## 二、读取SD卡下的文件

> 连接：https://jingyan.baidu.com/article/17bd8e522d2a8185ab2bb823.html