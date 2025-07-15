# **Lab 10 - Design a flow to generate username and password**​

**Objective:** The objective of this lab is to create and test a Power
Automate Desktop flow that generates a username, and a random password
based on user input. By completing this lab, participants will learn how
to design and automate a flow using Power Automate Desktop actions,
including handling text manipulation and generating random text.

**Estimated Time:** 20 mins

### **Task 1: Create a Power Automate Desktop Flow**

1.  Navigate to +++**https://make.powerautomate.com/**+++ and if required, sign in with your Office 365 tenant credentials. Select **My flows** from the left pane and then select **Desktop flows**. Select **+New desktop flow**.

    ![](./media/image1.1png)

2.  Select **Open** on the pop-up that says **This site is trying to open Power Automate**.

    ![](./media/image1.2.1.png)
    
3.  You will be on the **Power Automate Desktop app**, you can see the **Welcome to Power Automate** pop-up. Select **Skip** on the pop-up. Then select **Got it**.

    ![](./media/image1.2.2.png)

    ![](./media/image1.2.3.png)
  
4. On the **Build a desktop flow** screen, enter the **Flow name** - +++**Generate Username and Password**+++ and then select **Launch app**.

    ![](./media/image1.2.png)

5.   On the **Power Automate Desktop**, make sure you are in **Contoso(defualt)** environment. From the top left corner select **+ New flow.**
    

   ![](./media/image1.png)

6.  Enter the Flow name +++**Generate Username and Password**+++, confirm that 
    the **Power Fx** is turn off and click on the **Create**.

    ![](./media/imageaz.png)


7.  From left Actions bar search +++**Display input dialog**+++ action and
    double click on the action to select.

    ![](./media/image3.png)


8.  Set the **Input dialog title** property to +++**Name Input**+++ and
    the **Input dialog message** property to +++**Please enter your first
    and last name (for example, Adele Vance)**+++. This action displays a
    message that prompts the user for input. Click on the **Save**
    button.

    ![](./media/image4.png)


9.  From left Actions bar search +++**Split text**+++ action and double click
    on the action to select.

     ![](./media/image5.png)


10.  In the **Text to split** field of Split text action,
    enter +++**%UserInput%**+++ and then click on **Save**.

    ![](./media/image1z.png)


11.  From left Actions bar search +++**Change text case**+++ action and double
    click on the action to select.

    ![](./media/image7.png)


12.  In the Text to convert field, enter +++**%TextList\[0\]%**+++. 

13.  With the index of a list type variable, provide the first item of
    the list, which is the first name. Set the Convert to as **Lower
    case** and then click on the **Save**.

    ![](./media/image8.png)


14. From left Actions bar search +++**Change text case**+++ action and double
    click on the action to select.

    ![](./media/image9.png)

15. In the **Text to convert** field of action, enter
    +++**%TextList[1]%**+++.

16. With the index of a list type variable, provide the first item of
    the list, which is the first name. Set the Convert to property to
    **Lower case** and then click on **Save**.

    ![](./media/image10.png)


17. From left Actions bar search +++**Get subtext**+++ action and double click
    on the action to select.

    ![](./media/image11.png)


18. In the Original text field, enter +++**%TextWithNewCase%**+++, In the
    Start index section, set Character position to +++**0**+++

19. In the Length section, set Number of chars to +++**1**+++. This setting
    gets the first character of the text string.

20. Click on the **Save**.

    ![](./media/image12.png)


21. To generate a random password, add a **Create random text** action.
    The action’s properties can be left at their default values. Then
    click on **Save.**

    ![](./media/image13.png)


22. From left Actions bar search +++**Display message**+++ action and double
    click on the action to select.

    ![](./media/image14.png)


23. In the **Message box title** field, enter +++**Username & Password**+++,
    and in the **Message to display** field, enter the following
    content:

        +++Hello, %UserInput%, your username is: %SubText%%TextWithNewCase2% Your temporary password is: %RandomText%+++

24. The username (first letter of first name, combined with family name)
    is displayed and the result of the **Generate random text** action
    shows as the user’s password. Click on the **save** button.

    ![](./media/image15.png)


25. The **completed flow** should look like the following figure.

    ![](./media/image16.png)


### **Task 2: Test the flow**

1.  Click on the **Run** button for test the flow.

    ![](./media/image17.png)


2.  Enter the **First and Last Name** for the testing purpose and click
    on the **Ok** Button.

    ![](./media/image18.png)


3.  The **Final output** of the test case look like below once.

      ![](./media/image19.png)


**Conclusion:** In this lab, participants successfully designed and
tested a Power Automate Desktop flow that generates a username and
random password based on user input. By utilizing text manipulation
actions, such as splitting, changing case, and generating random text,
participants gained practical experience in automating user-specific
tasks. The flow demonstrates how to dynamically create a username and
password using basic Power Automate Desktop features. This lab lays
the foundation for building more complex automation flows in future
tasks.
