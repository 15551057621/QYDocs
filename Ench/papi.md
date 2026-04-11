:::tip
这些是 LeviLamina 服务器提供的 PlaceholderAPI 变量。分为几个类别，提供中文名和简要说明。
:::  
## 服务器信息  

| 变量名 | 描述 | 备注 |
|--------|------|-----------|
| `levilamina_version` | LeviLamina版本 | 返回 LeviLamina 框架的版本号 |
| `system_name` | 系统名称 | 返回运行服务器的操作系统名称 |
| `system_version` | 系统版本 | 返回运行服务器的操作系统版本 |
| `server_version` | 服务器版本 | 返回服务器软件版本号   |
| `server_protocol_version` | 服务器协议版本 | 返回服务器使用的网络协议版本   |
| `server_port` | 服务器端口 | 返回服务器 IPv4 端口   |
| `server_port_v6` | 服务器IPv6端口 | 返回服务器 IPv6 端口   |
| `server_name` | 服务器名称 | 返回在 server.properties 中设置的服务器名称   |
| `server_mspt` | 服务器MSPT | 返回服务器每刻耗时（毫秒）   |
| `server_mspt_colored` | 服务器MSPT（带颜色） | 根据 MSPT 高低返回带颜色代码的 MSPT | 
| `server_tps` | 服务器TPS | 返回服务器每秒刻数   |
| `server_tps_colored` | 服务器TPS（带颜色） | 根据 TPS 高低返回带颜色代码的 TPS | 
| `server_uptime` | 服务器运行时间 | 返回服务器自启动后的运行时间   |
| `server_start_time` | 服务器启动时间 | 返回服务器启动的时间戳   |
| `server_online` | 服务器在线状态 | 返回服务器是否在线（通常为 true）   |
| `server_world_name` | 服务器主世界名称 | 返回主世界的名称   |
| `server_difficulty` | 服务器难度 | 返回服务器游戏难度（如：简单、普通、困难）   |
| `server_max_players` | 服务器最大玩家数 | 返回服务器允许的最大玩家数量   |
| `server_has_whitelist` | 服务器是否有白名单 | 返回服务器是否启用了白名单   |
| `server_on_allowlist` | 服务器是否在允许列表上 | 同 server_has_whitelist，检查白名单状态   |
| `server_total_entities` | 服务器总实体数 | 返回服务器中所有实体的总数   |
| `server_ram_max` | 服务器最大内存 | 返回服务器分配的最大内存   |
| `server_ram_used` | 服务器已用内存 | 返回服务器已使用的内存   |
| `server_ram_free` | 服务器空闲内存 | 返回服务器剩余的空闲内存   |
| `server_ram_bds_used` | BDS已用内存 | 返回 Bedrock Dedicated Server 进程本身使用的内存   |


## 玩家信息 
| 变量名 | 描述 | 返回值说明 | 
|--------|------|-----------|
| `player_realname` | 玩家真实名称 | 返回玩家的真实游戏ID   |
| `player_ip` | 玩家IP地址 | 返回玩家的 IP 地址   |
| `player_uuid` | 玩家UUID | 返回玩家的唯一标识符   |
| `player_xuid` | 玩家XUID | 返回玩家的 Xbox 唯一标识符   |
| `player_device` | 玩家设备类型 | 返回玩家使用的设备类型（如：Android, iOS, Windows 等）   |
| `player_client_version` | 玩家客户端版本 | 返回玩家客户端的版本号   |
| `player_protocol_version` | 玩家协议版本 | 返回玩家客户端使用的网络协议版本   |
| `player_language` | 玩家语言 | 返回玩家客户端的设置语言   |
| `player_ping` | 玩家延迟 | 返回玩家的网络延迟（ping值）   |
| `player_permlevel` | 玩家权限等级 | 返回玩家的权限等级（如：成员，操作员）   |
| `player_is_op` | 玩家是否为管理员 | 返回玩家是否是服务器管理员（操作员）   |
| `player_gamemode` | 玩家游戏模式 | 返回玩家的当前游戏模式   |
| `player_can_fly` | 玩家是否能飞行 | 返回玩家当前是否被允许飞行   |
| `player_flying` | 玩家是否在飞行 | 返回玩家当前是否正在飞行   |
| `player_exp_level` | 玩家经验等级 | 返回玩家的经验等级   |
| `player_hunger` | 玩家饥饿值 | 返回玩家当前的饥饿值   |
| `player_max_hunger` | 玩家最大饥饿值 | 返回玩家的最大饥饿值   |
| `player_saturation` | 玩家饱食度 | 返回玩家当前的饱食度   |
| `player_max_saturation` | 玩家最大饱食度 | 返回玩家的最大饱食度   |
| `player_bed_pos` | 玩家床位置 | 返回玩家床的坐标   |
| `player_chatTag` | 玩家聊天标签 | 返回玩家在聊天中的前缀标签   |
| `player_llmoney` | 玩家LLMoney经济 | 返回玩家在 LLMoney 经济系统中的余额  |
 
## 实体信息 
| 变量名 | 描述 | 备注 | 
|--------|------|-----------|
| `entity_name` | 实体名称 | 返回指定实体的名称   |
| `entity_type_name` | 实体类型名称 | 返回指定实体的类型名称   |
| `entity_pos` | 实体位置 | 返回指定实体的坐标   |
| `entity_health` | 实体生命值 | 返回指定实体的当前生命值   |
| `entity_max_health` | 实体最大生命值 | 返回指定实体的最大生命值   |
| `entity_biome` | 实体所在生物群系 | 返回指定实体所在的生物群系名称   |
| `entity_score` | 实体分数 | 返回指定实体的计分板分数   |
| `entity_rotation` | 实体旋转角度 | 返回指定实体的旋转角度（偏航角、俯仰角）   |

## 系统与工具  
| 变量名 | 描述 | 备注 |
|--------|------|-----------|
| `levilamina_version` | LeviLamina版本 | 返回 LeviLamina 框架的版本号   |
| `system_name` | 系统名称 | 返回运行服务器的操作系统名称   |
| `system_version` | 系统版本 | 返回运行服务器的操作系统版本   |
| `system_locale_code` | 系统区域代码 | 返回服务器的系统区域设置代码   |
| `translate_language` | 翻译语言 | 返回翻译功能使用的目标语言   |
| `i18n_translate` | 国际化翻译 | 用于翻译指定键名的文本   |
| `random` | 随机数 | 返回一个随机数   |
| `percentage` | 百分比 | 计算一个值相对于另一个值的百分比   |
| `round` | 四舍五入 | 对数字进行四舍五入到指定小数位   |
| `format` | 格式化 | 根据格式字符串格式化数据   |
| `scope` | 作用域 | 用于临时设置 PAPI 变量的解析上下文   |
| `slice` | 切片 | 返回字符串或列表的切片   |
| `dict` | 字典 | 用于创建键值对字典   |
| `join` | 连接 | 将列表中的元素用分隔符连接成字符串   |
| `replace` | 替换 | 替换字符串中匹配的文本   |
| `replaceAll` | 全部替换 | 替换字符串中所有匹配的文本   |
| `compare` | 比较 | 比较两个值   |
| `operation` | 数学运算 | 执行数学运算（加、减、乘、除等）   |
| `camel_case` | 驼峰命名法 | 将字符串转换为驼峰命名   |
| `snake_case` | 蛇形命名法 | 将字符串转换为蛇形命名   |
| `upper_case` | 大写 | 将字符串转换为大写   |
| `lower_case` | 小写 | 将字符串转换为小写   |
| `intToHexStr` | 整数转十六进制字符串 | 将整数转换为十六进制字符串   |
| `strToHexStr` | 字符串转十六进制字符串 | 将字符串转换为十六进制表示   |
| `doHash` | 计算哈希值 | 计算字符串的哈希值（算法1）   |
| `doHash2` | 计算哈希值2 | 计算字符串的哈希值（算法2）   |
| `doHash3` | 计算哈希值3 | 计算字符串的哈希值（算法3）   |
| `removeEscapeCode` | 移除转义代码 | 移除字符串中的颜色代码等转义序列   |

## 表情符号（Emoji）  
emoji_... （各类表情符号）   
这些变量返回代表游戏内各种按钮、物品、动作的 Unicode 表情符号。  
名称基本描述了它们代表的内容，例如：   
- emoji_ps_cross -> PlayStation 的 X 按钮 
- emoji_xbox_a -> Xbox 的 A 按钮 
- emoji_wooden_sword -> 木剑 
- emoji_attack_touch -> 触摸屏的攻击按钮 
- emoji_heart -> 心形 
- emoji_solid_star -> 实心星星