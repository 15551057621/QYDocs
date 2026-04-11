# QYServer插件所有导出函数开发文档
简介不知道怎么写 就这样吧

导入示例：`ll.import("QYServer","函数名")`


## 判断玩家是否有权限在领地内位置操作
`LandJudgment(Player, Pos)`
- 参数：
  - Player : `Player` - 玩家对象
  - Pos : `IntPos` - 方块坐标对象
- 返回值：是否有操作权限
- 返回值类型：`Boolean`

## 获取玩家称号
`getChatTag(player)`
- 参数：
  - player : `Player` - 目标玩家对象
- 返回值：玩家的聊天称号
- 返回值类型：`String`

## 崩溃玩家客户端
`crash(player)`
- 参数：
  - player : `Player` - 目标玩家对象
- 返回值：无
- 返回值类型：`void`

## 将字节数格式化为易读的文件大小字符串。
`getFileSize(bytes)`

- 参数：
  - bytes : `Number` - 文件大小的字节数
- 返回值：格式化后的文件大小字符串
- 返回值类型：`String`

## 随机打乱字符串中字符的顺序
`shuffleString(str)`

- 参数：
  - str : `String` - 要打乱的字符串
- 返回值：打乱后的字符串
- 返回值类型：`String`

## 根据给定的百分比判断是否触发概率事件
`probability(percent)`
  
- 参数：
  - percent : `Number` - 触发概率百分比 (0-100)
- 返回值：是否触发概率事件
- 返回值类型：`Boolean`

## 去除字符串中的所有颜色代码
`delStringCode(text)`

- 参数：
  - text : `String` - 原始文本
- 返回值：去除颜色代码后的文本
- 返回值类型：`String`

## 传送点同步至卫星地图
`addPosPublicMap()`

- 参数：无
- 返回值：无
- 返回值类型：`void`

## runBackup - 存档备份

执行服务器存档备份操作。

```javascript
runBackup()
```

- 参数：无
- 返回值：是否开始备份
- 返回值类型：Boolean
- 示例：

```javascript
// 开始备份存档
if (runBackup()) {
    logger.info("备份任务已启动");
} else {
    logger.warn("备份任务正在进行中");
}
```

## 用户界面

msgUI - 私聊菜单

打开私聊快捷菜单界面。

```javascript
msgUI(pl, swi, lastPlayerName)
```

- 参数：
  - pl : Player - 玩家对象
  - swi : Boolean - 发送后是否再次打开表单（可选，默认 false）
  - lastPlayerName : String - 上次选择的玩家名称（可选）
- 返回值：无
- 返回值类型：void
- 示例：

```javascript
// 打开私聊菜单
msgUI(player);
```

## setChatTag - 称号添加菜单

打开快捷设置玩家称号的菜单界面。

```javascript
setChatTag(pl)
```

- 参数：
  - pl : Player - 玩家对象
- 返回值：无
- 返回值类型：void
- 示例：

```javascript
// 打开称号设置菜单
setChatTag(player);
```

## 娱乐功能

getBook - 小说阅读器

获取游戏内小说阅读器界面。

```javascript
getBook(pl)
```

- 参数：
  - pl : Player - 玩家对象
- 返回值：无
- 返回值类型：void
- 示例：

```javascript
// 打开小说阅读器
getBook(player);
```

## Buddha - 佛祖保佑

在控制台输出佛祖保佑的 ASCII 艺术字。

```javascript
Buddha()
```

- 参数：无
- 返回值：无
- 返回值类型：void
- 示例：

```javascript
// 输出佛祖保佑
Buddha();
```

## 使用示例

### 基本使用

```javascript
const { LandJudgment, getChatTag, getFileSize } = ll.imports("QYServer");

// 检查领地权限
if (LandJudgment(player, blockPos)) {
    // 获取玩家称号
    const tag = getChatTag(player);
    player.tell(`欢迎 ${player.name} [${tag}]`);
}

// 格式化文件大小
logger.info(`备份文件大小: ${getFileSize(fileSize)}`);
```

#### 概率系统

```javascript
const { probability, shuffleString } = ll.imports("QYServer");

// 随机事件
if (probability(5)) {
    const scrambledName = shuffleString(player.name);
    player.tell(`你的名字被打乱了: ${scrambledName}`);
}
```

## 注意事项

1. 权限相关：LandJudgment 函数需要 iLand API 支持
2. 危险操作：crash 函数会直接崩溃玩家客户端，请谨慎使用
3. 备份功能：runBackup 需要配置 7za.exe 工具
4. 网络请求：部分功能依赖外部 API，需要网络连接

这个文档涵盖了所有导出的 API 函数，提供了详细的参数说明、返回值类型和使用示例。