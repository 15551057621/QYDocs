# 服务器文件夹与文件结构说明

## 文件夹目录

### 正常情况下不能动
> 此类为原版BDS运行时所需数据

| 文件夹名称 | 说明 |
| :--- | :--- |
| `behavior_packs` | 原版行为包定义 |
| `resource_packs` | 原版资源包定义 |
| `config` | 原版组件定义 |
| `definitions` | 原版行为包辅助定义文件 |
| `development_behavior_packs` | 行为包调试文件夹 |
| `development_resource_packs` | 资源包调试文件夹 |
| `development_skin_packs` | 皮肤包调试文件夹 |
| `world_templates` | 世界模板 |

### 有用且能动
> 谨慎操作

| 文件夹名称 | 说明 |
| :--- | :--- |
| `libraries` | 基岩通信协议库 |
| `logs` | 日志文件 |
| `plugins` | 插件文件夹 |
| `worlds` | 存档文件 |

#### logs 子目录
> 数据日志输出文件
  
| 文件夹/文件名称 | 说明 |
| :--- | :--- |
| `BehaviorLog` | 玩家行为日志 |
| `LegacyScriptEngine` | LSE敏感操作日志 (通常没有用,可以直接删) |
| `crash` | 崩溃日志 (通常没有用,可以直接删) |
| `LeviAntiCheat.log` | LAC反作弊检测日志 |
| `latest.log` | 控制台输出历史日志 |

##### logs/LegacyScriptEngine 子目录
> 开发调试用
  
| 文件名称 | 说明 |
| :--- | :--- |
| `Sensitive_Operation_Records-Js.log` | JS插件敏感日志 |
| `Sensitive_Operation_Records-Lua.log` | Lua插件敏感日志 |
| `Sensitive_Operation_Records-NodeJs.log` | NodeJS插件敏感日志 |

##### logs/crash 子目录
> 山西崩溃用
  
| 文件名称 | 说明 |
| :--- | :--- |
| `minidump_日期.dmp` | 内存转储文件 |
| `trace_日期.log` | 直接可读的崩溃报告 (txt格式) |

#### worlds 子目录
| 文件夹名称 | 说明 |
| :--- | :--- |
| `QYServer` | 主地图存档 |
| `Sky` | 光遇存档 |
| `backrooms` | 后室存档 |

##### worlds/QYServer 子目录
| 文件夹/文件名称 | 说明 |
| :--- | :--- |
| `behavior_packs` | 行为包文件夹 |
| `db` | 数据文件 |
| `resource_packs` | 资源包文件夹 |
| `dimension_config.json` | 多维度定义文件 |
| `level.dat` | 存档全局定义文件 |
| `level.dat_old` | level.dat的备份文件 |
| `levelname.txt` | 世界名称 |
| `world_behavior_packs.json` | 行为包入口定义文件 |
| `world_icon.jpeg` | 存档图标 |
| `world_resource_packs.json` | 资源包入口定义文件 |

## 文件列表

| 文件名称 | 说明 |
| :--- | :--- |
| `PeEditor.exe` | LL本体生成器 |
| `PreLoader.dll` | LL预加载文件 |
| `PreLoaderConfig.json` | 预加载配置文件 |
| `allowlist.json` | 白名单列表(没开的情况下没有用) |
| `bdsdown.exe` | BDS下载器 |
| `bedrock_runtime_data` | BDS运行时数据 |
| `bedrock_server_mod.exe` | LLBDS本体 |
| `config.json` | 多维度插件配置文件 |
| `packet-statistics.txt` | 数据包发送统计 |
| `permissions.json` | 玩家权限配置文件 |
| `profanity_filter.wlist` | 敏感词汇配置文件 |
| `server.properties` | BDS核心配置文件 |