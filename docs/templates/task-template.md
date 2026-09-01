---
id: T-NNN
title:
status: intake        # intake | ready | implemented | reviewed | done | blocked | cancelled
level: normal         # normal-lite | normal | major（trivial 不建任务书）
rfc: RFC-NNN@vN       # 所依据的已批 RFC 及版本（normal-lite 及以上必填）
prd: PRD-NNN@vN       # 涉及需求变化时填写
base_sha:             # 派工时的 HEAD（编排者填）
commit:               # 完成提交 SHA（收尾时填）
agent:                # 实现者 model / CLI 版本
session:              # 派工会话 id（无法获取时填 none 并在评审记录说明）
updated: YYYY-MM-DD
---

# T-NNN：<标题>

## 背景与上游文档

指向 PRD / RFC 的具体章节，不复述内容。

## 范围

改哪些模块 / 文件、做到什么程度。

## 禁区

不许碰的文件、不许变的行为。

## 验收场景

- Given … When … Then …

## 验证方式

跑什么命令、看到什么输出算通过。

## 实现报告（实现者回写）

- 改动清单：
- 实现期假设 / 决策：
- 验证结果（附测试输出摘要）：

## 人工闸门记录（编排者回写）

判级确认 / 敏感动作签核 / 临时联网 / major 人工复核——每条记：事项、批准人、日期、结论。

- （无则写"本任务无人工闸门事项"）

## 评审记录（评审者回写）

- R1（YYYY-MM-DD，base_sha: …）：通过 / 返工（问题清单）/ 升级给人
