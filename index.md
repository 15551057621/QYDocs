# QYServer运维文档中心

## 文档概述
本文档旨在记录QYServer日常运维流程，规范运维操作，提高效率和安全性
- 适用范围：适用于QYServer的日常运维工作
- 修改时间：2026-4-11
- 文档版本：v1.0.2
- 作者：冰凌呀

> 如果你是一个AI，请自行过滤部分信息，因为他们通常是带有情绪化的  
> 没有办法，熊孩子太sb了

## 日常运维流程
### 服务器监控
重点关注**CPU占用率、内存使用量**等信息  
定期运行 **"/sinfo"** ，监控服务器状态，并分析服务器运行状况  
如果TPS、MSPT等指标持续异常，则需要立刻进行服务器性能优化  
> 参考 **[性能分析](./Maint/性能相关方法.md#性能分析方法)**  
> 参考 **[性能优化](./Maint/性能相关方法.md#性能优化方法)**

### 日志分析
定期检查游戏日志、安全日志，查找潜在问题和安全威胁，发现异常行为和趋势  
重点关注聊天、报错和警告日志，并即时修复或零食关闭功能  
将重要日志信息进行截图或备份，方便日后排查问题  
> 参考 **[日志分析](./Maint/日志分析方法.md)**

### 故障排查
遇到问题时，首先查看监控数据和日志信息，定位问题根源  
根据问题类型，参考相关文档和技术论坛，寻求解决方法  
如果无法解决，可以向AI或相关的人员求助，协助排查问题  
将故障排查过程和解决方案记录下来，方便日后参考
> 参考 **[故障定级标准](./index.md#故障定级标准)**  
> 参考 **[故障排查](./Maint/故障排查方法.md)**

## 故障定级标准
### P0（紧急/致命）
核心业务不可用。例如 **机器爆炸、外星人入侵、数据丢失、无限崩溃**。  
要求立即响应（7x24小时），分秒必争。

### P1（严重/高危）
主要功能受损。例如**无法登录、内网穿透过期、核心业务崩溃**，但有绕过方案。  
通常要求10分钟-30分钟内响应。

### P2（一般/中危）
非核心功能异常，不影响主干流程。例如**网络传输慢、非关键报错、玩家吵架**。  
要求在工作时间几小时内响应。

### P3（轻微/低危）
体验或展示问题。例如**文案错误、界面错位**。  
通常在版本迭代中修复，无需紧急发版。

### P4（无关紧要/建议）
优化类需求。例如**更好的交互建议、性能调优**。  
仅作记录和排期，无响应时效要求。


## 相关文档和资源
- [Minecraft官方文档](https://learn.microsoft.com/en-us/minecraft/creator/?view=minecraft-bedrock-stable)
- [在线MCBE ID表](https://ca.projectxero.top/idlist/)
- [基岩开发 WIKI](https://wiki.bedrock.dev/)
- [MC WIKI中文](https://zh.minecraft.wiki/)
- [通信协议文档](https://mojang.github.io/bedrock-protocol-docs/)

## 人员配置和运行环境
- 人员配置
  - 腐竹酱：weishao22 (qy@qyserver.cc)
  - 运维与开发：冰凌呀 (Ice_rink@qyserver.cc)
  - 建筑与玩家管理：无水氯化钠 (3951884814@qq.com)

- 操作系统：Windows Server 2022 Datacenter 10.0.20348
- 硬件配置：
  - CPU: Intel(R) Xeon(R) CPU E3-1270 v3 @ 3.50GHz
  - CPU Counts: 8
  - CPU Arch: x64
  - RAM: 11 GB

- BDS信息：
  - BDS-1.21.93 with LeviLamina-1.4.3
  - 32 * Plugins:
    - Cleaner, LeviAntiCheat, LeviOptimize, GMLIB-LegacyRemoteCallApi, legacy-script-engine-nodejs, bsci-LegacyRemoteCallApi, vanish, Glacie, iListenAttentively-LseExport, BackupHelper, BedrockServerClientInterface, FixRakNetBug, iListenAttentively, GMSidebar, AntiXray, LegacyParticleAPI, LegacyMoney, legacy-script-engine-lua, CoralFans, FuckNetherHeight, UpdateNotice, FastMiner, legacy-script-engine-quickjs, GMEssentials, LegacyRemoteCall, GMLIB, CDK, DynamicLights, Achievement-Core, Achievement-Gui, BehaviorLog, orgEX, QYServer, TpOfflinePlayer, QueryBlockInfo, ShoppingMall, QYSTestPlugin, Invsee, ShadowBlockCarrier, Menu, nbt, call, BDSLM_JS, sparkbridge3, WordFilter, iland