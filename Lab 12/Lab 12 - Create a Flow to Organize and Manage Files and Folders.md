# Lab 12 - Creare un flusso per organizzare e gestire file e cartelle

**Obiettivo:** L'obiettivo di questo lab è automatizzare il processo di
backup dei file da una cartella designata sul desktop utilizzando
**Power Automate Desktop**. I partecipanti creeranno un flusso che copia
i file da una cartella denominata **Contoso_Files**, li sposta in una
cartella di backup appena creata e aggiunge un timestamp al file di
backup. Questo lab offre esperienza pratica nell'automazione delle
attività di gestione dei file, tra cui la creazione di cartelle, la
copia di file e la ridenominazione con formati di data e ora dinamici.

**Tempo stimato:** 20 minuti

### Attività 1: Creare una cartella e un flusso desktop

1.  Creare una cartella sul desktop e rinominala come **Contoso_Files.**

- ![A blue wavy lines on a dark background AI-generated content may be
  incorrect.](./media/image1.png)

2.  **Selezionare Report.txt** file dalla cartella **C:\* folder and
    move the .**txt\*\* nella cartella **Contoso_Files**.

- ![A black rectangle with white dots AI-generated content may be
  incorrect.](./media/image2.png)

3.  Aprire Power Automate Desktop e **Login** con **Office 365 tenant
    credential**. Scegliere l'ambiente **Contoso** dalla barra
    superiore.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

4.  Fare clic su **+ New flow** nell'angolo in alto a sinistra e inizia
    a creare un nuovo flusso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

5.  Immettere +++**Backup File Flow**+++ come nome del flusso e
    selezionare la casella di controllo del **Power Fx enable
    (Preview).** Quindi fare clic su **Create**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image5.png)

6.  Dalla barra di spostamento **Actions** a sinistra, cercare +++**Get
    special folder**+++ nell'area di lavoro. Seleziona l'azione facendo
    doppio clic su di essa per aggiungerla al flusso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image6.png)

7.  Quindi fare clic sul pulsante **Save** per salvare l'impostazione
    predefinita del pulsante.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image7.png)

8.  Dalla barra di spostamento **Actions** a sinistra, cercare l'azione
    +++**Get files in folder**+++ nell'area di lavoro. Seleziona
    l'azione facendo doppio clic su di essa per aggiungerla al flusso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image8.png)

9.  Aggiungere l'azione **Get files in folder** per impostare il campo
    Folder su +++\*\*C:\_Files+++ **Questa impostazione selezionerà la
    cartella creata in precedenza sul desktop**. Quindi fare clic sul
    pulsante **Save**\*\*.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image9.png)

10. Dalla barra di navigazione **Actions** a sinistra, cerca l'azione
    +++**Create Folder**+++ nell'area di lavoro. Selezionare l'azione
    facendo doppio clic su di essa per aggiungerla al flusso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image10.png)

11. Nel campo **Create new folder into** dell'azione Create folder,
    inserire +++\*\*C:\*+++ Nel campo **New folder name**, inserire
    **Contoso_Backup**. Dopo aver inserito le informazioni, fare clic
    sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image11.png)

12. Dalla barra di navigazione **Actions** a sinistra, cercare l'azione
    +++**Copy file(s)**+++ nell'area di lavoro. Selezionare l'azione
    facendo doppio clic su di essa per aggiungerla al flusso.

- ![A screenshot of a chat AI-generated content may be
  incorrect.](./media/image12.png)

13. Impostare il campo **File(s) to Copy** su +++**=File**+++, il campo
    **Destination Folder**  su +++**\*\*C:\_Backup**+++ e l'opzione a
    discesa **+++If File(s) Exists+++ **su Overwrite**. Dopo
    l'installazione, fare clic sul** pulsante **Save**\*\*.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image13.png)

14. Dalla barra di navigazione **Actions** a sinistra, cercare l'azione
    +++ **Rename file(s)**+++ nell'area di lavoro. Seleziona l'azione
    facendo doppio clic su di essa per aggiungerla al flusso.

- ![A screenshot of a chat AI-generated content may be
  incorrect.](./media/image14.png)

15. Impostare il campo **File(s) to rename** su
    **+++\*\*C:\_Backup.txt**+++. Nel menu a discesa Rename scheme**,
    selezionare l'opzione** Aggiungi data/ora**. Impostare l' opzione**
    a discesa Separatore su **Nothing**\*\* e l'opzione **DateTime
    Format** su +++**dd.MM.yy_HH.mm**+++. Dopo l'installazione, fare
    clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image15.png)

16. Il flusso **completato** dovrebbe essere simile allo screenshot
    seguente.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image16.png)

### Attività 2: Testare il flusso

1.  Al termine del flusso di esecuzione, sul desktop sarà presente una
    nuova cartella denominata File di backup. La cartella conterrà tutto
    il contenuto della cartella denominata Important e un file di testo
    aggiuntivo denominato Backup Log, in cui verranno aggiunte al nome
    del file la data e l'ora dell'ultima esecuzione del flusso.

- ![A close up of a blue rose AI-generated content may be
  incorrect.](./media/image17.png)

  ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image18.png)

### Conclusione:

In questo laboratorio, i partecipanti hanno creato con successo un
flusso di Power Automate Desktop per automatizzare l'organizzazione e la
gestione di file e cartelle. Eseguendo il backup dei file da una
cartella designata denominata Contoso_Files a una cartella di backup
appena creata, i partecipanti hanno acquisito esperienza pratica nelle
attività essenziali di gestione dei file, tra cui la creazione di
cartelle, la copia di file e la ridenominazione dinamica dei file con
timestamp. Questo lab evidenzia l'efficacia di Power Automate Desktop
nel semplificare i processi di organizzazione dei file, ridurre il
lavoro manuale e garantire che il backup dei file importanti venga
eseguito in modo sicuro. I partecipanti hanno lasciato con conoscenze
pratiche su come sfruttare l'automazione per una gestione efficiente dei
file, migliorando la loro produttività nelle attività quotidiane.
