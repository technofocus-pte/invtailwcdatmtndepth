# Lab 3 - Build an Automated Flow to Notify Manager When a New Item is Created in Dynamics 365 Business Central

**Objective:** In this lab, participants will learn how to create an
automated flow in Power Automate that sends an email notification
whenever a new item is created in Microsoft Dynamics 365 Business
Central. By following a structured process, participants will become
familiar with triggering flows based on Business Central data,
collecting relevant item information, applying conditional logic, and
executing actions to send email alerts. This hands-on experience will
empower participants to leverage Power Automate for enhancing business
processes and notifications.

**Estimated Time:** 15 mins

### Task 1: Sign up in Microsoft Dynamic 365 Business Central

1.  Navigate to
    +++**https://www.microsoft.com/en-us/dynamics-365/products/business-central**++
    and click on the **Try for Free.**

    <img src="./media/image1.png" style="width:6.26806in;height:2.8in" />

2.  Enter your Office 365 tenant ID and click Next.

    <img src="./media/image2.png"
style="width:6.26806in;height:2.74722in" />

3.  Then click on the **Sign in** and enter the credentials.

    <img src="./media/image3.png"
style="width:6.26806in;height:2.75625in" />

4. Select United states as country or region.

<img src="./media/image4.1.png"
style="width:6.26806in;height:2.64097in" />

6.  Then click on **Get started** to access Business Central.

    <img src="./media/image4.png"
style="width:6.26806in;height:2.64097in" />

7.  Select the **Skip Survey** button to proceed.

    <img src="./media/image5.png"
style="width:6.26806in;height:3.16667in" />

### Task 2: Start Power Automate

1.  Open a new tab next to Dynamic 365 business central and Navigate to
    +++**https://make.powerautomate.com/**+++ in your browser and click on the
    **Sign in** option.

    <img src="./media/image6.png"
style="width:6.26806in;height:2.81667in" />

2.  Enter the **Microsoft 365 tenant id** in the respected field and
    click on the **Next** button.

    <img src="./media/image7.png"
style="width:6.26806in;height:3.66806in" />

3.  Enter the **password** in the respected field and click on the
    **Sign in.**

    <img src="./media/image8.png"
style="width:6.26806in;height:3.75278in" />

4.  From the top navigation bar select the environment **Dev One.**

    <img src="./media/image9.png"
style="width:6.26806in;height:2.87569in" />

5.  Click **+Create** in the left menu.

    <img src="./media/image10.png"
style="width:6.26806in;height:3.85769in" />

6.  Select the **Automated cloud flow** tile.

    <img src="./media/image11.png"
style="width:6.26806in;height:3.06181in" />

### Task 3: Create the Trigger Based on Business Central Data

1.  In the **Flow name** box, enter **Email notification for new
    furniture**.

    <img src="./media/image12.png"
style="width:6.26806in;height:2.86944in" />

2.  In **Choose your flow's trigger search bar**, enter **business
    central**. Scroll down to view the triggers and select **When a
    record is created (V3)** trigger.

3.  Click **Create**.

    <img src="./media/image13.png"
style="width:6.26806in;height:3.94514in" />

4.  Fill in the trigger details:

    1.  **Environment name**: Enter **PRODUCTION**.

    2.  **Company name**: Select **CRONUS USA, Inc.** from the list.

    3.  **Table name**: Select **items**.

    <img src="./media/image14.png"
style="width:6.26806in;height:3.40278in" />

### Task 4: Collect Data from Business Central

1.  Click **+ button** add then select **Add an action**.

    <img src="./media/image15.png"
style="width:6.26806in;height:2.91944in" />

2.  In the **Add an action** window, type **Dynamics 365 Business
    Central** in the search box and choose the **Get record (V3)**
    action.

    <img src="./media/image16.png"
style="width:6.26806in;height:3.18889in" />

3.  Enter the following information:

    1.  **Environment**: **PRODUCTION**.

    2.  **Company name**: Select **CRONUS USA, Inc.**.

    3.  **Table name**: Select **items**.

    4.  **Row id**: Select the **Row Id** token from Dynamic content.

    <img src="./media/image17.png"
style="width:6.26806in;height:3.79375in" />

### Task 5: Make the Condition

1.  Click on the **+ button** below Get record and select **Add an
    action**.

    <img src="./media/image18.png"
style="width:6.26806in;height:3.40764in" />

2.  In the **Add an action** search bar, Enter **Control**. Choose the
    **Condition** action.

    <img src="./media/image19.png"
style="width:6.26806in;height:3.05764in" />

3.  Set the condition:

    1.  In the first **Choose a value** box, select the **Item Category
        Code** token from Dynamic content.

    2.  Keep the **is equal to** option.

    3.  In the second **Choose a value** box, enter **FURNITURE**.

    <img src="./media/image20.png"
style="width:6.26806in;height:2.16806in" />

### Task 6: Create an Action Based on the Condition

1.  In the **If yes** condition window, click **Add an action**.

    <img src="./media/image21.png"
style="width:6.26806in;height:2.21597in" />

2.  Search for **office 365 outlook** in the Add an action window and
    click on see more. In the office 365 outlook trigger select **Send
    an Email (V2).**

    <img src="./media/image22.png"
style="width:6.26806in;height:3.23819in" />

    <img src="./media/image23.png"
style="width:6.26806in;height:4.04514in" />

3.  Fill in the email details:

    1.  **To**: Enter your email address.

    2.  **Subject**: Enter **New furniture released**.

    3.  **Body**:

        1.  Add the text **New** **furniture**.

        2.  Add the token **Number** from Dynamic content.

        3.  Add the token **displayName** from Dynamic content.

        4.  Add the text **has just released.**

    <img src="./media/image24.png"
style="width:6.26806in;height:4.46667in" />

4.  Click **Save** to finalize your flow.

    <img src="./media/image25.png"
style="width:6.26806in;height:2.74653in" />

### Task 7: Test the Flow

1. From the top bar, click on the **Test** button.

    <img src="./media/image26.png"
style="width:6.26806in;height:2.69722in" />

2. Select the **Manual** Process and then click on **Test**.

    <img src="./media/image27.png"
style="width:6.26806in;height:3.45278in" />

3.  Navigate back to the **Business Central website** and from the top
    bar, go to **Sales** 🡪 **Items**.

    <img src="./media/image28.png"
style="width:6.26806in;height:2.79722in" />

4.  Click on the **+ New button**

    <img src="./media/image29.png"
style="width:6.26806in;height:2.81111in" />

5.  Select **ITEM**, and then click **OK**.

    <img src="./media/image30.png"
style="width:6.26806in;height:3.31875in" />

6.  In the Item Category Code field, select **FURNITURE** and in the
    Description field, write **Office Chair.**

    <img src="./media/image31.png"
style="width:6.26806in;height:2.79306in" />

7.  Click on the **Save** button.

    <img src="./media/image32.png"
style="width:6.26806in;height:2.79306in" />

8.  The automated response is received on your provided **Email**.

    <img src="./media/image33.png"
style="width:6.26806in;height:1.89722in" />

### Conclusion: 

By the end of this lab, participants will have
successfully created an automated email notification flow in Power
Automate for new items in Business Central. They will have gained
practical experience in setting up triggers, actions, and conditions,
which are essential skills for automating workflows. Participants will
also understand how to gather and manipulate data from Business
Central effectively, enabling them to streamline communications and
enhance productivity in their respective organizations. This knowledge
will serve as a foundation for further exploration of Power Automate
capabilities in automating various business processes.
