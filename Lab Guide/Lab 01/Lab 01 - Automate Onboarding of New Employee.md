# **Lab 1 - Automate Onboarding of New Employee**

**Objective:** The primary objective of this lab is to guide
participants in automating the employee onboarding process using
Microsoft Power Platform. The exercises focus on creating SharePoint
lists to store employee and HR information, customizing forms in Power
Apps for data entry, and implementing automated workflows using Power
Automate. Participants will learn to leverage SharePoint for data
management, utilize Power Apps to enhance user experience, and integrate
automated processes to streamline onboarding tasks. This hands-on
experience aims to equip participants with practical skills to
effectively manage and automate HR processes within their organizations.

**Estimated time:** 60 mins

# Exercise 1: Create Employees, HR and Manager list in Share point.

## Task 1: Verifying your Dataverse environment 

1.  Open a browser and go to
    +++**https://admin.powerplatform.microsoft.com**+++. Sign in with your
    office 365 tenant credential.

2.  Select **Manage** > **Environments** on the left navigation. The **Dev One** Developer
    environment should have been created for you as shown in the image
    below.

    
    ![](./media/image1.2.1.png)

3.  Use the same developer environment to execute all the exercises of
    this lab.

## Task 2: Create a site in SharePoint 

1.  On the **Power Platform admin center**, select App launcher from the top left corner. Select **SharePoint**
    from list of **apps**.

    ![](./media/image2.1.png)

2.  Select **NOT NOW** on the **News from sites** pop-up.

    ![](./media/image2.2.png)

3.  Click on **+Create site** on top menu.

    ![](./media/image4.png)


4.  Select **Communication site** tile in **Create a site** window.

    ![](./media/image5.png)


5.  Scroll down and select **Blank** template.

    ![](./media/image6.png)


6.  Click on **Use template**.

    ![](./media/image7.png)


7.  Enter Site name and description then click on **Next** button.

    - Site Name: +++**Contoso Corp**+++

    - Site Description: +++**Onboarding new employee.**+++


    ![](./media/image8.png)


8.  Keep the default language and then click on **Create Site.**

    ![](./media/image9.png)


    ![](./media/image10.png)


## Task 3: Create an Employees list in SharePoint site from CSV file

1.  Click on **Home --> New --> List.**


    ![](./media/image11.png)


2.  Select **From CSV** tile from **Create a list** window.

  

    ![](./media/image3.2.1.png)


3.  Click on **Upload file** and browse to **C:\Lab Files** and select
    **Employee.csv** file.

    ![](./media/image13.png)


4.  Change the **Work Email** column type to **single line of text** and
    then click on **Next**.


    ![](./media/image14.png)


5.  Enter then Name as: +++**Employee Onboarding**+++ and if asked, enter Description: +++**New
    Contoso Corp employee**+++ and then click on **Create**.

  

    ![](./media/image15.png)


   

    ![](./media/image16.png)


6.  The Employees list is created for you now. Rename the **Title**
    column to +++**Emp_id**+++ by selecting **Title drop-down** > **Column settings** > **Rename**.


    ![](./media/image17.png)



    ![](./media/image18.png)


7.  Now the employee table should like this

    
    ![](./media/image19.png)


8.  Click on **Settings -\>List settings.**

    ![](./media/image20.png)


9.  Click on the **Department** column link.

    ![](./media/image21.png)


10. Change the below values and then click on **Ok**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

  
    ![](./media/image22.png)


11. Repeat the above step for the **Job title** column.

12. Select the **Have you been to orientation yet?** column and make below
    changes and then click **OK**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

    - Type each choice on a separate line : **Yes No**

    ![](./media/image23.png)


13. Repeat the above step for **Orientation Location** with below properties and then select **Ok**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

    - Type each choice on a separate line : **Redmond Reno**


    ![](./media/image3.13.png)


14. Repeat above step for **Manager** column with below properties add and then select **Ok**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**


    ![](./media/image25.png)

15. Click on **Home** to go back to the **Site**.

    ![](./media/image3.15.1.png)

## Task 4: Create a HR list in SharePoint site from CSV file

1.  Click on **Home --> New --> List.**


    ![](./media/image26.png)


2.  Select **From CSV tile** from **Create a list window.**


    ![](./media/image4.2.1.png)


3.  Click on Upload **file** and browse **C:\Lab Files** and select
    **Import_HR_M365.CSV** and click **Open**.


    ![](./media/image28.png)


4.  Change **Work Email** column type to **Single line of text** and
    then click on **Next**.


    ![](./media/image29.png)


5.  Enter below details

    - Name : +++**Contoso HR**+++

    - Description (If asked) : +++**Contoso Human Resource**+++, then click on **Create**
      button.


    ![](./media/image30.png)


6.  Click on **Title --> Column settings --> Rename** columnt to
    +++**Emp_id**+++.


    ![](./media/image31.png)



    ![](./media/image32.png)


7.  The HR table should like below image now.



    ![](./media/image33.png)


# Exercise 2: Create Power Apps for SharePoint Lists

In this exercise, you will build your application to send an email to an employee with official information and asking them to fill and upload documents.

## Task 1: Customize Employee form with PowerApps for HRs to fill.

1.  From your SharePoint **Contoso Corp** site, select **Employee Onboarding** list from the horizontal palette, copy the URL and save it in Notepad. 


    ![](./media/image34.png)


2.  Open a new tab and go to +++**https://make.powerapps.com/**+++. Sign in with your Microsoft 365 admin credentials and select your **Dev One** (Developer) environment. 

    ![](./media/image2.1.2.png)

3.  Click on **Apps** from left navigation menu. Select **New App -->
    Start with a page design.**



    ![](./media/image35.png)

4.  Select **Blank Canvas** tile.

    ![](./media/image36.png)

5.  Select **Skip** on the **Welcome to Power Apps Studio**. Right click on **Screen1** and select **Rename.**

    ![](./media/image37.png)


6.  Rename to **HrEmployeeform**


    ![](./media/image38.png)


7.  Select the form and click on **Insert --> Edit form.**


    ![](./media/image39.png)



8.  Search for **SharePoint** and select the **SharePoint connector** from
    **Select a data source** dropdown.


    ![](./media/image40.png)


9.  Under the **SharePoint**, select **Connect deirectly** and then select **Connect.**


    ![](./media/image2.1.9.png)


10. Enter the **SharePoint list URL** copied from step 1 into **Enter
    SharePoint URL** text field and then click on **Connect**.

    
    ![](./media/image42.png)


11. Select the **Employee Onboarding** list and then click on **Connect**.

    
    ![](./media/image43.png)


12. Drag and fit the form on the screen.

  
    ![](./media/image44.png)


13. Reduce the size of the Form1 component as indicated in the image below and then click on **Insert** --> **Rectangle** to insert a header into the screen.

   
    ![](./media/image45.png)


14. Adjust the rectangle to the screen width. Click on **Insert -->
    Text label**.


    ![](./media/image46.png)


15. Adjust the width and location of the text field component so it's cantered within the rectangle and update the following properties.

    - **Text: New Employee Onboarding Form**

    - **Font Size:** 27

    - **Font weight:** Bold

    - **Text alignment:** Centre

    - **Color:** White


    ![](./media/image47.png)


16. Select **Emp_Id** field and change value **required**. Click on
    **Advanced** under **Properties** and select **Unlock to change
    properties**.

    **Note**: If you don't see the **Emp_Id** field, select the **Form1** on the canvas, then select **Fields** > **Add fields**. Choose **Emp_Id** from the list. If **Emp_Id** isn’t available, select **Title** instead, and click **Add**.

    ![](./media/image48.png)

    ![](./media/image2.1.17.png)

17.  Now set the **Required** value to true. You should see a star next
    **Emp_id** field.


     ![](./media/image49.png)


18.  Repeat the previous two steps for the **First Name** and **Last Name** fields. 

     **Note**: If you don't see these fields, then select **HrEmployeeform**, navigate to **Properties**, click **Edit field**, then proceed to add the fields and reorder accordingly. 


     ![](./media/image50.png)


19. Click outside of the form control to deselect it and then click on **Insert** --> **Button**. 



    ![](./media/image51.png)

20. Drag and place the button under **Department** field in the form and
    update below properties.

    **Text**: **Submit**


    ![](./media/image52.png)



21. Click on **New Screen** and select the **Success** template.


    ![](./media/image53.png)


22. Select the newly added screen, and rename it to **Success**, as indicated in the image 
below.


    ![](./media/image54.png)


23. Select **Lb1Successmsg1** and change the **Text** property to **New employee
    added**.


    ![](./media/image55.png)


24. Now, click on **Insert --> Icons --> Back arrow.**


    ![](./media/image56.png)


25. Position and resize the new icon as you see fit. Then, select the newly added icon and update the properties as follows


- Tool Tip: **Go Back**

- OnSelect: +++**Back(ScreenTransition.CoverRight)**+++


    ![](./media/image57.png)


26. Click on **HrEmployeeform.** Select the **Submit Button** you added in the step 20 and update the **OnSelect** property with the following formula. 

     **Note:** Update the formula with your SharePoint Form.

    +++**SubmitForm(*Form1*);ResetForm(*Form1*);Navigate(*Success*)**+++


    ![](./media/image58.png)


27. Select **Form1**, ensure the **OnSuccess** property is selected in the dropdown and then update it using the formula below 

    +++**ResetForm(Self); RequestHide();Notify("New Employee
    added",NotificationType.Success)**+++


    ![](./media/image59.png)


28. Click on the **Save --> Save as** button and enter the name as
    **EmpformforHr** and then click on **Save**.


    ![](./media/image60.png)


29. Select the form and change the **Default mode** to **New** and then
    click on the **Save ->** **Preview** icon.


    ![](./media/image61.png)


30. Enter a random **Emp id**, **First Name** and **Last Name** and then click
    on **Submit** button.


    ![](./media/image62.png)


31. You should see the **New employee added** message. Click on the **Back**
    button.


    ![](./media/image63.png)


32. Colse the **Preview mode** and select **Ok** on the pop-up theat appears on the Power Apps portal. Click on **Publish** button and then click on **Publish this
    version** button.


    ![](./media/image64.png)


33. Go back to the SharePoint tab in a browser. You should see the employee
    record of the new employee added by you in the list.

## Task 2: Create employee onboarding Canvas app for the employee

1.  Open a new tab and go to +++**https://make.powerapps.com/**+++. Sign in with your Microsoft 365 admin credentials and select your **Dev One** (Developer) environment. 

2.  Click on the **Apps** from the left navigation menu. Select **New App** ->
    **Start with a page design.**


    ![](./media/image35.png)

3.  Select **Blank Canvas** tile.


    ![](./media/image36.png)


4.  Select **Skip** on the **Welcome to Power Apps Studio**. Right click on **Screen1** and select **Rename.**


    ![](./media/image37.png)


5.  Rename to **Employeeform**

   

    ![](./media/image65.png)



6.  Click on **Insert** and select **Edit** form.


    ![](./media/image66.png)


7.  Search for **SharePoint** and select **SharePoint connector** from
    **Select a data source** dropdown.


    ![](./media/image40.png)


8.  Select the **SharePoint** connection which is already created in the previous task.


    ![](./media/image2.2.9.png)


9. Select the connection created in the previous task from the list.

10. Select **Employee Onboarding** list and then click on **Connect**.


    ![](./media/image43.png)


11. Drag and fit the form into the screen.


    ![](./media/image68.png)


12. Select the **Form 1** and Set the **Display mode**** to **New** under properties.


    ![](./media/image69.png)


13. Reduce the size of the **Form1** component as indicated in the image below and then click on **Insert** --> **Rectangle** to insert a header into the screen. 


    ![](./media/image70.png)


14. Change the width of the rectangle to the screen and select
    **Insert --> Text label**.


    ![](./media/image71.png)


15. Select the Label and set below **properties.**

    - **Text: Employee Onboarding Form**

    - **Font Size: 25**

    - **Font weight: Bold**

    - **Text alignment: Centre**

    - **Colour: White**


    ![](./media/image72.png)


16. Select the **Emp_Id** field name and change **Font size** to **16**
    and **Font weight** to **Bold** under Properties.

    **Note**: If you don't see the **Emp_Id** field, select the **Form1** on the canvas, then select **Fields** > **Add field**. Choose **Emp_Id** from the list. If **Emp_Id** isn’t available, select **Title** instead, and click **Add**.

    ![](./media/image73.png)


17. Repeat above step for all fields.


    ![](./media/image74.png)


18. Select **Orientation location** item and set **Visible** property to
    **Off**.


    ![](./media/image75.png)


19. Select **Have you been to orientation yet**? text field and click on
    **edit** label.


    ![](./media/image76.png)


20. Change label value to **Orientationdropdown**


    ![](./media/image77.png)


21. Select **Orientation Location data card** from the **Tree view** and replace the **false** value of  **Visible**  property to the formula as shown in below image.

    +++**If(*Orientationdropdown*.Selected.Value="No",true,false)**+++


    ![](./media/image78.png)


22. Click on **Save** and enter app name as: **EmployeeOnboardingForm**
    and then click on **Save** button.


    ![](./media/image79.png)


23. Select the **Emp_Id**/**Title** field and click **on Advanced --> Unlock to change
    properties** and update **Display mode** to
    **Parent.DisplayMode.View**. Repeat this for **First Name**, **Last Name** fields too.


    ![](./media/image80.png)



    ![](./media/image81.png)



    ![](./media/image82.png)



    ![](./media/image83.png)


    ![](./media/image84.png)


24. Select the **Work email** Field **Unlock property** and update
    **Required** property to **true.** Repeat for other fields if
    required.


    ![](./media/image85.png)


25. Select the **Form1** and update **OnFailure** field value to

    +++**Notify("Required Fields can't be empty.",NotificationType.Error)**+++


    ![](./media/image86.png)


26. Select **OnSuccess** and set the value to

    +++**Notify("Thank you for filling out the form",NotificationType.Success)**+++


    ![](./media/image87.png)


27. Now, Let’s add button to submit at the end of the form. Click on
    **Insert --> Button.**


    ![](./media/image88.png)


28. Change the Properties of the button and save the form.

    - Text: **Submit.**

    - Onselect: +++**SubmitForm(*Form1*);NewForm(*Form1*)**+++


    ![](./media/image89.png)


29. Click on **Save** and then click on **Preview** app buttons.


    ![](./media/image90.png)


30. Enter details and then click on **Submit**.


    ![](./media/image91.png)


31. You should see success notification.


    ![](./media/image92.png)


32. Close the preview window.

33. Click on **App** from **Tree View**. Select **OnStart** and enter
    the below formula.

    ```
    Set(
    
        onboardinglistitem,
    
        LookUp(
    
            'Employee Onboarding',
    
            ID = Value(Param("ItemID"))
    
        )
    
    )
    ```


    ![](./media/image93.png)


34. Select the **Form1** from **Tree View**. Select **Item** and enter the
    value as: **onboardinglistitem**


    ![](./media/image94.png)


35. Click on **Save** and **Publish --> Publish this version**.


    ![](./media/image95.png)


36. Go back to the **Power Apps Home** page, Click on **Apps --> Your
    app (EmployeeOnboardingForm) --> Details**.


    ![](./media/image96.png)


37. Copy the Weblink to use in next task.


    ![](./media/image97.png)


38. Close the preview window and navigate to your SharePoint tab and
    check the above record in the list.


    ![](./media/image98.png)


## Task 3: Create Power Automate flow to send a form to the new employee

1.  Go back to **SharePoint** tab and copy the URL of your **Contoso Corp** site.


    ![](./media/image99.png)


2.  Open a new tab and go to +++https://make.powerautomate.com/+++ and sign in with
    your admin tenant account.

3.  Select your **Dev One** developer environment.

4.  Click on **My flows** from left navigation menu Click on **New
    Flow --> Automated Cloud flow.**


    ![](./media/image100.png)


5.  Enter the flow name as: **Onboarding new employee**. Search for
    **When an item is created** and select it from SharePoint and then
    click on **Create**.


    ![](./media/image101.png)


6.  Select the **When an item is created** step. Click on **Site Address --> Enter custom value.**


    ![](./media/image102.png)


7.  Enter the Address copied in Step 1 and then select the **Employee
    Onboarding** list as shown in below image.


    ![](./media/image103.png)


8.  Click on **+** to add new action.


    ![](./media/image104.png)


9.  Seach for and select **Send an email (V2)**


    ![](./media/image105.png)


10. Select **Settings** for the **To** field and select **Use dynamic content**.  Click on to text field and select **Enter the data from previous
    step**.

    ![](./media/image2.3.10.png)

    ![](./media/image106.png)


11. Select **Work email.**


    ![](./media/image107.png)


12. Enter the Subject line as: +++**Welcome to Firm**+++ select **First Name**
    from previous step.


    ![](./media/image108.png)


13. Enter below data in the **Body** of the email. Insert dynamic values as
    shown in image.

    +++Hi+++ **First name** (From dynamic content) **Last name** (From dynamic content),

    +++Please click on link below to complete your onboarding form+++

    ![](./media/image109.png)


    ![](./media/image110.png)


14. Enter the Weblink copied in Task 2 – and add **&itemID=** at the end
    of the link and select Dynamic ID as shown in below image.


    ![](./media/image111.png)



    ![](./media/image112.png)


15. Cut the link and then enter the text: **Onboarding Form** and select
    and click on link icon. paste the link copied from above step.


    ![](./media/image113.png)


16. Save the flow now.


    ![](./media/image114.png)



    ![](./media/image115.png)


## Task 4: Test the flow.

1.  Go back to **Power Apps tab**, select **EmpformforHr** app.


    ![](./media/image116.png)


2.  If asked then allow permissions.


    ![](./media/image117.png)


3.  Fill the form with your details. Enter work email as your admin
    tenant id and **Submit** the form.


    ![](./media/image118.png)




    ![](./media/image119.png)


4.  Go back to the **Power Automate** portal, select **My flows** > **Onboarding new employee** flow and check flow **Status**. Click on the run to see the flow status in the designer.



    ![](./media/image120.png)



    ![](./media/image121.png)


5.  Open a new tab and go to +++**https:\\outlook.com**+++ and sign in with your
    Office 365 tenant account and check inbox. Click on the **Onboarding
    Form** link in the email generated from HR.



    ![](./media/image122.png)


**Conclusion:** Upon completing this lab, participants will have
developed a comprehensive understanding of how to create and manage
employee onboarding workflows using Microsoft Power Platform tools. They
will successfully create and configure SharePoint lists to store
employee data, build customized Power Apps forms for HR use, and set up
automated Power Automate flows for seamless communication with new
employees. This experience will empower participants to enhance their
organizational onboarding processes, improve data accuracy, and foster a
more efficient workflow in HR management. Overall, the lab equips
participants with valuable skills that can be applied in real-world
scenarios to optimize business operations.
