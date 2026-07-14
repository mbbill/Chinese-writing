# Chinese Writing

`chinese-writing` 是一套中文写作规则。任何包含中文正文的输出都应遵守这些规则。

## 安装

把本仓库地址交给支持 skills 的 AI，并要求它安装：

```text
请安装这个仓库中的 skill：
https://github.com/mbbill/Chinese-writing
```

AI 安装时需要以下信息：

- skill 名称：`chinese-writing`
- skill 目录：仓库根目录
- skill 入口文件：`SKILL.md`
- Codex 界面元数据：`agents/openai.yaml`

AI 应根据当前工具和运行环境选择安装目录及安装方式。安装后，重新启动已有会话以加载 skill。

## 规则

完整规则见 [`SKILL.md`](SKILL.md)。主要要求包括：

- 使用自然、准确、克制的现代中文。
- 直接说明对象、行为、条件、原因和结果。
- 根据证据控制判断强度。
- 说明评价所依据的比较标准。
- 避免商业黑话、宣传式语言、无必要的比喻和拟人化。
- 删除不增加信息的修饰语、铺垫和重复结论。
- 原文有歧义时指出歧义，不补充缺少依据的信息。

skill 会在输出中文正文时自动触发，也可以显式调用 `$chinese-writing`。纯代码、数据或仅包含非中文内容的输出不会触发。
