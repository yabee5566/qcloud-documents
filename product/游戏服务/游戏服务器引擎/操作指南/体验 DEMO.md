## 操作场景
本文档主要指导您如何使用“快捷实验”工具，体验 GSE 主流程，入门游戏服务器托管服务。


## 前提条件
已填写 [游戏服务器引擎申请表](https://cloud.tencent.com/apply/p/k0b6pvbhs6)，并获得使用资格。

## 整体流程
![](https://main.qcloudimg.com/raw/7b9bc4a44cd555b4ecadb4385c0fc36a.png)

调用 GSE 包含4个步骤：
1. 集成 ServerSDK。
2. 发布并集成 ServerSDK 的程序。
3. 调用云 API 请求服务地址，快速创建游戏服务器会话和玩家会话.
4. 访问服务。

## 操作步骤
### 快捷实验，体验全流程



1. 登录 [游戏服务器引擎控制台](https://console.cloud.tencent.com/gse)，选择左侧菜单【快捷实验】>【示范DEMO】。
2. 选择左上侧服务区域，单击【一键上传示范包】，提示创建成功后，进入【下一步】。
![](https://main.qcloudimg.com/raw/754a5828880cd9c95b480428ff8278bd.png)
>?这部分为开发者的代码集成 ServerSDK，请将代码和依赖上传，GSE 为您提供示范包，并可一键上传。
3. 单击【一键创建服务器舰队】，提示创建成功后，进入【下一步】。
![](https://main.qcloudimg.com/raw/3c89dff0d5f6da8da253edc1df40661e.png)
4. 单击【创建游戏服务器会话】，提示创建游戏服务器会话成功。
![](https://main.qcloudimg.com/raw/d601c9da2980aff4f7e93eaaf86d88ce.png)
>?此步骤为开发者通过调用云 API 完成，请在页面快速构建。
5. 单击【创建玩家会话】，提示创建玩家会话成功。单击一次【创建玩家会话】可以打开一个客户端网页。
![](https://main.qcloudimg.com/raw/594f74eadaf6987b1f81a56a1151c847.png)
6. 单击【跳转至客户端网页】，进入客户端连接游戏服务器页面，单击【连接】，提示服务器：连接成功。
![](https://main.qcloudimg.com/raw/c97d4c87d458c37ea342e33fee5046ca.png)
>?这部分为开发者通过上一步调用云 API 返回的 IP、port 连接游戏服务器进程，这里模拟了整个连接过程。 



  


### 演示弹性伸缩能力

#### 修改扩缩容配置
1. 登录 [游戏服务器引擎控制台](https://console.cloud.tencent.com/gse)，单击左侧菜单【服务器舰队】。
2. 选择刚一键创建的服务器舰队 ID，进入舰队详情，选择【扩缩容】。
![](https://main.qcloudimg.com/raw/4108225b034a0017f7da14962f2291b8.png)
3. 在其页面单击右上角【修改】，修改扩缩容配置，详情如下：
 - 游戏服务会话缓冲配置成50%，当服务器承载的游戏对局超过50%时，即会扩容。
 - 实例范围调整到0 - 3，让其有扩的空间。
 ![](https://main.qcloudimg.com/raw/c3f0fd4a1d4bf569ae7f279f02fad797.png)
 4. 修改完配置后，单击【确定】。


#### 创建多个游戏服务器会话，触发扩容

>?
- DEMO 默认配置1台服务器承载10个，直到第5个时，缓冲是50%。
- 超过5个游戏服务器会话需进行扩缩。需要创建6个游戏服务器会话。

1. 选择【快捷实验】>【部署示范包】，连续再单击5次【创建游戏服务器会话】，从而共创建6个游戏服务器会话。
![](https://main.qcloudimg.com/raw/68ba85a1f7f6f15c9ba9e285811bbf14.png)
2. 单击左侧菜单[【服务器舰队】](https://console.cloud.tencent.com/gse/fleet)，选择刚一键创建的服务器舰队 ID，进入舰队详情，选择【示例列表】。在其页面观察服务实例数量，2分钟后，您将发现服务器被扩容至2台。
![](https://main.qcloudimg.com/raw/7e0f3d123d47e1592837d4513d155091.png)


#### 结束游戏服务器会话，触发缩容
1. 选择【快捷实验】>【部署示范包】，进入客户端页面，单击【结束游戏会话】，即可结束5个游戏服务器会话。
![](https://main.qcloudimg.com/raw/36e9ffa11fa53218524b165c9dbdd903.png)
2. 单击左侧菜单[【服务器舰队】](https://console.cloud.tencent.com/gse/fleet)，选择刚一键创建的服务器舰队 ID，进入舰队详情，选择【示例列表】。在其页面观察服务实例数量，2分钟后，您将发现服务器被缩容至1台。
![](https://main.qcloudimg.com/raw/24c88db2fca81311d6e1f1199ae25c16.png)
