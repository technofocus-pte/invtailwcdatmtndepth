# **Lab 5 - Creazione e analisi del processo di Accounts Payable Refund** 

**Obiettivo:** l'obiettivo di questo lab è creare e analizzare un
processo di rimborso della contabilità fornitori utilizzando le
funzionalità di process mining di Power Automate. I partecipanti
impareranno a importare i dati da un file CSV, a creare un nuovo
processo e a utilizzare l'app desktop Process Mining per analizzare gli
indicatori chiave di prestazione (KPI) e altre metriche per ottenere
informazioni dettagliate sull'efficienza e le prestazioni del processo
di rimborso della contabilità fornitori.

**Tempo stimato:** 30 minuti

### Attività 1: Creare un processo

1.  Vai a +++**https://make.powerautomate.com/**+++. Se richiesto,
    accedere con le credenziali del tenant di Office 365. Selezionare
    **United States** come paese/area geografica, quindi seleziona **Get
    started**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image1.png)

2.  Selezionare il tuo ambiente: **Dev One**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image2.png)

3.  Nel riquadro di navigazione a sinistra, selezionare **More** 🡪
    **Process mining**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

4.  Nella sezione **Create new process**, selezionare **Start here**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

5.  Nella schermata **Create a new process**, immettere un nome per il
    processo: +++**Processmining**+++, quindi selezionare **Import
    data**, selezionare **Data flow** e quindi selezionare **Continue**.
    (Facoltativo) Inserire una descrizione per il processo.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image5.png)

6.  Se viene chiesto di **choose where to export**, selezionare
    **PowerBi embedded** da **Choose your destination** e quindi
    selezionare **Continue**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image6.png)

### Attività 2: Importare dati

1.  Nella schermata **Choose a data source**, selezionare **Text/CSV**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image7.png)

2.  Sotto l'intestazione **Connection settings**, selezionare **Upload
    file (Preview)**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image8.png)

3.  Selezionare **Browse**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image9.png)

7.  Trovare e selezionare
    **SampleData_AP_Refunds_Financial_EventLog.csv**. Location:
    **C:Files**

&nbsp;

4.  Selezionare **Open**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image10.png)

5.  Se ti viene chiesto di autenticarti, selezionare **Sign in** e
    seguire le istruzioni. (Configura il blocco popup su consenti.)

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image11.png)

6.  Selezionare **Next**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image12.png)

7.  Visualizzare l'anteprima dei dati del file e selezionare **Next**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image13.png)

8.  Quando viene visualizzata la query di alimentazione, che consente di
    trasformare i dati, selezionare **Next**.

- ![](./media/image14.png)

9.  Abbinare il **Attribute Name** dai dati di esempio al **Attribute
    Type** in base alle esigenze.

- ![](./media/image15.png)

10. In questo esempio, gli attributi dei dati che verranno modificati
    sono
    **InvoiceValue**, **Resource**, **StartTimestamp**, **EndTimestamp**, **CaseId**
    e **ActivityName** come indicato di seguito.

- **InvoiceValue** – Financial per case (first event)

  **Resource** – Resourse

  **StartTimestamp** – Event Start

  **EndTimestamp** – Event End

  **CaseId** – Case ID

  **ActivityName** - Activity

  ![A screenshot of a data AI-generated content may be
  incorrect.](./media/image16.png)

11. Al **termine**, il mapping degli attributi dovrebbe essere simile
    allo screenshot seguente.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image17.png)

12. Selezionare **Save and analyze**. L'esecuzione dell'analisi potrebbe
    richiedere alcuni minuti.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image18.png)

13. Al termine del **processo di analisi**, vedrai una mappa del
    processo e un dashboard con altre informazioni dettagliate sul tuo
    processo. Sulla dashboard, puoi visualizzare molte metriche che ti
    aiuteranno ad **analizzare il tuo processo.**

- ![](./media/image19.png)

### Attività 3: Analizzare un processo

Portiamo l'analisi del nostro processo oltre i KPI. Useremo l'app
desktop Power Automate Process Mining, in cui è possibile modificare e
analizzare i processi creati nella funzionalità di process mining.

1.  Dalla barra in alto, fare clic su **Download process Mining app**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image20.png)

2.  Fare doppio clic sul file di **PowerAutomateProcessMining** App
    installer in Downloads.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image21.png)

3.  Fare clic su **Install**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image22.png)

4.  Dopo aver installato l'app Processmining, l'app si avvia
    automaticamente, in caso contrario, avvia l'app manualmente. Dopo
    aver avviato l'app, selezionare **English** come lingua e fare clic
    su **Next Step**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image23.png)

5.  Selezionare tutte le **caselle di controllo** come mostrato
    nell'immagine e fare clic su **Next**.

- ![](./media/image24.png)

6.  Quindi fare clic sul pulsante **Apply and mine**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image25.png)

7.  Quindi selezionare il pulsante **Use**, navigherà alla finestra di
    accesso.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image26.png)

8.  Inserire l'ID tenant dell'amministratore e fare clic sul pulsante
    **Sign In**.

- ![A computer screen with a blue background AI-generated content may be
  incorrect.](./media/image27.png)

9.  Immettere quindi la password del tenant amministratore e fare clic
    su **Sign in**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image28.png)

8.  Se viene visualizzato un popup che dice ‘Stay signed in to all your
    apps’, quindi seleziona **No, sign in to this app only**.

> ![](./media/image29.png)

10. Sulla barra degli strumenti dell'app Power Automate Process Mining,
    seleziona l'ambiente **Dev** **One** in alto a destra.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image30.png)

11. Cercare il processo che hai creato con la funzionalità di process
    mining in Power Automate (**Processmining**).

12. Selezionare **Default** per visualizzare la vista predefinita. Sei
    pronto per utilizzare le funzionalità avanzate dell'app desktop
    Process Mining.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image31.png)

  > Nota: se viene visualizzato un messaggio relativo a **Model size is
  > too large for your PC configuration** e vengono fornite le opzioni
  > Yes e No per l'esecuzione, selezionare **Yes**.

  ![](./media/image32.png)

13. Sulla barra degli strumenti del pannello Personalizza, seleziona
    **Frequenza** (la prima icona), quindi seleziona **Conteggio casi**
    nel **menu a discesa Metrica.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image33.png)

  > La mappa del processo visualizza il numero di case del processo che
  > includono l'attività specificata in ogni nodo.

14. Nel pannello **Customize**, seleziona **Performance** (icona
    dell'orologio), quindi selezionare **Mean duration** dal menu a
    discesa.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image34.png)

  > Si noti che la fase **Refund with special voucher**  ha una durata
  > media lunga rispetto ad altre fasi.

  ![A diagram of a customer service AI-generated content may be
  incorrect.](./media/image35.png)

15. Nel pannello **Customize**, selezionare **Finance** (l'icona del
    pezzo di carta), quindi selezionare **Mean** dal menu a discesa
    **Metric.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image36.png)

  > Si noti che lo stesso passaggio di **Refund with Special Voucher** 
  > comporta solo $ 631,11 di valore della fattura, che è meno della
  > metà della maggior parte degli altri passaggi.

  ![A white sign with black text AI-generated content may be
  incorrect.](./media/image37.png)

16. Selezionare **Save**.

- ![](./media/image38.png)

### Conclusione:

In questo laboratorio, i partecipanti hanno creato e analizzato un
processo di rimborso della contabilità fornitori utilizzando le
funzionalità di Process Mining di Power Automate. Importando i dati CSV,
hanno costruito una mappa e una dashboard dettagliate dei processi, che
hanno potuto esaminare gli indicatori chiave di prestazione (KPI) e le
metriche di processo. Attraverso l'app desktop Power Automate Process
Mining, i partecipanti hanno eseguito analisi più approfondite,
identificando inefficienze come lunghe durate e valori delle fatture più
bassi in passaggi specifici. Questo laboratorio ha dimostrato come il
Process Mining possa aiutare le organizzazioni a ottimizzare i flussi di
lavoro finanziari, migliorare l'efficienza e semplificare le operazioni
di contabilità fornitori.
