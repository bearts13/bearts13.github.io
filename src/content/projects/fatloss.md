---
title: "fatloss"
published: 2026-08-01T10:00:00+08:00
draft: false
order: 90
description: "Flutter 写的减肥记录 App：用对话的方式记饮食和运动，自动算热量与营养，首页是数据看板，体重单独跟踪。"
image: "/assets/img/projects/fatloss-poster-wide.png"
status: "developing"
tags:
  - Flutter
  - Android
  - AI
  - 健康
link: []
---

## 这是什么

一个把「记饮食 / 记运动」这件麻烦事变得不麻烦的 App。核心思路是**对话式记录**：不用在表单里一项项选，直接说话或打字，AI 负责把它拆成结构化的餐食与运动数据。

## 主要功能

- **AI 对话记录**：一句话搞定一餐，自动解析出食物与热量
- **数据看板**：按天展示热量、营养、运动完成度的环形图
- **体重独立跟踪**：体重变化单独成页，整体状态一眼可见
- **历史与对话合并**：回看记录和继续对话在同一个地方
- **详细设置**：AI API 配置、用户档案、详细设置与历史记录分层放置，含颜色主题与暗色模式

## 技术栈

Flutter + Dart + SQLite 本地存储，接入小米 MIMO 2.5 做对话解析（需自行配置 API Key）。

## 当前状态

v1.1.0（build 18）正在社区内测试，APK 通过蓝奏云分发、GitHub Releases 备份。安卓端收尾中，之后会考虑 iOS。
