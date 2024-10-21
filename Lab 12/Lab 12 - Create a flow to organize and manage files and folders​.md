# Lab 12 - Create a flow to organize and manage files and folders​

**Objective:** The objective of this lab is to automate the process of
backing up files from a designated folder on the desktop using **Power
Automate Desktop**. Participants will create a flow that copies files
from a folder named **Contoso_Files**, moves them to a newly created
backup folder, and appends a timestamp to the backup file. This lab
provides practical experience in automating file management tasks,
including creating folders, copying files, and renaming them with
dynamic date and time formats.

**Estimated Time:** 20 mins

# Task 1: Create folder and Desktop flow

1.  Create a folder on your desktop and rename as **Contoso_Files.**

    <img src="./media/image1.png"
style="width:6.26806in;height:1.60486in" />

2.  **Select Report.txt** file from the **C:\Labfiles** folder and move
    the .**txt** file in the **Contoso_Files** folder.

    <img src="./media/image2.png"
style="width:6.26806in;height:2.30278in" />

3.  Open Power automate desktop and **Login** with **Office 365 tenant
    credential**. Choose environment **Contoso** form the top bar.

    <img src="./media/image3.png" style="width:6.26806in;height:3.175in" />

4.  Click on the **+ New flow** from the top left corner and start
    creating new flow.

    <img src="./media/image4.png"
style="width:4.41705in;height:4.06702in" />

5.  Enter **Backup File Flow** as flow name and select check box of the
    **Power Fx enable (Preview).** Then click on the **Create**.

    <img src="./media/image5.png"
style="width:6.26806in;height:3.65486in" />

6.  From the left-hand **Actions** navigation bar, Search for **Get
    special folder** action to the workspace. Select the action by
    double clicking on it to add into the flow.

    <img src="./media/image6.png"
style="width:5.25879in;height:2.22519in" />

7.  Then click on **Save** button to save the default setting of the
    button.

    <img src="./media/image7.png"
style="width:6.26806in;height:1.32986in" />

8.  From the left-hand **Actions** navigation bar, Search for **Get
    files in folder** action to the workspace. Select the action by
    double clicking on it to add into the flow.

    <img src="./media/image8.png"
style="width:6.26806in;height:1.72083in" />

9.  Add **Get files in folder** action to set the Folder field to
    **C:\Users\trade\OneDrive\Desktop\Contoso_Files** This setting will
    select the folder that you previously created on the desktop. Then
    click on the **Save** button.

    <img src="./media/image9.png"
style="width:6.26806in;height:2.18056in" />

10. From the left-hand **Actions** navigation bar, Search for **Create
    Folder** action to the workspace. Select the action by double
    clicking on it to add into the flow.

    <img src="./media/image10.png"
style="width:6.26806in;height:2.17847in" />

11. In the **Create new folder into** field of Create folder action,
    enter **C:\Users\trade\OneDrive\Desktop\\** In the **New folder
    name** field, enter **Contoso_Backup**. After entering the
    information slick on the **Save** button.

    <img src="./media/image11.png"
style="width:6.26806in;height:2.19931in" />

12. From the left-hand **Actions** navigation bar, Search for **Copy
    file(s)** action to the workspace. Select the action by double
    clicking on it to add into the flow.

    <img src="./media/image12.png"
style="width:6.26806in;height:1.92361in" />

13. Set the **File(s) to Copy** field to **=Files**, the **Destination
    Folder** field
    to **C:\Users\trade\OneDrive\Desktop\Contoso_Backup**, and the **If
    File(s) Exists** drop-down option to **Overwrite**. After setup
    click on the **Save** button.

    <img src="./media/image13.png" style="width:6.26806in;height:2.275in" />

14. From the left-hand **Actions** navigation bar, Search for **Rename
    file(s)** action to the workspace. Select the action by double
    clicking on it to add into the flow.

    <img src="./media/image14.png"
style="width:6.26806in;height:2.16319in" />

15. Set the **File(s) to rename** field
    to **C:\Users\trade\OneDrive\Desktop\Contoso_Backup\Reports.txt**.
    In the **Rename scheme** drop-down menu, select the **Add
    datetime** option. Set the **Separator** drop-down option
    to **Nothing** and the **DateTime Format** option
    to **dd.MM.yy_HH.mm**. After Setup Click on the Save button.

    <img src="./media/image15.png"
style="width:6.26806in;height:5.51667in" />

16. The **completed** flow should resemble the following screenshot.

    <img src="./media/image16.png"
style="width:6.26806in;height:2.71597in" />

# Task 2: Test the flow

1.  After the run flow has completed, you will have a new folder called
    Backup Files on your desktop. The folder will contain all contents
    of the folder named Important and an additional text file called
    Backup Log, which will have the last date and time that the flow has
    run appended to its file name.

    <img src="./media/image17.png"
style="width:6.26806in;height:1.95278in" />

    <img src="./media/image18.png"
style="width:6.26806in;height:1.09931in" />

**Conclusion:** In this lab, participants successfully created a Power
Automate Desktop flow to automate the organization and management of
files and folders. By backing up files from a designated folder named
Contoso_Files to a newly created backup folder, participants gained
hands-on experience in essential file management tasks, including folder
creation, file copying, and dynamic file renaming with timestamps. This
lab highlights the effectiveness of Power Automate Desktop in
streamlining file organization processes, reducing manual effort, and
ensuring that important files are securely backed up. Participants left
with practical knowledge of how to leverage automation for efficient
file management, enhancing their productivity in everyday tasks.
