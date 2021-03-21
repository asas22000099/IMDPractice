# Flutter调研

#### 1813094 许诺

## 简介

Flutter 是 Google 开源的 UI 工具包，帮助开发者通过一套代码库高效构建多平台精美应用，支持移动、Web、桌面和嵌入式平台。

Flutter 通过 **热重载** 提供快速开发周期，该功能支持应用程序在运行状态下重载代码而无需重新启动应用程序或者丢失程序运行状态。

## 编写一个Flutter应用

* 如果想要编译在WEB上应用的程序，需要先开启WEB支持。也可以给已有应用添加WEB支持。

* 第一次进行真机调试可能需要较长时间，时候可以采取热加载；使用命令行可以直接输入 **r** 进入热加载

* Flutter 提供了丰富的 Material 风格的 widgets，在 Flutter 中，几乎所有都是 widget，包括对齐 (alignment)、填充 (padding) 和布局 (layout)

* 有很多的外部开源软件包可以使用

* 应用在调试模式下意味着在更大的性能开销笑实现了更快的开发速率，比图热重载功能的启用，因此动画效果较差，当要分析应用性能或进行发布时，应该使用profile或者release构建

## 用户界面

### Widget介绍

* Flutter的核心思想是用widget构建UI界面，widget描述了在当前配置和状态下视图应该呈现的样子，状态改变就会重新构建，框架则会对比前后变化的不同，以确定底层渲染树从一个状态转换到下一个状态所需的最小更改。

* Widget 的主要工作是实现 build方法，该方法根据其它较低级别的 widget 来描述这个 widget。框架会逐一构建这些 widget，直到最底层的描述 widget 几何形状的 RenderObject。

* Flutter自带一套强大的widget，也提供了许多 widget，可帮助构建遵循 Material Design 的应用。

* 为了获得(MaterialApp)主题的数据，许多 Material Design 的 widget 需要在 MaterialApp 中才能显现正常。

* 在 StatefulWidget 上调用 createState() 之后，框架将新的状态对象插入到树中，然后在状态对象上调用 initState()，可以重写 initState 来完成只需要发生一次的工作；完成之后可以调用状态对象上的 dispose() 方法。可以重写dispose 方法来清理状态。

* 使用 key 可以控制框架在 widget 重建时与哪些其他 widget 进行匹配，要求两个 widget 具有相同的 key 和 runtimeType
全局 key 可以用来标识唯一子 widget。全局 key 在整个 widget 结构中必须是全局唯一的，而不像本地 key 只需要在兄弟 widget 中唯一。由于它们是全局唯一的，因此可以使用全局 key 来检索与 widget 关联的状态。

### 布局构建

* Widgets 是用于构建 UI 的类。

* Widgets 可以用于布局和展示 UI 元素。

* 通过组合简单的 widgets 来构建复杂的 widgets

* 使用child或children奖可见widget添加到布局widget

* 通过实现app的build()方法将布局widget添加到页面

* 可以指定 Row 或 Column 如何在垂直和水平方向上对齐其子项。

* 可以拉伸或限制特定的子 widgets，可进行嵌套。

* 可以指定子 widgets 如何占用 Row 或 Column 的可用空间。

* 可通过将 mainAxisSize 设置为 MainAxisSize.min 是的子项紧密组合在一起
