---
layout: post
title: 'RPM Commands for KDE Linux'
date: 2024-10-13 00:00:00 +1200
categories: linux
tags: linux
---

## List All Installed Packages

```bash
rpm -qa
```

## Find A Package

We can grep the list to find packages by name

```bash
rpm -qa | grep code
```

## Update Package

```
sudo dnf update code
```