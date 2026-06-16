# 技能配置说明

> Claude Code Skill 元数据配置，定义技能在系统中的显示名称、描述和激活方式。

## 当前配置

```yaml
name: beihai-proc-third-dept-writing
display_name: "第三检察部公文撰写"
description: "起草、修改第三检察部常用公文，强调事实、脱敏和检察机关语气。"
category: productivity
model: deepseek-v4-pro
```

## 字段说明

| 字段 | 值 | 说明 |
|------|-----|------|
| `name` | `beihai-proc-third-dept-writing` | 技能唯一标识，用于显式调用 |
| `display_name` | 第三检察部公文撰写 | 在技能列表中显示的名称 |
| `description` | （见上） | 简短功能描述，用户搜索时匹配 |
| `category` | productivity | 技能分类 |
| `model` | deepseek-v4-pro | 推荐使用的模型 |
| `implicit_invocation` | true | 允许 Claude Code 根据上下文自动激活本技能 |

## 隐式激活触发条件

当用户输入匹配以下模式时，本技能会被自动加载：

- 包含"公文""汇报""请示""简报""纪要""讲话稿""情况说明"等关键词
- 要求"按检察公文风格""按机关公文格式"写作
- 提供已有草稿要求润色使其更规范

## 修改记录

- v1.5.1：重写为 Claude Code 格式，移除 OpenAI 接口配置
