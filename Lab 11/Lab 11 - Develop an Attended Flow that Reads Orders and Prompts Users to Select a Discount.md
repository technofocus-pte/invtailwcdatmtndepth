# 实验 11 - 开发一个有人值守的流程，用于读取订单并提示用户选择折扣

**目标：** 本实验的目标是开发一个 **attended Power Automate Desktop
flow**，该流可自动执行从 Excel
文件读取订单的过程，并提示用户根据特定条件应用折扣。参与者将创建一个流，该流读取数据，检查订单金额是否超过特定阈值，并提示用户决定是否应用折扣，并可选择输入折扣值。然后，该流程将使用应用的折扣更新
Excel 工作表。

**预计时间：** 25 分钟

### 任务 1：创建 Power Automate 桌面流

1.  打开 **Power automate** 桌面并使用 **office 365 tenant
    credential**。

2.  选择环境 **Contoso**，然后单击 **+ New then Flow** 并开始创建新流。

- ![](./media/image1.png)

3.  输入 +++**Message Box Communication**+++ 作为流名称，并确认 Power Fx
    enable （Preview） 已关闭。然后点击 **Create**。

- ![](./media/image2.png)

4.  首先提示用户选择一个 Excel 文件。添加 +++**Display select file
    dialog**+++作，并将 File filter 字段配置为仅允许 xlsx 文件。

- ![](./media/image3.png)

5.  输入**Dialog Title** +++ **Select Excel**+++，输入文件夹在 **initial
    folder** 中的位置 **+++ C：**文件+++ 过滤器 as **\*.xlsx**然后单击
    **Save** 按钮。

- ![](./media/image4.png)

6.  在从所选文件中读取任何数据之前，您必须使用 **Launch
    Excel**作启动该文件。从作中添加 **Launch Excel**。然后配置以下设置。

    - 启动 Excel: **add open the following document**

    - 文档路径: +++**%SelectedFile%**+++

    &nbsp;

    - 点击保存按钮

- ![](./media/image5.png)

7.  要从 Excel 文件中读取数据，请添加从 **Excel 工作表读取**作在 Excel
    实例中输入 **%ExcelInstance%**，然后在检索字段中选择 **All available
    values from worksheet**。点击 **Save** 按钮。

- ![](./media/image6.png)

8.  添加 **Get first free column/row from Excel worksheet** 作，以检索
    Excel 工作表中的第一个空闲列和行。在 **Excel 实例中输入**
    %ExcelInstance%，然后单击**save**按钮。

- ![](./media/image7.png)

9.  添加一个名为 **Counter** 的 Set Variable from作 并将其初始化为
    **1**，然后单击保存。

- ![](./media/image8.png)

10. 从作中添加 **Display input dialog** 并配置以下字段。

    - **Input Dialog Title**: +++**Header**+++

    - **Input Dialog Message**: +++**Enter the Header**+++

    - **Default Value**: +++**Discount**+++

    - 点击**save**按钮。

- ![](./media/image9.png)

11. 从作中添加 **Write to Excel worksheet**
    并使用以下详细信息对其进行配置:

    - **Excel instance**: %ExcelInstance%

    - **Value to write**: +++**%UserInput%**+++

    - **Write role**: On specific cell

    - **Column**: +++**9**+++

    - **Row**: +++**%Counter%**+++

    - 点击**save**按钮。

- ![](./media/image10.png)

12. 添加一个 **For each** 循环 for作以迭代检索到的数据，并将
    +++**%ExcelData%**+++ 添加到要迭代的值部分。然后点击 Save。

- ![](./media/image11.png)

13. 要检查 **Gross** 列（G 列或工作表中的第六列，在工作表中列的名称为
    “6”）的值，请添加 **convert text to number** 作。配置文本以转换为
    +++**%CurrentItem\[6\]%**+++，然后单击保存按钮。

- ![](./media/image12.png)

14. 添加 **If**作以检查它是否超过 100,000 并配置它，如下所示:

    - **First operand**: +++**%TextAsNumber%**+++

    - **Operator**: Greater than or equal to (\>=)

    - **Second Operand**: +++**100000**+++

- ![](./media/image13.png)

15. 在 **If** 下添加 **Display
    message**作，以向用户提供必要的信息，并提示他们选择 **Yes** 或
    **No**。然后点击 **Save** 按钮。在 **it** 中输入以下详细信息:

    - **Message Box title**: +++**Add discount**+++
    - **Message to display**:
      - +++**Product:** %CurrentItem\[2\]%+++
      - +++**Units**: %CurrentItem\[3\]%+++
      - +++**Gross:** %TextAsNumber%+++
    - **Message box button**: Yes – No

- ![](./media/image14.png)

16. 在 Display message action 下添加第二个
    **If**作，以检查在上一步中按下了哪个按钮。在相关字段中输入以下详细信息:

- **First** **operand**: +++%ButtonPressed3%+++

- **Operator:** Equal to (=)

- **Second operand:** +++Yes+++

 

- ![](./media/image15.png)

17. 在第二个 If Add **Display Input Dialog**
    作下。在字段中添加给定的以下参数，然后单击 **Save** 按钮。

Input dialog title: +++Discount Value+++

Input dialog message: +++Enter the Discount Value+++

![](./media/image16.png)

18. 添加 **Write to excel worksheet** 作在第二个 **IF**
    作下方，并在其中输入以下详细信息:

- **Excel instance:** +++%ExcelInstance%+++

- **Value to writer**: +++%UserInput2%+++

- **Write mode:** On specific cell

- **Column:** +++9+++

- **Row:** +++%Counter%+++

&nbsp;

- ![](./media/image17.png)

19. 在 第一 **IF End，** 添加作**Increase Variable 下，** 添加变量名称为
    **%Counter%** ，增加 **1** ，然后单击 **Save** 按钮。

> ![](./media/image18.png)

20. 从顶部栏**Save** 测试的流程。

- ![](./media/image19.png)

# 任务 2：测试流

1.  单击 **Run** 按钮执行测试。

> ![](./media/image20.png)

2.  第一个工作表文件夹将打开，从中选择 **excel file**。

> ![](./media/image21.png)

3.  标题窗口将弹出，因为我们将 折扣 设置为默认单击 **OK** 按钮。

> ![](./media/image22.png)

4.  出现 **Add Discount** 窗口，显示此产品超过 **100000，**选择 **yes**
    或 **no**。在此测试中，我们选择 **yes**
    （**是的**，我们为此产品提供折扣。

> ![](./media/image23.png)

5.  然后输入 **Discount Value** 对于测试，我们输入 **10000**，然后单击
    **ok**。

> ![](./media/image24.png)

6.  在 Sheet 中，discount 值将更新。

![](./media/image25.png)

7.   所有产品的循环都在**连续**运行。

### 结论：

在本实验中，参与者开发了一个有人值守的 Power Automate Desktop 流，该流从
Excel文件中读取订单数据，检查订单金额是否超过设定的阈值，并提示用户应用折扣。该流程允许用户通过提示与流程交互并输入折扣值，从而有效地自动化决策过程。此实验室提供自动化涉及
Excel、用户输入和条件逻辑的任务的实践经验，使参与者能够使用 Power
Automate Desktop 简化类似的业务流程。
