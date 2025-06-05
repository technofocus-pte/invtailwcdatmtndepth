# Lab 4 - Creare un Automated Flow per richiamare l'app MSN Weather e visualizzare i dettagli meteo correnti nella pagina del sito 

**Obiettivo:** l'obiettivo di questo lab è guidare i partecipanti
attraverso il processo di integrazione di un flusso cloud di Power
Automate con un sito Power Pages. I partecipanti impareranno come creare
un sito Web Power Page utilizzando i modelli, impostare un flusso cloud
per recuperare i dati meteorologici correnti dal servizio meteo MSN e
creare una pagina Web personalizzata che visualizza queste informazioni
meteo. Al termine del laboratorio, i partecipanti acquisiranno
esperienza pratica con Power Pages e Power Automate, consentendo loro di
creare applicazioni Web dinamiche e interattive che rispondono agli
input degli utenti.

**Tempo stimato:** 25 minuti

### Attività 1: Accedere e creare il sito Web Power Page

1.  Vai a Power Pages usando
    +++**https://make.powerpages.microsoft.com**/+++.

2.  Assicurati di essere nell'ambiente di sviluppo - **Dev One** e
    quindi fare clic su **Get started**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image1.png)

3.  Selezionare **Skip** nella pagina **Tell us about yourself**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image2.png)

4.  Nella pagina **Create a site**, scorrere verso il basso e
    selezionare **Start with a template**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image3.png)

5.  Fare clic su **Starter layout 1**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image4.png)

6.  Nella pagina **Stater layout 1**, selezionare **Choose this
    template**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image5.png)

7.  Immettere il nome del sito come +++**contoso**+++ nel campo
    rispettato e fare clic sul pulsante **Done** per creare il sito Web.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image6.png)

### Attività 2: Creare un flusso cloud

8.  Puoi vedere, sei navigato al tuo sito. Se viene visualizzato un
    pop-up relativo all **Introducing Copilot in Power Pages**,
    selezionare **Next** fino a quando non si arriva all'ultimo
    passaggio e selezionare **Done**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image7.png)

  **Nota:** È possibile chiudere il pop-up di **Enable site copilot**.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image8.png)

2.  Flusso: sulla barra di navigazione a sinistra, selezionare Setup,
    quindi selezionare **Cloud flow.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image9.png)

3.  Selezionare **+ Create** nuovo flusso dalla barra superiore.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image10.png)

4.  Cercare Power Pages nella barra di ricerca, quindi scorri verso il
    basso e selezionare **When Power Pages call a flow trigger.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image11.png)

5.  Selezionare **+ Add an input**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image12.png)

6.  Scegliere **Text**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image13.png)

7.  Aggiungere un nome come **Location** e fare clic su + **New step**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image14.png)

8.  Cercar +++**MSN Weather**+++.

9.  Selezionare l'azione **Get current weather**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image15.png)

10. Attivare il cursore sul testo di input **Location**, Selezionare il
    parametro **Location** in **When Power Pages calls a flow** dal
    contenuto dinamico.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image16.png)

11. Selezionare **+ New step**, Cercare **Power Pages**, Selezionare
    l'azione **Return value(s) to Power Pages**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image17.png)

12. Selezionare **+ Add** e output, **Select Text**, Inserire
    +++**Pressure**+++ come titolo.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image18.png)

13. Nella sezione Valore Pressure per rispondere, scegli Contenuto
    dinamico **Pressure**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image19.png)

14. Ripetere l'operazione per creare i passaggi di output seguenti
    utilizzando il tipo di testo:

    1.  +++Humidity+++

    2.  +++Temperature+++

    3.  +++UV index+++

    4.  +++Wind speed+++

    5.  +++Location+++

    6.  +++Visibility Distance+++

    7.  +++Latitude+++

    8.  +++Longitude+++

    9.  +++Temperature Units+++

    10. +++Pressure Units+++

    11. +++Speed Units+++

    12. +++Distance Units+++

    13. +++Conditions+++

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image20.png)

15. Assegna un nome al flusso +++**Get current weather**+++.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image21.png)

16. Selezionare **Save** e chiudere la sezione del flusso

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image22.png)

17. Selezionare **+ Add roles** in Roles, selezionare il ruolo
    **Anonymous Users**, selezionare **Add**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image23.png)

18. Fare clic sul pulsante **Save**.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image24.png)

19. **Copiare** l'**URL.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image25.png)

  **Nota:** questo è l'URL univoco utilizzato per connettersi al flusso
  cloud associato. Utilizzerai questo URL in un secondo momento per
  chiamare il flusso meteorologico corrente.

### Attività 3: Creare una pagina per visualizzare i dati meteo MSN

9.  Selezionare Area di lavoro Pages, Selezionare **+ Page.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image26.png)

10. Se viene visualizzata la finestra **Describe a page to create it**,
    selezionare **Other ways to add a page**.

- ![A screenshot of a computer screen AI-generated content may be
  incorrect.](./media/image27.png)

11. Assegnare alla pagina un nome +++**Todays_weather_report**+++ e
    quindi fare clic sul pulsante **Add**.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image28.png)

4.  Selezionare **Edit code** per aprire Visual Studio Code e quindi
    fare clic su **Open visual studio code.**

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image29.png)

  **Nota:** se viene visualizzato un pop-up che dice ‘The extension
  ‘Power Platform Tools’ wants to sign in using Microsoft’, quindi
  seleziona **Allow**.

  ![A black screen with white text AI-generated content may be
  incorrect.](./media/image30.png)

5.  **Incollare** questo codice:

-   <style>
          div.weatherdetail {
              border: 1px solid #F3F2F1;
              border-radius: 12px;
              box-shadow: 0px 1.2px 3.6px rgba(0, 0, 0, 0.1), 0px 6.4px 14.4px rgba(0, 0, 0, 0.13);
              padding: 24px;
          }
          .weather label {
              font-family: 'Nunito';
              font-style: normal;
              font-weight: 600;
              font-size: 18px;
              color: #323130;
          }
          .weather button {
              font-family: 'Segoe UI';
              padding: 8px 16px;
              font-size: 16px;
              background-color: #6219D9;
              color: white;
              border: none;
              border-radius: 4px;
              cursor: pointer;
              outline: none;
          } 
          div.weather {
              display: flex;
              flex-direction: column;
              align-items: flex-start;
              padding: 100px;
              gap: 36px;
              width: 840px;
          }
          span.temperature {
              font-family: Segoe UI;
              font-size: 96px;
              font-style: normal;
              font-weight: 600;
              color: #6219d9;
          }
          span.weatherinfov1 {
              font-family: Segoe UI;
              font-size: 28px;
              font-style: normal;
              font-weight: 400;
              color: #201f1e;
          }
          span.weatherinfov2 {
              font-family: Segoe UI;
              font-size: 24px;
              font-style: normal;
              font-weight: 600;
              color: #a19f9d;
          }
      </style>

      <div class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; margin: 0px; min-height: auto; padding: 8px;">
          <div class="container" style="display: flex; flex-wrap: wrap;">
              <div class="col-md-12 columnBlockLayout weather" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 310px; word-break: break-word; padding: 0 180px; margin: 60px 0px;">
                  <h1>What's the weather?</h1>
                  <form id="cityForm">
                      <label for="locationInput">Enter a location to find out</label>
                      <br>
                      <input type="text" style="width: 840px; border: 1px solid #D2D0CE;" id="locationInput" required />
                      <p>
                      <p>
                          <button type="submit">Submit</button>
                      </p>
                  </form>
                  <div id="weatherdetail" class="weatherdetail" style="display: none;width: 840px">
                      <div>
                          <div>
                              <span class="temperature" id="temperature"> </span>
                              <span class="weatherinfov1" id="temperature_units"></span>
                          </div>
                          <div>
                              <span class="weatherinfov1" style="font-size: 36px;" id="location"> </span>
                              <br>
                              <span class="weatherinfov1" style="font-size: 24px;" id="cordinates"></span>
                              <p>
                          </div>
                      </div>
                      <div style="display: flex;">
                          <div style="flex: 1;">
                              <span class="weatherinfov2">Wind: </span>
                              <span class="weatherinfov1" id="windspeed"></span>
                              <span class="weatherinfov1" id="speed_units"> </span>
                          </div>
                          <div style="flex: 1;">
                              <span class="weatherinfov2">Visibility: </span>
                              <span class="weatherinfov1" id="visibility"></span>
                              <span class="weatherinfov1" id="distance_units"></span>
                          </div>
                      </div>
                      <div style="display: flex;">
                          <div style="flex: 1;">
                              <span class="weatherinfov2">UV Index: </span>
                              <span class="weatherinfov1" id="uv"></span>
                          </div>
                          <div style="flex: 1;">
                              <span class="weatherinfov2">Conditions: </span>
                              <span class="weatherinfov1" id="condition"></span>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>

      <script>
          document.getElementById("cityForm").addEventListener("submit", function (event) {
              event.preventDefault(); // Prevent form submission
              var weatherDiv = document.getElementById("weatherdetail");
              weatherDiv.style.display = "none";

              var location = document.getElementById("locationInput").value;

              var _url = "<Cloud flow URL>";

            var data = {};
            data["Location"] = location;

              var payload = {};
              payload.eventData = JSON.stringify(data);
              shell
                  .ajaxSafePost({
                      type: "POST",
                      url: _url,
                      data: payload
                  })
                  .done(function (response) {
                      const result = JSON.parse(response);
                      document.getElementById("temperature").innerHTML = result["temperature"];
                      document.getElementById("windspeed").innerHTML = result["wind_speed"];
                      document.getElementById("visibility").innerHTML = result["visibility_distance"];
                      document.getElementById("uv").innerHTML = result["uv_index"];
                      document.getElementById("location").innerHTML = result["location"];
                      document.getElementById("condition").innerHTML = result["conditions"];
                      document.getElementById("temperature_units").innerHTML = result["temperature_units"];
                      document.getElementById("speed_units").innerHTML = result["speed_units"];
                      document.getElementById("distance_units").innerHTML = result["distance_units"];
                      document.getElementById("cordinates").innerHTML = parseFloat(result["latitude"]).toFixed(2) + ', ' + parseFloat(result["longitude"]).toFixed(2);
                      weatherDiv.style.display = "block";
                  })
                  .fail(function () {
                      alert("failed");
                  });
          });
      </script>

  ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image31.png)

6.  **Sostituire** l' **URL** con quello che hai copiato nel passaggio
    precedente.

- ![A screenshot of a computer program AI-generated content may be
  incorrect.](./media/image32.png)

7.  **Salvare** il codice selezionando CTRL + S.

8.  Tornare al portale di Power Pages e selezionare **Sync** in Design
    Studio.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image33.png)

### Attività 4: Testare l'integrazione del flusso

Per testare la funzionalità di integrazione del flusso:

12. Selezionare **Preview** \> **Desktop** per aprire il sito.

- ![A screenshot of a computer AI-generated content may be
  incorrect.](./media/image34.png)

13. Immettere un codice postale o una città nella casella di testo
    **Location**, ad esempio **Seattle**.

14. Selezionare il pulsante **Submit**.

- ![A screenshot of a weather report AI-generated content may be
  incorrect.](./media/image35.png)

### Conclusione:

In questo laboratorio, i partecipanti hanno integrato con successo Power
Automate con un sito Power Pages, migliorando le loro competenze nella
creazione di siti Web, nello sviluppo di flussi cloud e nella
personalizzazione di pagine Web. Hanno imparato a progettare
un'interfaccia intuitiva che recupera e visualizza dati meteorologici
dinamici utilizzando Power Automate. Testando l'integrazione del flusso,
i partecipanti hanno anche sviluppato competenze per la risoluzione dei
problemi, consentendo loro di creare applicazioni interattive
all'interno di Power Platform in modo efficace.
