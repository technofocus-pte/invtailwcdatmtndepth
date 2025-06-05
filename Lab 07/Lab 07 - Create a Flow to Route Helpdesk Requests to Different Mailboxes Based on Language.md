# 實驗 07 - 創建一個流，以根據語言將幫助台請求路由到不同的郵箱

**目標：** 本實驗的目標是指導參與者完成創建 Power Automate
流的過程，該流根據語言檢測將技術支持請求路由到不同的郵箱。該流程與 GPT
功能集成，以匯總傳入的電子郵件並根據特定觸發器自動執行路由流程，從而幫助簡化組織內的通信工作流程。

**預計時間：** 15 分鐘

### 任務 1：創建流以根據語言將支持請求路由到不同的郵箱

1.  登錄到 **+++https://make.powerautomate.com/using+++** office 365
    admin tenant 帳戶。

2.  從 左側導航窗格中選擇 **Templates**，在頂部的搜索框中輸入
    **+++Summarize emails using GPT+++**，然後在出現時選擇流。

- ![](./media/image1.png)

3.  接下來，該模板將向您顯示此流程中將使用哪些連接。如果他們旁邊沒有綠色複選標記，請選擇連接旁邊的“登錄”來修復連接，然後選擇
    **“Continue**”。

- ![](./media/image2.png)

4.  選擇觸發器，when a new email arrives (V3)**。**
    屬性面板將從左側打開，並帶有更新“主題過濾器”參數的注釋。目前，Subject
    Filter為 AI Builder。

5.  將主題篩選器更新為 **Project Kick-off**。

- ![](./media/image3.png)

6.  選擇 **Create text with a GPT using a prompt**
    作，以便在左側打開屬性面板。在屬性面板中，Prompt 字段顯示 **AI
    Summarize**。

7.  選擇 **Test prompt** 以打開 Prompt 設置。

- ![](./media/image4.png)

8.  該模板具有 GPT
    將使用的預定義提示，但您可以在此窗口中更新和測試新提示。按照下一步作更新提示。

9.  要測試提示，請在 **Input** 部分中輸入給定的示例數據。然後選擇 Prompt
    部分底部的 **Test prompt**。您可以在 Prompt response
    部分下看到響應。

- +++Once upon a time in the quaint town of Eldoria, nestled between
  rolling hills and dense forests, lived a young girl named Elara. Her
  days were spent exploring the mystical woods that bordered the town,
  and whispers of ancient tales filled her imagination.+++

  ![](./media/image5.png)

10. 在本練習中，我們將保持打開 Prompt Settings 時的所有內容。

11. 將流**保存**在 右上角。現在我們可以運行流。

![](./media/image6.png)

> 注意：如果您看到給定的警告，請忽略：“Create text with GPT using a
> prompt”作後沒有內容審批作。

### 任務 2：測試流

1.  從 MOD 管理員的租戶 ID 或您的電子郵件 ID 向 MOD 管理員的租戶 ID
    發送電子郵件，主題為 **Project Kick-off**
    ，電子郵件正文中應包含以下內容：

- Dear Team,

      I hope this email finds you well. We are excited to announce the
      kick-off of our new project, "Phoenix". The initial meeting is scheduled
      for Monday, June 1st, at 10 AM via Zoom. Please come prepared with any
      questions or suggestions. Your input is vital for the project's success.

      Kindly confirm your attendance by the end of the day tomorrow. Looking
      forward to a productive session and a successful project launch.

      Best regards,

      Miriam Graham

      Project Manager

      Contoso

2.  您將在Teams中收到一條消息，其中包含電子郵件的摘要。在右下角，您可以找到一個鏈接以轉到您的流。

- ![](./media/image7.png)

3.  本單元使用 GPT 來匯總傳入的電子郵件。AI
    檢測信息可能不準確。始終確保驗證來自 GPT 的信息。

### 結論：

在本實驗中，參與者成功創建了一個 Power Automate
流，通過基於語言檢測路由電子郵件並使用 GPT
總結內容來簡化幫助台請求。通過將自動化集成到電子郵件工作流程中，該實驗室演示了如何根據語言觸發器有效地管理多個團隊或部門之間的通信。該練習還展示了如何在
Power Automate 中使用 GPT
來提高生產力並減少手動排序。此解決方案可幫助組織提高工作流程效率並縮短幫助台查詢的響應時間。
