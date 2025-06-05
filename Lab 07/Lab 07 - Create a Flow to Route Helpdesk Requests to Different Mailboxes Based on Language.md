# Lab 07 - Creare un flusso per instradare le richieste dell'helpdesk a diverse caselle di posta in base alla lingua

**Obiettivo:** l'obiettivo di questo lab è guidare i partecipanti
attraverso il processo di creazione di un flusso Power Automate che
instrada le richieste del supporto tecnico a diverse cassette postali in
base al rilevamento della lingua. Il flusso si integra con le
funzionalità di GPT per riepilogare le e-mail in arrivo e automatizzare
il processo di instradamento in base a trigger specifici, contribuendo a
semplificare i flussi di lavoro di comunicazione all'interno
dell'organizzazione.

**Tempo stimato:** 15 minuti

### Attività 1: Creare un flusso per instradare le richieste del supporto tecnico a cassette postali diverse in base alla lingua

1.  Accedere all'account tenant amministratore di Office 365
    **+++https://make.powerautomate.com/using+++**.

2.  Selezionare **Templates** dal riquadro di navigazione a sinistra,
    inserisci +++**Summarize emails using GPT**+++ nella casella di
    ricerca in alto e selezionare il flusso quando viene visualizzato.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image1.png)

3.  Successivamente, il modello mostra quali connessioni verranno
    utilizzate in questo flusso. Se non hanno un segno di spunta verde
    accanto a loro, correggi la connessione selezionando " Sign in"
    accanto alla connessione, quindi selezionare **Continue**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image2.png)

4.  Selezionare il trigger, **when a new email arrives (V3).** Il
    pannello delle proprietà si aprirà da sinistra con una nota per
    aggiornare il parametro Subject Filter. Attualmente, **Subject
    Filter** è AI Builder.

5.  Aggiornare il Subject Filter su **Project Kick-off**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

6.  Selezionare l'opzione **Create text with a GPT using a prompt** per
    aprire il pannello delle proprietà a sinistra. Nel pannello delle
    proprietà, il campo Prompt mostra **AI Summarize**.

7.  Selezionare **Test prompt** per aprire le impostazioni del prompt.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

8.  Il modello ha un prompt predefinito che GPT utilizzerà, ma è
    possibile aggiornare e testare un nuovo prompt in questa finestra.
    Seguiere il passaggio successivo per aggiornare la richiesta.

9.  Per verificare un prompt, immettere i dati di esempio specificati
    nella sezione **Input**. Quindi selezionare **Test prompt** nella
    parte inferiore della sezione Prompt. Puoi vedere la risposta nella
    sezione Risposta rapida.

- +++Once upon a time in the quaint town of Eldoria, nestled between
  rolling hills and dense forests, lived a young girl named Elara. Her
  days were spent exploring the mystical woods that bordered the town,
  and whispers of ancient tales filled her imagination.+++

  ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image5.png)

10. Per questo esercizio, lasceremo tutto com'era quando abbiamo aperto
    le Impostazioni del prompt.

11. **Salvare** il flusso nell'angolo in alto a destra. Ora possiamo
    eseguire il flusso.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image6.png)

> Nota: Ignora se viene visualizzato l'avviso indicato: l'azione ‘Create
> text with GPT using a prompt’ non ha un'azione di approvazione dei
> contenuti dopo di essa.

### Attività 2: Testare il flusso

1.  Inviare un'e-mail dall'ID tenant di MOD Admin o il tuo ID e-mail
    all'ID tenant di MOD Admin con oggetto **Project Kick-off** e quanto
    segue nel corpo dell'email:

- Dear Team,

      I hope this email finds you well. We are excited to announce the
      kick-off of our new project, "Phoenix". The initial meeting is scheduled
      for Monday, June 1st, at 10 AM via Zoom. Please come prepared with any
      questions or suggestions. Your input is vital for the project's success.

      Kindly confirm your attendance by the end of the day tomorrow. Looking
      forward to a productive session and a successful project launch.

      Best regards,

      Miriam Graham

      Project Manager

      Contoso

2.  Riceverai un messaggio in Teams con un riepilogo dell'e-mail.
    Nell'angolo in basso a destra, puoi trovare un link per accedere al
    tuo flusso.

- ![A screenshot of a web page AI-generated content may be
  incorrect.](./media/image7.png)

3.  Questa unità utilizza un GPT per riepilogare le e-mail in arrivo. Le
    informazioni di rilevamento dell'intelligenza artificiale possono
    essere imprecise. Assicurati sempre di verificare le informazioni
    del GPT.

### Conclusione:

In questo laboratorio, i partecipanti hanno creato con successo un
flusso Power Automate per semplificare le richieste all'helpdesk
instradando i messaggi di posta elettronica in base al rilevamento della
lingua e utilizzando GPT per riepilogare il contenuto. Integrando
l'automazione nel flusso di lavoro delle e-mail, il laboratorio ha
dimostrato come gestire in modo efficiente la comunicazione tra più team
o reparti in base ai trigger linguistici. L'esercizio ha anche mostrato
come utilizzare GPT all'interno di Power Automate per migliorare la
produttività e ridurre lo smistamento manuale. Questa soluzione aiuta le
organizzazioni a migliorare l'efficienza del flusso di lavoro e a
ridurre i tempi di risposta per le richieste dell'helpdesk.
