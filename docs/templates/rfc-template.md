---
id: RFC-NNN
title:
status: draft         # draft | in-review | approved | superseded
version: 1
approvers: []         # 人签 approved 时填（主研发）；以承载该版本的 git 提交为批准基线
approved_version:     # 人签 approved 时固定的版本号
prd: PRD-NNN@vN
feishu:
updated: YYYY-MM-DD
---

# RFC-NNN：<标题>

## 背景

对应哪份 PRD、要解决什么问题。

## 方案概述

一段话讲清怎么做。

## 详细设计

模块划分 / 数据结构 / 接口 / 关键时序。讲得清比写得全重要。

## 非功能要求

性能、安全、可观测性、可运维性；没有就写"无特殊要求"，不许留空。

## 验收场景

继承并细化 PRD 的场景，作为测试与符合性评审的依据。

- Given … When … Then …

## 备选方案与取舍

认真考虑过什么、为什么不选。

## 附录：实现决策回写（非规范性）

实现期由代理追加，格式：`YYYY-MM-DD [角色] 决定 + 理由`。
本节**不得与已批准正文冲突**：若决定改变正文语义，必须走升版重批（version+1，退回 in-review），不得写在这里了事。
