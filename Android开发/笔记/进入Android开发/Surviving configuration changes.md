## 概述
到目前为止，您已经了解了什么是状态。您还学习了如何在组合之间保持状态。在本篇阅读中，您将了解配置更改以及它们导致的状态丢失。然后，您将学习如何在配置更改中保持状态。完成本篇阅读后，您应该能够开发能够在配置更改中存活的应用程序。

## 状态丢失

### 设备配置
在应用程序的生命周期中，设备的某些属性可能会发生变化。这些包括设备方向、语言、主题更改以及启用多窗口模式等。在 Android 世界中，这些变化被称为配置更改。

### 活动重建
当发生配置更改时，正在运行的活动将被重新启动，这意味着它将被销毁并重新创建。当这种情况发生时，活动中保存的任何实例数据都会丢失。即使使用 remember 保存的数据也会丢失。

这意味着什么？这意味着所有视图状态都会丢失。重新创建后，活动将返回到初始状态。这是默认行为。

配置更改并不是活动可能重新创建的唯一情况。当设备的内存不足时，它可能选择销毁一个活动，直到再次需要时才重新创建。这也会导致之前提到的状态丢失。

### 存活的活动重建
如果您想要在配置更改中保持状态，该怎么办？Compose 为大多数情况提供了一个简单的解决方案。

当您希望您的 UI 状态在配置更改中保持时，您可以使用 rememberSaveable 而不是 remember。RememberSaveable 和 remember 一样负责保存状态。不过，与 remember 不同的是，它还可以在配置更改中保存状态。


### RememberSaveable 的限制
大部分情况下，rememberSaveable 很容易使用。你只需将状态包装起来，它就会被持久化。如果你的数据是可以保存在 Android Bundle 中的数据类型之一，那么你的工作就完成了。然而，如果你想存储更复杂的数据，你就需要更加努力一些。
将一个更复杂的类转换为可以保存在 Bundle 中的类的一种方法是使其实现 Parcelable 接口。Parcelable 接口适用于可以写入和读取 Parcel 的类。而 Parcel 则是可以保存在 Bundle 中的容器。[kotlin-parcelize](https://developer.android.com/kotlin/parcelize) 是一个 Android 插件，可以让你轻松地使你的类符合 Parcelable 接口。
如果 Parcel 不适用于你的情况，你可以使用 [mapSaver](https://developer.android.com/jetpack/compose/state#mapsaver)或[listSaver](https://developer.android.com/jetpack/compose/state#listsaver) 将数据结构显式转换为 Map 或 List。这两者都需要你提供两个 lambda 函数：一个用于将数据转换为相关的集合类型，另一个用于将该集合转换回原始数据类型。
### 总结思考
通过本文，你了解了配置更改。你还了解了 Activity 的重建及其影响。最后，你学会了如何通过使用 rememberSaveable 来应对 Activity 的重建。作为一名 Android 开发者，知道如何应对配置更改对你的工作至关重要，因为几乎所有现代应用都要求能够在 Activity 重建时保持正常运行。