# Lab 8 - Process custom documents with AI builder

**Objective:** The objective of this lab is to guide participants
through creating their first AI model using AI Builder in Power
Automate. The model will be trained to extract custom information, such
as invoice numbers, customer IDs, total amounts, and due dates, from
documents like invoices. Participants will learn how to sign into AI
Builder, choose document types, define fields to extract, upload
documents for training, and finally, integrate the trained model with
Power Automate and Power Apps.

**Estimated Time:** 45 mins

## Exercise 1: Create your first model

### Task 1: Sign in to AI Builder

1.  **Navigate** to power automate with the help of
    <https://www.microsoft.com/en-us/power-platform/products/power-automate>
    .Click on the **Sign in** button from the top right corner. Sign in
    to Power Automate using Microsoft 365 tenant credentials.

    <img src="./media/image1.png"
style="width:6.26806in;height:2.82778in" />

2.  Select the environment **Dev one** from the top bar.

    <img src="./media/image2.png"
style="width:6.26806in;height:2.87569in" />

3.  Navigate to the left pane and select **AI Hub**, then click on **AI
    Models.** If you don't see AI Hub, click on **More** to locate it.

    <img src="./media/image3.png"
style="width:6.26042in;height:2.85417in" />

4.  Choose **Extract custom information from documents** option.

    <img src="./media/image4.png"
style="width:6.26042in;height:2.64583in" />


5.  Scroll Down and click on **Create custom model** to proceed.

    <img src="./media/image5.png"
style="width:6.26806in;height:3.18611in" />

### Task 2: Choose document type

1.  When choosing the document type, you have three options:

    - **Fixed template documents:** This option is ideal when, for a given
      layout, the fields, tables, checkboxes, and other items can be found
      in similar places. You can teach this model to extract data from
      structured documents that have different layouts. This model has a
      quick training time.

    - **General documents:** This option is ideal for any kind of documents,
      especially when there is no set structure or when the format is
      complex. You can teach this model to extract data from structured or
      unstructured documents that have different layouts. This model is
      powerful but had long training time.

    - **Invoices:** Invoice documents are standard account payable forms.
      This model type comes with standards fields, and you can teach this
      model to extract additional custom data or update the standard data.

2.  Select Fixed template documents and click **Next**.

    <img src="./media/image6.png"
style="width:6.26806in;height:2.64931in" />

### Task 3: Choose information to extract

Define the fields and tables you want your model to extract. We'll extract the following fields:

- Invoice number
- Customer ID
- Total amount
- Due date

1.  Click **+** **Add** and select Text field, then click **Next**.

    <img src="./media/image7.png"
style="width:6.26806in;height:2.85556in" />

    <img src="./media/image8.png"
style="width:6.26806in;height:3.40556in" />

2.  Enter the text field name as **Invoice Number** and select **Done**.
    Repeat this step for **Customer** **ID**.

    <img src="./media/image9.png"
style="width:4.14167in;height:2.52778in" />

3.  Click **+ Add** and select **Number field** (preview), then click
    Next.

    <img src="./media/image10.png"
style="width:6.26806in;height:2.26111in" />

    <img src="./media/image11.png"
style="width:6.26806in;height:2.47014in" />

4.  Enter the number field name as **Total amount** and select **Done**.

    <img src="./media/image12.png"
style="width:6.26042in;height:2.5625in" />

5.  Click **+ Add** and select Date field (preview).

    <img src="./media/image13.png"
style="width:6.26806in;height:2.41875in" />

    <img src="./media/image14.png"
style="width:6.26806in;height:2.48611in" />

6.  Enter the date field name as **Due Date** and select **Done**.

    <img src="./media/image15.png"
style="width:4.06702in;height:4.21703in" />

7.  To extract line-item details from the invoice, create a table named
    Items with columns Description and Item total Click **+ Add** and
    select Date field (preview).

    <img src="./media/image16.png"
style="width:6.26806in;height:2.48889in" />

8.  Select Add and then **Table**, and click **Next**.

    <img src="./media/image17.png"
style="width:6.26806in;height:2.96181in" />

9.  Define the table name as **Items**. **Next, add two columns:
    Description and Item total**.

10. Select Column1 and rename it to Description, then click Confirm.

11. Click **+ New column**, enter the column name as Item total, then
    select Add. Finally, click **Done**.

    <img src="./media/image18.png"
style="width:6.26806in;height:2.95208in" />

12. Click **Next** to proceed to the next step in your model.

    <img src="./media/image19.png"
style="width:6.26806in;height:2.63056in" />

### Task 4: Define collections and upload documents

Define collections and upload documents. A collection groups documents
with the same layout. Create a collection for each unique layout your
model needs to process. Since there are two invoice providers using
different templates, we'll create two collections.

1.  Click **New collection** and rename the first collection to
    **Adatum**.

2.  Add another **New collection** and name it **Contoso**.

    <img src="./media/image20.png"
style="width:6.26806in;height:2.65486in" />

3.  Click on the Adatum and then click on the Add document. Then select
    My device, For **Adatum**, upload the five documents which is available in **C:\Lab Files\AI Builder Document Processing
    Sample Data\Invoices\Adatum\Train** folder.

    <img src="./media/image21.png"
style="width:6.26806in;height:2.66944in" />

    <img src="./media/image22.png"
style="width:6.26806in;height:2.71528in" />

4.  Click on the **Upload 5 document** and then click on **Done**.

    <img src="./media/image23.png"
style="width:6.26806in;height:3.69931in" />

    <img src="./media/image24.png"
style="width:6.26806in;height:4.16111in" />

5.  Click on the Contoso and then click on the Add document. Then select
    My device, For **Contoso**, upload the five documents from the **C:\Lab Files\AI
    Builder Document Processing Sample Data/Contoso /Train** folder.

    <img src="./media/image25.png"
style="width:6.26806in;height:2.64236in" />

    <img src="./media/image26.png"
style="width:6.26806in;height:2.62917in" />

6.  Click on the **Upload 5 document** and then click on **Done**.

    <img src="./media/image27.png"
style="width:6.26806in;height:3.69861in" />

    <img src="./media/image28.png"
style="width:6.26806in;height:4.13958in" />

7.  After uploading the sample documents to each collection, select
    **Next** to continue.

    <img src="./media/image29.png"
style="width:6.26806in;height:2.64861in" />

### Task 5: Tag documents

Start teaching your AI model how to extract the fields and tables by
tagging the sample documents you've uploaded. As you tag the expected
fields in each document, a check will appear over that document, and the
red dot at the top corner will disappear.

1.  Select the **Contoso** collection from the right panel to begin
    tagging.

    <img src="./media/image30.png"
style="width:6.26806in;height:2.64028in" />

2.  **Tag Fields:**

- Start by tagging fields like **Invoice Number,** **Due date, and Total
  amount.**

- Draw a rectangle around each field in the document, then select the
  corresponding field name.

- Resize your selection if needed. Hovering over words will show light
  blue boxes, indicating where you can draw rectangles.

    <img src="./media/image31.png"
style="width:6.26806in;height:2.66111in" />

    <img src="./media/image32.png"
style="width:6.26806in;height:2.61181in" />

    <img src="./media/image33.png"
style="width:6.26806in;height:2.65069in" />

3.  Field or Table Not in Document:

- If a field or table isn’t present, like the Customer ID in the Contoso
  collection, select the ellipsis **(…)** next to the field on the right
  panel and choose **Not available in the document**.

    <img src="./media/image34.png"
style="width:6.26806in;height:2.64583in" />

4.  Tag Tables:

    - Draw a rectangle around the table you want to tag and select the table
      name.

    - Draw rows by left-clicking between row separators.

    - Draw columns by pressing Ctrl + left-click (or ⌘ left-click on macOS).

    - Assign the headers by selecting the header column and mapping it to
      the desired one.

    - If you've tagged the table's header, select Ignore first row to
      prevent it from being extracted as content.

    <img src="./media/image35.png"
style="width:6.26806in;height:2.62778in" />

    <img src="./media/image36.png" style="width:6.26806in;height:2.65in" />

    <img src="./media/image37.png"
style="width:6.26806in;height:2.66528in" />

1.  Tag all five documents with same process. Once you've tagged a
    document, move to the next one using the navigation arrows at the
    top right of the document preview.

    <img src="./media/image38.png"
style="width:6.26806in;height:2.63611in" />

1.  Now select the **Adatum** Collection.

    <img src="./media/image39.png"
style="width:6.26806in;height:2.63542in" />

1.  **Tag Fields:**

    - Start by tagging fields like **Invoice Number, Customer ID and Total
      amount.**

    - Draw a rectangle around each field in the document, then select the
      corresponding field name.

    - Resize your selection if needed. Hovering over words will show light
      blue boxes, indicating where you can draw rectangles.

    <img src="./media/image40.png"
style="width:6.26806in;height:2.65208in" />

    <img src="./media/image41.png"
style="width:6.26806in;height:2.64097in" />

    <img src="./media/image42.png"
style="width:6.26806in;height:2.61597in" />

1.  Go to **Due Date** option and select **Not available in
    collection.**

    <img src="./media/image43.png"
style="width:6.26806in;height:2.38125in" />

1.  Tag Tables:

    - Draw a rectangle around the table you want to tag and select the
      table name.

    - Draw rows by left-clicking between row separators.

    - Draw columns by pressing Ctrl + left-click (or ⌘ left-click on
      macOS).

    - Assign the headers by selecting the header column and mapping it
      to the desired one.

    - If you've tagged the table's header, select Ignore first row to
      prevent it from being extracted as content.

    <img src="./media/image44.png"
style="width:5.35081in;height:2.23672in" />

    <img src="./media/image45.png"
style="width:5.17529in;height:2.20119in" />

    <img src="./media/image46.png"
style="width:5.1437in;height:2.22879in" />

    <img src="./media/image47.png"
style="width:5.37027in;height:2.25199in" />

1.  Tag all five documents with same process. Once you've tagged a
    document, move to the next one using the navigation arrows at the
    top right of the document preview.

### Task 6: Model summary and train

1.  Select the **Next** button at the bottom of the screen.

    <img src="./media/image48.png"
style="width:6.26806in;height:2.69028in" />

2.  Review the **Model summary**. Under Information to extract you'll
    see that Customer ID and Due Date only appeared in five examples out
    of **10**, whereas everything else appeared in all 10 examples.

3.  If everything looks acceptable, select **Train**.

    <img src="./media/image49.png"
style="width:6.26806in;height:2.56042in" />

## Exercise 2: Use your model

### Task 1: Quick test

1.  After your model completes training, you can view important details
    about your newly trained model on a details page.

    <img src="./media/image50.png"
style="width:6.26806in;height:2.88819in" />

2.  To see your model in action, select **Quick test**.

    <img src="./media/image51.png"
style="width:6.26806in;height:3.42222in" />

3.  Drag and drop or upload an image from your device to test. From the
    previous sample data, use the files from the Test folders that we
    didn’t use for training (either from AI Builder Document processing
    Sample Data\Adatum\Test or AI Builder Document processing Sample
    Data\Contoso\Test).

4.  You can now view the detected fields that you chose and the
    associated confidence scores for retrieving the individual fields
    compared to the trained model.

    <img src="./media/image52.png"
style="width:6.26806in;height:3.75417in" />

### Task 2: Publish your model

1.  Your model can't be used until you publish it. If you're satisfied
    with your model, select **Publish** to make it available for use.

    <img src="./media/image53.png"
style="width:6.26806in;height:3.02431in" />

### Task 3: Use your model in Power Automate

Now that your model is published, you can use your Document processing
model to process documents using Power Automate. A special AI Builder
action can be used to ingest documents from emails, document libraries,
and other sources, and output the processed data.

1.  Select **Use model**.

    <img src="./media/image54.png"
style="width:6.26806in;height:2.78819in" />

2.  Select **Build intelligent automations** and select one of the
    triggers proposed. For this module, we use the **Microsoft 365
    Outlook work account**.

    <img src="./media/image55.png"
style="width:6.26806in;height:2.99861in" />

    <img src="./media/image56.png" style="width:6.26806in;height:3in" />

3.  Make sure that you're signed into the flow and then
    select **Continue** to confirm the creation of the flow.

    The flow is already configured to run when you receive an email with
an attachment and the email subject is AI Builder. Let's see it in
action!

    <img src="./media/image57.png" style="width:6.26806in;height:3.55in" />

4.  Select **Save** on the top right to test the flow.

    <img src="./media/image58.png"
style="width:6.26806in;height:2.44167in" />

5.  Select **Test**.

    <img src="./media/image59.png"
style="width:6.26806in;height:2.64931in" />

6.  Select **Manually** and then select **Test**.

    <img src="./media/image60.png"
style="width:6.26806in;height:3.91667in" />

7.  Now send yourself an email with the subject **AI Builder** and
    attach the document you used for quick test previously.

8.  After a few seconds, you see the flow running. The flow extracts the
    data from the attachment and sends you back an email with the
    results.

Congratulations! You built an intelligent automation flow. You can then
customize the flow to your needs to perform any other action you might
want.

### Task 4: Use your model in Power Apps

Now that your model is published, you can use your Document processing
model in a canvas app. A special component is available for you to add
that analyzes any image and extracts the text based on your trained
Document processing mode.

1.  From the  <https://make.powerautomate.com/, select **AI Hub**, and
    select your model under Recently Created.

    <img src="./media/image61.png"
style="width:6.26806in;height:2.91806in" />

2.  Select **Use model**.

    <img src="./media/image62.png"
style="width:6.26806in;height:2.94792in" />

3.  Select **Build intelligent apps** to begin the canvas app creation
    experience.

    <img src="./media/image63.png"
style="width:6.26806in;height:2.93472in" />

4.  Within your canvas app, a **Form processor component** is
    automatically added and linked to your published Document processing
    model.

    > **Note:** If you want to add additional AI models to the app, select
Insert and then select Form processor to add a Form processor
component. Next, select the AI model property from the right-hand
properties panel. A list of AI models appears to select. Only
published models appear in the drop-down list.

    <img src="./media/image64.png"
style="width:6.26806in;height:3.42222in" />



5.  Next, we select which field from the invoice to display.
    Select **Insert** and then add a **Label** component.

6.  With the label selected, make sure that **Text** property is
    selected in the top left-hand corner. In the formula bar,
    write FormProcessor1.Fields. This code gives you access to the other
    properties from the model as well. For this exercise, we choose
    Invoice Number. The result looks similar to this image.

    <img src="./media/image65.png" style="width:6.26806in;height:0.22708in"
alt="Screenshot of a field name in the Fields property in Power Apps." />

    > **Note:** Notice how 'Invoice Number' is in single quotes in the
previous image. This is because when the Invoice Number column was
created, the column name was created with a space in between the
words. If your columns weren't created with spaces, you don't need the
single quotes and your code may look like this image instead.

    <img src="./media/image66.png" style="width:6.26806in;height:0.30903in"
alt="Screenshot of InvoiceNumber without spaces." />

7.  Next, we add a gallery so we can see the data from the items of the
    invoice. Select **Insert** and then **Vertical Gallery**.

8.  In the Items property of the gallery,
    write: FormProcessor1.Tables.Items

    <img src="./media/image67.png"
style="width:6.26806in;height:2.89514in" />

9.  Select **Play** on the upper right of the Power Apps studio to
    preview the app.

10. Select **Analyze** and then select the image that you used to quick
    test previously.

    <img src="./media/image68.png"
style="width:6.26806in;height:2.91806in" />

11. A preview of your document shows the **Invoice Number** and the
    items from the invoice.

    <img src="./media/image69.png"
style="width:6.26806in;height:2.87778in" />

### Conclusion:

By the end of this lab, participants will have
successfully built and trained a custom AI model capable of extracting
specific data fields from documents. They will have tested the model
with real-world data, integrated it into automated workflows within
Power Automate, and used it within a canvas app in Power Apps. This lab
demonstrates how AI models can be used to automate document processing
and streamline business tasks, providing practical experience in
leveraging AI Builder for intelligent automation.
