# 實驗 2 - 構建庫存管理應用程序

**目標：** 本實驗的目標是指導參與者使用 Microsoft Power Apps 和 Copilot
創建功能性庫存管理應用程序。參與者將學習使用 Power Automate 設置他們的
Dataverse 環境、設計應用程序屏幕、管理數據以及自動化庫存補貨工作流程。

**預計時間：** 40 分鐘

## 練習 1：構建庫存管理應用程序

### 任務 1：驗證您的 Dataverse 環境

1.  打開瀏覽器並轉到
    **+++https://admin.powerplatform.microsoft.com+++**。使用您的 Office
    365 管理員帳戶登錄。

2.  選擇 **Environment** 在左側導航欄中。**Developer environment**
    應該已為您創建，如下圖所示。（使用管理員帳戶提供 Microsoft Power App
    for Developer
    許可證後，系統會自動創建此環境。每個管理員賬戶的環境名稱都不同。

- ![](./media/image1.png)

3.  使用相同的開發人員環境執行此實驗室的所有練習。

> **注意**：本實驗使用 **Dev one**
> 開發人員環境。不同用戶的環境名稱可能不同。請確保選擇您的開發人員環境。

### 任務 2：使用 Copilot 創建庫存管理應用程序。

1.  打開瀏覽器並轉到 **+++https://make.powerapps.com+++** 使用 Office
    365 管理員租戶帳戶登錄。

2.  單擊右上角的環境，然後選擇 **您的開發人員** 環境（Dev One
    是本實驗指南中使用的開發人員環境）

- ![](./media/image2.png)

3.  輸入以下提示，然後單擊 **Enter** 按鈕。

- +++**build a candy inventory management app**+++

  ![](./media/image3.png)

4.  選擇“**Start with Copilot”**磁貼

- ![](./media/image4.png)

5.  輸入以下提示，然後單擊 **Generate** 在 Copilot 的幫助下創建表格

- +++**Candy Inventory management**+++

  ![](./media/image5.png)

6.  Copilot 生成表，如下圖所示。

- ![](./media/image6.png)

7.  單擊 Candy 旁邊的三個點，然後單擊 **View data。**

- ![](./media/image7.png)

8.  Candy 表中的數據應包含下圖所示的數據。

- ![](./media/image8.png)

9.  單擊 **Supplier –\> View data** 並瀏覽數據，然後關閉視圖窗口。

- ![](./media/image9.png)

10. 使用您的工作/個人工作電子郵件 ID 更新其中一個供應商電子郵件 ID

- ![](./media/image10.png)

11. 單擊 **Order – \> View data**

- ![](./media/image11.png)

12. Ener below 提示符，然後單擊
    Enter。此列用於在數量低於再訂購點時進行通知。

- +++**Add reorder point column to Candy table**+++

  ![](./media/image12.png)

13. 添加 type為 Number 的 candyInStock 列。如果 Quantity
    小於再訂購點，則 Quantity 列將自動添加 candyInStock。

- +++**Add** candyInStock\*\* column to Candy table with sample stock
  count\*\*+++

  ![](./media/image13.png)

14. 該表已更新為再訂購點列和 Candy in Stock 列

- ![](./media/image14.png)

15. 點擊 **Save and open app** 按鈕

- ![](./media/image15.png)

16. 在 **Done working？** 窗口中，單擊 **Save and open app**
    並等待應用程序創建。

- ![](./media/image16.png)

  ![](./media/image17.png)

17. 跳過歡迎窗口。

- ![](./media/image18.png)

18. 應用程序已創建，應如下圖所示。

- ![](./media/image19.png)

19. 單擊**Save**按鈕並輸入名稱 **MSCandy Inventory management
    app**，然後單擊保 Save 按鈕。

- ![](./media/image20.png)

  ![](./media/image21.png)

20. 探索應用程序。單擊 **Tree view** 中的 **Candy screen**
    。您可以將屏幕的標簽更新為 **Candy Inventory management**

- ![](./media/image22.png)

21. 瀏覽 Supplier 屏幕並根據您的要求進行更新。

- ![](./media/image23.png)

### 任務 3：創建糖果質量屏幕

1.  單擊 **New Screen** 並選擇 **Blank** 模板。

- ![](./media/image24.png)

2.  選擇新屏幕並右鍵單擊 **Rename**

- ![](./media/image25.png)

3.  將屏幕命名為 +++**Candy quality screen**+++

- ![](./media/image26.png)

4.  單擊 屏幕區域，然後選擇 **Create a new table （preview）**

- ![](./media/image27.png)

5.  單擊 **New table –\> Add columns and data。**

- ![](./media/image28.png)

6.  單擊 **New column -\> Edit column。**

- ![](./media/image29.png)

7.  輸入 Display name 作為 **Candy ID** ，然後單擊 **Update** 按鈕。

- ![](./media/image30.png)

8.  單擊 New column 並輸入以下詳細信息，然後單擊 **Save** 。

    - **Display Name:** Candy Name

    - **Data Type:** Choice

    - **Required:** Yes.

    - **Choices:** add below choices

      - Chocolate Bar

      - Gummy Bears

      - Jellybeans

      - Lollipop

      - Sour Patch Kids

- ![](./media/image31.png)

9.  單擊 New Column 並添加包含以下詳細信息的列，然後單擊 **Save** 。

    - **Display Name:** Candy Quality
    - **Data type:** Choice
    - **Required:** Yes
    - **Choice:** labels
      - Defective
      - Nondefective

- ![](./media/image32.png)

> **注意：** 您可以根據應用程序要求添加更多列。

10. 編輯表名並使用 **+++Candy Quality check+++** 進行更新。
    ![](./media/image33.png)

11. 單擊 **Save and exit -\> Save and exit**。 ![](./media/image34.png)

12. 您將導航回 Power Apps 應用頁面。選擇新添加的屏幕，然後單擊 Insert
    並選擇 **Edit form** ，如下圖所示。 ![](./media/image35.png)

13. 單擊容器，然後選擇數據源表作為 **+++Candy Qualities table+++**。
    ![](./media/image36.png)

14. 您應該會看到如下圖所示的表單。 ![](./media/image37.png)

15. 將表格調整到頁面中間。單擊 **Insert-\> Text label。**
    ![](./media/image38.png)

16. 調整文本標簽並輸入文本：**+++Candy Quality check+++**
    並更新文本樣式。 ![](./media/image39.png)

17. 選擇 **Form**。點擊 **Insert** 並選擇 **Button**。
    ![](./media/image40.png)

18. 拖動提交按鈕並將其放在容器的中間。選擇按鈕並將 **properties**
    文本更改為 **Submit** ，如下圖所示。 ![](./media/image41.png)

19. 選擇 **Submit** 按鈕，然後選擇 **OnSelect** 函數並輸入以下函數。

> **備註：** 公式中的 Form4 應替換為您的表單名稱
> SubmitForm（Form4）;NewForm（Form4） 的

![](./media/image42.png)

20. 選擇容器，在 properties 下，選擇 **Default** 模式 到 **New**。
    ![](./media/image43.png)

21. 單擊 **Save** ，然後單擊預覽 **Preview app** 按鈕，如下圖所示。
    ![](./media/image44.png)

22. 輸入 Candy 詳細信息，然後單擊 Submit 按鈕。 ![](./media/image45.png)

23. 切換回 Dataverse 環境中的 Candy 質量表，您應該會看到上面添加的記錄。
    ![](./media/image46.png)

24. 關閉預覽窗口。

## 練習 2：創建 Power Automate 流以補充庫存。

### 任務 1：創建 Power Platform 流以觸發補貨電子郵件

1.  切換回 Power Automate 選項卡，然後單擊 **My flows -\> New flow
    -cloud flow。** ![](./media/image47.png)

2.  將流名稱輸入為：**+++Candy Restock Flow+++**。搜索 **+++When a
    row+++** ，選擇 Dataverse 的 **When a row is added or modified**
    作，然後單擊**Create**。 ![](./media/image48.png)

3.  選擇作並設置以下參數。

    - 更改類型; Added or Modified
    - 表名稱: Candies
    - 範圍: Organization ![](./media/image49.png)

4.  在“when a row is added, modified or deleted”
    在作後添加作**。**![](./media/image50.png)

5.  搜索 **Condition** 並選擇 **Control’s Condition**作。
    ![](./media/image51.png)

6.  單擊 Chosen value 並選擇 Choose from previous step dynamic action。
    ![](./media/image52.png)

7.  搜索 **+++Quantity+++** 列並選擇它。 ![](./media/image53.png)

8.  選擇**一個小於** （condition） 的條件**，**然後單擊 Enter data from
    previous action （輸入來自上一個作的數據）。
    ![](./media/image54.png)

9.  搜索 **+++Reorder points+++** 列並選擇它。 ![](./media/image55.png)

10. **在 True condition** 下 Add an action。![](./media/image56.png)

11. 選擇 **+++Approvals+++**作。 ![](./media/image57.png)

12. 選擇 **+++Start and wait for an Approvals+++**。
    ![](./media/image58.png)

13. 選擇 Approval Type as：**+++Approve/Reject – First to
    Respond+++**。輸入 標題 為：**+++ Approve to Restock+++** - 然後單擊
    動態 按鈕以選擇上一步中的數據。 ![](./media/image59.png)

14. 搜索 **Candy Name+++** 並選擇它**。** ![](./media/image60.png)

15. 輸入以下詳細信息。

- Assigned to: Your work email id.

      Details:

      Hi Sir,  

      is out of stock - for customers to place an order. Please approve to
      restock.  

      Thanks

> **注意：** 您可以根據需要自定義詳細信息部分。

![](./media/image61.png)

16. 在**approval**作後**Add an action**。 ![](./media/image62.png)

17. 搜索 +++**condition**+++ 並選擇 **Control – Condition。**
    ![](./media/image63.png)

18. 單擊 Choose value，然後從 Start 中選擇 **Outcome** 並等待 Approval
    作。 ![](./media/image64.png)

19. 選擇條件 **is equal to** ，然後輸入值 **Approve**。
    ![](./media/image65.png)

20. 在 True condition 下，**Add an action**。 ![](./media/image66.png)

21. 搜索 **Update Row** 並從 **Microsoft Dataverse** 部分中
    選擇它。![](./media/image67.png)

22. 選擇您的 **Candy** 表，然後單擊 **Row Id**，選擇 Dynamic action。
    ![](./media/image68.png)

23. 從表中搜索唯一標識符列並選擇它。 ![](./media/image69.png)

24. 單擊 **Advanced Parameters** 下拉列表，然後選擇 **Quantity** 列。
    ![](./media/image70.png)

25. 輸入以下函數 （在應用程序中鍵入） 並折疊作。

> > **注意：** 以下函數不適合您，因為您的列架構名稱可能不同。轉到 table
> > –\> column 並複製 schema name。

- +++add(triggerBody()?\[‘cr8a3_Quantity’\],triggerBody()?\[‘cr8a3_CandyInStock’\])+++

  ![](./media/image71.png)

26. 單擊 **Save** 按鈕以保存 Power Automate 流。
    ![](./media/image72.png)

### 任務 2：測試補貨流

1.  切換回 **PowerApps** 選項卡，單擊 左側樹視圖中的 Candy
    screen，然後選擇 **play**。

> > **注：** 您可以更新屏幕的 Title

- ![](./media/image73.png)

2.  選擇 Candy 並單擊 **Edit**。 ![](./media/image74.png)

3.  輸入 **Quantity** 值 **小於再訂購點** 並 **commit** 更改。
    ![](./media/image75.png)

4.  切換回 Power Automate 流選項卡，然後單 My flows -\> Your flow。
    ![](./media/image76.png)

5.  Flow 正在運行並處於狀態。 ![](./media/image77.png)

6.  打開一個新選項卡，轉到 **+++https://outlook.com+++**，然後使用
    Office 365 管理員帳戶登錄。您應該已經收到了一封需要補貨的電子郵件。
    **Approve** 並 **submit**。 ![](./media/image78.png)

- ![](./media/image79.png)

7.  流程現在成功了。 ![](./media/image80.png)

- ![](./media/image81.png)

8.  切換回PowerApps並檢查上述產品數量。它應該已經更新（當它小於再訂購點時，有庫存的糖果 +
    數量） ![](./media/image82.png)

### 結論：

在本實驗結束時，參與者將能夠驗證他們的 Dataverse 環境，利用 Copilot
構建庫存管理應用程序，設計帶有自定義字段的糖果質量檢查屏幕，並實施 Power
Automate流以根據庫存水平觸發補貨請求。此外，他們還將獲得測試和驗證自動化工作流程的技能，以確保在審批流程後準確更新庫存。這種結構化方法將使參與者能夠有效地利用
Power Apps 和 Power Automate
的功能，從而提高他們在應用開發和流程自動化方面的技能。
