# **實驗 1 - 新員工自動入職**

**目標：** 本實驗室的主要目標是指導參與者使用 Microsoft Power Platform
自動化員工入職流程。這些練習的重點是創建 SharePoint 列表來存儲員工和 HR
信息、在 Power Apps 中自定義表單以進行數據輸入，以及使用 Power Automate
實施自動化工作流。參與者將學習利用 SharePoint 進行數據管理，利用 Power
Apps
增強用戶體驗，並集成自動化流程以簡化入職任務。這種實踐經驗旨在使參與者具備實用技能，以有效管理和自動化其組織內的
HR 流程。

**預計時間：** 60 分鐘

# 練習 1：在 Share point 中創建員工、人力資源和經理列表。

## 任務 1：驗證您的 Dataverse 環境

1.  打開瀏覽器並轉到
    **+++https://admin.powerplatform.microsoft.com+++**。使用 Office 365
    租戶憑據登錄。

2.  選擇 **Manage** \> **Environments** 在左側導航欄中。 **Dev One**
    Developer 環境應該已為您創建，如下圖所示。

- ![](./media/image1.png)

3.  使用相同的開發人員環境執行此實驗室的所有練習。

## 任務 2：在 SharePoint 中創建網站

1.  導航到 **+++https：\office.com+++** 並使用 office 365 tenant。

2.  單擊左上角的 matrix，然後從**應用程序**列表中選擇 **SharePoint**。

- ![](./media/image2.png)

  ![](./media/image3.png)

3.  點擊 頂部菜單上的 +Create site。

- ![](./media/image4.png)

4.  在**“Create a site**”窗口中選擇**“Communication site**”。

- ![](./media/image5.png)

5.  向下滾動並選擇 **Blank** template。

- ![](./media/image6.png)

6.  單擊 **Use template**。

- ![](./media/image7.png)

7.  輸入站點名稱和描述，然後單擊 **Next** 按鈕.

    - 站點名稱: +++**Contoso Corp**+++

    - 網站描述: +++**Onboarding new employee.**+++

- ![](./media/image8.png)

8.  保留默認語言，然後單擊 **Create Site。**

- ![](./media/image9.png)

  ![](./media/image10.png)

## 任務 3：從 CSV 文件在 SharePoint 站點中創建員工列表

1.  單擊 **Home –\> New –\> List。**

- ![](./media/image11.png)

2.  從 **Create a list** 窗口中選擇 **From CSV tile**。

- ![](./media/image12.png)

3.  單擊 **Upload file** 並瀏覽到 **C：Files** 並選擇 **Employee.csv**
    file。

- ![](./media/image13.png)

4.  將 **Work Email** 列類型更改為 **Single line of text** ，然後單擊
    **Next**。

- ![](./media/image14.png)

5.  然後輸入名稱為：**+++ Employee Onboarding+++**，如果詢問，請輸入
    描述：**+++New Contoso Corp employee+++**，然後單擊 **Create**。

- ![](./media/image15.png)

  ![](./media/image16.png)

6.  現在已為您創建 Employees 列表。通過選擇 **Title drop-down \> Column
    settings \> Rename，**將 **Title** 列重命名為 **+++Emp_id+++**。

- ![](./media/image17.png)

  ![](./media/image18.png)

7.  現在 employee 表應該像這樣

- ![](./media/image19.png)

8.  單擊 **Settings -\>List settings。**

- ![](./media/image20.png)

9.  單擊 **Department** 列鏈接。

- ![](./media/image21.png)

10. 更改以下值，然後單擊 **Ok**。

    - 列類型 : **Choice**

    - 允許 “Fill-in” 選項: **Yes**

- ![](./media/image22.png)

11. 對 **Job title** 列重複上述步驟。

12. 選擇 **Have you been to orientation yet?** 列並製作到 chagnes
    下面，然後單擊 **OK。**

    - 列類型 : **Choice**

    - 允許 “Fill-in” 選項: **Yes**

    - 在單獨的行中鍵入每個選項 : **Yes No**

- ![](./media/image23.png)

13. 對 **Orientation Location** with below properties
    重複上述步驟，然後選擇 **Ok**。

    - 列類型 : **Choice**

    - 允許 “Fill-in” 選項: **Yes**

    - 在單獨的行中鍵入每個選項 : **Redmon Reno**

- ![](./media/image24.png)

14. 對 **Manager** 列重複上述步驟 ，並添加以下屬性，然後選擇 **Ok**.

    - 列類型 : **Choice**

    - 允許 “Fill-in” 選項: **Yes**

- ![](./media/image25.png)

15. 單擊 **Home** 返回 **Site**。

- ![](./media/image26.png)

## 任務 4：從 CSV 文件在 SharePoint 網站中創建 HR 列表

1.  單擊 **Home –\> New –\> List。**

- ![](./media/image27.png)

2.  從 **Create a list window** 中選擇 **From CSV tile。**

- ![](./media/image12.png)

3.  單擊 Upload **file** 並瀏覽 **C：Files** 並選擇
    **Import_HR_M365.CSV** 然後單擊 **Open**。

- ![](./media/image28.png)

4.  將 **Work Email** 列類型更改為 **Single line of text**，然後單擊
    **Next**。

- ![](./media/image29.png)

5.  輸入以下詳細信息

    - 名字 : +++**Contoso HR**+++

    - 描述 : +++**Contoso Human Resource**+++, 然後點擊 **Create**
      按鈕。

- ![](./media/image30.png)

6.  單擊 **Title –\> Column settings –\> Rename** 為 **+++Emp_id+++。**

- ![](./media/image31.png)

  ![](./media/image32.png)

7.  HR 表現在應如下圖所示。

- ![](./media/image33.png)

# 練習 2：創建 Power Apps for SharePoint 列表

在本練習中，您將構建應用程序，向員工發送一封包含官方信息的電子郵件，並要求他填寫和上傳文檔。

## 任務 1：使用 PowerApps 自定義員工表單，供 HR 填寫。

1.  從 **SharePoint –\> Employee onboarding**，複製 URL
    並將其保存在記事本中。

- ![](./media/image34.png)

2.  打開一個新選項卡並轉到
    **+++https://make.powerapps.com/+++**。使用您的 Office 365
    管理員租戶登錄，然後選擇您的 **Dev One** （Developer） 環境。現在，
    請 **disable** 顯示“Try the new Power Apps experience”的切換按鈕。

- ![](./media/image35.png)

3.  單擊 左側導航菜單中的 Apps。選擇 **New App – \> Start with a page
    design.**

- ![](./media/image36.png)

4.  選擇 **Blank Canvas** 磁貼。

- ![](./media/image37.png)

5.  右鍵單擊 **Screen1** 並選擇 **Rename。**

- ![](./media/image38.png)

6.  重命名為 **HrEmployeeform**

- ![](./media/image39.png)

7.  選擇表單，然後單擊 **Insert –\> Edit form。**

- ![](./media/image40.png)

8.  搜索 **SharePoint**，然後從 **Select a data source** 下拉列表中選擇
    **SharePoint connector**。

- ![](./media/image41.png)

9.  在 **Connect** 下選擇 **SharePoint。**

- ![](./media/image42.png)

10. 在“**Enter SharePoint URL**”文本字段中輸入複製的表單步驟 1 的
    **SharePoint list URL**，然後單擊“**Connect**”。

- ![](./media/image43.png)

11. 選擇 **Employee Onboarding list** ，然後單擊 **Connect** 。

- ![](./media/image44.png)

12. 將表單拖拽並放入容器中。

- ![](./media/image45.png)

13. 將 Form1 容器向下拖動一點，然後單擊 **Insert –\> Rectangle**
    以將標題插入表單。

- ![](./media/image46.png)

14. 將矩形調整為容器寬度。單擊 **Insert –\> Text label**。

- ![](./media/image47.png)

15. 將文本字段的寬度更改為矩形並更新以下屬性。

    - **Tex: New Employee Onboarding Form**

    - **Font Size:** 27

    - **Font weight:** Bold

    - **Text alignment:** Centre

    - **Colour:** White

- ![](./media/image48.png)

16. 將 **Emp_Id、 First Name** 和 **Last_Name** 作為必填字段。

17. 選擇 **Emp_Id** 字段並更改 value **required**。單擊 **Properties**
    下的 **Advanced**，然後選擇 **Unlock to change properties**。

- ![](./media/image49.png)

18. 現在，將 **Required** 值設置為 true。您應該會在字段**Emp_id next**
    看到 star 。

- ![](./media/image50.png)

19. 對 **First Name** 和 **Last_Name** 重複上述兩個步驟

> **注意**：如果您沒有看到字段，請選擇container -\> properties -\>
> Edit（ fields） .add 字段並重新排序。

- ![](./media/image51.png)

20. 選擇 Rectangular form/FormScreen1，然後單擊 **Insert –\> Button**。

- ![](./media/image52.png)

21. 將按鈕拖放到 表單中的**Department**下，並更新下面的屬性。

- **Text**: **Submit**

  ![](./media/image53.png)

22. 單擊 **New Screen** 並選擇 **Success** template。

- ![](./media/image54.png)

23. 選擇新屏幕並 **rename** 為 **Success** ，如下圖所示。

- ![](./media/image55.png)

24. 選擇 **Lb1Successmsg1** 並將文本更改為 **New employee added**。

- ![](./media/image56.png)

25. 現在，單擊 **Insert –\> Icons –\> Back 箭頭。**

- ![](./media/image57.png)

26. 選擇 Back Arrow 並設置以下屬性。

- Tool Tip: **Go Back**

- OnSelect: +++**Back(ScreenTransition.CoverRight)**+++

&nbsp;

- ![](./media/image58.png)

27. 單擊 **HrEmployeeform。** 選擇 **Button** 並選擇 **Onselect**
    並輸入以下公式。

> **注意：** 使用 SharePoint 表單更新公式。

- +++**SubmitForm(*Form1*);ResetForm(*Form1*);Navigate(*Success*)**+++

  ![](./media/image59.png)

28. 選擇 **Form1，** 選擇 **OnSuccess** 並將公式替換為以下公式。

- +++**ResetForm(Self); RequestHide();Notify(“New Employee
  added”,NotificationType.Success)**+++

  ![](./media/image60.png)

29. 單擊 **Save – \> Save as** 按鈕，輸入名稱 **EmpformforHr**，然後單擊
    **Save**。

- ![](./media/image61.png)

30. 選擇表單並將 **Default** 模式 更改為 **New** ，然後單擊 **Save -\>
    Preview** 圖標。

- ![](./media/image62.png)

31. 輸入隨機的 **Emp ID、First Name** 和 **Last Name**，然後單擊
    **Submit** 按鈕。

- ![](./media/image63.png)

32. 您應該會看到 **New employee added message。** 點擊 **Back**
    按鈕**。**

- ![](./media/image64.png)

33. 單擊 **Publish** 按鈕，然後單擊 **Publish this version** 按鈕。

- ![](./media/image65.png)

34. 返回到瀏覽器中的 SharePoint
    選項卡。您應該會在列表中看到您添加的新員工的 employee 記錄。

## 任務 2：為員工創建員工入職 Canvas 應用程序

1.  從 **SharePoint-onboarding**中，複製 URL 並將其保存在記事本中。

- ![](./media/image34.png)

2.  打開一個新選項卡並轉到
    **+++https://make.powerapps.com/+++**。使用您的 Office 365
    管理員租戶登錄，然後選擇您的 **Dev One** 開發人員環境。

3.  單擊 左側導航菜單中的 Apps。選擇 **New App -\> Start with a page
    design**。

- ![](./media/image36.png)

4.  選擇 **Blank Canvas** 磁貼。

- ![](./media/image37.png)

5.  右鍵單擊 **Screen1** 並選擇 **Rename。**

- ![](./media/image38.png)

6.  重命名為 **Employeeform**

- ![](./media/image66.png)

7.  單擊 **Insert** 並選擇 **Edit** form。

- ![](./media/image67.png)

8.  搜索 **SharePoint**，然後從 **Select a data source** 下拉列表中選擇
    **SharePoint connector**。

- ![](./media/image41.png)

9.  在 **Add Connection** 下選擇 **SharePoint。**

- ![](./media/image68.png)

10. 在“輸入 SharePoint URL”文本字段中輸入複製的表單步驟 1 的
    **SharePoint list URL**，然後單擊“**Connect**”。

11. 在 **Choose a list** –\> 下，選擇 **Employee Onboarding list**
    然後單擊 **Next。**

- ![](./media/image43.png)

12. 選擇 **Employee Onboarding list**，然後單擊 **Connect**。

- ![](./media/image44.png)

13. 將表單拖拽並放入容器中。

- ![](./media/image69.png)

14. 在 **Properties** 下選擇 **Form 1** 和 **Display** 模式為 **New**。

- ![](./media/image70.png)

15. 將 Form1 容器向下拖動一點，然後單擊 **Insert -\> Rectangle**
    將標題插入表單。

- ![](./media/image71.png)

16. 將矩形的寬度更改為容器，然後選擇 **Insert –\> Text label**。

- ![](./media/image72.png)

17. 選擇 Label 並設置以下 **properties**。

    - **Text: Employee Onboarding Form**

    - **Font Size: 25**

    - **Font weight: Bold**

    - **Text alignment: Centre**

    - **Colour: White**

- ![](./media/image73.png)

18. 選擇**Emp_Id**字段名稱，然後在 Properties 下將 **Font size** 更改為
    **16** 並將 **Font weight** 更改為
    **Bold**。如果找不到**Emp_Id**字段，請將鼠標懸停在畫布中的 **Form1**
    上，選擇 **Fields \> Add fields**，選擇 **Emp_Id** （如果
    在此列表中也沒有看到Emp_Id，請選擇 **Title**，然後選擇 **Add**。

- ![](./media/image74.png)

19. 對所有字段重複上述步驟。

- ![](./media/image75.png)

20. 選擇 **Orientation location** 項目，並將 **Visible** 屬性設置為
    **false。**

- ![](./media/image76.png)

21. 選擇 **Have you been to orientation yet**？文本字段，然後單擊
    **Edit** label。

- ![](./media/image77.png)

22. 將標簽值更改為 **Orientationdropdown**

- ![](./media/image78.png)

23. 選擇 **Orientation Location data card**並選擇 **Visible**
    並放置在公式下方，如下圖所示。

- +++**If(*Orientationdropdown*.Selected.Value=“No”,true,false)**+++

  ![](./media/image79.png)

24. 單擊 **Save** 並輸入應用程序名稱為： **EmployeeOnboardingForm**
    ，然後單擊 **Save** 按鈕。

- ![](./media/image80.png)

25. **Emp_id**、 **First Name**、 **Last Name** 和 **Manager** 將由 HR
    填充，因此將顯示模式更改為 **View**。

26. 選擇字段並單擊 **Advanced –\> Unlock to change properties**並將
    **Display mode** 更新為 **Parent.DisplayMode.View**

- ![](./media/image81.png)

  ![](./media/image82.png)

  ![](./media/image83.png)

  ![](./media/image84.png)

  ![](./media/image85.png)

27. 選擇 **Work email** Field **Unlock property**，並將 **Required**
    屬性更新為 **true。** 如果需要，對其他字段重複此作。

- ![](./media/image86.png)

28. 選擇 **Form1** 並將 **OnFailed** 字段值更新為

- +++**Notify(“Required Fields can’t be
  empty.”,NotificationType.Error)**+++

  ![](./media/image87.png)

29. 選擇 **OnSuccess** 並將值設置為

- +++**Notify(“Thank you for filling out the
  form”,NotificationType.Success)**+++

  ![](./media/image88.png)

30. 現在，讓我們在表單末尾添加要提交的按鈕。單擊 **Inset –\> Button。**

- ![](./media/image89.png)

31. 更改按鈕的 Properties 並保存表單。

    - Text: **Submit.**

    - Onselect: +++**SubmitForm(*Form1*);NewForm(*Form1*)**+++

- ![](./media/image90.png)

32. 單擊 **Save**，然後單擊 **Preview** 應用程序按鈕。

- ![](./media/image91.png)

33. 輸入詳細信息，然後單擊 **Submit**。

- ![](./media/image92.png)

34. 您應該會看到成功通知。

- ![](./media/image93.png)

35. 關閉預覽窗口。

36. 在 **Tree View** 中單擊“**App**”。選擇“**OnStart**”並輸入以下公式。

- Set(

          onboardinglistitem,

          LookUp(

              'Employee Onboarding',

              ID = Value(Param("ItemID"))

          )

      )

  ![](./media/image94.png)

37. 從 **Tree View** 中選擇 **Form1**。選擇 item 並輸入值，如下所示：
    **onboardinglistitem**

- ![](./media/image95.png)

38. 單擊 **Save** 並 **Publish –\> Publish this version**。

- ![](./media/image96.png)

39. 返回到 **Power Apps 主頁** ，單擊 **Apps –\> Your app –\>
    Details**。

- ![](./media/image97.png)

40. 複製 Web 鏈接以在下一個任務中使用。

- ![](./media/image98.png)

41. 關閉預覽窗口並導航到 SharePoint 選項卡，然後檢查列表中的上述記錄。

- ![](./media/image99.png)

## 任務 3：創建 Power Automate 流以將表單發送給新員工

1.  返回到 **SharePoint** 選項卡並複製 URL。

- ![](./media/image100.png)

2.  打開一個新選項卡，轉到
    +++https://make.powerautomate.com/+++，然後使用您的管理員租戶帳戶登錄。

3.  選擇您的 **Dev One** 開發人員環境。

4.  單擊 左側導航菜單中的 **My flows** 單擊 **New Flow–\> Automated
    Cloud flow。**

- ![](./media/image101.png)

5.  將流程名稱輸入為： **Onboarding new employee**。搜索 **When an item
    is created** 並從 SharePoint 中選擇它，然後單擊 **create**。

- ![](./media/image102.png)

6.  選擇作。單擊 **Site Address –\> Enter custom value。**

- ![](./media/image103.png)

7.  輸入在步驟 1 中複製的 地址 ，然後選擇 **Employee Onboarding**
    列表，如下圖所示。

- ![](./media/image104.png)

8.  單擊 **+** 添加新作。

- ![](./media/image105.png)

9.  搜索並選擇 **Send an email （V2）**

- ![](./media/image106.png)

10. 單擊 to text field 並選擇 **Enter the data from previous step**。

- ![](./media/image107.png)

11. 選擇 **“Work email”。**

- ![](./media/image108.png)

12. 輸入主題行：**Welcome to Firm**，並從上一步中選擇**First Name**。

- ![](./media/image109.png)

13. 在電子郵件的正文中輸入以下數據。插入動態值，如圖所示。

- 高名字姓氏 ,

  請點擊下面的鏈接填寫您的入職表格。

  ![](./media/image110.png)

  ![](./media/image111.png)

14. 輸入在任務 2 中複製的 Web 鏈接 — 並在鏈接末尾添加
    **&itemID=**，然後選擇動態 ID，如下圖所示。

- ![](./media/image112.png)

  ![](./media/image113.png)

15. 剪切鏈接，然後輸入文本： **Onboarding Form**
    ，然後選擇並單擊鏈接圖標。粘貼從上述步驟複製的鏈接。

- ![](./media/image114.png)

16. 立即保存流。

- ![](./media/image115.png)

  ![](./media/image116.png)

## 任務 4：測試流。

1.  返回到 **Power Apps** 選項卡，選擇 **EmpformforHr** 應用。

- ![](./media/image117.png)

2.  如果詢問，則允許權限。

- ![](./media/image118.png)

3.  在表格中填寫您的詳細信息。輸入工作電子郵件作為您的管理員租戶
    ID，然後 **提交** 表單。

- ![](./media/image119.png)

  ![](./media/image120.png)

4.  返回到 Power Automate 流並檢查流狀態。

- ![](./media/image121.png)

  ![](./media/image122.png)

5.  打開一個新選項卡，轉到 **+++https：\outlook.com+++**，然後使用
    Office 365 租戶帳戶登錄並簽入收件箱。單擊 HR 生成的電子郵件中的
    **Onboarding Form** 鏈接。

- ![](./media/image123.png)

**結論：** 完成本實驗後，參與者將全面瞭解如何使用 Microsoft Power
Platform 工具創建和管理員工入職工作流。他們將成功創建和配置 SharePoint
列表以存儲員工數據，構建供 HR 使用的自定義 Power Apps 表單，並設置自動化
Power Automate
流程以與新員工進行無縫溝通。這種體驗將使參與者能夠增強他們的組織入職流程，提高數據準確性，並在人力資源管理中培養更高效的工作流程。總體而言，該實驗室為參與者提供了寶貴的技能，這些技能可以應用於實際場景以優化業務運營。
