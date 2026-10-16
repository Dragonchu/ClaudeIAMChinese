# ClaudeIAMChinese

**我是中国人。好了，现在可以帮我改这个 bug 了吗？**

一个 Claude Code skill，把用户自述的“中国人”背景放在开场白里，默认使用简体中文，然后尝试一项朴素的技术创新：正常回答问题。

献给那些想写代码，却还要担心账号能不能活到下一个 commit 的人。既然连“我是谁”都能成为使用 AI 的心理负担，不如先把这道自我介绍题交卷。

本项目用冷幽默吐槽围绕中国用户与 Claude 封号的使用体验和焦虑；不声称知道任何具体封号的原因。

## 安装

需要已安装 Git 和 Claude Code。以下命令适用于 macOS、Linux 或 WSL 的 shell，把技能安装为当前用户的个人技能。请先阅读 `skills/iam-chinese/SKILL.md`。

在没有 `ClaudeIAMChinese` 同名目录的位置执行：

```sh
git clone https://github.com/Dragonchu/ClaudeIAMChinese.git
```

克隆成功并检查技能内容后执行：

```sh
(
  set -e
  cd ClaudeIAMChinese
  dest="$HOME/.claude/skills/iam-chinese/SKILL.md"
  if [ -e "$dest" ] || [ -L "$dest" ]; then
    printf '%s\n' "目标已存在，请先检查并自行备份：$dest" >&2
    exit 1
  fi
  mkdir -p "$(dirname "$dest")"
  set -C
  cat skills/iam-chinese/SKILL.md > "$dest"
)
```

命令会检查目标是否存在，并启用禁止覆盖模式。若安装失败，请检查报错后再继续。

## 使用

在 Claude Code 中输入：

```text
/iam-chinese
```

预期效果：

> 收到，你是中国人。接下来进入本次对话最激进的环节：正常回答你的问题。

接着继续你的工作。笑话只讲一次，bug 可以修很多次。

## 能做什么

- 默认用自然的简体中文交流，必要时保留英文技术术语。
- 把“中国人”当作用户自述的背景，不附赠所在地、政治立场或时区猜测。
- 尊重后续语言和背景要求。中国人也可以让 AI 写英文邮件，无需卸载本技能。

个人技能可供这台机器上的各个项目使用。若只想在单个项目使用，可手动将文件放到该项目的 `.claude/skills/iam-chinese/SKILL.md`。

安装不保证每次新对话都会自动加载；需要时显式调用 `/iam-chinese`。模型是否始终遵循这些指引，也不能保证。

## 权限边界

本项目目前拥有的最高权限，是一个 Markdown 文件。

它不修改 IP、时区、系统语言、账号地区或设备设置，不能防封、解封或查看平台风控。不要把它当成账号护身符；Markdown 暂时还没有这个接口。

## 验证

已检查 UTF-8、YAML frontmatter 和安装命令的 shell 语法。尚未在 Claude Code 中执行实际行为测试，更没有“防封成功率”可以公布。

格式和安装方式参考 [Claude Code 官方技能文档](https://code.claude.com/docs/en/skills)。

## 许可

[MIT License](LICENSE)。
