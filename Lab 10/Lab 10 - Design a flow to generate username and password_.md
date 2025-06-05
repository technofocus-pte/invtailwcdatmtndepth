# 实验 10 - 设计一个流来生成用户名和密码

**目标：** 本实验的目标是创建和测试一个 Power Automate Desktop
流，该流根据用户输入生成用户名和随机密码。通过完成此实验，参与者将学习如何使用
Power Automate Desktop作设计和自动化流，包括处理文本作和生成随机文本。

**预计时间：** 20 分钟

# 任务 1：创建 Power Automate 桌面流

1.  登录并打开具有 **Power Automate Desktop with office 365
    tenant**，然后选择一个环境 （**Contoso**）。从左上角选择 **+ New
    flow。**

- ![](./media/image1.png)

2.  输入 流名称 +++ **Generate Username and Password** +++，确认 **Power
    Fx** 已关闭，然后单击 **Create。**

- ![](./media/image2.png)

3.  从左侧作栏搜索 +++ **Display input dialog**
    +++作，然后双击要选择的作。

- ![](./media/image3.png)

4.  将“**Input dialog title**”属性设置为 +++**Name
    Input**+++，将“**Input dialog message**”属性设置为 +++ **Please
    enter your first and last name (for example, Adele
    Vance)**+++。此作将显示一条消息，提示用户输入。点击 **Save** 按钮。

- ![](./media/image4.png)

5.  从左侧作栏搜索 **+++ Split text +++**作，然后双击要选择的作。

- ![](./media/image5.png)

6.  在 Split text作的 **Text to split** 字段中，输入
    +++**%UserInput%**+++，然后单击 **Save**。

- ![](./media/image6.png)

7.  在左侧作栏中，搜索 +++ **Change text case**
    +++作，然后双击要选择的作。

- ![](./media/image7.png)

8.  在 Text to convert 字段中，输入 +++**%TextList\[0\]%**+++。

9.  使用列表类型变量的索引，提供列表的第一项，即名字。设置 转换成 为
    **Lower case**，然后单击 **Save**。

- ![](./media/image8.png)

10. 在左侧作栏中，搜索 +++ **Change text case**
    +++作，然后双击要选择的作。

- ![](./media/image9.png)

11. 在 **Text to convert** 作字段中，输入 +++**%TextList\[1\]%**+++。

12. 使用列表类型变量的索引，提供列表的第一项，即名字。将 Convert to
    属性设置为 **Lower case** ，然后单击 **Save**。

- ![](./media/image10.png)

> 13\. 在左侧作栏搜索 +++ **Get subtext**+++作，然后双击要选择的作。

- ![](./media/image11.png)

13. 在 Original text 字段中，输入 +++**%TextWithNewCase%**+++，在 Start
    index 部分中，将 Character position 设置为 +++**0**+++

14. 在 Length 部分中，将 Number of chars 设置为
    +++**1**+++。此设置获取文本字符串的第一个字符。

15. 点击 **Save**.

- ![](./media/image12.png)

16. 要生成随机密码，请添加 **Create random text**
    作。作的属性可以保留为默认值。然后点击 **Save。**

- ![](./media/image13.png)

17. 从左侧作栏搜索 +++ **Display message** +++作，然后双击要选择的作。

- ![](./media/image14.png)

18. 在**Message box title**字段中，输入**+++ Username &
    Password**+++，然后在** Message to display** 字段中，输入以下内容：

- +++Hello, %UserInput%, your username is: %SubText%%TextWithNewCase2% Your temporary password is: %RandomText%+++

19. 将显示用户名（名字的第一个字母，与姓氏组合），并且 **Generate random
    text**作的结果显示为用户的密码。点击 **Save** 按钮。

- ![](./media/image15.png)

20. **完成的流程** 应如下图所示。

- ![](./media/image16.png)

# 任务 2：测试流

1.  单击 **Run** 按钮以测试流。

- ![](./media/image17.png)

2.  输入 **First and Last Name**用于测试目的，然后单击 **Ok** 按钮。

- ![](./media/image18.png)

3.  测试用例的 **Final output** 如下所示一次。

- ![](./media/image19.png)

**结论：** 在本实验中，参与者成功设计并测试了一个 Power Automate Desktop
流，该流根据用户输入生成用户名和随机密码。通过利用文本作作，例如拆分、更改大小写和生成随机文本，参与者获得了自动化用户特定任务的实践经验。该流程演示了如何使用基本的
Power Automate Desktop
功能动态创建用户名和密码。此实验室为在未来任务中构建更复杂的自动化流程奠定了基础。
