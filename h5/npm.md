
#### npm install xxxx --legacy-peer-deps

npm v7+ installs peerDependencies by default，使用
--legacy-peer-deps让npm以v3-v6的方式去继续执行安装操作
从而忽略冲突

<br/>

#### 获取npm源
npm config get registry

<br/>

#### npm cache verify
npm cache verify 命令会检查缓存目录，并删除所有过期和无效的缓存条目

<br/>

#### 淘宝镜像 
```javaScript
https://registry.npm.taobao.org/ 

npm install xxx --registry=https://registry.npm.taobao.org/
```

<br/>

#### npm config set python "path"
设置 npm 使用的 Python 路径

<br/>


#### 参考
[--legacy-peer-deps](https://bbs.huaweicloud.com/blogs/349716)