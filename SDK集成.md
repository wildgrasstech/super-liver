> 对接前需要将app的包名发送给我们，然后我们这边进行依赖发布。
> 

### 根 build.gradle

添加仓库

```
 maven {
            credentials {
                username '621344be8af5d39eb3f17f3e'
                password 'AEFqUjoF0Tzm'
            }
            url '<https://packages.aliyun.com/maven/repository/2190199-release-52iISc/>'
        }

```


### app/build.gradle

添加依赖：

```
implementation 'mypackagename:keepalive:1.0.1'

```

初始化：

```
//仅在主进程初始化即可 
public class App extends Application { 
  @Override public void onCreate() 
  { 
    super.onCreate(); //只在主进程初始化即可 
    if (ProcessUtils.isMainProcess(this)) { 
      FG fg = new FG(); 
      fg.setKey("key"); 
      fg.init(this); 
    } 
  } 
}

```

完成接入

### SDK 引用的第三方库
以下是SDK内部引用的一些第三方工具类库，如果有冲突可联系调整
```
dependencies {
  implementation 'com.android.support:support-annotations:28.0.0' 
  implementation 'com.blankj:utilcodex:1.31.0' 
  implementation 'com.google.code.gson:gson:2.9.0' 
  implementation 'commons-io:commons-io:2.11.0' 
}
```

### SDK Android 权限
以下是SDK 内部一些功能需要用到的权限
```
<uses-permission android:name="android.permission.AUTHENTICATE_ACCOUNTS" android:maxSdkVersion="22" /> 
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" /> 
<uses-permission android:name="android.permission.REORDER_TASKS" /> 
<uses-permission android:name="android.permission.WRITE_SYNC_SETTINGS" /> 
<uses-permission android:name="android.permission.INTERNET" />
```
