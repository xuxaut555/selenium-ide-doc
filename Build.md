开发测试案例有三个主要的方法：录制、利用上下文菜单添加验证和断言以及编辑和修改测试案例。通常自动化测试工程师应该同时掌握这三种方法。

# 录制

很多新手都是从录制一个与网站交互的测试用例，开始学习自动化测试的。当第一次打开 Selenium IDE 时，录制按钮默认是启动的。如果你不想要 Selenium IDE 自动开始录制，在系统设置中可以关掉。具体操作如下：点击 Options 菜单 > Options… 菜单项，打开系统设置对话框，取消勾选 "Start recording immediately on open."
  
录制期间，Selenium IDE 会根据你的操作自动在测试用例中插入命令。通常，这将包括: 

- 点击一个链接，click 或 clickAndWait 命令 
- 输入值，type 命令
- 从一个下拉列表中选择选项，select 命令
- 点击复选框或单选按钮，click 命令

这里有一些陷阱需要注意：
  
- type 命令需要点击网页的某些区域的才能录制。
- 链接跳转通常录制成 click 命令。你会经常需要把 click 命令改为 clickAndWait，来确保您的测试用例会暂停，直到新页面加载完成。否则，您的测试用例将在页面加载新的 UI 元素之前继续运行命令。这将会导致意想不到的测试用例运行失败。

# 通过上下文菜单添加断言和验证

测试用例通常需要检查网页的属性，这需要用到断言和验证命令。我们不会描述这些命令的细节，在 Selenium 的命令 Selenese 章节中有详细介绍。这里我们会简单地描述如何将它们添加到测试用例中。 　

在 Selenium IDE 录制时，在浏览器显示被测应用程序的页面上右键单击页面上的任何地方。您将看到一个上下文菜单显示验证 和/或 断言命令。

第一次使用 Selenium 时，在右键快捷菜单中 Selenium 能只列出几个命令。当你使用 IDE 一段时间后，您会发现额外的命令很快就会被添加到这个菜单上。Selenium IDE 将试图预测当前网页上您需要选择的UI元素会用到的命令以及参数。

让我们看看这是如何工作的。打开一个网页，选择页面上的一块文本。这个文本可以是一个段落或标题，他都会正常工作。现在，右击选中的文本，上下文菜单中应该给你一个 verifyTextPresent 命令和建议参数应该文本本身。

同时，注意到所有可用命令的菜单选项。这表明更多的命令，以及建议的参数，可以用来测试你当前选择的 UI 元素。

尝试更多的 UI 元素。右击图片，或用户控件按钮或复选框。您可能需要使用显示所有可用的命令来查看 verifyTextPresent 以外的选项。一旦你选择其他选项，更常用的将出现在一级上下文菜单。例如，为一个图片选择 verifyElementPresent 后，会导致该命令在你下一次选择一个图片并单击鼠标右键时，该命令出现在上下文菜单中。

再一次，这些命令将在 Selenium 命令章节中有详细解释。现在，请随意使用IDE来录制测试用例，从网页上右键选择命令插入到测试用例中，然后运行它。通过不断体验IDE，你可以学到很多关于 Selenium 的命令。

# 编辑

## 插入命令

**表格视图**

---
首先，选择要插入命令的位置。在测试用例窗格中，左键单击一条命令，新插入的命令将会出现在这条命令前面。右键单击该命令并在上下文菜单中选择插入命令，IDE 将在选定的命令前面添加一个空白行。然后，在命令字段编辑域文本框中输入新命令及其参数。

**源视图**
首先，选择要插入命令的位置。在测试用例窗格中，在要插入的两命令之间点击鼠标左键，输入 HTML 标记，创建一个包含三列的表格行。三列分别对应命令（第一列），第一个参数（第二列)，和第二个参数（第三列）。例如:

```html
<tr>
    <td>Command</td>
    <td>target (locator)</td>
    <td>Value</td>
</tr>
```

## 插入注释

注释可以添加到测试用例中，来增加可读性。运行测试用例时，这些注释会被忽略。

通过添加空白的注释，注释还可以用来在测试案例中增加垂直方向的空白（一个或多个空行）。一个空的命令在执行是会出错，而空白注释却不会。


**表格视图**
选择在您的测试用例,你想插入评论。右键单击并选择插入评论。现在使用命令字段中,输入评论。你的评论将会出现在紫色的文本。

**源视图**
选择在您的测试用例,你想插入评论。添加一个html样式的评论。,< !——你的评论在这里——>。


## 编辑命令和注释

**表格视图**
选择要修改或编辑的行，它使用命令,目标和价值领域。

**源视图**
自源视图提供了相当于一个WYSIWYG(你所见即所得)编辑器,只需修改这行你哎呀命令,参数,或评论。


## 打开和保存测试案例



---
[IDE 的功能](Features.md) | [目录](README.md) | [运行测试案例](Run.md)