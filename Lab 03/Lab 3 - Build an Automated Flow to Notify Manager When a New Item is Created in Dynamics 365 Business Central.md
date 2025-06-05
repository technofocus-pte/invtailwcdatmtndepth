# 實驗 3 - 構建一個自動化流，以便在 Dynamics 365 Business Central 中創建新項目時通知經理

**目標：** 在本實驗中，參與者將學習如何在 Power Automate
中創建自動化流，每當在 Microsoft Dynamics 365 Business Central
中創建新項目時，該流都會發送電子郵件通知。通過遵循結構化流程，參與者將熟悉如何根據
Business Central
數據觸發流、收集相關項目信息、應用條件邏輯以及執行作以發送電子郵件警報。這種實踐經驗將使參與者能夠利用
Power Automate 來增強業務流程和通知。

**預計時間：** 15 分鐘

### 任務 1：在 Microsoft Dynamic 365 Business Central 中註冊

1.  導航到
    **+++https://www.microsoft.com/en-us/dynamics-365/products/business-central+++**
    並單擊 **Try for Free**。

- ![](./media/image1.png)

2.  輸入您的 Office 365 租戶 ID，然後單擊 **Next**。

- ![](./media/image2.png)

3.  然後單擊 **Sign in** 並輸入憑據。

- ![](./media/image3.png)

4.  選擇 **“United states** ”作為國家或地區，輸入您的 **電話號碼**
    ，然後選擇“ **Get started**”。

- ![](./media/image4.png)

5.  然後單擊 **Get started** 以訪問 Business Central。

- ![](./media/image5.png)

6.  選擇 **Skip Survey** 按鈕以繼續。

- ![](./media/image6.png)

7.  您將被定向到 Dynamics 365 Business Central 主頁。

- ![](./media/image7.png)

### 任務 2：啟動 Power Automate

1.  打開 Dynamic 365 business central 旁邊的新選項卡，然後導航到
    +++**https://make.powerautomate.com/**+++ 在瀏覽器中。

- ![](./media/image8.png)

2.  如果詢問， 請在 respected 字段中輸入 **Microsoft 365 tenant
    ID**，然後單擊 **Next** 按鈕。

- ![](./media/image9.png)

3.  在相應字段中輸入**密碼**，然後單擊“**Sign in**”。

- ![](./media/image10.png)

4.  從頂部導航欄中，選擇環境 **Dev One。**

- ![](./media/image11.png)

5.  點擊 左側菜單中的 +**Create**。

- ![](./media/image12.png)

6.  選擇 **Automated cloud flow** 磁貼。

- ![](./media/image13.png)

### 任務 3：基於 Business Central 數據創建觸發器

1.  在 **Flow name** 框中，**+++Email notification for new
    furniture+++**。

- ![](./media/image14.png)

2.  在 **Choose your flow's trigger search bar** 中，輸入 **business
    central**。向下滾動以查看觸發器，然後選擇 **When a record is created
    （V3）**。

3.  單擊 **Create**。

- ![](./media/image15.png)

4.  填寫觸發器詳細信息:

    1.  **Environment name**: 輸入 +++**PRODUCTION**+++.

    2.  **Company name**: 從列表中選擇 CRONUS USA， Inc.。

    3.  **Table name**: 選擇**items**。

- ![](./media/image16.png)

### 任務 4：從 Business Central 收集數據

1.  單擊 **+ 按鈕** 添加 ，然後選擇 **Add an action**。

- ![](./media/image17.png)

1.  在 **Add an action** 窗口中，在搜索框中鍵入 **+++Dynamics 365
    Business Central+++**，然後選擇 **Get record (V3)** 作。

- ![](./media/image18.png)

2.  輸入以下信息:

    1.  **Environment**: +++**PRODUCTION**+++.

    2.  **Company name**: Select **CRONUS USA, Inc.**.

    3.  **Table name**: 選擇 **items**。

    4.  **Row id**: 從 Dynamic content 中選擇 **Row Id** 令牌。

- ![](./media/image19.png)

### 任務 5：制定條件

1.  單擊 **Get record** 下的 **+** 按鈕，然後選擇 **Add an action**。

- ![](./media/image20.png)

2.  在 **Add an action** 搜索欄中，輸入 **Control**。選擇 **Condition**
    作。

- ![](./media/image21.png)

3.設置條件:

1.  在第一個 **Choose a value** 框中，從 Dynamic content 中選擇 **Item
    Category Code** 令牌。

2.  保留 **is equal to** 選項。

3.  在第二個 **Choose a value** 框中，輸入 +++**FURNITURE**+++。

- ![](./media/image22.png)

### 任務 6：根據條件創建作

1.  在 **If yes or True** condition 窗口中，單擊 **Add an action**。

- ![](./media/image23.png)

2.  在“添加作”窗口中搜索 **+++office 365 outlook+++**，然後單擊“See
    more”。在 Office 365 Outlook 觸發器中，選擇 **Send an Email (V2)。**

- ![](./media/image24.png)

  ![](./media/image25.png)

3.填寫電子郵件詳細信息:

1.  **To**: 輸入“管理員”，然後從建議中選擇“**Mod
    Admin**”，即您在此實驗室中使用的 Office 365 租戶電子郵件 ID。

2.  **Subject**: 輸入+++**New furniture released**+++。

3.  **Body**:

    1.  添加文本 **New furniture**。

    2.  從Dynamic content中添加令牌**Number**。

    3.  從 Dynamic content 添加令牌 **displayName**。

    4.  添加文本 +++**has just released.**+++

- ![](./media/image26.png)

1.  單擊 **Save** 以完成您的流程。

- ![](./media/image27.png)

### 任務 7：測試流

1.  在頂部欄中，單擊 **Test** 按鈕。

- ![](./media/image28.png)

2.  選擇 **Manual** 流程，然後單擊 **Test**。

- ![](./media/image29.png)

3.  導航回 **Business Central 網站**，然後從頂部欄轉到 **Sales** 🡪
    **Items**。

- ![](./media/image30.png)

4.  點擊 **+ New button**

- ![](./media/image31.png)

5.  選擇 **ITEM，**然後單擊 **OK。**

- ![](./media/image32.png)

6.  在 Item Category Code 字段中，選擇 **FURNITURE** ，然後在
    Description 字段中，輸入 **Office Chair。**

- ![](./media/image33.png)

7.  點擊 **Save** 按鈕。

- ![](./media/image34.png)

8.  在 Power Automate 門戶上，單擊位於左上角的 **App launcher**。選擇
    **Outlook**，然後您可以看到在 MOD Admin
    提供的**電子郵件**中收到了自動回復。

- ![](./media/image35.png)

### 結論：

在本實驗結束時，參與者將成功在 Power Automate 中為 Business Central
中的新項目創建自動電子郵件通知流。他們將獲得設置觸發器、作和條件的實踐經驗，這些都是自動化工作流程的基本技能。參與者還將瞭解如何有效地從
Business Central
收集和作數據，使他們能夠簡化通信並提高各自組織的工作效率。這些知識將作為進一步探索
Power Automate 在自動化各種業務流程方面的功能的基礎。
