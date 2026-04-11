# 导出函数列表
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

## 秒数格式化
`formatSeconds(seconds)`

- 参数：
  - seconds : `Number` - 要格式化的秒数
- 返回值：格式化后的时间字符串（如 "1天 2小时 3分钟 4秒"）
- 返回值类型：`String`

## 表情符号转换
`textToEmoji(msg, mode)`

- 参数：
  - msg : `String` - 需要处理的原始消息文本
  - mode : `Number` - 替换模式（0: 标准表情转特殊字符，1: 特殊字符转标准表情）
- 返回值：转换后的消息文本
- 返回值类型：String
- 说明：转换映射表定义在 config.replaceMap 中

## Minecraft 格式代码与 ANSI 颜色代码互转
`mcCode2Ansi(text, mode)`

- 参数：
  - text : `String` - 需要转换的文本
  - mode : `Number` - 转换模式（0: Minecraft 代码转 ANSI，1: ANSI 转 Minecraft 代码）
- 返回值：转换后的文本
- 返回值类型：`String`
- 说明：支持 §0-§f 颜色代码、§l/§o/§n/§m 样式代码，以及 ANSI 组合代码

