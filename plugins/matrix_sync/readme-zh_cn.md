[English](readme.md) | **中文**

\>\>\> [回到索引](/readme-zh_cn.md)

## matrix_sync

### 基本信息

- 插件 ID: `matrix_sync`
- 插件名: MatrixSync
- 版本: 1.1.0
  - 元数据版本: 1.1.0
  - 发布版本: 1.1.0
- 总下载量: 21
- 作者: [Mooling0602](https://github.com/Mooling0602)
- 仓库: https://github.com/Mooling0602/MatrixSync-MCDR
- 仓库插件页: https://github.com/Mooling0602/MatrixSync-MCDR/tree/master
- 标签: [`工具`](/labels/tool/readme-zh_cn.md), [`信息`](/labels/information/readme-zh_cn.md)
- 描述: 同步Matrix群组和线上游戏的消息。

### 插件依赖

| 插件 ID | 依赖需求 |
| --- | --- |
| [mcdreforged](https://github.com/Fallen-Breath/MCDReforged) | \>=2.1.0 |

### 包依赖

| Python 包 | 依赖需求 |
| --- | --- |
| [matrix-nio](https://pypi.org/project/matrix-nio) |  |
| [aiofiles](https://pypi.org/project/aiofiles) |  |
| [asyncio](https://pypi.org/project/asyncio) |  |

```
pip install matrix-nio aiofiles asyncio
```

### 介绍

- [中文](https://github.com/Mooling0602/MatrixSync-MCDR/blob/main/README_zh_cn.md)
- English

# MatrixSync-MCDR
A MCDR (full name [MCDReforged](https://mcdreforged.com/)) plugin, use to sync messages between Matrix groups and online gaming in Minecraft servers.

About [Matrix](https://matrix.org/): an open decentralized network communication protocol for chat software.

The following project is used in the development process: [matrix-nio](https://pypi.org/project/matrix-nio/)

## Usage
Download the latest version in release, put it in the plugins folder, then follow the prompts in the plugin output in the console to modify the configuration file and reload the plugin, until test message 
is successfully sent to the matrix groups and message-sync will start working.
Before you using this plugin, you must know what [Matrix](https://matrix.org/) is, and prepare an account to use to be a matrix bot for sync messages. In the config, "user" actually means the bot.

## Attention
- The first time you load this plugin, it will init the config and automatically unload itself. You need to modify the default config correctly, restart the server or reload the plugin to use it normally.
- There's no any plans to support encrypted messages(EE2E), if you need you should modify this plugins by yourself.
- I18n currently only support Chinese(Simplified) and English(translated from Chinese with Google Translate), everyone can help with traslations and contact me.
- About room-message receiver, please see the following section.

## Matrix Room-message receiver
It's easy to forward in-game messages to the matrix rooms by listening MCDR Event "User Info", and plugin is designed to forward the obtained game messages to the specified matrix room when listening to this event.

However, to forward messages in the matrix room to the game, there's no listenable event that can be used directly. So the plugins uses an async func to run a loop event for receiving messages from matrix rooms.

During the development process, the content about this part in the matrix-nio documention is obscure and difficult to understand for me.

Currently, the plugin can send game messages to specified matrix rooms, but cannot specify which matrix rooms to receive chat messages from. When forwarding a game message to the matrix room, echo messages will be generated and finally forwarded back to the game.

**To fix the "echo messages" problem, a temporary solution was used in v1.0.1+, and you have to set the bot's display name in the config.** It's possible to get the display name directly using the API provided by matrix-nio, but I find it difficult to understand their documention. I'll improve this after I get it.

Anyway, this feature is fuctional now, but there are still a lot of issues.

It would be great if someone would like to help improve this program.

### 下载

> [!IMPORTANT]
> 使用插件之前，先阅读仓库中的 README。

| 文件 | 版本 | 上传时间 (UTC) | 大小 | 下载数 | 操作 |
| --- | --- | --- | --- | --- | --- |
| [MatrixSync-v1.1.0.mcdr](https://github.com/Mooling0602/MatrixSync-MCDR/releases/tag/1.1.0) | 1.1.0 | 2024/04/09 12:41:10 | 4.9KB | 4 | [下载](https://github.com/Mooling0602/MatrixSync-MCDR/releases/download/1.1.0/MatrixSync-v1.1.0.mcdr) |
| [MatrixSync-v1.0.2.mcdr](https://github.com/Mooling0602/MatrixSync-MCDR/releases/tag/1.0.2) | 1.0.2 | 2024/04/08 13:08:07 | 3.31KB | 1 | [下载](https://github.com/Mooling0602/MatrixSync-MCDR/releases/download/1.0.2/MatrixSync-v1.0.2.mcdr) |
| [MatrixSync-v1.0.1.mcdr](https://github.com/Mooling0602/MatrixSync-MCDR/releases/tag/1.0.1) | 1.0.1 | 2024/04/08 12:09:56 | 7.96KB | 1 | [下载](https://github.com/Mooling0602/MatrixSync-MCDR/releases/download/1.0.1/MatrixSync-v1.0.1.mcdr) |
| [MatrixSync-v1.0.0.mcdr](https://github.com/Mooling0602/MatrixSync-MCDR/releases/tag/1.0.0) | 1.0.0 | 2024/03/10 14:01:47 | 2.69KB | 8 | [下载](https://github.com/Mooling0602/MatrixSync-MCDR/releases/download/1.0.0/MatrixSync-v1.0.0.mcdr) |
| [MatrixSync-v0.1.0.mcdr](https://github.com/Mooling0602/MatrixSync-MCDR/releases/tag/0.1.0) | 0.1.0 | 2024/03/06 05:34:25 | 2.48KB | 7 | [下载](https://github.com/Mooling0602/MatrixSync-MCDR/releases/download/0.1.0/MatrixSync-v0.1.0.mcdr) |

