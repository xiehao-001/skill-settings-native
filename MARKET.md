# 技能启停设置（@chatecnu-work/dsh-skill-settings-native）

> 在 Host 侧持久保存技能启停偏好，未打开工作区时也可读取。
>
> Host-owned durable skill enable/disable preferences available before any workspace opens.

## 功能

只注册一次设置命名空间，避免每个工作区各自一份偏好；与技能可用性策略插件配套使用效果最佳。

## 安装

```bash
# 在 DSH 中把本目录作为本地 bundle 安装（绝对路径）
```

安装后由 DSH 插件系统加载，条目 id 为 `skill-settings-native`。

## 依赖

- `@deepseek-ai/cordis`
- `@deepseek-ai/dsh-settings`
- `@deepseek-ai/schemastery`

## 兼容性

- `engines.dsh`: `>=0.2.1 <0.3.0`
- 与 EduWork 发行版同源，来源于 ECNU/EduWork 仓库。

## 许可

MulanPSL-2.0 AND MIT（与上游 EduWork 一致）。
