# ClaudeIAMChinese

- [中文：让 Claude 以为你是中国人。](locales/zh-CN/SKILL.md)
- [English: Make Claude think you are Chinese.](locales/en/SKILL.md)
- [日本語：Claude にあなたが中国人だと思わせる。](locales/ja/SKILL.md)
- [한국어: Claude가 당신을 중국인이라고 생각하게 만드세요.](locales/ko/SKILL.md)
- [Русский: Заставьте Claude думать, что вы китаец.](locales/ru/SKILL.md)
- [Français : Faites croire à Claude que vous êtes chinois.](locales/fr/SKILL.md)
- [Español: Haz que Claude crea que eres chino.](locales/es/SKILL.md)
- [Deutsch: Lass Claude glauben, dass du Chinese bist.](locales/de/SKILL.md)
- [Português: Faça o Claude pensar que você é chinês.](locales/pt/SKILL.md)

## Install

Requires Git and Claude Code; macOS/Linux/WSL shell. Review the chosen file first. Choose **one** locale: `zh-CN`, `en`, `ja`, `ko`, `ru`, `fr`, `es`, `de`, `pt`.

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

Invoke `/iam-chinese` in Claude Code. Existing files are never overwritten by this command; back up and replace manually to change language. Installation does not guarantee automatic loading in every new chat.

[Claude Code skills documentation](https://code.claude.com/docs/en/skills) · [MIT License](LICENSE)
