# Chinese Writing

`chinese-writing` 是一套供 Codex 和 Claude Code 使用的中文写作规则。只要输出包含中文正文，就应用这些规则。

## 主要规则

- 使用自然、准确、克制的现代中文。
- 直接说明对象、行为、条件、原因和结果。
- 根据证据控制判断强度，不使用证据无法支持的绝对化表达。
- 说明“更好”“更安全”或“更可靠”等评价的比较标准。
- 避免商业黑话、宣传式语言、无必要的比喻和拟人化。
- 删除不增加信息的修饰语、铺垫和重复结论。
- 原文有歧义时指出歧义，不自行补充缺少依据的信息。

完整规则见 [`SKILL.md`](SKILL.md)。

## 安装

将仓库克隆到本地：

```sh
git clone git@github.com:mbbill/Chinese-writing.git ~/Dev/chinese-writing
```

为 Codex 建立符号链接：

```sh
mkdir -p ~/.codex/skills
ln -s ~/Dev/chinese-writing ~/.codex/skills/chinese-writing
```

为 Claude Code 建立符号链接：

```sh
mkdir -p ~/.claude/skills
ln -s ~/Dev/chinese-writing ~/.claude/skills/chinese-writing
```

如果目标位置已经存在同名文件或目录，请先移动或删除原有内容。重新启动已有会话，使 Codex 或 Claude Code 重新加载 skill。

## 使用

skill 会在输出中文正文时自动触发。也可以显式调用：

```text
$chinese-writing
```

纯代码、数据或仅包含非中文内容的输出不会触发。

## 更新

```sh
git -C ~/Dev/chinese-writing pull
```

Codex 和 Claude Code 通过符号链接读取同一份文件，因此不需要分别复制更新。

## 文件

- `SKILL.md`：触发条件和中文写作规则。
- `agents/openai.yaml`：Codex 使用的界面元数据。
