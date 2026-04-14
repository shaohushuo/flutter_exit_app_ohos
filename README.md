# flutter_exit_app_ohos

[![Pub Version](https://img.shields.io/pub/v/flutter_exit_app_ohos.svg)](https://pub.flutter-io.cn/packages/flutter_exit_app_ohos)

**flutter_exit_app 的鸿蒙（OpenHarmony）化实现**

这是 [flutter_exit_app](https://pub.dev/packages/flutter_exit_app) 插件的鸿蒙化适配版本，为 OpenHarmony 平台提供应用退出功能。

## 功能介绍

该插件在 OpenHarmony 平台上实现了应用退出功能，通过调用 `UIAbilityContext.terminateSelf()` 方法优雅地终止应用。

## 使用方法

### 安装

在 `pubspec.yaml` 中添加依赖：

```yaml
dependencies:
  flutter_exit_app: ^2.1.1        # 原插件，提供 API 接口
  flutter_exit_app_ohos: ^2.1.1   # 鸿蒙化实现
```

### 示例代码

```dart
import 'package:flutter_exit_app/flutter_exit_app.dart';

// 退出应用
await FlutterExitApp.exitApp();

// 获取平台版本（用于测试）
// final platformVersion = await FlutterExitApp.platformVersion;
```

**注意**：调用代码与原插件完全一致，无需修改现有代码。

## 示例

[](./example/demo.gif)

## 技术实现

### 鸿蒙端实现

鸿蒙端的实现基于 `@ohos/flutter_ohos` Flutter Plugin API，主要涉及：

- `FlutterPlugin`：插件主接口
- `MethodCallHandler`：处理方法调用
- `AbilityAware`：感知 Ability 生命周期
- `common.UIAbilityContext`：获取 Ability 上下文用于调用 `terminateSelf()`

### Method Channel

插件使用名为 `flutter_exit_app` 的 Method Channel 进行 Dart 与鸿蒙原生代码的通信，与原插件保持一致。

支持的方法：

| 方法名 | 说明 |
|--------|------|
| `getPlatformVersion` | 获取平台版本信息 |
| `com.laoitdev.exit.app` | 退出应用 |

## 注意事项

1. 在鸿蒙平台上，应用退出通过 `UIAbilityContext.terminateSelf()` 实现
2. 确保在合适的用户交互场景下调用退出功能（如用户确认退出时）
3. 频繁或不当的退出调用可能影响用户体验


