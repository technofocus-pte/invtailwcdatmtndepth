# Lab 5 - Creating and Analyzing the Accounts Payable Refund Process

**Objective:** The objective of this lab is to create and analyze an
accounts payable refund process using Power Automate Process Mining
capabilities. Participants will learn to import data from a CSV file,
create a new process, and utilize the Process Mining desktop app to
analyze key performance indicators (KPIs) and other metrics to gain
insights into the efficiency and performance of the accounts payable
refund process.

**Estimated Time:** 30 mins

### Task 1: Create a process

1.  Go to +++**https://make.powerautomate.com/**+++. If asked, sign in with your Office 365 tenant credentials. Select **United States** as country/region and then select     **Get started**.

    <img src="./media/image1.png" style="width:4.70255in;height:2.8375in"
alt="A screenshot of a computer Description automatically generated with medium confidence" />

2.  Select your environment – **Dev One**.

    <img src="./media/image2.png" style="width:6.5in;height:1.37153in"
alt="A screenshot of a computer Description automatically generated" />

3.  On the navigation pane to the left, select **More** 🡪 **Process
    mining**.

    <img src="./media/image3.png" style="width:6.5in;height:2.75764in" />

4.  In the **Create new process** section, select **Start here**.

    <img src="./media/image4.png" style="width:6.5in;height:2.84375in" />

5.  In the **Create a new process** screen, enter a process name –
    +++**Processmining**+++, and then select **Import data**, select **Data flow** and then select
    **Continue**. (Optional) Enter a description for your process.

    <img src="./media/image5.png" style="width:6.5in;height:4.56042in"
alt="A screenshot of a computer Description automatically generated" />

### Task 2: Import data

1.  In the **Choose a data source** screen, select **Text/CSV**.

    <img src="./media/image6.png"
style="width:4.83334in;height:3.71181in" />

2.  Under the **Connection settings** heading, select **Upload file
    (Preview)**.

    <img src="./media/image7.png" style="width:6.5in;height:4.10347in" />

3.  Select **Browse**.

    <img src="./media/image8.png" style="width:6.5in;height:4.09861in"
alt="A screenshot of a computer Description automatically generated" />

4.  Find and select **SampleData_AP_Refunds_Financial_EventLog.csv**.
    Location: **C:\Labfiles**

5.  Select **Open**.

    <img src="./media/image9.png" style="width:6.5in;height:4.4in"
alt="A screenshot of a computer Description automatically generated" />

6.  If you're asked to authenticate, select **Sign in** and follow the
    prompts. (Configure Pop-up blocker to allow.)

    <img src="./media/image10.png" style="width:6.5in;height:4.08194in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select **Next**.

    <img src="./media/image11.png" style="width:6.5in;height:5.02639in" />

8.  Preview file data and select **Next**.

    <img src="./media/image12.png" style="width:6.5in;height:4.03958in"
alt="A screenshot of a computer Description automatically generated" />

9.  When you see the power query, which allows you to transform your
    data, select **Next**.

    <img src="./media/image13.png" style="width:6.5in;height:4.00486in" />

10. Match the **Attribute Name** from sample data to the **Attribute
    Type** as appropriate.

    <img src="./media/image14.png" style="width:6.5in;height:4.30139in" />

11. In this sample, the data attributes you’ll change
    are **InvoiceValue**, **Resource**, **StartTimestamp**, **EndTimestamp**, **CaseId**,
    and **ActivityName** as follow.
    
    **InvoiceValue** – Financial per case (first event)
    
    **Resource** – Resourse
    
    **StartTimestamp** – Event Start
    
    **EndTimestamp** – Event End
    
    **CaseId** – Case ID
    
    **ActivityName** - Activity

    <img src="./media/image15.png" style="width:6.5in;height:4.63056in" />

13. When you're **finished**, the attribute mapping should look like the
    following screenshot.

    <img src="./media/image16.png" style="width:6.5in;height:4.8125in" />

14. Select **Save and analyze**. The analysis might take a few minutes
    to run.

    <img src="./media/image17.png" style="width:6.5in;height:4.64444in"
alt="A screenshot of a computer Description automatically generated" />

15. When the **analysis process is complete**, you’ll see a process map
    and a dashboard with other insights about your process. On the
    dashboard, you can view many metrics that will help you **analyze
    your process.**

    <img src="./media/image18.png" style="width:6.5in;height:2.75701in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Analyze a process

Let’s take the analysis of our process beyond KPIs. We'll use the Power
Automate Process Mining desktop app, where you can edit and analyze your
processes created in the process mining capability.

1.  From the top bar, click on the **Download process Mining app**.

    <img src="./media/image19.png" style="width:6.5in;height:1.59514in"
alt="A screenshot of a computer Description automatically generated" />

2.  Double click on **PowerAutomateProcessMining** App installer file in
    Downloads.

    <img src="./media/image20.png" style="width:6.5in;height:4.05556in"
alt="A screenshot of a computer Description automatically generated" />

3.  Click on **Install**.

    <img src="./media/image21.png" style="width:6.5in;height:5.2625in" />

4. After Installing Processmining app, the app is automatically launch, if not please please launch app manually. After launching app, select **English** as language and click on **Next Step**.

    <img src="./media/image21a.png" style="width:6.5in;height:5.2625in" />

5. Select all the **check boxes** as shown in image and click on the **Next**.

    <img src="./media/image21b.png" style="width:6.5in;height:5.2625in" />

6. Then click on **Apply and mine** button.

    <img src="./media/image21c.png" style="width:6.5in;height:5.2625in" />

7. Then select **Use** button, it will navigate to login window.

   <img src="./media/image21d.png" style="width:6.5in;height:5.2625in" />

8. Enter you admin tenant Id and click on the **Sign In** button.

   <img src="./media/image21e.png" style="width:6.5in;height:5.2625in" />

9. Then enter your admin tenant password and click on **Sign in**.

   <img src="./media/image21f.png" style="width:6.5in;height:5.2625in" />

10. If pop up appears saying ‘Stay signed in to all your apps’ then select **No, sign in to this app only**.

    <img src="./media/image22.1.png" style="width:6.5in;height:5.2625in" />

11. On the Power Automate Process Mining app toolbar, select the
    environment – **Dev** **One** from the top right.

    <img src="./media/image23.png" style="width:6.5in;height:2.98611in" />

12. Search for the process that you created with the process mining
    capability in Power Automate (**Processmining**).

13. Select **Default** to display the default view. You’re ready to use
    the advanced capabilities of the Process Mining desktop app.

    <img src="./media/image24.png" style="width:6.5in;height:2.07639in"
alt="A screenshot of a computer Description automatically generated" />

    > Note: If It shows an message related to **Model size is too large for your PC configuration** and give Yes and No option for execution, select **Yes**.

       <img src="./media/image21g.png" style="width:6.5in;height:5.2625in" />


14. On the **Customize** panel toolbar, select **Frequency** (the first
    icon), and then select **Case count** in the **Metric** dropdown
    menu.

    <img src="./media/image25.png" style="width:6.5in;height:3.02083in"
alt="A screenshot of a computer Description automatically generated" />

    > The process map displays the number of cases of the process that
include the activity specified at each node.

15. On the **Customize** panel, select the **Performance** (clock icon),
    and then select **Mean duration** from the dropdown menu.

    <img src="./media/image26.png" style="width:6.5in;height:2.95139in"
alt="A screenshot of a computer Description automatically generated" />

    > Notice that the **Refund with special voucher** step has a long mean
duration compared to other steps.

    <img src="./media/image27.png" style="width:2.89624in;height:2.1253in" alt="A picture containing text, screenshot, circle, diagram Description automatically generated" />

16. On the **Customize** panel, select **Finance** (the piece of paper
    icon), and then select **Mean** from the **Metric** dropdown menu.

    <img src="./media/image28.png" style="width:6.5in;height:2.98819in" />

    > Notice that the same **Refund with Special Voucher** step involves
only \$631.11 in invoice value, which is less than half of most of the
other steps.

    <img src="./media/image29.png" style="width:3.52083in;height:1in"
alt="Screenshot of the refund with special voucher mean." />

17. Select **Save**.

    <img src="./media/image30.png" style="width:6.5in;height:0.62153in" />

### Conclusion:

In this lab, participants created and analyzed an
accounts payable refund process using Power Automate Process Mining
capabilities. By importing CSV data, they constructed a detailed process
map and dashboard, allowing them to examine key performance indicators
(KPIs) and process metrics. Through the Power Automate Process Mining
desktop app, participants performed deeper analysis, identifying
inefficiencies such as long durations and lower invoice values in
specific steps. This lab demonstrated how Process Mining can help
organizations optimize financial workflows, improve efficiency, and
streamline accounts payable operations.
