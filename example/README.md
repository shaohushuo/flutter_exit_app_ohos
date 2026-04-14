# flutter_exit_app_ohos 示例应用

本应用演示如何使用 `flutter_exit_app_ohos` 插件。

## 开始使用

这是一个 Flutter 应用程序的起点项目。

### 运行示例

```bash
cd example
flutter run
```

### 功能说明

点击按钮即可调用 `FlutterExitApp.exitApp()` 方法退出应用。

在 OpenHarmony 平台上，应用会通过 `UIAbilityContext.terminateSelf()` 方法优雅地终止。


## 示例

![](./demo.gif)

## 参考资源

如果你是第一次接触 Flutter 项目，可以参考以下资源：

- [教程：编写你的第一个 Flutter 应用](https://docs.flutter.cn/get-started/codelab)
- [示例：实用的 Flutter 代码样本](https://docs.flutter.cn/cookbook)

更多 Flutter 开发教程，请查看 [官方文档](https://docs.flutter.cn/)。
