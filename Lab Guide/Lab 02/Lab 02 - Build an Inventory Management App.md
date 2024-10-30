# Lab 2 - Build an Inventory Management App

**Objective:** The objective of this lab is to guide participants
through the creation of a functional inventory management application
using Microsoft Power Apps and Copilot. Participants will learn to set
up their Dataverse environment, design app screens, manage data, and
automate inventory restocking workflows with Power Automate.

**Estimated Time:** 40 min

## Exercise 1: Build Inventory Management App

### Task 1: Verifying your Dataverse environment 

1.  Open a browser and go to
    <https://admin.powerplatform.microsoft.com>. Sign in with your work
    /school/admin account.

2.  Select **Environments** on the left navigation. The **Developer
    environment** should have been created for you as shown in the image
    below. (This environment is created automatically as soon as you
    provide Microsoft Power App for Developer license using your
    work/school accounts. The name of the environment will be different
    for every admin account.)

    ![](./media/image1.png)

3.  Use the same developer environment to execute all the exercises of
    this lab.

    > **Note**: **Dev one** developer environment is used in this lab. The
name of the environment can be different for different users. Make
sure to select your developer environment.

### Task 2: Create inventory management app using Copilot.

1.  Open a browser and go to <https://apps.powerapps.comand sign in
    with Work, School or admin tenant account.

2.  Click on the environment on right top corner and select **your
    developer** environment (Dev one is a developer environment used in
    this lab guide)

    ![](./media/image2.png)

3.  Enter the below prompt and click on **the Enter** button.

    build a candy inventory management app

    ![](./media/image3.png)

4.  Select the **Start with Copilot** tile

    ![](./media/image4.png)


5.  Enter below prompt and click on **Generate** to create table with
    the help of Copilot

    **Candy Inventory management**

    ![](./media/image5.png)


6.  Copilot generates the tables as shown in the below image.

    ![](./media/image6.png)

7.  Click on three dots next to Candy and then click on **View data.**

    ![](./media/image7.png)


8.  The data in the Candy table should have data as shown in the image
    below.

    ![](./media/image8.png)


9.  Click on **Supplier -\View data** and explore the data and then
    close the view window.

    ![](./media/image9.png)


10. Update one of the Supplier email ids with your work/personal working
    email id

    ![](./media/image10.png)


11. Click on **Order -\View data**

    ![](./media/image11.png)


12. Ener below prompt in the text box and click on Enter. This column is
    required to notify when the quantity went below the reorder point.

    Add reorder point column to Candy table

    <img src="./media/image12.png"
style="width:6.49306in;height:2.82639in" />

13. Add candyInStock column with type as Number. If Quantity is less
    than reorder points, then Quantity column will automate add with
    candyInStock.

    Add **candyInStock** column to Candy table with sample stock count

    ![](./media/image13.png)

14. The table has been updated with reorder point column and Candy in
    Stock column 

    ![](./media/image14.png)


15. Click on the **Save and open app** button

    ![](./media/image15.png)

16. On **Done working?** window, click on **Save and open app** and wait
    for the app to be created.

    ![](./media/image16.png)

    ![](./media/image17.png)


17. Skip the welcome window.

    ![](./media/image18.png)


18. The app gets created and should look like the image below.

    ![](./media/image19.png)


19. Click on the **save** button and enter the name **MSCandy Inventory
    management app**, then click on **Save** button.

    ![](./media/image20.png)


    ![](./media/image21.png)


20. Explore the app. Click on **the Candy screen** from Tree view. You
    can update the label of the screen to **Candy Inventory management**

    ![](./media/image22.png)


21. Explore the Supplier screen and update as per your requirements.

    ![](./media/image23.png)


### Task 3: Create candy quality Screen

1.  Click on **New Screen** and select **Blank** template.

    ![](./media/image24.png)

2.  Select the new screen and right click -\**rename**

    ![](./media/image25.png)


3.  Name the screen as **Candy quality screen**

    ![](./media/image26.png)


4.  Click on Screen area and select **Create a new table(preview)**

     ![](./media/image27.png)


5.  Click on **New table -\Add columns and data.**

    ![](./media/image28.png)


6.  Click on **New column-\Edit column.**

    ![](./media/image29.png)


7.  Enter the Display name as **Candy ID** and then click on **Update**
    button.

    ![](./media/image30.png)


8.  Click on New column and enter below details and then click on
    **Save**.

    - **Display Name:** Candy Name
    - **Data Type:** Choice
    - **Required:** Yes.
    - **Choices:**add below choices

        - Chocolate Bar

        - Gummy Bears

        - Jellybeans

        - Lollipop

        - Sour Patch Kids

    ![](./media/image31.png)


9.  Click on New Column and add a column with below details and then
    click on **Save**.

    - **Display Name:** Candy Quality
    - **Data type:** Choice
    - **Required:** Yes
    - **Choice –** labels
      - Defective
      - Nondefective

    ![](./media/image32.png)


    > **Note:** You can add more columns as per your app requirements.

10.  Edit the table name and update with **Candy Quality**check.

    ![](./media/image33.png)


11.  Click on **Save and exit -\Save and exit**.

    ![](./media/image34.png)

12.  You will navigate back to the Power Apps app page. Select the newly
    added screen and click on Insert and select **Edit form** as shown
    in below image.

    ![](./media/image35.png)


13.  Click the container and select the data source table as **Candy
    Qualities table**.

    ![](./media/image36.png)

14.  You should see the form like below image.

    ![](./media/image37.png)


15.  Adjust the table to the middle of the page. Click on **Insert-\>
    Text label.**

    ![](./media/image38.png)


16.  Adjust the text label and enter the text as: **Candy Quality check**
    and update the styles of text.

    ![](./media/image39.png)


17.  Select the **Form**. Click on **Insert** and select **Button**.

    ![](./media/image40.png)


18.  Drag the submit button and place it in the middle of the container.
    Select the button and change the **properties** text to **Submit**
    as shown in below image.

    ![](./media/image41.png)

19.  Select the **Submit** button and select **OnSelect** function and
    enter below function.

    > **Note**: Form4 in the formula should be replaced with your form name

    SubmitForm(*Form4*);NewForm(*Form4*)    

    ![](./media/image42.png)


20. Select the container, under properties, select **Default** mode to
    **New**.

    ![](./media/image43.png)


21. Click on **Save** and then click on **Preview app** button as shown
    in below image.

    ![](./media/image44.png)

22. Enter Candy details and then click on the Submit button.

    ![](./media/image45.png)


23. Switch back to your Candy quality table in Dataverse environment and
    you should see the record added above.

    ![](./media/image46.png)


24. Close the preview window.

## Exercise 2: Create a Power Automate flow to restock the inventory.

### Task 1: Create a Power platform flow to trigger restock email

1.  Switch back to Power Automate tab and click on **My flows** -\>
    **New flow -\Automated cloud flow.**

    ![](./media/image47.png)


2.  Enter the flow name as: **Candy Restock Flow**. Search for **When a
    row** is and select Dataverse’s **When a row is added or modified**
    action and then click on **Create**.

    ![](./media/image48.png)


3.  Select the action and set the parameters below.

    - Change Type; Added or Modified
    - Table Nam: Candies
    - Scope: Organization

    ![](./media/image49.png)


4.  Add an action after an action **“when a row is added, modified or
    deleted”.**

    ![](./media/image50.png)


5.  Search for **Condition** and select **Control’s Condition** action.

    ![](./media/image51.png)

6.  Click on Chose value and select choose from previous step dynamic
    action.

     ![](./media/image52.png)


7.  Search for **Quantity** column and select it.

    ![](./media/image53.png)


8.  Select a condition that **is less than** and click on Enter data
    from previous action.

    ![](./media/image54.png)


9.  Search for the **Reorder points** column and select it.

    ![](./media/image55.png)


10.  **Add an action** under **True** condition.

    ![](./media/image56.png)


11.  Select **Approvals** action.

    ![](./media/image57.png)


12.  Select **Start and wait for an Approvals.**

    ![](./media/image58.png)


13.  Select Approval Type as: **Approve/Reject – First to Respond**.
    Enter Title as: **Approve to Restock –** and click on Dynamic button
    to select the data from previous step.

    ![](./media/image59.png)


14.  Search for **Candy** **Name** and select it.

    ![](./media/image60.png)

15.  Enter below details.

    Assigned to: Your work email id.

    Details:

    Hi Sir,  
    
    is out of stock - for customers to place an order. Please approve to
    restock.  
    
    Thanks

    > Note: You can customize the details section as per your requirements.

    ![](./media/image61.png)


16. **Add an action** after **approval** action.

    ![](./media/image62.png)


17. Search for **condition** and select **Control – Condition**.

    ![](./media/image63.png)


18. Click on Choose value and select **Outcome** from Start and wait for
    an Approval action.

    ![](./media/image64.png)


19. Select the condition as **is equal to** and enter the value as
    **Approve**.

    ![](./media/image65.png)

20. Under **True** condition, **add an action**.

    ![](./media/image66.png)


21. Search for **Update Row** and select it from **Microsoft Dataverse**
    section.

    ![](./media/image67.png)


22. Select your **Candy** table and Click on **Row Id** select Dynamic
    action.

    ![](./media/image68.png)


23. Search for a unique identifier column from your table and select it.

    ![](./media/image69.png)


24. Click on **Advanced Parameters** drop down and select **Quantity**
    column.

    ![](./media/image70.png)

25. Enter the below function (you type in your app) and collapse the
    action.

    > **Note:** the below function does not work for you as your column
schema name might be different. Go to table-\column and copy schema
name

    add(triggerBody()?\['cr8a3_Quantity'\],triggerBody()?\['cr8a3_CandyInStock'\])

    ![](./media/image71.png)


26. Click on **the Save** button to save the Power Automate flow.

    ![](./media/image72.png)


### Task 2: Test the restock flow

1.  Switch back to **PowerApps** tab and click on **Candy** screen from
    left Tree view and select **play**.

    > Note: You can update the Title of the screen

    ![](./media/image73.png)


2.  Select the Candy and click on **Edit**.

    ![](./media/image74.png)


3.  Enter the **Quantity** value **less than reorder points** and
    **commit** changes.

    ![](./media/image75.png)


4.  Switch back to Power Automate flow tab and click on My flows -\>
    Your flow.

    ![](./media/image76.png)

5.  Flow is running and is at condition.

    ![](./media/image77.png)


6.  Open a new tab and go to https://outlook.com and sign in with your
    work/admin account. You should have got an email to restock.
    **Approve** and **submit**.

    ![](./media/image78.png)


    ![](./media/image79.png)


7.  The flow is successful now.

    ![](./media/image80.png)


    ![](./media/image81.png)


8.  Switch back to PowerApps and check the above product quantity. It
    should have been updated (Candy in stock+ Quantity when its less
    than reorder point)

    ![](./media/image82.png)


### Conclusion:

By the end of this lab, participants will be able to
verify their Dataverse environment, build an inventory management app
utilizing Copilot, design a Candy Quality Check screen with custom
fields, and implement Power Automate flows to trigger restock requests
based on inventory levels. Additionally, they will gain skills in
testing and validating automated workflows to ensure accurate inventory
updates following approval processes. This structured approach will
empower participants to effectively leverage the capabilities of Power
Apps and Power Automate, enhancing their skills in app development and
process automation.
