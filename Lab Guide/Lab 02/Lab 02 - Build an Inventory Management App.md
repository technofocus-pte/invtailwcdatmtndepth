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

    <img src="./media/image1.png" style="width:6.5in;height:1.75903in"
alt="A screenshot of a computer Description automatically generated" />

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

    <img src="./media/image2.png" style="width:6.5in;height:2.5in" />

3.  Enter the below prompt and click on **the Enter** button.

    build a candy inventory management app

    <img src="./media/image3.png" style="width:6.5in;height:3.03889in" />

4.  Select the **Start with Copilot** tile

    <img src="./media/image4.png" style="width:6.5in;height:3.08333in"
alt="A screenshot of a computer Description automatically generated" />

5.  Enter below prompt and click on **Generate** to create table with
    the help of Copilot

    **Candy Inventory management**

    <img src="./media/image5.png" style="width:6.49306in;height:4.09722in"
    alt="A screenshot of a computer Description automatically generated" />

6.  Copilot generates the tables as shown in the below image.

    <img src="./media/image6.png" style="width:6.5in;height:2.84375in"
alt="A screenshot of a computer Description automatically generated" />

7.  Click on three dots next to Candy and then click on **View data.**

    <img src="./media/image7.png"
style="width:6.48611in;height:3.18056in" />

8.  The data in the Candy table should have data as shown in the image
    below.

    <img src="./media/image8.png" style="width:6.5in;height:4.23889in"
alt="A screenshot of a computer Description automatically generated" />

9.  Click on **Supplier -\View data** and explore the data and then
    close the view window.

    <img src="./media/image9.png" style="width:6.5in;height:3.87153in"
alt="A screenshot of a computer Description automatically generated" />

10. Update one of the Supplier email ids with your work/personal working
    email id

    <img src="./media/image10.png"
style="width:6.49306in;height:4.0625in" />

11. Click on **Order -\View data**

    <img src="./media/image11.png" style="width:6.5in;height:3.87014in"
alt="A screenshot of a computer Description automatically generated" />

12. Ener below prompt in the text box and click on Enter. This column is
    required to notify when the quantity went below the reorder point.

    Add reorder point column to Candy table

    <img src="./media/image12.png"
style="width:6.49306in;height:2.82639in" />

13. Add candyInStock column with type as Number. If Quantity is less
    than reorder points, then Quantity column will automate add with
    candyInStock.

    Add **candyInStock** column to Candy table with sample stock count

    <img src="./media/image13.png"
style="width:6.4375in;height:3.22917in" />

14. The table has been updated with reorder point column and Candy in
    Stock column 

    <img src="./media/image14.png" style="width:6.5in;height:2.99167in"
alt="A screenshot of a computer Description automatically generated" />

15. Click on the **Save and open app** button

    <img src="./media/image15.png" style="width:6.45in;height:3.175in" />

16. On **Done working?** window, click on **Save and open app** and wait
    for the app to be created.

    <img src="./media/image16.png" style="width:6.5in;height:3.34167in" />

    <img src="./media/image17.png" style="width:6.5in;height:4.08542in"
alt="A screenshot of a computer Description automatically generated" />

17. Skip the welcome window.

    <img src="./media/image18.png"
style="width:6.49167in;height:3.60833in" />

18. The app gets created and should look like the image below.

    <img src="./media/image19.png" style="width:6.5in;height:3.16042in"
alt="A screenshot of a computer Description automatically generated" />

19. Click on the **save** button and enter the name **MSCandy Inventory
    management app**, then click on **Save** button.

    <img src="./media/image20.png"
style="width:6.49306in;height:3.06944in" />

    <img src="./media/image21.png" style="width:6.5in;height:3.18542in"
alt="A screenshot of a computer Description automatically generated" />

20. Explore the app. Click on **the Candy screen** from Tree view. You
    can update the label of the screen to **Candy Inventory management**

    <img src="./media/image22.png" style="width:6.5in;height:3.49097in"
alt="A screenshot of a computer Description automatically generated" />

21. Explore the Supplier screen and update as per your requirements.

    <img src="./media/image23.png" style="width:6.5in;height:3.18194in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Create candy quality Screen

1.  Click on **New Screen** and select **Blank** template.

    <img src="./media/image24.png" style="width:6.5in;height:5.3125in" />

2.  Select the new screen and right click -\**rename**

    <img src="./media/image25.png"
style="width:6.49306in;height:5.84028in" />

3.  Name the screen as **Candy quality screen**

    <img src="./media/image26.png"
style="width:6.49306in;height:5.26389in" />

4.  Click on Screen area and select **Create a new table(preview)**

    <img src="./media/image27.png"
style="width:6.49306in;height:3.55556in" />

5.  Click on **New table -\Add columns and data.**

    <img src="./media/image28.png"
style="width:6.49306in;height:4.45139in" />

6.  Click on **New column-\Edit column.**

    <img src="./media/image29.png"
style="width:6.49306in;height:4.79861in" />

7.  Enter the Display name as **Candy ID** and then click on **Update**
    button.

    <img src="./media/image30.png"
style="width:6.49306in;height:4.95833in" />

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

    <img src="./media/image31.png" style="width:6.5in;height:5.90069in"
alt="A screenshot of a computer Description automatically generated" />

9.  Click on New Column and add a column with below details and then
    click on **Save**.

    - **Display Name:** Candy Quality
    - **Data type:** Choice
    - **Required:** Yes
    - **Choice –** labels
      - Defective
      - Nondefective

    <img src="./media/image32.png" style="width:6.5in;height:4.39236in"
alt="A screenshot of a computer Description automatically generated" />

    > **Note:** You can add more columns as per your app requirements.

10.  Edit the table name and update with **Candy Quality**check.

    <img src="./media/image33.png" style="width:6.5in;height:4.37986in"
alt="A screenshot of a computer Description automatically generated" />

11.  Click on **Save and exit -\Save and exit**.

    <img src="./media/image34.png" style="width:6.5in;height:3.09583in" />

12.  You will navigate back to the Power Apps app page. Select the newly
    added screen and click on Insert and select **Edit form** as shown
    in below image.

    <img src="./media/image35.png"
style="width:6.49375in;height:4.95486in" />

13.  Click the container and select the data source table as **Candy
    Qualities table**.

    <img src="./media/image36.png" style="width:6.5in;height:3.49375in" />

14.  You should see the form like below image.

    <img src="./media/image37.png" style="width:6.5in;height:3.21736in"
alt="A screenshot of a computer Description automatically generated" />

15.  Adjust the table to the middle of the page. Click on **Insert-\>
    Text label.**

    <img src="./media/image38.png"
style="width:6.49375in;height:4.46181in" />

16.  Adjust the text label and enter the text as: **Candy Quality check**
    and update the styles of text.

    <img src="./media/image39.png" style="width:6.5in;height:4.08958in"
alt="A screenshot of a computer Description automatically generated" />

17.  Select the **Form**. Click on **Insert** and select **Button**.

    <img src="./media/image40.png"
style="width:6.49375in;height:4.44861in" />

18.  Drag the submit button and place it in the middle of the container.
    Select the button and change the **properties** text to **Submit**
    as shown in below image.

    <img src="./media/image41.png" style="width:6.5in;height:3.18611in" />

19.  Select the **Submit** button and select **OnSelect** function and
    enter below function.

    > **Note**: Form4 in the formula should be replaced with your form name

    SubmitForm(*Form4*);NewForm(*Form4*)    

    <img src="./media/image42.png"
style="width:6.49375in;height:3.71181in" />

20. Select the container, under properties, select **Default** mode to
    **New**.

    <img src="./media/image43.png"
style="width:6.49375in;height:2.13472in" />

21. Click on **Save** and then click on **Preview app** button as shown
    in below image.

    <img src="./media/image44.png" style="width:6.5in;height:3.14722in" />

22. Enter Candy details and then click on the Submit button.

    <img src="./media/image45.png" style="width:6.5in;height:2.71806in"
alt="A screenshot of a computer Description automatically generated" />

23. Switch back to your Candy quality table in Dataverse environment and
    you should see the record added above.

    <img src="./media/image46.png" style="width:6.5in;height:2.20486in"
alt="A screenshot of a computer Description automatically generated" />

24. Close the preview window.

## Exercise 2: Create a Power Automate flow to restock the inventory.

### Task 1: Create a Power platform flow to trigger restock email

1.  Switch back to Power Automate tab and click on **My flows** -\>
    **New flow -\Automated cloud flow.**

    <img src="./media/image47.png"
style="width:6.49375in;height:3.39722in" />

2.  Enter the flow name as: **Candy Restock Flow**. Search for **When a
    row** is and select Dataverse’s **When a row is added or modified**
    action and then click on **Create**.

    <img src="./media/image48.png"
style="width:6.49375in;height:4.16042in" />

3.  Select the action and set the parameters below.

    - Change Type; Added or Modified
    - Table Nam: Candies
    - Scope: Organization

    <img src="./media/image49.png"
style="width:6.49167in;height:3.70833in" />

4.  Add an action after an action **“when a row is added, modified or
    deleted”.**

    <img src="./media/image50.png"
style="width:6.08333in;height:4.32708in" />

5.  Search for **Condition** and select **Control’s Condition** action.

    <img src="./media/image51.png" style="width:6.49375in;height:3.75in" />

6.  Click on Chose value and select choose from previous step dynamic
    action.

    <img src="./media/image52.png"
style="width:6.49375in;height:3.85903in" />

7.  Search for **Quantity** column and select it.

    <img src="./media/image53.png"
style="width:6.49375in;height:3.85903in" />

8.  Select a condition that **is less than** and click on Enter data
    from previous action.

    <img src="./media/image54.png"
style="width:6.49375in;height:3.80139in" />

9.  Search for the **Reorder points** column and select it.

    <img src="./media/image55.png"
style="width:6.49375in;height:3.87153in" />

10.  **Add an action** under **True** condition.

    <img src="./media/image56.png"
style="width:6.44861in;height:4.80764in" />

11.  Select **Approvals** action.

    <img src="./media/image57.png"
style="width:6.49375in;height:3.21806in" />

12.  Select **Start and wait for an Approvals.**

    <img src="./media/image58.png"
style="width:6.49375in;height:3.58333in" />

13.  Select Approval Type as: **Approve/Reject – First to Respond**.
    Enter Title as: **Approve to Restock –** and click on Dynamic button
    to select the data from previous step.

    <img src="./media/image59.png"
style="width:6.49375in;height:4.14097in" />

14.  Search for **Candy** **Name** and select it.

    <img src="./media/image60.png" style="width:6.49167in;height:3.25in" />

15.  Enter below details.

    Assigned to: Your work email id.

    Details:

    Hi Sir,  
    
    is out of stock - for customers to place an order. Please approve to
    restock.  
    
    Thanks

    > Note: You can customize the details section as per your requirements.

    <img src="./media/image61.png" style="width:6.5in;height:3.51806in"
alt="A screenshot of a computer Description automatically generated" />

16. **Add an action** after **approval** action.

    <img src="./media/image62.png"
style="width:6.49375in;height:5.00625in" />

17. Search for **condition** and select **Control – Condition**.

    <img src="./media/image63.png"
style="width:6.49375in;height:3.35903in" />

18. Click on Choose value and select **Outcome** from Start and wait for
    an Approval action.

    <img src="./media/image64.png"
style="width:6.49375in;height:5.08333in" />

19. Select the condition as **is equal to** and enter the value as
    **Approve**.

    <img src="./media/image65.png" style="width:6.375in;height:4.225in" />

20. Under **True** condition, **add an action**.

    <img src="./media/image66.png"
style="width:6.49375in;height:4.70486in" />

21. Search for **Update Row** and select it from **Microsoft Dataverse**
    section.

    <img src="./media/image67.png"
style="width:6.49375in;height:4.44236in" />

22. Select your **Candy** table and Click on **Row Id** select Dynamic
    action.

    <img src="./media/image68.png"
style="width:6.49167in;height:3.63333in" />

23. Search for a unique identifier column from your table and select it.

    <img src="./media/image69.png"
style="width:6.49167in;height:2.93333in" />

24. Click on **Advanced Parameters** drop down and select **Quantity**
    column.

    <img src="./media/image70.png" style="width:6.5in;height:5.16667in" />

25. Enter the below function (you type in your app) and collapse the
    action.

    > **Note:** the below function does not work for you as your column
schema name might be different. Go to table-\column and copy schema
name

    add(triggerBody()?\['cr8a3_Quantity'\],triggerBody()?\['cr8a3_CandyInStock'\])

    <img src="./media/image71.png"
style="width:6.49167in;height:4.24167in" />

26. Click on **the Save** button to save the Power Automate flow.

    <img src="./media/image72.png"
style="width:6.49375in;height:2.85903in" />

### Task 2: Test the restock flow

1.  Switch back to **PowerApps** tab and click on **Candy** screen from
    left Tree view and select **play**.

    > Note: You can update the Title of the screen

    <img src="./media/image73.png"
style="width:6.49167in;height:2.66667in" />

2.  Select the Candy and click on **Edit**.

    <img src="./media/image74.png"
style="width:6.49167in;height:2.25833in" />

3.  Enter the **Quantity** value **less than reorder points** and
    **commit** changes.

    <img src="./media/image75.png"
style="width:6.49167in;height:2.51667in" />

4.  Switch back to Power Automate flow tab and click on My flows -\>
    Your flow.

    <img src="./media/image76.png" style="width:6.5in;height:4.44167in" />

5.  Flow is running and is at condition.

    <img src="./media/image77.png" style="width:6.5in;height:4.81806in"
alt="A screenshot of a computer Description automatically generated" />

6.  Open a new tab and go to https://outlook.com and sign in with your
    work/admin account. You should have got an email to restock.
    **Approve** and **submit**.

    <img src="./media/image78.png" style="width:6.5in;height:3.30694in"
alt="A screenshot of a computer Description automatically generated" />

    <img src="./media/image79.png"
style="width:6.49167in;height:4.75833in" />

7.  The flow is successful now.

    <img src="./media/image80.png" style="width:6.5in;height:4.30278in"
alt="A screenshot of a computer Description automatically generated" />

    <img src="./media/image81.png" style="width:6.5in;height:4.05486in"
alt="A screenshot of a computer Description automatically generated" />

8.  Switch back to PowerApps and check the above product quantity. It
    should have been updated (Candy in stock+ Quantity when its less
    than reorder point)

    <img src="./media/image82.png" style="width:6.5in;height:3.07639in"
alt="A screenshot of a computer Description automatically generated" />

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
