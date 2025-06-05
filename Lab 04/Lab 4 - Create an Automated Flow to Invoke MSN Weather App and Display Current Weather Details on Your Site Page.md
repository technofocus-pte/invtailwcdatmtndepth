# Lab 4: Erstellen eines automatisierten Flows zum Aufrufen der MSN-Weather-App und Anzeigen aktueller Wetterdetails auf der Websiteseite

**Ziel:** Das Ziel dieses Labs besteht darin, die Teilnehmer durch den
Prozess der Integration eines Power Automate-Cloudflows mit einer Power
Pages-Website zu führen. Die Teilnehmer lernen, wie sie mithilfe von
Vorlagen eine Power Page-Website erstellen, einen Cloud-Flow einrichten,
um aktuelle Wetterdaten vom MSN-Wetterdienst abzurufen, und eine
benutzerdefinierte Webseite erstellen, auf der diese Wetterinformationen
angezeigt werden. Am Ende des Labs sammeln die Teilnehmer praktische
Erfahrungen mit Power Pages und Power Automate, die es ihnen
ermöglichen, dynamische und interaktive Webanwendungen zu erstellen, die
auf Benutzereingaben reagieren.

**Geschätzte Zeit:** 25 Minuten

### Aufgabe 1: Anmelden und Erstellen einer Power Page-Website

1.  Wechseln Sie mit +++**https://make.powerpages.microsoft.com/**+++ zu
    Power Pages.

2.  Stellen Sie sicher, dass Sie sich in der Entwicklerumgebung – **Dev
    One** befinden, und klicken Sie dann auf **Get started**.

- ![](./media/image1.png)

3.  Wählen Sie auf der Seite **Tell us about yourself** die Option
    **Skip** aus.

- ![](./media/image2.png)

4.  Scrollen Sie auf der Seite **Create a site** nach unten, und wählen
    Sie **Start with a template** aus.

- ![](./media/image3.png)

5.  Klicken Sie auf **Starter-Layout 1**.

- ![](./media/image4.png)

6.  Wählen Sie auf der Seite **Stater-Layout 1** die Option **Choose
    this template** aus.

- ![](./media/image5.png)

7.  Geben Sie den Websitenamen als +++**contoso**+++ in das
    entsprechende Feld ein, und klicken Sie auf die Schaltfläche
    **Done**, um die Website zu erstellen.

- ![](./media/image6.png)

### Aufgabe 2: Erstellen eines Cloud-Flows

1.  Sie können sehen, dass Sie zu Ihrer Website navigiert werden. Wenn
    Sie ein Popup-Fenster zur **Introducing Copilot in Power Pages**
    sehen, wählen Sie **Next** aus, bis Sie zum letzten Schritt kommen
    und **Done** auswählen können.

- ![](./media/image7.png)

  **Hinweis:** Sie können das Popup-Fenster von **Enable site copilot**
  schließen.

![](./media/image8.png)

2.  Fließen Sie in der linken Navigationsleiste, wählen Sie Setup und
    dann **Cloud-Flow** aus.

- ![](./media/image9.png)

3.  Wählen Sie in der oberen Leiste + **Create** **new flow** aus.

- ![](./media/image10.png)

4.  Suchen Sie Power Pages in der Suchleiste, scrollen Sie dann nach
    unten, und wählen Sie **When Power Pages call a flow trigger** aus.

- ![](./media/image11.png)

5.  Wählen Sie **+ Add an input** aus.

- ![](./media/image12.png)

6.  Wählen Sie **Text**.

- ![](./media/image13.png)

7.  Fügen Sie einen Namen als **Location** hinzu und klicken Sie auf +
    **New step**.

- ![](./media/image14.png)

8.  Suchen Sie nach +++**MSN Weather**+++.

9.  Wählen Sie die Aktion **Get current weather** aus.

- ![](./media/image15.png)

10. Platzieren Sie den Cursor im Texteingabefeld “**Location**” und
    wählen Sie den Parameter “**Location**” unter “**When Power Pages
    calls a flow**” im dynamischen Inhalt aus.

- ![](./media/image16.png)

11. Wählen Sie **+ New step** aus, suchen Sie nach Power Pages, wählen
    Sie **Return value(s) to Power Pages**-Aktion aus.

- ![](./media/image17.png)

12. Wählen Sie **+ Add** und Output, **wählen Sie Text**, geben Sie +++
    **Pressure** +++ als Titel ein.

- ![](./media/image18.png)

13. Wählen Sie im Abschnitt “Pressure value to respond” die Option
    dynamic content **Pressure** aus.

- ![](./media/image19.png)

14. Wiederholen Sie diesen Vorgang, um die folgenden Ausgabeschritte mit
    dem Texttyp zu erstellen:

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

- ![](./media/image20.png)

15. Nennen Sie den Flow +++ **Get current weather** +++.

- ![](./media/image21.png)

16. Wählen Sie **Save** aus, und schließen Sie den Flow-Abschnitt

- ![](./media/image22.png)

17. Wählen Sie unter Roles die Option **+ Add roles** aus, wählen Sie
    die Rolle **Anonymous Users** aus, wählen Sie **Add** aus.

- ![](./media/image23.png)

18. Klicken Sie auf die Schaltfläche **Save**.

- ![](./media/image24.png)

19. **Kopieren Sie** die **URL.**

- ![](./media/image25.png)

  **Hinweis:** Dies ist die eindeutige URL, die für die Verbindung mit
  dem zugehörigen Cloud-Flow verwendet wird. Sie verwenden diese URL
  später, um den aktuellen Wetterflow aufzurufen.

### Aufgabe 3: Erstellen einer Seite zum Anzeigen von MSN-Wetterdaten

1.  Wählen Sie Arbeitsbereich "Pages" aus, und wählen Sie **"+ Page"**
    aus.

- ![](./media/image26.png)

2.  Wenn das Fenster **" Describe a page to create it** " angezeigt
    wird, wählen Sie "**Other ways to add a page**" aus.

- ![](./media/image27.png)

3.  Benennen Sie die Seite +++**Todays_weather_report**+++ und klicken
    Sie dann auf die Schaltfläche **Add**.

![](./media/image28.png)

4.  Wählen Sie **Edit code** aus, um Visual Studio Code zu öffnen, und
    klicken Sie dann auf **Open Visual Studio Code.**

- ![](./media/image29.png)

  **Hinweis:** Wenn ein Popup-Fenster mit der Meldung " The extension
  ‘Power Platform Tools’ wants to sign in using Microsoft " angezeigt
  wird, wählen Sie **Allow** aus.

  ![](./media/image30.png)

5.  **Fügen Sie** diesen Code ein:

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

  ![](./media/image31.png)

6.  **Ersetzen Sie** die **URL** durch die URL, die Sie im vorherigen
    Schritt kopiert haben.

- ![](./media/image32.png)

7.  **Speichern Sie** den Code, indem Sie CTRL+S auswählen.

8.  Kehren Sie zum Power Pages-Portal zurück, und wählen Sie in Design
    Studio “**Sync**” aus.

- ![](./media/image33.png)

### Aufgabe 4: Testen der Flow-Integration

So testen Sie die Flow-Integrationsfunktionalität:

1.  Wählen Sie **Preview** \> **Desktop** aus, um die Website zu öffnen.

- ![](./media/image34.png)

2.  Geben Sie eine Postleitzahl oder einen Ort in das Textfeld
    **Location** ein, z. B**. Seattle**.

3.  Wählen Sie die Schaltfläche **Submit** aus.

- ![](./media/image35.png)

### Schlussfolgerung:

In diesem Lab haben die Teilnehmer Power Automate erfolgreich in eine
Power Pages-Website integriert und so ihre Fähigkeiten in den Bereichen
Website-Erstellung, Cloud-Flow-Entwicklung und Webseitenanpassung
verbessert. Sie lernten, eine benutzerfreundliche Oberfläche zu
entwerfen, die mithilfe von Power Automate dynamische Wetterdaten abruft
und anzeigt. Durch das Testen der Flow-Integration entwickelten die
Teilnehmer auch Fähigkeiten zur Fehlerbehebung, die sie in die Lage
versetzten, interaktive Anwendungen innerhalb der Power Platform
effektiv zu erstellen.
