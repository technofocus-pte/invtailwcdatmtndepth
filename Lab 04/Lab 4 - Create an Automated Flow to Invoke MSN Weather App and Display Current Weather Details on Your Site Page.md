# Laboratoire 4 - Création d'un Automated Flow pour appeler l'application MSN Météo et afficher les détails météorologiques actuels sur la page de votre site

**Objectif :** L'objectif de ce laboratoire est de guider les
participants tout au long du processus d'intégration de Power Automate
cloud flow à un site Power Pages. Les participants apprendront à créer
un site Web Power Page à l'aide de modèles, à configurer un flux de
cloud pour récupérer les données météorologiques actuelles du service
météo MSN et à créer une page Web personnalisée qui affiche ces
informations météorologiques. À la fin de l'atelier, les participants
acquerront une expérience pratique de Power Pages et de Power Automate,
ce qui leur permettra de créer des applications Web dynamiques et
interactives qui répondent aux entrées de l'utilisateur.

**Temps estimé :** 25 minutes

### Tâche 1 : Se connecter et créer un site Web Power Page

1.  Accédez à Power Pages à l'aide de
    +++**https://make.powerpages.microsoft.com/**+++.

2.  Assurez-vous que vous êtes dans l'environnement du développeur –
    **Dev One** , puis cliquez sur **Get started**.

- ![](./media/image1.png)

3.  Sélectionnez **Skip** à la **page Parlez-nous de vous**.

- ![](./media/image2.png)

4.  Sur **la page Créer un site**, faites défiler l'écran vers le bas et
    sélectionnez **Start with a template**.

- ![](./media/image3.png)

5.  Cliquez sur **la mise en page de démarrage 1**.

- ![](./media/image4.png)

6.  Sur la page **Mise en page Stater 1**, sélectionnez **Choisir ce
    modèle**.

- ![](./media/image5.png)

7.  Entrez le nom du site sous la forme ++**+contoso**+++ dans le champ
    respecté et cliquez sur le bouton **Done** pour créer le site web.

- ![](./media/image6.png)

### Tâche 2 : Créer cloud flow

1.  Vous pouvez voir, vous êtes dirigé vers votre site. Si vous voyez
    apparaître l' **introduction de Copilot dans Power Pages**,
    sélectionnez **Next** jusqu'à ce que vous arriviez à la dernière
    étape et pouvez sélectionner **Done**.

- ![](./media/image7.png)

  **Remarque :** Vous pouvez fermer la fenêtre contextuelle de l'
  **option Activer le copilote du site**.

![](./media/image8.png)

2.  Flux dans la barre de navigation de gauche, sélectionnez
    Configuration, puis sélectionnez **Cloud flow.**

- ![](./media/image9.png)

3.  Sélectionnez **+ Create** un flux dans la barre supérieure.

- ![](./media/image10.png)

4.  Recherchez Power Pages dans la barre de recherche, puis faites
    défiler vers le bas et sélectionnez **Lorsque Power Pages appelle un
    déclencheur de flux.**

- ![](./media/image11.png)

5.  Sélectionnez **+ Add an input**.

- ![](./media/image12.png)

6.  Choisissez **Texte**.

- ![](./media/image13.png)

7.  Ajoutez un nom en tant que **Localisation** et cliquez sur +
    Nouvelle étape.

- ![](./media/image14.png)

8.  Recherchez +++**MSN Weather**+++.

9.  Sélectionnez l' action **Obtenir la météo actuelle**.

- ![](./media/image15.png)

10. Curseur de focus sur **le** texte d'entrée **Location** Sélectionnez
    le paramètre **Location** sous **Lorsque Power Pages appelle un
    flux** à partir de contenu dynamique.

- ![](./media/image16.png)

11. Sélectionnez **+ New step**,, Recherchez Power Pages, Sélectionnez
    **Retour(s) valeur(s) à l'action Power Pages** .

- ![](./media/image17.png)

12. Sélectionnez **+ Add** et afficher, **Select Text**, Entrez
    +++**Pressure+**++ comme titre.

- ![](./media/image18.png)

13. Dans la section Valeur de pression pour répondre, choisissez Contenu
    dynamique **Pressure**.

- ![](./media/image19.png)

14. Répétez l'opération pour créer les étapes de sortie suivantes à
    l'aide du texte :

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

15. Nommez le flux +++ **Get current weather**+++

- ![](./media/image21.png)

16. Sélectionnez **Saver** et fermez la section de flux

- ![](./media/image22.png)

17. Sélectionnez **+ Add roles** sous Rôles, Sélectionnez **Rôle
    Utilisateurs anonymes**, Sélectionnez **Add**.

- ![](./media/image23.png)

18. Cliquez sur le bouton **Save**.

- ![](./media/image24.png)

19. **Copiez** l' **URL**.

- ![](./media/image25.png)

  **Remarque :** Il s'agit de l'URL unique utilisée pour se connecter au
  flux de cloud associé. Vous utiliserez cette URL ultérieurement pour
  appeler le flux météorologique actuel.

### Tâche 3 : Créer une page pour afficher les données météo MSN

1.  Sélectionnez Espace de travail Pages, sélectionnez **+ Page.**

- ![](./media/image26.png)

2.  Si **la fenêtre Décrire une page pour la créer s'** affiche,
    sélectionnez **Autres méthodes d'ajout d'une page**.

- ![](./media/image27.png)

3.  Nommez la page +++**Todays_weather_report**+++, puis cliquez sur le
    bouton **Add**.

![](./media/image28.png)

4.  Sélectionnez **Modifier le code** pour ouvrir Visual Studio Code,
    puis cliquez sur **Ouvrir le code Visual Studio.**

- ![](./media/image29.png)

  **Remarque :** Si une fenêtre contextuelle s'affiche indiquant
  ‘L'extension 'Power Platform Tools' souhaite se connecter à l'aide de
  Microsoft ‘, sélectionnez **Allow**.

  ![](./media/image30.png)

5.  **Collez** ce code :

-         <style>
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

6.  **Remplacez** l' **URL** par celle que vous avez copiée à l'étape
    précédente.

- ![](./media/image32.png)

7.  **Save** le code en sélectionnant CTRL + S.

8.  Revenez au portail Power Pages et sélectionnez **Synchroniser** dans
    Design Studio.

- ![](./media/image33.png)

### Tâche 4 : Tester l'intégration du flux

Pour tester la fonctionnalité d'intégration de flux :

1.  Sélectionnez **Preview** \> **Desktop** pour ouvrir le site.

- ![](./media/image34.png)

2.  Entrez un code postal ou une ville dans la zone de texte
    Emplacement, par exemple**, Seattle**.

3.  Sélectionnez le bouton **Submit**.

- ![](./media/image35.png)

### Conclusion:

Dans ce laboratoire, les participants ont réussi à intégrer Power
Automate à un site Power Pages, améliorant ainsi leurs compétences en
matière de création de sites Web, de développement de flux cloud et de
personnalisation de pages Web. Ils ont appris à concevoir une interface
conviviale qui récupère et affiche des données météorologiques
dynamiques à l'aide de Power Automate. En testant l'intégration du flux,
les participants ont également développé des compétences de dépannage,
ce qui leur a permis de créer efficacement des applications interactives
au sein de la Power Platform.
