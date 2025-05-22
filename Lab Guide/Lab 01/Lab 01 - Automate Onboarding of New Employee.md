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

1.  Navigate to +++**https:\\office.com**+++ and
    sign in with your office 365 tenant.

2.  Click on matrix in the upper-left corner and select **SharePoint**
    from list of **apps**.


    ![](./media/image2.png)


    ![](./media/image3.png)


4.  Click on **+Create site** on top menu.

    ![](./media/image4.png)


5.  Select **Communication site** tile in **Create a site** window.

    ![](./media/image5.png)


6.  Scroll down and select **Blank** template.

    ![](./media/image6.png)


7.  Click on **Use template**.

    ![](./media/image7.png)


8.  Enter Site name and description then click on **Next** button.

    - Site Name: +++**Contoso Corp**+++

    - Site Description: +++**Onboarding new employee.**+++


    ![](./media/image8.png)


9.  Keep the default language and then click on **Create Site.**

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


4.  Change **Work Email** column type to **single line of text** and
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


9.  Click on **Department** column link.

    ![](./media/image21.png)


10. Change below values and then click on **Ok**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

  
    ![](./media/image22.png)


11. Repeat the above step for **Job title** column.

12. Select **Have you been to orientation yet?** column and make below
    chagnes and then click **OK**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

    - Type each choice on a separate line : **Yes No**

    ![](./media/image23.png)


13. Repeat above step for **Orientation Location** with below properties and then select **Ok**.

    - Type of Column : **Choice**

    - Allow 'Fill-in' choices: **Yes**

    - Type each choice on a separate line : **Redmon Reno**


    ![](./media/image24.png)


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

    - Description : +++**Contoso Human Resource**+++, then click on **Create**
      button.


    ![](./media/image30.png)


6.  Click on **Title --> Column settings --> Rename** columnt to
    +++**Emp_id**+++.


    ![](./media/image31.png)



    ![](./media/image32.png)


7.  The HR table should like below image now.



    ![](./media/image33.png)


# Exercise 2: Create Power Apps for SharePoint Lists

In this exercise, you will build your application to send an email to
employee with official information and asking him to fill and upload
documents.

## Task 1: Customize Employee form with PowerApps for HRs to fill.

1.  From your **SharePoint --> Employee onboarding**, copy URL and save
    it in Notepad.


    ![](./media/image34.png)


2.  Open a new tab and go to +++**https://make.powerapps.com/**+++. Sign in
    with your office 365 admin tenant and select your **Dev One**
    (Developer) environment. For now, **disable** the toggle button that says 'Try the new Power Apss experience'.

    ![](./media/image2.2.1.png)

3.  Click on **Apps** from left navigation menu. Select **New App -->
    Start with a page design.**



    ![](./media/image35.png)

4.  Select **Blank Canvas** tile.

    ![](./media/image36.png)

5.  Right click on **Screen1** and select **Rename.**

    ![](./media/image37.png)


6.  Rename to **HrEmployeeform**


    ![](./media/image38.png)


7.  Select the form and click on **Insert --> Edit form.**


    ![](./media/image39.png)



8.  Search for **SharePoint** and select **SharePoint connector** from
    **Select a data source** dropdown.


    ![](./media/image40.png)


9.  Select **SharePoint** under **Connect.**


    ![](./media/image41.png)


10. Enter the **SharePoint list URL** copied form step 1 into **Enter
    SharePoint URL** text field and then click on **Connect**.

    
    ![](./media/image42.png)


11. Select **Employee Onboarding** list and then click on **Connect**.

    
    ![](./media/image43.png)


12. Drag and fit the form into the container.

  
    ![](./media/image44.png)


13. Drag the Form1 container little down and click on **Insert -->
    Rectangle** to insert header to the form.

   
    ![](./media/image45.png)


14. Adjust the rectangle to the container width. Click on **Insert -->
    Text label**.


    ![](./media/image46.png)


15. Change the width of the text field to the rectangle and update below
    properties.

    - **Tex: New Employee Onboarding Form**

    - **Font Size:** 27

    - **Font weight:** Bold

    - **Text alignment:** Centre

    - **Colour:** White


    ![](./media/image47.png)


16. Make **Emp_Id, First Name** and **Last_Name** as required fields.

17. Select **Emp_Id** field and change value **required**. Click on
    **Advanced** under **Properties** and select **Unlock to change
    properties**.


    ![](./media/image48.png)


18.  Now set the **Required** value to true. You should see star next
    **Emp_id** field.


     ![](./media/image49.png)


19.  Repeat above two steps for **First Name** and **Last_Name**

     **Note**: If you don’t see field then select the container -> properties -> Edit( fields) .add field and re-order.


     ![](./media/image50.png)


20. Select the Rectangular form/FormScreen1 and then click on **Insert
    --> Button**.



    ![](./media/image51.png)

21. Drag and place the button under **Department** filed in the form and
    update below properties.

    **Text**: **Submit**


    ![](./media/image52.png)



22. Click on **New Screen** and select **Success** template.


    ![](./media/image53.png)


23. Select the new screen and **rename** to **Success** as shown in
    below images.


    ![](./media/image54.png)


24. Select **Lb1Successmsg1** and change the text to **New employee
    added**.


    ![](./media/image55.png)


25. Now, Click on **Insert --> Icons --> Back arrow.**


    ![](./media/image56.png)


26. Select Back Arrow and set below properties.

- Tool Tip: **Go Back**

- OnSelect: +++**Back(ScreenTransition.CoverRight)**+++


    ![](./media/image57.png)


27. Click on **HrEmployeeform.** Select **Button** and select
    **Onselect** and enter below formula.

     **Note:** Update the formula with your SharePoint Form.

    +++**SubmitForm(*Form1*);ResetForm(*Form1*);Navigate(*Success*)**+++


    ![](./media/image58.png)


28. Select **Form1,** select **OnSuccess** and replace the formula with
    below formula.

    +++**ResetForm(Self); RequestHide();Notify("New Employee
    added",NotificationType.Success)**+++


    ![](./media/image59.png)


29. Click on **Save --> Save as** button and enter the name as
    **EmpformforHr** and then click on **Save**.


    ![](./media/image60.png)


30. Select the form and change the **Default** mode to **New** and then
    click on the **Save ->** **Preview** icon.


    ![](./media/image61.png)


31. Enter random **Emp id, First Name** and **Last Name** and then click
    on **Submit** button.


    ![](./media/image62.png)


32. You should see **New employee added message.** Click on **Back**
    button**.**


    ![](./media/image63.png)


33. Click on **Publish** button and then click on **Publish this
    version** button.


    ![](./media/image64.png)


34. Go back to SharePoint tab in a browser. You should see the employee
    record of the new employee added by you in the list.

## Task 2: Create employee onboarding Canvas app for the employee

1.  From your **SharePoint-\Employee onboarding**, copy URL and save
    it in the Notepad.


    ![](./media/image34.png)


2.  Open a new tab and go to +++**https://make.powerapps.com/**+++. Sign in
    with your office 365 admin tenant and select your **Dev One** developer
    environment.

3.  Click on **Apps** from left navigation menu. Select **New App ->
    Start with a page design.**


    ![](./media/image35.png)

4.  Select **Blank Canvas** tile.


    ![](./media/image36.png)


5.  Right click on **Screen1** and select **Rename.**


    ![](./media/image37.png)


6.  Rename to **Employeeform**

   

    ![](./media/image65.png)



7.  Click on **Insert** and select **Edit** form.


    ![](./media/image66.png)


8.  Search for **SharePoint** and select **SharePoint connector** from
    **Select a data source** dropdown.


    ![](./media/image40.png)


9.  Select **SharePoint** under **Add Connection.**


    ![](./media/image2.9.1.png)


10. Enter the **SharePoint list URL** copied form step 1 into Enter
    SharePoint URL text field and then click on **Connect**.

11. Under **Choose a list** --> select **Employee Onboarding** list and
    then click on **Next.**


    ![](./media/image42.png)


12. Select **Employee Onboarding** list and then click on **Connect**.


    ![](./media/image43.png)


13. Drag and fit the form into the container.


    ![](./media/image68.png)


14. Select **Form 1** and **Display** mode to **New** under properties.


    ![](./media/image69.png)


15. Drag the Form1 container little down and click on **Insert ->
    Rectangle** to insert header to the form.


    ![](./media/image70.png)


16. Change the width of the rectangle to the container and select
    **Insert --> Text label**.


    ![](./media/image71.png)


17. Select the Label and set below **properties.**

    - **Text: Employee Onboarding Form**

    - **Font Size: 25**

    - **Font weight: Bold**

    - **Text alignment: Centre**

    - **Colour: White**


    ![](./media/image72.png)


18. Select the **Emp_Id** field name and change **Font size** to **16**
    and **Font weight** to **Bold** under Properties. If you dont find **Emp_Id** field, then hover the mouse over **Form1**     in the canvas, select **Fields** > **Add fields**, select **Emp_Id** (If you dont see **Emp_Id** in this list too, then      select **Title**) and then select **Add**.  


    ![](./media/image73.png)


19. Repeat above step for all fields.


    ![](./media/image74.png)


20. Select **Orientation location** item and set **Visible** property to
    **false.**


    ![](./media/image75.png)


21. Select **Have you been to orientation yet**? text field and click on
    **edit** label.


    ![](./media/image76.png)


22. Change label value to **Orientationdropdown**


    ![](./media/image77.png)


23. Select **Orientation Location data card** and select **Visible** and
    place below formula as shown in below image.

    +++**If(*Orientationdropdown*.Selected.Value="No",true,false)**+++


    ![](./media/image78.png)


24. Click on **Save** and enter app name as: **EmployeeOnboardingForm**
    and then click on **Save** button.


    ![](./media/image79.png)


25. **Emp_id**, **First Name**, **Last Name** and **Manager** will be
    filled by HR, so change the display mode to **View**.

26. Select the field and click **on Advanced --> Unlock to change
    properties** and update **Display mode** to
    **Parent.DisplayMode.View**


    ![](./media/image80.png)



    ![](./media/image81.png)



    ![](./media/image82.png)



    ![](./media/image83.png)


    ![](./media/image84.png)


27. Select the **Work email** Field **Unlock property** and update
    **Required** property to **true.** Repeat for other fields if
    required.


    ![](./media/image85.png)


28. Select the **Form1** and update **OnFailed** field value to

    +++**Notify("Required Fields can't be empty.",NotificationType.Error)**+++


    ![](./media/image86.png)


29. Select **OnSuccess** and set the value to

    +++**Notify("Thank you for filling out the form",NotificationType.Success)**+++


    ![](./media/image87.png)


30. Now, Let’s add button to submit at the end of the form. Click on
    **Inset --> Button.**


    ![](./media/image88.png)


31. Change the Properties of the button and save the form.

    - Text: **Submit.**

    - Onselect: +++**SubmitForm(*Form1*);NewForm(*Form1*)**+++


    ![](./media/image89.png)


32. Click on **Save** and then click on **Preview** app buttons.


    ![](./media/image90.png)


33. Enter details and then click on **Submit**.


    ![](./media/image91.png)


34. You should see success notification.


    ![](./media/image92.png)


35. Close the preview window.

36. Click on **App** from **Tree View**. Select **OnStart** and enter
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


37. Select the **Form1** from **Tree View**. Select item and enter the
    value as: **onboardinglistitem**


    ![](./media/image94.png)


38. Click on **Save** and **Publish --> Publish this version**.


    ![](./media/image95.png)


39. Go back to the **Power Apps Home** page, Click on **Apps --> Your
    app --> Details**.


    ![](./media/image96.png)


40. Copy the Weblink to use in next task.


    ![](./media/image97.png)


41. Close the preview window and navigate to your SharePoint tab and
    check the above record in the list.


    ![](./media/image98.png)


## Task 3: Create Power Automate flow to send a form to the new employee

1.  Go back to **SharePoint** tab and copy the URL.


    ![](./media/image99.png)


2.  Open a new tab and go to +++https://make.powerautomate.com/+++ and sign in with
    your admin tenant account.

3.  Select your **Dev One** developer environment.

4.  Click on **My flows** from left navigation menu Click on **New
    Flow --> Automated Cloud flow.**


    ![](./media/image100.png)


5.  Enter the flow name as: **Onboarding new employee**. Search for
    **When an item is created** and select it from SharePoint and then
    click on **create**.


    ![](./media/image101.png)


6.  Select the action. Click on **Site Address --> Enter custom value.**


    ![](./media/image102.png)


7.  Enter the Address copied in Step 1 and then select the **Employee
    Onboarding** list as shown in below image.


    ![](./media/image103.png)


8.  Click on **+** to add new action.


    ![](./media/image104.png)


9.  Seach for and select **Send an email (V2)**


    ![](./media/image105.png)


10. Click on to text field and select **Enter the data from previous
    step**.


    ![](./media/image106.png)


11. Select **Work email.**


    ![](./media/image107.png)


12. Enter the Subject line as: **Welcome to Firm** select **First Name**
    from previous step.


    ![](./media/image108.png)


13. Enter below data in Body of the email. Insert dynamic values as
    shown in image.

    Hi first name Lastname,

    Please click on link below to complete your onboarding form.

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


2.  IF asked then allow permissions.


    ![](./media/image117.png)


3.  Fill the form with your details. Enter work email as your admin
    tenant id and **submit** the form.


    ![](./media/image118.png)




    ![](./media/image119.png)


4.  Go back to the Power Automate flow and check flow Status.



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
