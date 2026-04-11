# 如何升级服务端

## 写在前面
 在非必要的情况下尽量不要去更新！
 毕竟咱也不知道下个版本会不会突然就哪个东西坏掉了

> ⚠️ 如果必须要更新的话 一定要先做以下操作
- 第一  先给服务器供一供
- 第二  给服务端上个香
- 第三  跳段钢管舞给服务器看，以表诚意
- 第四  给js之父、c++之父上个香
- 第五  人格，启动！
- 第六  星街里还传来，巴扬琴声吗∽

## 备份旧服务端

把整个旧服务端复制到新文件夹
> ⚠️一定要确保完整复制，不要复制到一半就去升级

## 准备一个全新的服务端

 去下载一个全新的整合包 并生成 bedrock\_server\_mod 文件

 整合包下载链接：[点击此处前往](https://www.minebbs.com/resources/levilamina-legacyscriptengine.7230/ "点我")

 移除 Python 加载器 (`./plugins/legacy-script-engine-nodejs/`)

 py插件少之又少，放那不用还会占进程

 把py献祭了，功德给其他加载器吃

## 复制基础数据

 \- 将以下文件移动到新服务端的同路径下

 -示例

    旧路径 (`old_server/plugins/LeviLamina/data`)

    新路径 (`new_server/plugins/LeviLamina/data`)

 **要移动的文件**

 `./config.json`                #多维度配置

` ./permissions.json`           #玩家权限配置

 `./server.properties`          #BDS核心配置

 `./plugins/LeviLamina/data`    #玩家数据映射表 (整个data文件夹都要备份)

## 判断插件类型并升级

 ⚠️ 只有lse插件才能多版本适配，dll插件不能

#### 不需要更新的lse插件

| 插件名称 | 说明 |
| :--- | :--- |
| Achievement | 成就插件配置文件 |
| Achievement-Core | 成就插件本体 |
| Achievement-Gui | 成就插件表单本体 |
| BDSLM_JS | 网页地图 |
| BehaviorLog | 玩家行为日志 |
| DynamicLights | 发包移动光源 |
| PMenu | 中菜单 |
| QYServer | Qy基础插件 |
| QueryBlockInfo | 快捷方块行为日志查询 |
| ShadowBlockCarrier | 搬运方块 |
| TpOfflinePlayer | 离线玩家定位 |
| call | 小木斧 |
| iland | 领地 |
| nbt | nbt剪辑 |
| lib | 领地依赖 |

#### 需要更新的前置库 (dll)

| 名称 | 说明 | 下载链接 |
| :--- | :--- | :--- |
| GMLIB | gm基础前置 | [github.com/GroupMountain/GMLIB-Release](https://github.com/GroupMountain/GMLIB-Release) |
| GMLIB-LegacyRemoteCallApi | gm基础lse导出 | [github.com/GroupMountain/GMLIB-LegacyRemoteCallApi](https://github.com/GroupMountain/GMLIB-LegacyRemoteCallApi) |
| iListenAttentively | gm事件库 | [github.com/MiracleForest/iListenAttentively-Release](https://github.com/MiracleForest/iListenAttentively-Release) |
| more-dimensions | 多维度依赖 | [github.com/LiteLDev/MoreDimensions](https://github.com/LiteLDev/MoreDimensions) |
| legacy-script-engine | lse加载器 | 整合包内自带对应版本 |
                                                                 
#### 需要更新的插件 (dll)
                                                                 
| 名称 | 说明 | 下载链接 |
| :--- | :--- | :--- |
| AntiXray | 反矿透 | [github.com/GlacieTeam/AntiXray](https://github.com/GlacieTeam/AntiXray) |
| Cleaner | 实体清理 | [github.com/GroupMountain/Cleaner](https://github.com/GroupMountain/Cleaner) |
| FreeCamera | 自由视角 | [github.com/GroupMountain/FreeCamera](https://github.com/GroupMountain/FreeCamera) |
| FuckNetherHeight | 去除下界高度 | [github.com/GroupMountain/FuckNetherHeight](https://github.com/GroupMountain/FuckNetherHeight) |
| GMEssentials | GM基础插件 | [github.com/GroupMountain/GMEssentials-Release](https://github.com/GroupMountain/GMEssentials-Release) |
| GMSidebar | 侧边栏 | [github.com/GroupMountain/GMSidebar](https://github.com/GroupMountain/GMSidebar) |
| Glacie | 多协议兼容 | [github.com/GlacieTeam/Glacie](https://github.com/GlacieTeam/Glacie) |
| LeviAntiCheat | 反作弊 | [github.com/LiteLDev/LeviAntiCheat](https://github.com/LiteLDev/LeviAntiCheat) |
| LeviOptimize | 性能优化 | [github.com/LiteLDev/LeviOptimize](https://github.com/LiteLDev/LeviOptimize) |
| UpdateNotice | 低版本客户端警告 | [minebbs.com/resources/12002](https://minebbs.com/resources/12002) |
| simple-dimensions | 多维度 | [github.com/ye111566/more-dimension-helper/](https://github.com/ye111566/more-dimension-helper/) |
                                                                         
### 5.迁移dll插件数据

 AntiXray #反矿透

 `./plugins/AntiXray/config/config.json`

 Cleaner #实体清理

 `./plugins/Cleaner/config/config.json`

 GMEssentials #GM基础插件

 `./plugins/GMEssentials/config/config.json`

 GMSidebar #侧边栏

 `./plugins/GMSidebar/config/config.json`

 Glacie #多协议兼容

 `./plugins/Glacie/config/config.json`

 `./plugins/lang/zh_CN.json`

 LeviAntiCheat #反作弊

 `./plugins/LeviAntiCheat/config/config.json`

 LeviOptimize #性能优化

`./plugins/LeviOptimize/config/config.json`

 simple-dimensions #多维度

`./config.json`

### 6.迁移并升级存档

 把旧存档复制到新服务端内

 打开存档"behavior\_packs"文件夹

 修改模组"manifest.json"文件：

 \- 在文件内找到"dependencies"项

 \- 修改这个项内所有"version"的值为 SAPI最新测试版本号

 示例：

   旧代码：

```
        "dependencies": [{
	    	"module_name": "@minecraft/server",
		    "version": "2.0.0-beta"
	    },
	    {
	    	"module_name": "@minecraft/server-ui",
	    	"version": "2.0.0-beta"
	    }]
```

   新代码：

```
         "dependencies": [{
	    	"module_name": "@minecraft/server",
		    "version": "2.1.0-beta" // 这改了
	    },
	    {
	    	"module_name": "@minecraft/server-ui",
	    	"version": "2.1.0-beta" // 这改了
	    }]
```

 查看SAPI版本号：

   @minecraft/server (https://learn.microsoft.com/en-us/minecraft/creator/scriptapi/minecraft/server/changelog?view=minecraft-bedrock-stable)

   @minecraft/server-ui (https://learn.microsoft.com/en-us/minecraft/creator/scriptapi/minecraft/server-ui/changelog?view=minecraft-bedrock-stable)

 \- 需要修改的模组

 QYServer

 \- 需要更新的模组

 USF #基础运行框架 (https://usfdown.zuyst.top/)

           

### 7.开机运行

 确保以上操作都正确完成时，开机运行测试

 \*如果一个没抱错，并且插件功能正常时

 \- 上线正式服



 \*如果报错了个别插件，不影响总体运行

 \- 判断不能运行的插件是否重要

 \- 不重要直接上线，重要老老实实回旧版本



 \*报错了好多，十分影响总体运行

 \- 老老实实回旧版本

The End

by fangfubin0782
