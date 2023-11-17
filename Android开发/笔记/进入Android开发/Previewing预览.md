## 介绍
Jetpack Compose Preview 是一个库，允许您快速预览使用 Jetpack Compose UI 工具包构建的 Android 应用程序设计。它使得快速测试和预览设计变得简单。@Preview 注解用于告诉 Jetpack Compose Preview 如何生成您正在工作的组件的预览。

## 安装 Jetpack Compose Preview
为了使用 Jetpack Compose Preview，您必须将库依赖项添加到您的项目中。为此，请将以下代码行添加到您的 app/build. Gradle 文件的 dependencies 部分：
Implementation androidx. Ui: ui-tooling: 0.1.0-dev 13

## 预览您的 UI
当您的项目设置完成后，您可以开始预览您的 UI 元素。为此，请在 Android Studio 工具栏中打开预览选项卡。这将打开 Jetpack Compose Preview 窗口。从这里，您可以选择要预览的布局文件，以及自定义预览的主题、大小和方向。您还可以添加任何其他要预览的组件或视图。

## 进行更改
一旦您对 UI 的布局感到满意，您可以对代码进行更改。为此，请在 Android Studio 工具栏中打开代码选项卡。这将打开 Jetpack Compose 代码编辑器。从这里，您可以对代码进行更改，以自定义 UI 元素的外观。

## 探索@Preview 注解
@Preview 注解用于告诉 Jetpack Compose Preview 如何生成您正在工作的设计的预览。它有三个可选参数：
Name：描述预览的字符串。这用于在预览列表中标识预览。
ShowDecoration：一个布尔值，指示预览中是否应显示装饰。
Group：指示预览所属的组的字符串。这用于在预览列表中对预览进行分组。

## 生成预览
安装 Jetpack Compose Preview 并将@Preview 注解添加到您的设计后，您可以通过在终端中运行以下命令来生成预览：

<span style="background:#affad1">./gradlew composePreview</span>

这将生成您设计的预览并在预览列表中显示出来。

预览也可以在不运行命令的情况下查看，对于那些刚接触 Compose 的人来说，这通常是一个更好的方法。例如，您可以使用 Compose 模板之一创建一个新项目，打开 MainActivity，点击右上角的 Split，然后点击 Build and refresh 以查看预览。

## 结论
Jetpack Compose Preview 是一个快速预览使用 Jetpack Compose 构建的设计的绝佳工具。@Preview 注解用于告诉 Jetpack Compose Preview 如何生成设计的预览。安装后，您可以通过在终端中运行 composePreview 命令来生成预览。