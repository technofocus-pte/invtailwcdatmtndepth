# 实验 3 - 构建一个自动化流，以便在 Dynamics 365 Business Central 中创建新项目时通知经理

**目标：** 在本实验中，参与者将学习如何在 Power Automate
中创建自动化流，每当在 Microsoft Dynamics 365 Business Central
中创建新项目时，该流都会发送电子邮件通知。通过遵循结构化流程，参与者将熟悉如何根据
Business Central
数据触发流、收集相关项目信息、应用条件逻辑以及执行作以发送电子邮件警报。这种实践经验将使参与者能够利用
Power Automate 来增强业务流程和通知。

**预计时间：** 15 分钟

### 任务 1：在 Microsoft Dynamic 365 Business Central 中注册

1.  导航到
    **+++https://www.microsoft.com/en-us/dynamics-365/products/business-central+++**
    并单击 **Try for Free**。

- ![](./media/image1.png)

2.  输入您的 Office 365 租户 ID，然后单击 **Next**。

- ![](./media/image2.png)

3.  然后单击 **Sign in** 并输入凭据。

- ![](./media/image3.png)

4.  选择 **“United states** ”作为国家或地区，输入您的 **电话号码**
    ，然后选择“ **Get started**”。

- ![](./media/image4.png)

5.  然后单击 **Get started** 以访问 Business Central。

- ![](./media/image5.png)

6.  选择 **Skip Survey** 按钮以继续。

- ![](./media/image6.png)

7.  您将被定向到 Dynamics 365 Business Central 主页。

- ![](./media/image7.png)

### 任务 2：启动 Power Automate

1.  打开 Dynamic 365 business central 旁边的新选项卡，然后导航到
    +++**https://make.powerautomate.com/**+++ 在浏览器中。

- ![](./media/image8.png)

2.  如果询问， 请在 respected 字段中输入 **Microsoft 365 tenant
    ID**，然后单击 **Next** 按钮。

- ![](./media/image9.png)

3.  在相应字段中输入**密码**，然后单击“**Sign in**”。

- ![](./media/image10.png)

4.  从顶部导航栏中，选择环境 **Dev One。**

- ![](./media/image11.png)

5.  点击 左侧菜单中的 +**Create**。

- ![](./media/image12.png)

6.  选择 **Automated cloud flow** 磁贴。

- ![](./media/image13.png)

### 任务 3：基于 Business Central 数据创建触发器

1.  在 **Flow name** 框中，**+++Email notification for new
    furniture+++**。

- ![](./media/image14.png)

2.  在 **Choose your flow's trigger search bar** 中，输入 **business
    central**。向下滚动以查看触发器，然后选择 **When a record is created
    （V3）**。

3.  单击 **Create**。

- ![](./media/image15.png)

4.  填写触发器详细信息:

    1.  **Environment name**: 输入 +++**PRODUCTION**+++.

    2.  **Company name**: 从列表中选择 CRONUS USA， Inc.。

    3.  **Table name**: 选择**items**。

- ![](./media/image16.png)

### 任务 4：从 Business Central 收集数据

1.  单击 **+ 按钮** 添加 ，然后选择 **Add an action**。

- ![](./media/image17.png)

1.  在 **Add an action** 窗口中，在搜索框中键入 **+++Dynamics 365
    Business Central+++**，然后选择 **Get record (V3)** 作。

- ![](./media/image18.png)

2.  输入以下信息:

    1.  **Environment**: +++**PRODUCTION**+++.

    2.  **Company name**: Select **CRONUS USA, Inc.**.

    3.  **Table name**: 选择 **items**。

    4.  **Row id**: 从 Dynamic content 中选择 **Row Id** 令牌。

- ![](./media/image19.png)

### 任务 5：制定条件

1.  单击 **Get record** 下的 **+** 按钮，然后选择 **Add an action**。

- ![](./media/image20.png)

2.  在 **Add an action** 搜索栏中，输入 **Control**。选择 **Condition**
    作。

- ![](./media/image21.png)

3.设置条件:

1.  在第一个 **Choose a value** 框中，从 Dynamic content 中选择 **Item
    Category Code** 令牌。

2.  保留 **is equal to** 选项。

3.  在第二个 **Choose a value** 框中，输入 +++**FURNITURE**+++。

- ![](./media/image22.png)

### 任务 6：根据条件创建作

1.  在 **If yes or True** condition 窗口中，单击 **Add an action**。

- ![](./media/image23.png)

2.  在“添加作”窗口中搜索 **+++office 365 outlook+++**，然后单击“See
    more”。在 Office 365 Outlook 触发器中，选择 **Send an Email (V2)。**

- ![](./media/image24.png)

  ![](./media/image25.png)

3.填写电子邮件详细信息:

1.  **To**: 输入“管理员”，然后从建议中选择“**Mod
    Admin**”，即您在此实验室中使用的 Office 365 租户电子邮件 ID。

2.  **Subject**: 输入+++**New furniture released**+++。

3.  **Body**:

    1.  添加文本 **New furniture**。

    2.  从Dynamic content中添加令牌**Number**。

    3.  从 Dynamic content 添加令牌 **displayName**。

    4.  添加文本 +++**has just released.**+++

- ![](./media/image26.png)

1.  单击 **Save** 以完成您的流程。

- ![](./media/image27.png)

### 任务 7：测试流

1.  在顶部栏中，单击 **Test** 按钮。

- ![](./media/image28.png)

2.  选择 **Manual** 流程，然后单击 **Test**。

- ![](./media/image29.png)

3.  导航回 **Business Central 网站**，然后从顶部栏转到 **Sales** 🡪
    **Items**。

- ![](./media/image30.png)

4.  点击 **+ New button**

- ![](./media/image31.png)

5.  选择 **ITEM，**然后单击 **OK。**

- ![](./media/image32.png)

6.  在 Item Category Code 字段中，选择 **FURNITURE** ，然后在
    Description 字段中，输入 **Office Chair。**

- ![](./media/image33.png)

7.  点击 **Save** 按钮。

- ![](./media/image34.png)

8.  在 Power Automate 门户上，单击位于左上角的 **App launcher**。选择
    **Outlook**，然后您可以看到在 MOD Admin
    提供的**电子邮件**中收到了自动回复。

- ![](./media/image35.png)

### 结论：

在本实验结束时，参与者将成功在 Power Automate 中为 Business Central
中的新项目创建自动电子邮件通知流。他们将获得设置触发器、作和条件的实践经验，这些都是自动化工作流程的基本技能。参与者还将了解如何有效地从
Business Central
收集和作数据，使他们能够简化通信并提高各自组织的工作效率。这些知识将作为进一步探索
Power Automate 在自动化各种业务流程方面的功能的基础。
