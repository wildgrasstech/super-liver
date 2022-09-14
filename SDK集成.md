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
implementation 'com.team.cleaner:keepalive:1.0.1'

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
