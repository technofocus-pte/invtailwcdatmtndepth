# Lab 2 - Creare un' Inventory Management App

**Obiettivo:** l'obiettivo di questo lab è guidare i partecipanti
attraverso la creazione di un'applicazione funzionale per la gestione
dell'inventario utilizzando Microsoft Power Apps e Copilot. I
partecipanti impareranno a configurare il proprio ambiente Common Data
Service, progettare schermate dell'app, gestire i dati e automatizzare i
flussi di lavoro di rifornimento dell'inventario con Power Automate.

**Tempo stimato:** 40 min

## Esercizio 1: Creare un' Inventory Management App

### Attività 1: Verifica dell'ambiente Dataverse

1.  Aprire un browser e vai a
    +++**https://admin.powerplatform.microsoft.com**+++. Accedere con
    l'account amministratore di Office 365.

2.  Selezionare **Environments** nel menu di navigazione a sinistra.
    **Developer environment** dovrebbe essere stato creato
    automaticamente, come illustrato nell'immagine seguente. Questo
    ambiente viene creato automaticamente non appena fornisci la licenza
    di Microsoft Power App for Developer utilizzando i tuoi account
    amministratore. Il nome dell'ambiente sarà diverso per ogni account
    amministratore.

- ![](./media/image1.png)

3.  Utilizzare lo stesso ambiente di sviluppo per eseguire tutti gli
    esercizi di questo laboratorio.

> **Nota**: in questo laboratorio viene utilizzato l'ambiente di
> sviluppo **Dev one**. Il nome dell'ambiente può essere diverso per
> utenti diversi. Assicurati di selezionare l'ambiente di sviluppo.

### Attività 2: Creare un' inventory management app utilizzando Copilot. 

1.  Aprire un browser e passare a +++**https://make.powerapps.com**+++
    Accedere con l'account tenant amministratore di Office 365.

2.  Fare clic sull'ambiente nell'angolo in alto a destra e selezionare
    **your developer** (Dev one è un ambiente di sviluppo utilizzato in
    questa guida di laboratorio)

- ![](./media/image2.png)

3.  Immettere il prompt sottostante e fare clic sul pulsante **Enter**.

- +++**build a candy inventory management app**+++

  ![](./media/image3.png)

4.  Selezionare il riquadro **Start with Copilot**

- ![](./media/image4.png)

5.  Immettere il prompt sottostante e fare clic su **Generate** per
    creare una tabella con l'aiuto di Copilot

- +++**Candy Inventory management**+++

  ![](./media/image5.png)

6.  Copilot genera le tabelle come mostrato nell'immagine seguente.

- ![](./media/image6.png)

7.  Fare clic su tre punti accanto a Candy e quindi fare clic su **View
    data.**

- ![](./media/image7.png)

8.  I dati nella tabella Candy dovrebbero avere i dati mostrati
    nell'immagine seguente.

- ![](./media/image8.png)

9.  Fare clic su **Supplier –\> View data** ed esplorare i dati, quindi
    chiudere la finestra di visualizzazione.

- ![](./media/image9.png)

10. Aggiorna uno degli ID e-mail del fornitore con il tuo ID e-mail di
    lavoro/personale

- ![](./media/image10.png)

11. Cliccare su **Order –\> View data**

- ![](./media/image11.png)

12. Entrare il prompt sotto nella casella di testo e fare clic su
    **Enter**. Questa colonna è necessaria per notificare quando la
    quantità è scesa al di sotto del punto di riordino.

- +++**Add reorder point column to Candy table**+++

  ![](./media/image12.png)

13. Aggiungere la colonna candyInStock con il tipo come Number. Se la
    quantità è inferiore ai punti di riordino, la colonna Quantità
    automatizzerà l'aggiunta con candyInStock.

- +++**Add** candyInStock\*\* column to Candy table with sample stock
  count\*\*+++

  ![](./media/image13.png)

14. La tabella è stata aggiornata con la colonna dei punti di riordino e
    la colonna Candy in magazzino

- ![](./media/image14.png)

15. Fare clic sul pulsante **Save and open app**

- ![](./media/image15.png)

16. Sulla finestra **Done working?**, cliccare su **Save and open app**
    e attendere che l'app venga creata.

- ![](./media/image16.png)

  ![](./media/image17.png)

17. Saltare la finestra di benvenuto.

- ![](./media/image18.png)

18. L'app viene creata e dovrebbe assomigliare all'immagine qui sotto.

- ![](./media/image19.png)

19. Fare clic sul pulsante **Save** e inserire il nome **MSCandy
    Inventory management app**, quindi fare clic sul pulsante **Save**.

- ![](./media/image20.png)

  ![](./media/image21.png)

20. Esplorare l'app. Fare clic su **Candy screen** dalla vista ad
    albero. È possibile aggiornare l'etichetta dello schermo alla
    **Candy Inventory management**

- ![](./media/image22.png)

21. Esplorare la schermata Supplier e aggiornare secondo le tue
    esigenze.

- ![](./media/image23.png)

### Attività 3: Creare un candy quality Screen

1.  Fare clic su **New Screen** e selezionare **Blank** template.

- ![](./media/image24.png)

2.  Selezionare la nuova schermata e fare clic con il pulsante destro
    del mouse su **Rename**

- ![](./media/image25.png)

3.  Assegnare un nome allo schermo +++**Candy quality screen**+++

- ![](./media/image26.png)

4.  Fare clic sull'area Schermo e selezionare **Create a new
    table(preview)**

- ![](./media/image27.png)

4.  Fare clic su **New table –\> Add columns and data.**

- ![](./media/image28.png)

5.  Fare clic su **New column -\> Edit column.**

- ![](./media/image29.png)

6.  Inserire il nome visualizzato come **Candy ID**, quindi fare clic
    sul pulsante **Update**.

- ![](./media/image30.png)

7.  Cliccare su Nuova colonna e inserire i dettagli sottostanti e poi
    cliccare su **Save**.

    - **Display Name:** Candy Name

    - **Data Type:** Choice

    - **Required:** Yes.

    - **Choices:** add below choices

      - Chocolate Bar

      - Gummy Bears

      - Jellybeans

      - Lollipop

      - Sour Patch Kids

- ![](./media/image31.png)

8.  Fare clic su New Column e aggiungere una colonna con i dettagli
    sottostanti, quindi fare clic su **Save**.

    - **Display Name:** Candy Quality
    - **Data type:** Choice
    - **Required:** Yes
    - **Choice:** labels
      - Defective
      - Nondefective

- ![](./media/image32.png)

> **Nota:** puoi aggiungere altre colonne in base ai requisiti dell'app.

10. Modificare il nome della tabella e aggiornala con +++**Candy Quality
    check**+++. ![](./media/image33.png)

11. Fare clic su **Save and exit -\> Save and exit**.
    ![](./media/image34.png)

12. Tornerai alla pagina dell'app Power Apps. Selezionare la schermata
    appena aggiunta e fare clic su Insert e selezionare **Edit form**
    come mostrato nell'immagine sottostante. ![](./media/image35.png)

13. Fare clic sul contenitore e selezionare la tabella dell'origine dati
    come +++**Candy Qualities table**+++. ![](./media/image36.png)

14. Dovresti vedere il modulo come nell'immagine sottostante.
    ![](./media/image37.png)

15. Regolare la tabella al centro della pagina. Fare clic su **Insert-\>
    Text label.** ![](./media/image38.png)

16. Regolare l'etichetta del testo e inserire il testo come: +++**Candy
    Quality check**+++ e aggiorna gli stili del testo.
    ![](./media/image39.png)

17. Selezionare il **Form**. Fare clic su **Insert** e selezionare
    **Button**. ![](./media/image40.png)

18. Trascinare il pulsante di invio e posizionalo al centro del
    contenitore. Seleziona il pulsante e modifica il testo delle
    **properties** in **Submit** come mostrato nell'immagine
    sottostante. ![](./media/image41.png)

19. Selezionare il pulsante **Submit** e selezionare la funzione
    **OnSelect** e immettere la funzione seguente.

> **Nota:** Form4 nella formula deve essere sostituito con il nome del
> modulo SubmitForm(Form4); NewForm(Form4).

![](./media/image42.png)

20. Selezionare il contenitore, in properties, selezionare Modalità
    **Default** su **New**. ![](./media/image43.png)

21. Fare clic su **Save,** quindi fare clic sul pulsante **Preview app**
    come mostrato nell'immagine sottostante. ![](./media/image44.png)

22. Inserire i dettagli di Candy e quindi fare clic sul pulsante
    **Submit**. ![](./media/image45.png)

23. Tornare alla tabella della qualità di Candy nell'ambiente Dataverse
    e dovresti vedere il record aggiunto sopra. ![](./media/image46.png)

24. Chiudere la finestra di anteprima.

## Esercizio 2: Creare un flusso di Power Automate per rifornire l'inventario.

### Attività 1: Creare un flusso di Power Platform per attivare l'e-mail di rifornimento

1.  Torna alla scheda Power Automate e fare clic su **My flows** -\>
    **New flow -cloud flow.** ![](./media/image47.png)

2.  Inserire il nome del flusso come: +++**Candy Restock Flow**+++.
    Cercare +++ **When a row**+++ è e selezionare l'azione **When a row
    is added or modified** di Common Data Service, quindi fare clic su
    **Create**. ![](./media/image48.png)

3.  Selezionare l'azione e imposta i parametri sottostanti.

    - Change Type; Added or Modified
    - Table Nam: Candies

    &nbsp;

    - Scope: Organization ![](./media/image49.png)

4.  Aggiungere un'azione dopo un'azione **“when a row is added, modified
    or deleted”.** ![](./media/image50.png)

5.  Cercare **Condition** e selezionare l'azione **Control’s
    Condition**. ![](./media/image51.png)

6.  Fare clic su Chose value e selezionare scegli dall'azione dinamica
    del passaggio precedente. ![](./media/image52.png)

7.  Cercare la colonna +++**Quantity**+++ e selezionala.
    ![](./media/image53.png)

8.  Selezionare una condizione **is less than** e fare clic su ‘Enter
    data from previous action’. ![](./media/image54.png)

9.  Cercare la colonna +++**Reorder points**+++ e selezionala.
    ![](./media/image55.png)

10. **Aggiungere un'azione** in condition **True**.
    ![](./media/image56.png)

11. Selezionare l'azione +++**Approvals**+++. ![](./media/image57.png)

12. Selezionare +++**Start and wait for an Approvals**+++ .
    ![](./media/image58.png)

13. Selezionare Approval Type come: +++**Approve/Reject – First to
    Respond**+++. Inserire il titolo come: +++**Approve to
    Restock**+++ - e fare clic sul pulsante Dinamico per selezionare i
    dati del passaggio precedente. ![](./media/image59.png)

14. Cercare **Candy Name+++** e selezionalo**.**
    ![](./media/image60.png)

15. Inserire i dettagli qui sotto.

- Assegnato a: il tuo ID e-mail di lavoro.

      Assigned to: Your work email id.

      Details:

      Hi Sir,  

      is out of stock - for customers to place an order. Please approve to
      restock.  

      Thanks

> **Nota:** Puoi personalizzare la sezione dei dettagli in base alle tue
> esigenze.

![](./media/image61.png)

16. **Aggiungere un'azione** dopo l'azione **approval**.
    ![](./media/image62.png)

17. Cercare +++**condition**+++ e selezionare **Control – Condition**.
    ![](./media/image63.png)

18. Fare clic su Choose value e selezionare **Outcome** da Inizio e
    attendere un'azione di approvazione. ![](./media/image64.png)

19. Selezionare la condizione **is equal to** e immettere il valore
    **Approve**. ![](./media/image65.png)

20. In condition **True,** **add an action**. ![](./media/image66.png)

21. Cercare **Update Row** e selezionala dalla sezione **Microsoft
    Dataverse**. ![](./media/image67.png)

22. Selezionare la tua tabella **Candy** e fare clic su **Row Id**,
    selezionare l'azione Dynamic. ![](./media/image68.png)

23. Cercare una colonna di identificatore univoco dalla tabella e
    selezionala. ![](./media/image69.png)

24. Fare clic sul menu a discesa **Advanced Parameters** e selezionare
    la colonna **Quantity**. ![](./media/image70.png)

25. Inserire la funzione sottostante (digiti nella tua app) e comprimi
    l'azione.

- > **Nota:** la funzione seguente non funziona per te poiché il nome
  > dello schema della colonna potrebbe essere diverso. Vai alla colonna
  > \> tabella e copia il nome dello schema.

  +++add(triggerBody()?\[‘cr8a3_Quantity’\],triggerBody()?\[‘cr8a3_CandyInStock’\])+++

  ![](./media/image71.png)

26. Fare clic sul pulsante **Salva** per salvare il flusso di Power
    Automate. ![](./media/image72.png)

### Attività 2: Testare il flusso di rifornimento

1.  Tornare alla scheda **PowerApps** e fare clic sulla schermata
    **Candy** dalla vista ad albero a sinistra e selezionare **Play**.

- > **Nota:** è possibile aggiornare il titolo della schermata

  ![](./media/image73.png)

2.  Selezionare la Candy e fare clic su **Edit**.
    ![](./media/image74.png)

3.  Immettere il valore **Quantity**, **less than reorder points** e
    **confermare** le modifiche. ![](./media/image75.png)

4.  Tornare alla scheda Power Automate flow e fare clic su My flows -\>
    Your flow. ![](./media/image76.png)

5.  Il flusso è in esecuzione ed è in condizione.
    ![](./media/image77.png)

6.  Aprire una nuova scheda e vai a +++**https://outlook.com**+++ e
    accedi con il tuo account amministratore di Office 365. Dovresti
    aver ricevuto un'e-mail per rifornire. **Approve** e **submit**.
    ![](./media/image78.png)

- ![](./media/image79.png)

7.  Il flusso ha avuto successo ora. ![](./media/image80.png)

- ![](./media/image81.png)

8.  Tornare a PowerApps e controlla la quantità di prodotti sopra
    indicata. Dovrebbe essere stato aggiornato (caramelle in magazzino +
    quantità quando è inferiore al punto di riordino)
    ![](./media/image82.png)

### Conclusione:

Al termine di questo laboratorio, i partecipanti saranno in grado di
verificare il proprio ambiente Dataverse, creare un'app di gestione
dell'inventario utilizzando Copilot, progettare una schermata di
controllo della qualità delle caramelle con campi personalizzati e
implementare i flussi Power Automate per attivare le richieste di
rifornimento in base ai livelli di inventario. Inoltre, acquisiranno
competenze nel testare e convalidare flussi di lavoro automatizzati per
garantire aggiornamenti accurati dell'inventario dopo i processi di
approvazione. Questo approccio strutturato consentirà ai partecipanti di
sfruttare in modo efficace le funzionalità di Power Apps e Power
Automate, migliorando le proprie competenze nello sviluppo di app e
nell'automazione dei processi.
