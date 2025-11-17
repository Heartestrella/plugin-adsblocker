# nonebot_plugin_adsblocker

简单、轻量的 NoneBot 插件，用于检测并阻断群聊/私聊中的广告类消息。提供可配置的匹配规则、白名单与日志通知，适合在机器人里做基础的广告拦截与记录。

## 功能亮点

- 基于DeepSeek的违规消息检测
- 支持白名单（用户 / 群 / 频道）
- 可选的拦截通知与日志上报
- 简单的配置项，易于扩展与二次开发

## 适用场景

- 群聊中屏蔽常见广告、钓鱼链接或垃圾推送
- 私聊中自动撤回疑似广告内容并记录
- 作为更复杂审核系统的第一道过滤
- 检测二维码内容
## 兼容性

- 适用于 NoneBot2

## 安装

从 PyPI（如有）：
```bash
pip install nonebot-plugin-adsblocker
```

从 GitHub 仓库安装（开发/最新版）：
```bash
pip install git+https://github.com/Heartestrella/nonebot_plugin_adsblocker.git
```

或者把仓库作为子模块/源码放入你的项目中并在运行环境中安装依赖：
```bash
git clone https://github.com/Heartestrella/nonebot_plugin_adsblocker.git
cd nonebot_plugin_adsblocker
pip install -r requirements.txt
pip install -e .
```

## 快速使用

在 NoneBot 项目中加载本插件（示例）：

在启动脚本或 bot 初始化处：
```python
import nonebot

nonebot.init()
# 方式一：通过插件名加载
nonebot.load_plugin("nonebot_plugin_adsblocker")
# 方式二：如果根据项目结构，直接指定模块路径
nonebot.load_plugins("src/plugins")  # 若插件位于此路径
app = nonebot.get_asgi()
```

# 启动后，请通过指令/set_apikey sk-xxx 配置DeepSeek API


## 行为示例

- 当检测到消息被ds检测为广告时：
  - 向配置的超级管理员发送提醒信息 群内发送设置的提示词
  - <img width="955" height="454" alt="image" src="https://github.com/user-attachments/assets/6c34bccb-f155-4a00-b797-5f1ced87fa6d" />

  - <img width="963" height="273" alt="image" src="https://github.com/user-attachments/assets/7609370d-f94f-4965-bd6a-c456a41e4873" />



## 权限与注意事项

- 插件若需删除/撤回消息或查看群信息，需要给Bot群内管理员权限。

## 开发与调试

本仓库包含基本的开发流程建议：

- 克隆仓库并安装开发依赖：
```bash
git clone https://github.com/Heartestrella/nonebot_plugin_adsblocker.git
cd nonebot_plugin_adsblocker
pip install -r dev-requirements.txt
```

- 修改规则后，可在测试群/测试账号中验证效果，观察日志并调整正则或关键字。

- 请在提交 PR 前运行代码格式化、静态检查并补充必要测试（如有测试框架）。

## 贡献

欢迎提交 issue 或 PR。如果你要贡献：

1. 先开 issue 描述你的想法或问题
2. 基于最新主干创建分支并提交变更
3. 提交 PR，并在 PR 描述中说明变更目的与影响范围

## 许可证

请参见仓库根目录的 LICENSE 文件获取准确的授权信息。

## 联系方式

若有问题或建议，可以通过 issue 提交，或联系仓库维护者（见 GitHub 仓库主页）。

----
以上为基础 README 模板。若希望我把字段名和示例配置严格对齐到仓库现有实现（例如具体的配置项名称、日志接口、管理命令等），请把仓库中的配置/代码片段发给我，我会把文档调整为精确可用的版本。
