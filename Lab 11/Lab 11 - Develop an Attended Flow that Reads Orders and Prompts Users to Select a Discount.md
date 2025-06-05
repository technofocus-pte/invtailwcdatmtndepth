# Lab 11 - Sviluppare un flusso presidiato che legge gli ordini e richiede agli utenti di selezionare uno sconto

**Obiettivo:** L'obiettivo di questo lab è sviluppare un **flusso di
Power Automate Desktop con operatore che** automatizza il processo di
lettura degli ordini da un file Excel e richiede agli utenti di
applicare uno sconto in base a determinate condizioni. I partecipanti
creeranno un flusso che legge i dati, controlla se l'importo dell'ordine
supera una soglia specifica e chiede all'utente di decidere se applicare
uno sconto, con la possibilità di inserire il valore dello sconto. Il
flusso aggiornerà quindi il foglio Excel con lo sconto applicato.

**Tempo stimato:** 25 minuti

### Attività 1: Creare un flusso desktop di Power Automate

1.  Aprire **Power Automate Desktop** e accedere con **office 365 tenant
    credential**.

2.  Scegliere l'ambiente **Contoso** e fare clic su **+ New then Flow**
    e avviare la creazione di un nuovo flusso.

- ![](./media/image1.png)

3.  Immettere +++**Message Box Communication**+++ come nome del flusso e
    verificare che l'abilitazione Power Fx (anteprima) sia disattivata.
    Quindi fare clic su **Create**.

- ![](./media/image2.png)

4.  Per iniziare, viene richiesto all'utente di selezionare un file
    Excel. Aggiungere l'azione +++**Display select file dialog**+++ e
    configurare il campo Filtro file per consentire solo i file xlsx.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

5.  Inserire il **Dialog Title** come +++**Select Excel**+++, Inserire
    la posizione della cartella nella **cartella iniziale** come +++ C:
    Files+++ Filtra come **\*.xlsx** e quindi fare clic sul pulsante
    **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

6.  Prima di leggere i dati dal file selezionato, è necessario avviarlo
    utilizzando l'azione **Launch Excel**. Aggiungere **Launch Excel**
    dall'azione. Configurare quindi l'impostazione seguente.

    - Launch Excel: **add open the following document**

    - Document path: +++**%SelectedFile%**+++

    &nbsp;

    - Fare clic sul pulsante **Save**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image5.png)

7.  Per leggere i dati dal file Excel, aggiungere l'azione **Read from
    Excel worksheet**. Immettere **%ExcelInstance%** nell'istanza Excel
    e selezionare **All available values from worksheet** nel campo
    Recupera. Fare clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image6.png)

8.  Aggiungere l'azione **Get first free column/row from Excel
    worksheet** per recuperare la prima colonna e riga libera nel foglio
    di lavoro di Excel. Immettere **%ExcelInstance%** nell'istanza di
    Excel, quindi fare clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image7.png)

9.  Aggiungere un'azione Set Variable da denominata **Counter** e
    inizializzala su **1**, quindi fare clic su Save.

- ![](./media/image8.png)

10. Aggiungere **Display input dialog** dall'azione e configura i
    seguenti campi.

    - **Input Dialog Title**: +++**Header**+++

    - **Input Dialog Message**: +++**Enter the Header**+++

    - **Default Value**: +++**Discount**+++

    &nbsp;

    - Fare clic sul pulsante **Save**.

- ![](./media/image9.png)

11. Aggiungere **Write to Excel worksheet** dalle azioni e configuralo
    con i seguenti dettagli:

    - **Excel instance**: %ExcelInstance%

    - **Value to write**: +++**%UserInput%**+++

    - **Write role**: On specific cell

    - **Column**: +++**9**+++

    - **Row**: +++**%Counter%**+++

    &nbsp;

    - Fare clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image10.png)

12. Aggiungere un ciclo **For each** per l'azione per scorrere i dati
    recuperati e aggiungere il +++**%ExcelData%**+++ nella sezione
    valore per l'iterazione. Quindi fare clic su **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image11.png)

13. Per controllare il valore della colonna **Gross** (colonna G o la
    sesta colonna nel foglio di lavoro, nel foglio il nome della colonna
    è "6"), aggiungere l'azione **convert text to number**. Configura il
    testo da convertire come +++**%CurrentItem\[6\]%**+++ e quindi fare
    clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image12.png)

14. Aggiungere un'azione **If** per verificare se supera 100.000 e
    configurarla come indicato di seguito:

    - **First operand**: +++**%TextAsNumber%**+++

    - **Operator**: Greater than or equal to (\>=)

    - **Second Operand**: +++**100000**+++

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image13.png)

15. Aggiungere l'azione **Display message** in **If** per fornire le
    informazioni necessarie all'utente e richiedere di scegliere
    **Yes** o **No**. Quindi fare clic sul pulsante **Save**. Inserire i
    seguenti dettagli nell'it:

    - **Message Box title**: +++**Add discount**+++
    - **Message to display**:
      - +++**Product:** %CurrentItem\[2\]%+++
      - +++**Units**: %CurrentItem\[3\]%+++
      - +++**Gross:** %TextAsNumber%+++
    - **Message box button**: Yes – No

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image14.png)

16. Aggiungere una seconda azione **If** in Display message action per
    verificare quale pulsante è stato premuto nel passaggio precedente.
    Inserire i seguenti dettagli nei campi rispettati:

- **First** **operand**: +++%ButtonPressed3%+++

- **Operator:** Equal to (=)

- **Second operand:** +++Yes+++ 

&nbsp;

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image15.png)

17. In Seconda azione Se aggiungi **Display Input Dialog**. Aggiungere
    il parametro indicato di seguito nel campo e fare clic sul pulsante
    **Save**.

Input dialog title: +++Discount Value+++

Input dialog message: +++Enter the Discount Value+++

![](./media/image16.png)

18. Aggiungere l'azione **Write to excel worksheet** sotto la seconda
    azione **IF** e inserire i seguenti dettagli:

- **Excel instance:** +++%ExcelInstance%+++

- **Value to writer**: +++%UserInput2%+++

- **Write mode:** On specific cell

- **Column:** +++9+++

- **Row:** +++%Counter%+++

&nbsp;

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image17.png)

20. In Prima **IF End,** Aggiungere azione **Increase Variable,**
    aggiungere il nome della variabile come **%Counter%,** Aumentare di
    **1** e quindi fare clic sul pulsante **Save**.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image18.png)

21. Dalla barra in alto **Save** il flusso per il test.

- ![](./media/image19.png)

# Attività 2: Testare il flusso

1.  Fare clic sul pulsante **Run** per eseguire il test.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image20.png)

2.  Si aprirà la prima cartella del foglio, seleziona il **excel**
    **file** da essa.

> ![A screen shot of a computer AI-generated content may be
> incorrect.](./media/image21.png)

3.  Apparirà la finestra di intestazione, mentre impostiamo **Discount**
    come predefinito fare clic sul pulsante **OK**.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image22.png)

4.  Viene visualizzata la finestra **Add Discount**, che mostra che
    questo prodotto è superiore a **100000**, selezionare **yes** o
    **no**. In questo test selezioniamo **yes** (**yes**, diamo uno
    sconto su questo prodotto.)

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image23.png)

5.  Quindi inserire il **Discount Value**, Per il test inseriamo
    **10000** e quindi facciamo clic su **ok**.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image24.png)

6.  Nel foglio il valore dello sconto viene aggiornato.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image25.png)

7.  Il ciclo è in esecuzione **continua** per tutti i prodotti.

### Conclusione:

In questo laboratorio, i partecipanti hanno sviluppato un flusso di
Power Automate Desktop con operatore che legge i dati dell'ordine da un
file Excel, controlla se l'importo dell'ordine supera una soglia
impostata e richiede all'utente di applicare uno sconto. Il flusso
automatizza in modo efficiente il processo decisionale consentendo agli
utenti di interagire con il flusso tramite prompt e inserire valori di
sconto. Questo lab offre un'esperienza pratica nell'automazione delle
attività che coinvolgono Excel, input dell'utente e logica condizionale,
consentendo ai partecipanti di semplificare processi aziendali simili
utilizzando Power Automate Desktop.
