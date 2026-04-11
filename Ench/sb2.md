# SparkBridge3 插件API参考文档

本文档描述了在SparkBridge3插件开发中可用的核心API。插件可通过全局变量 `spark` 访问这些接口。

## 核心对象

### `spark` - 主API对象
插件的主要操作入口，包含所有核心功能。

---

## 环境与配置

### `spark.env.get(key)`
获取环境变量池中的值

- 参数：
  - key : `String`
  变量名
- 返回值：对应的变量值，不存在返回 `undefined`
- 返回值类型：`Any`

### `spark.env.set(key, value)`
设置环境变量池中的值，并触发更新事件

- 参数：
  - key : `String`
  变量名
  - value : `Any`
  要设置的值
- 返回值：无

### `spark.debug`
获取或设置调试模式状态

- 类型：`Boolean`
- 默认值：从配置文件读取

---

## 事件系统

### `spark.on(eventName, callback)`
监听系统事件

- 参数：
  - eventName : `String`
  事件名称
  - callback : `Function`
  回调函数
- 返回值：无

**内置事件列表：**

| 事件名 | 描述 | 回调参数 |
| :--- | :--- | :--- |
| `core.ready` | 核心启动完成 | 无 |
| `gocq.pack` | 原始OneBot数据包 | `pack: Object` |
| `message.group.normal` | 普通群消息 | `pack: Object`, `reply: Function` |
| `message.group.anonymous` | 匿名群消息 | `pack: Object`, `reply: Function` |
| `message.group.notice` | 群通知消息 | `pack: Object`, `reply: Function` |
| `notice.group.increase` | 群成员增加 | `pack: Object` |
| `notice.group.decrease` | 群成员减少 | `pack: Object` |
| `request.group` | 加群请求 | `pack: Object` |
| `request.friend` | 加好友请求 | `pack: Object` |
| `config.update.[pluginName]` | 插件配置更新 | `key: String`, `newValue: Any` |
| `env.update.[key]` | 环境变量更新 | `newValue: Any` |
| `env.update` | 任意环境变量更新 | `key: String`, `newValue: Any` |

---

## QQ机器人接口

### `spark.QClient`
QQ客户端操作对象，包含所有与机器人交互的方法。

#### `sendGroupMsg(groupId, message)`
发送群消息

- 参数：
  - groupId : `Number`
  群号
  - message : `String|Array`
  消息内容（支持CQ码或消息段数组）
- 返回值：消息发送结果
- 返回值类型：`Promise<Object>`

#### `sendPrivateMsg(userId, message)`
发送私聊消息

- 参数：
  - userId : `Number`
  QQ号
  - message : `String|Array`
  消息内容
- 返回值：消息发送结果
- 返回值类型：`Promise<Object>`

#### `sendGroupForwardMsg(groupId, messages)`
发送群合并转发消息

- 参数：
  - groupId : `Number`
  群号
  - messages : `Array`
  转发消息节点数组
- 返回值：发送结果
- 返回值类型：`Promise<Object>`

#### `sendGroupBan(groupId, userId, duration)`
群禁言

- 参数：
  - groupId : `Number`
  群号
  - userId : `Number`
  被禁言用户QQ
  - duration : `Number`
  禁言时长（秒）
- 返回值：无

#### `deleteMsg(messageId)`
撤回消息

- 参数：
  - messageId : `Number`
  消息ID
- 返回值：无

#### `getGroupMemberList(groupId)`
获取群成员列表

- 参数：
  - groupId : `Number`
  群号
- 返回值：群成员列表
- 返回值类型：`Promise<Array>`

#### `getGroupMemberInfo(groupId, userId)`
获取群成员信息

- 参数：
  - groupId : `Number`
  群号
  - userId : `Number`
  QQ号
- 返回值：群成员信息
- 返回值类型：`Promise<Object>`

#### `setGroupAddRequest(flag, subType, approve)`
处理加群请求

- 参数：
  - flag : `String`
  请求标识
  - subType : `String`
  请求子类型
  - approve : `Boolean`
  是否同意
- 返回值：无

#### `getLoginInfo()`
获取机器人登录信息

- 返回值：登录信息（包含QQ号、昵称等）
- 返回值类型：`Promise<Object>`

---

## 消息构建器

### `spark.msgbuilder`
消息段构建工具

#### `msgbuilder.text(content)`
创建文本消息段

- 参数：
  - content : `String`
  文本内容
- 返回值：消息段对象
- 返回值类型：`Object`

#### `msgbuilder.image(file)`
创建图片消息段

- 参数：
  - file : `String|Buffer`
  图片文件路径或Buffer数据
- 返回值：消息段对象
- 返回值类型：`Object`

#### `msgbuilder.at(qq)`
创建@消息段

- 参数：
  - qq : `Number|String`
  QQ号
- 返回值：消息段对象
- 返回值类型：`Object`

#### `msgbuilder.face(id)`
创建表情消息段

- 参数：
  - id : `Number`
  表情ID
- 返回值：消息段对象
- 返回值类型：`Object`

#### `msgbuilder.reply(messageId)`
创建回复消息段

- 参数：
  - messageId : `Number`
  被回复的消息ID
- 返回值：消息段对象
- 返回值类型：`Object`

#### `msgbuilder.format(message)`
格式化消息（自动将字符串转为文本段）

- 参数：
  - message : `String|Array`
  原始消息
- 返回值：格式化后的消息段数组
- 返回值类型：`Array`

#### `msgbuilder.ForwardMsgBuilder()`
创建合并转发消息构建器

- 返回值：转发消息构建器实例
- 返回值类型：`ForwardMsgBuilder`

**ForwardMsgBuilder 方法：**

| 方法 | 描述 |
| :--- | :--- |
| `addMsgById(id)` | 通过消息ID添加节点 |
| `addCustomsMsg(name, uin, content)` | 添加自定义节点 |
| `getMsg()` | 获取构建好的消息数组 |

---

## 数据包构建器

### `spark.packbuilder`
OneBot数据包构建工具

#### `packbuilder.PrivateMessagePack(userId, message, echo)`
构建私聊消息数据包

- 参数：
  - userId : `Number`
  QQ号
  - message : `Array`
  消息段数组
  - echo : `String`
  回声ID（用于识别响应）
- 返回值：OneBot数据包
- 返回值类型：`Object`

#### `packbuilder.GroupMessagePack(groupId, message, echo)`
构建群消息数据包

- 参数：
  - groupId : `Number`
  群号
  - message : `Array`
  消息段数组
  - echo : `String`
  回声ID
- 返回值：OneBot数据包
- 返回值类型：`Object`

#### `packbuilder.GroupBanPack(groupId, userId, duration)`
构建禁言数据包

- 参数：
  - groupId : `Number`
  群号
  - userId : `Number`
  QQ号
  - duration : `Number`
  禁言时长（秒）
- 返回值：OneBot数据包
- 返回值类型：`Object`

#### `packbuilder.DeleteMsgPack(messageId)`
构建撤回消息数据包

- 参数：
  - messageId : `Number`
  消息ID
- 返回值：OneBot数据包
- 返回值类型：`Object`

#### `packbuilder.GroupMemberListPack(groupId, echo)`
构建获取群成员列表数据包

- 参数：
  - groupId : `Number`
  群号
  - echo : `String`
  回声ID
- 返回值：OneBot数据包
- 返回值类型：`Object`

---

## Web面板接口

### `spark.web`
Web面板操作对象

#### `web.createConfig(pluginName)`
创建插件配置表单

- 参数：
  - pluginName : `String`
  插件名称
- 返回值：配置构建器
- 返回值类型：`ConfigBuilder`

**ConfigBuilder 方法（链式调用）：**

| 方法 | 描述 |
| :--- | :--- |
| `text(key, defaultValue, description)` | 添加文本输入项 |
| `number(key, defaultValue, description)` | 添加数字输入项 |
| `switch(key, defaultValue, description)` | 添加开关项 |
| `select(key, options, defaultValue, description)` | 添加下拉选择项 |
| `array(key, defaultValue, description)` | 添加数组编辑器 |
| `register()` | 注册配置表单 |

#### `web.registerApi(method, path, handler, needAuth)`
注册自定义API路由

- 参数：
  - method : `String`
  HTTP方法（GET/POST等）
  - path : `String`
  API路径（会自动添加 `/api/plugin/` 前缀）
  - handler : `Function`
  处理函数 `(req, res) => {}`
  - needAuth : `Boolean`
  是否需要登录认证
- 返回值：无

#### `web.registerPage(title, relativePath)`
注册自定义插件页面

- 参数：
  - title : `String`
  页面标题
  - relativePath : `String`
  相对于插件目录的HTML文件路径
- 返回值：无
> 注册后页面会出现在Web面板侧边栏

---

## 工具类

### `spark.getLogger()`
获取当前插件的日志记录器

- 返回值：Winston日志实例
- 返回值类型：`Object`

**日志方法：**
- `logger.info(message)` - 普通信息
- `logger.warn(message)` - 警告信息
- `logger.error(message)` - 错误信息
- `logger.debug(message)` - 调试信息（仅在debug模式下显示）

### `spark.getFileHelper(pluginName)`
获取文件操作助手

- 参数：
  - pluginName : `String`
  插件名称
- 返回值：文件操作对象
- 返回值类型：`FileObj`

**FileObj 方法：**

| 方法 | 描述 |
| :--- | :--- |
| `initFile(filename, defaultObject, autoUpdate)` | 初始化配置文件 |
| `read(filename)` | 读取文件内容 |
| `write(filename, data)` | 写入文件 |
| `getBuffer(filename)` | 获取文件Buffer |

### `spark.parseCQString`
CQ码解析工具

#### `parseCQString.parse(str)`
将CQ码字符串解析为消息段数组

- 参数：
  - str : `String`
  包含CQ码的字符串
- 返回值：消息段数组
- 返回值类型：`Array`

#### `parseCQString.stringify(segments)`
将消息段数组序列化为CQ码字符串

- 参数：
  - segments : `Array`
  消息段数组
- 返回值：CQ码字符串
- 返回值类型：`String`

---

## BDS环境专用接口

以下接口仅在BDS环境中可用（即 `spark.onBDS === true` 时）

### `mc` 对象
LLSE的Minecraft操作对象

**常用方法：**

| 方法 | 描述 |
| :--- | :--- |
| `mc.broadcast(msg)` | 广播消息到游戏内 |
| `mc.runcmd(cmd)` | 执行控制台命令 |
| `mc.runcmdEx(cmd)` | 执行命令并获取输出 |
| `mc.getOnlinePlayers()` | 获取在线玩家列表 |
| `mc.listen(event, callback)` | 监听游戏事件 |

**常用事件：**

| 事件名 | 描述 | 回调参数 |
| :--- | :--- | :--- |
| `onJoin` | 玩家进入服务器 | `player: Player` |
| `onLeft` | 玩家退出服务器 | `player: Player` |
| `onChat` | 玩家发言 | `player: Player`, `msg: String` |
| `onPreJoin` | 玩家开始连接 | `player: Player` |
| `onConsoleCmd` | 控制台执行命令 | `cmd: String` |

### `ll` 对象
LLSE的插件管理对象

**常用方法：**

| 方法 | 描述 |
| :--- | :--- |
| `ll.import(name)` | 导入其他插件导出的接口 |
| `ll.exports(name, object)` | 导出接口供其他插件使用 |
| `ll.registerPlugin(name, desc, version)` | 注册当前插件 |

---

## 示例代码

### 监听群消息并回复
```javascript
spark.on('message.group.normal', (pack, reply) => {
    if (pack.raw_message === 'ping') {
        reply('pong');
    }
});
```

注册Web配置表单

```javascript
spark.web.createConfig("my_plugin")
    .switch("enabled", true, "是否启用插件")
    .text("api_key", "", "API密钥")
    .number("interval", 60, "检查间隔(秒)")
    .register();
```

使用文件助手存储数据

```javascript
const file = spark.getFileHelper("my_plugin");
file.initFile("data.json", { count: 0 });
let data = JSON.parse(file.read("data.json"));
data.count++;
file.write("data.json", data);
```

在BDS环境中监听游戏事件

```javascript
if (spark.onBDS) {
    mc.listen("onJoin", (player) => {
        spark.QClient.sendGroupMsg(
            spark.env.get("main_group"),
            `玩家 ${player.realName} 进入了服务器`
        );
    });
}
```