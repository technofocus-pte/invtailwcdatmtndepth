# Lab 3 - Creazione di un flusso automatizzato per inviare una notifica al responsabile quando viene creato un nuovo elemento in Dynamics 365 Business Central

**Obiettivo:** In questo laboratorio, i partecipanti impareranno come
creare un flusso automatizzato in Power Automate che invia una notifica
e-mail ogni volta che viene creato un nuovo elemento in Microsoft
Dynamics 365 Business Central. Seguendo un processo strutturato, i
partecipanti acquisiranno familiarità con l'attivazione dei flussi
basati sui dati di Business Central, la raccolta di informazioni sugli
elementi pertinenti, l'applicazione della logica condizionale e
l'esecuzione di azioni per l'invio di avvisi e-mail. Questa esperienza
pratica consentirà ai partecipanti di sfruttare Power Automate per
migliorare i processi aziendali e le notifiche.

**Tempo stimato:** 15 minuti

### Attività 1: Iscrizione a Microsoft Dynamic 365 Business Central

1.  Passare a
    +++**https://www.microsoft.com/en-us/dynamics-365/products/business-central**+++
    e fare clic su **Try for Free.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image1.png)

2.  Immettere l'ID tenant di Office 365 e fare clic su **Next**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image2.png)

3.  Quindi fare clic su **Sign in** e inserire le credenziali.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

4.  Selezionare **United states** come paese o area geografica, inserire
    il tuo **phone number** e quindi selezionare **Get started**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

5.  Quindi fare clic su **Get started** per accedere a Business Central.

- ![A close-up of a business card AI-generated content may be
  incorrect.](./media/image5.png)

6.  Selezionare il pulsante **Skip Survey** per procedere.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image6.png)

7.  Verrà visualizzata la home page di Dynamics 365 Business Central.

- ![A screenshot of a website AI-generated content may be
  incorrect.](./media/image7.png)

### Attività 2: Avviare Power Automate

1.  Aprire una nuova scheda accanto a Dynamic 365 business central e
    passa a +++**https://make.powerautomate.com**/+++ nel browser.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image8.png)

2.  Se richiesto, immettere **Microsoft 365 tenant id** nel campo
    rispettato e fare clic sul pulsante **Next**.

- ![A screenshot of a login box AI-generated content may be
  incorrect.](./media/image9.png)

3.  Inserire la **password** nell'apposito campo e clicca su **Sign
    in.**

- ![A screenshot of a login screen AI-generated content may be
  incorrect.](./media/image10.png)

4.  Dalla barra di navigazione in alto, selezionare l'ambiente **Dev
    One.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image11.png)

5.  Fare clic su **+Create** nel menu a sinistra.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image12.png)

6.  Selezionare il riquadro **Automated cloud flow**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image13.png)

### Attività 3: Creare il trigger in base ai dati di Business Central

1.  Nella casella **Flow name**, inserire +++**Email notification for
    new furniture**+++.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image14.png)

2.  In **Choose your flow’s trigger search bar**, inserire **business
    central**. Scorrere verso il basso per visualizzare i trigger e
    selezionare **When a record is created (V3).**

3.  Fare clic su **Create**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image15.png)

4.  Inserire i dettagli del trigger:

    1.  **Environment name**: Entrare +++**PRODUCTION**+++.

    2.  **Company name**: Selezionare **CRONUS USA, Inc.** dal list.

    3.  **Table name**: Selezionare **items**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image16.png)

### Attività 4: Raccolta dati da Business Central

1.  Fare clic sul **pulsante +** (Aggiungi), quindi selezionare **Add an
    action**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image17.png)

2.  Nella finestra **Add an action**, digitare +++**Dynamics 365
    Business Central**+++ nella casella di ricerca e scegli l'azione
    **Get record (V3).**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image18.png)

3.  Inserire le seguenti informazioni:

    1.  **Environment**: +++**PRODUCTION**+++.

    2.  **Company name**: Selezionare **CRONUS USA, Inc.**.

    3.  **Table name**: Selezionare **items**.

    4.  **Row id**: Selezionare the **Row Id** token da Dynamic content.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image19.png)

### Attività 5: Creare la condizione

1.  Fare clic sul **pulsante +** sotto Get record e selezionare **Add an
    action**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image20.png)

2.  Nella barra di ricerca **Add an action**, inserire **Control**.
    Scegliere l'azione **Condition**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image21.png)

3.  Impostare la condizione:

    1.  Nella prima casella **Choose a value**, selezionare il token
        **Item Category Code** da Contenuto dinamico.

    2.  Mantenere l'opzione **is equal to**.

    3.  Nella seconda casella **Choose a value**, inserire
        +++**FURNITURE**+++.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image22.png)

### Attività 6: Creare un'azione in base alla condizione

1.  Nella finestra **If yes or True**, fare clic su **Add an action**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image23.png)

2.  Cercare +++**office 365 outlook**+++ nella finestra Add an action e
    fare clic su **see more**. Nel trigger di Office 365 Outlook
    selezionare **Send an Email (V2).**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image24.png)

  ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image25.png)

3.  Inserire i dettagli dell'e-mail:

    1.  **To**: Immettere "Admin" e selezionare **Mod Admin** dal
        suggerimento, ad esempio l'ID di posta elettronica del tenant di
        Office 365 che si sta utilizzando in questo lab.

    2.  **Subject**: Entrare +++**New furniture released**+++.

    3.  **Body**:

        1.  Aggiungere il testo **New** **furniture**.

        2.  Aggiungere il **numero** del token da Contenuto dinamico.

        3.  Aggiungere il token **displayName** da Contenuto dinamico.

        4.  Aggiungere il testo +++ **has just released**+++

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image26.png)

4.  Fare clic su **Save** per finalizzare il flusso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image27.png)

### Attività 7: Testare il flusso

1.  Dalla barra in alto, fare clic sul pulsante **Test**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image28.png)

2.  Selezionare il processo **Manual** e quindi fare clic su **Test**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image29.png)

3.  Tornare al **Business Central website** e dalla barra superiore vai
    a **Sales** 🡪 **Items**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image30.png)

4.  Fare clic sul pulsante **+ New**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image31.png)

5.  Selezionare **ITEM** e quindi fare clic su **OK**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image32.png)

6.  Nel campo Item Category Code, selezionare **FURNITURE** e nel campo
    Description, scrivere **Office Chair.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image33.png)

7.  Fare clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image34.png)

8.  Nel portale Power Automate, fare clic su **App launcher** situata
    nell'angolo in alto a sinistra. Seleziona **Outlook** e quindi puoi
    vedere che la risposta automatica viene ricevuta sull'**e-mail**
    fornita dall'amministratore MOD.

- ![A white background with blue text AI-generated content may be
  incorrect.](./media/image35.png)

### Conclusione:

Al termine di questo laboratorio, i partecipanti avranno creato
correttamente un flusso di notifica e-mail automatizzato in Power
Automate per i nuovi elementi in Business Central. Avranno acquisito
esperienza pratica nell'impostazione di trigger, azioni e condizioni,
che sono competenze essenziali per automatizzare i flussi di lavoro. I
partecipanti comprenderanno inoltre come raccogliere e manipolare i dati
da Business Central in modo efficace, consentendo loro di semplificare
le comunicazioni e migliorare la produttività nelle rispettive
organizzazioni. Queste conoscenze serviranno come base per un'ulteriore
esplorazione delle funzionalità di Power Automate nell'automazione di
vari processi aziendali.
