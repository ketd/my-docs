
到目前为止，您已经了解了 Activity 及其视图和布局。在本篇阅读中，您将更详细地探索 XML、其结构以及如何使用它来设计视图层次结构。

Android 应用程序由 Activity 组成，其中包含用户可以与之交互的 UI 元素。这些 UI 元素具有层次结构；顶部有一个根元素，下面可以有零个或多个子元素。所有的 UI 元素都是 View 类的子类，因此共享一些属性。一种特殊类型的 UI 元素称为视图组，它作为容器来对其他视图进行分组，并影响其他视图在屏幕上的绘制和相互交互。这些视图是从 ViewGroup 类继承而来的。

创建 Activity 后，您将其作为布局资源传递，该资源将在屏幕上呈现。这个布局资源是一个 XML 文件。XML 是用于存储结构化信息的文件；在这种情况下，是关于 Android 操作系统如何在屏幕上绘制视图的结构化信息。XML 文档具有层次结构，这使它们成为在 Android 中表示嵌套 UI 元素的理想媒介。

![[Pasted image 20231117153625.png]]
在 XML 布局的根部是一个视图组，它可以包含视图或其他视图组，而这些视图组又可以包含视图和视图组。这就像一棵有分支的树，每个分支可以有其他分支，也可以以叶子结束。有时，一个布局也可以只包含一个单独的视图。

视图组的例子包括：<span style="background:rgba(205, 244, 105, 0.55)">LinearLayout</span>、<span style="background:rgba(205, 244, 105, 0.55)">RelativeLayout </span>和<span style="background:rgba(205, 244, 105, 0.55)"> FrameLayout</span>；视图的例子包括 <span style="background:rgba(205, 244, 105, 0.55)">TextView</span>、<span style="background:rgba(205, 244, 105, 0.55)">Button</span>、<span style="background:rgba(205, 244, 105, 0.55)">ImageView</span> 和<span style="background:rgba(205, 244, 105, 0.55)"> ProgressBar</span>。每个视图组都有不同的行为和定位子视图的方式，因此具有不同的用途。

每个视图或视图组都有一些属性，您可以调整这些属性以实现您对 Little Lemon 应用程序的期望外观和感觉。其中一些属性是它们共享的。例如，所有视图和视图组都有 <span style="background:rgba(205, 244, 105, 0.55)">layout_height</span> 和 <span style="background:rgba(205, 244, 105, 0.55)">layout_width</span> 属性；这是您告诉 Android 操作系统您希望 UI 元素的大小是多大或多小的方式。其他一些属性对于特定的视图是不寻常的。例如，只有 ImageView 有一个 src 属性，这是告诉它要显示哪个图像的方式。当一个视图位于特定的视图组中时，它可以访问视图组的一些属性，以告诉视图组如何定位它。例如，RelativeLayout 中的一个 TextView 可以有一个 layout_centerInParent = true，这告诉 RelativeLayout 在水平和垂直方向上将 TextView 居中。
让我们通过一些代码示例来探索一下。这是一个 XML 布局：


![[Pasted image 20231117153810.png]]


第一行指示 Android Studio 如何解释 XML 文件中的字符。然后是视图组，这里是一个 LinearLayout。第 3 行和第 4 行都指示操作系统将此视图组绘制为填充其父级，即手机的宽度和高度。第 5 行和第 6 行表示此视图组的子项应该在彼此下方并居中显示。

视图组内有两个视图：一个 ImageView 和一个 TextView。它们都有一个 wrap_content 属性，意味着它们的宽度和高度将根据其内容确定。这是视图告诉视图组“我的大小应该是我显示的内容的大小”。例如，如果您增加或减少 TextView 显示的文本，TextView 的大小也会相应增加或减小。

就像 ImageView 有一个 src 属性来显示它应该显示的图像一样，TextView 也有一个 text 属性来显示它应该显示的文本。这些属性是特定于每个视图的；例如，如果您将 src 属性传递给 TextView，它将被忽略。

Android Studio 提供了一种在编写 XML 布局时预览的方法。因此，如果您预览上面的指令，右侧显示 UI 的蓝图，左侧显示用户运行应用程序时看到的内容。