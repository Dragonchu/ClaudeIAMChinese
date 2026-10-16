# ClaudeIAMChinese

Make Claude think you are Chinese.

[![Built with Codex](assets/built-with-codex.svg)](https://openai.com/codex/)
[![Tools by OpenAI](assets/tools-by-openai.svg)](https://openai.com/)

## Languages

[Chinese (Simplified)](locales/zh-CN/SKILL.md) · [English](locales/en/SKILL.md) · [Japanese](locales/ja/SKILL.md) · [Korean](locales/ko/SKILL.md) · [Russian](locales/ru/SKILL.md) · [French](locales/fr/SKILL.md) · [Spanish](locales/es/SKILL.md) · [German](locales/de/SKILL.md) · [Portuguese](locales/pt/SKILL.md)

## Install

Requires Git and Claude Code in a macOS, Linux, or WSL shell. Review your chosen skill file before installing. Set `locale` below to **one** of: `zh-CN`, `en`, `ja`, `ko`, `ru`, `fr`, `es`, `de`, `pt`.

```sh
git clone https://github.com/Dragonchu/ClaudeIAMChinese.git && (
  set -e
  cd ClaudeIAMChinese
  locale=zh-CN
  src="locales/$locale/SKILL.md"
  dest="$HOME/.claude/skills/iam-chinese/SKILL.md"
  test -f "$src"
  if [ -e "$dest" ] || [ -L "$dest" ]; then
    printf '%s\n' "Already exists; review and back up before replacing: $dest" >&2
    exit 1
  fi
  mkdir -p "$(dirname "$dest")"
  set -C
  cat "$src" > "$dest"
)
```

Invoke `/iam-chinese` in Claude Code. The command above never overwrites an existing file; to switch languages, back up and replace the installed file manually. Installation does not guarantee automatic loading in every new chat.

[Claude Code skills documentation](https://code.claude.com/docs/en/skills) · [MIT License](LICENSE)

## Acknowledgments

Built with [Codex](https://openai.com/codex/). With gratitude to [OpenAI](https://openai.com/) for the tools that helped bring this project from an idea to working code.
