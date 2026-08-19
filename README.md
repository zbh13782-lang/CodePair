# CodePair

个人维护的 AI 编程 Skills 仓库。

以后创建新项目时，可以直接从这里复制需要的 Skill，避免重复编写规则和提示词。

## 现有 Skills

| Skill | 用途 |
| --- | --- |
| `ai-pair-programmer` | 编写代码、修复 Bug、重构和补充测试 |
| `code-tutor` | 梳理项目架构、业务流程和代码调用链 |

Skills 位于 `.claude/skills/` 目录。

## 使用方法

在新项目根目录执行：

```bash
git clone --depth 1 https://github.com/zbh13782-lang/CodePair.git /tmp/CodePair
mkdir -p .claude/skills
cp -R /tmp/CodePair/.claude/skills/. .claude/skills/
rm -rf /tmp/CodePair
```

只复制单个 Skill：

```bash
git clone --depth 1 https://github.com/zbh13782-lang/CodePair.git /tmp/CodePair
mkdir -p .claude/skills
cp -R /tmp/CodePair/.claude/skills/ai-pair-programmer .claude/skills/
rm -rf /tmp/CodePair
```

## 目录结构

```text
.claude/skills/
├── ai-pair-programmer/
│   ├── SKILL.md
│   └── references/
└── code-tutor/
    ├── SKILL.md
    └── references/
```

新增 Skill 时，在 `.claude/skills/<skill-name>/` 下创建 `SKILL.md`；相关规范和模板放在同目录的 `references/` 中。

> `CLAUDE.md` 是通用协作规则。复制到其他项目时，建议与原有内容合并，不要直接覆盖。
