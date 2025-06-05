Laboratorio 4 - Cree un Automated Flow para invocar MSN Weather App y
mostrar los detalles meteorológicos en su sitio

**Objetivo:** El objetivo de este laboratorio es guiar a los
participantes en el proceso de integrar un Power Automate cloud flow con
un sitio Power Pages. Los participantes aprenderán a crear un Power Page
website con templates, configurar un cloud flow para buscar datos
meteorológicos actuales desde el servicio MSN Weather y construir un
webpage personalizado que muestra estos datos del tiempo. A finales de
este laboratorio, los participantes obtendrán una experiencia práctica
con Power Pages y Power Automate, habilitándolesen crear aplicaciones
web dinámicos e interactivos que responden a user input.

**Duración estimada:** 25 minutos

Tarea 1: inicie sesión y cree Power Page Website

1.  Vaya a Power Pages en
    +++\*\*[*https://make.powerpages.microsoft.com/\*\*+++*](https://make.powerpages.microsoft.com/**+++).

2.  Asegúrese que está en Developer environment – **Dev One** y haga
    clic en **Get started**.

> ![](./media/image1.png)

3.  Seleccione **Skip** en la página **Tell us about yourself**.

> ![](./media/image2.png)

4.  En la página **Create a site**, baje y seleccione **Start with a
    template**.

> ![](./media/image3.png)

5.  Haga clic en **Starter layout 1**.

> ![](./media/image4.png)

6.  En la página **Stater layout 1**, seleccione **Choose this
    template**.

> ![](./media/image5.png)

7.  Introduzca el site name como +++**contoso**+++ en el campo relevante
    y haga clic en el botón **Done** para crear el website.

> ![](./media/image6.png)

Tarea 2: Cree cloud flow

1.  Puede ver que se le lleva a su site. Si ve un pop up
    de **Introducing Copilot in Power Pages**, seleccione **Next** hasta
    que llegue al último paso y seleccione **Done**.

> ![](./media/image7.png)
>
> **Ojo:** Puede cerrar el popup de **Enable site copilot**.

![](./media/image8.png)

2.  En la barra de navegación izquierda, seleccione Setup, y luego
    seleccione **Cloud flow.**

> ![](./media/image9.png)

3.  Seleccione **+ Create** new flow desde la barra superior.

> ![](./media/image10.png)

4.  Busque power pages en el search bar, baje y seleccione **When Power
    Pages call a flow trigger.**

> ![](./media/image11.png)

5.  Seleccione **+ Add an input**.

> ![](./media/image12.png)

6.  Elija **Text**.

> ![](./media/image13.png)

7.  Agregue un nombre como **Location** y haga clic en + New step.

> ![](./media/image14.png)

8.  Busque +++**MSN Weather**+++.

9.  Seleccione el **Get current weather** action.

> ![](./media/image15.png)

10. Enfoque el cursor en **Location** input text
    Seleccione **Location** parameter en **When Power Pages calls a
    flow** desde dynamic content.

> ![](./media/image16.png)

11. Seleccione **+ New step**, busque Power Pages, Seleccione
    el **Return value(s) to Power Pages** action.

> ![](./media/image17.png)

12. Seleccione **+ Add** an output, Seleccione **Text**, introduzca
    +++**Pressure**+++ como el title.

> ![](./media/image18.png)

13. En la sección Pressure value to respond, elija el dynamic
    content **Pressure**.

> ![](./media/image19.png)

14. Repita lo mismo para crear los siguientes pasos mediante text type:

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

> ![](./media/image20.png)

15. Nombre el flow +++**Get current weather**+++.

> ![](./media/image21.png)

16. Seleccione **Save**, y cierre el flow section

> ![](./media/image22.png)

17. Seleccione **+ Add roles** en Roles, Seleccione **Anonymous
    Users** role, Seleccione **Add**.

> ![](./media/image23.png)

18. Haga clic en el botón **Save**.

> ![](./media/image24.png)

19. **Copie** el **URL**.

> ![](./media/image25.png)
>
> **Ojo:** Este es el URL único que se usa para conectar al cloud flow
> asociado. Va a usar este URL más tarde para llamar al current weather
> flow.

Tarea 3: Cree una página para mostrar MSN weather data

1.  Seleccione Pages workspace, Seleccione **+ Page.**

> ![](./media/image26.png)

2.  Si aparece la ventana **Describe a page to create it**, seleccione
    **Other ways to add a page**.

> ![](./media/image27.png)

3.  Nombre la página como +++**Todays_weather_report**+++ y haga clic en
    el botón **Add**.

> ![](./media/image27.png)

4.  Seleccione **Edit code** para abrir Visual Studio Code y haga clic
    en **open visual studio code.**

> ![](./media/image28.png)
>
> **Ojo:** Si aparece un pop up diciendo ‘The extension ‘Power Platform
> Tools’ wants to sign in using Microsoft’ seleccione **Allow**.
>
> ![](./media/image29.png)

5.  **Pegue** este código:

> `<style>`  
> `    div.weatherdetail {`  
> `        border: 1px solid #F3F2F1;`  
> `        border-radius: 12px;`  
> `        box-shadow: 0px 1.2px 3.6px rgba(0, 0, 0, 0.1), 0px 6.4px 14.4px rgba(0, 0, 0, 0.13);`  
> `        padding: 24px;`  
> `    }`  
> `    .weather label {`  
> `        font-family: 'Nunito';`  
> `        font-style: normal;`  
> `        font-weight: 600;`  
> `        font-size: 18px;`  
> `        color: #323130;`  
> `    }`  
> `    .weather button {`  
> `        font-family: 'Segoe UI';`  
> `        padding: 8px 16px;`  
> `        font-size: 16px;`  
> `        background-color: #6219D9;`  
> `        color: white;`  
> `        border: none;`  
> `        border-radius: 4px;`  
> `        cursor: pointer;`  
> `        outline: none;`  
> `    } `  
> `    div.weather {`  
> `        display: flex;`  
> `        flex-direction: column;`  
> `        align-items: flex-start;`  
> `        padding: 100px;`  
> `        gap: 36px;`  
> `        width: 840px;`  
> `    }`  
> `    span.temperature {`  
> `        font-family: Segoe UI;`  
> `        font-size: 96px;`  
> `        font-style: normal;`  
> `        font-weight: 600;`  
> `        color: #6219d9;`  
> `    }`  
> `    span.weatherinfov1 {`  
> `        font-family: Segoe UI;`  
> `        font-size: 28px;`  
> `        font-style: normal;`  
> `        font-weight: 400;`  
> `        color: #201f1e;`  
> `    }`  
> `    span.weatherinfov2 {`  
> `        font-family: Segoe UI;`  
> `        font-size: 24px;`  
> `        font-style: normal;`  
> `        font-weight: 600;`  
> `        color: #a19f9d;`  
> `    }`  
> `</style>`  
>   
> `<div class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; margin: 0px; min-height: auto; padding: 8px;">`  
> `    <div class="container" style="display: flex; flex-wrap: wrap;">`  
> `        <div class="col-md-12 columnBlockLayout weather" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 310px; word-break: break-word; padding: 0 180px; margin: 60px 0px;">`  
> `            <h1>What's the weather?</h1>`  
> `            <form id="cityForm">`  
> `                <label for="locationInput">Enter a location to find out</label>`  
> `                <br>`  
> `                <input type="text" style="width: 840px; border: 1px solid #D2D0CE;" id="locationInput" required />`  
> `                <p>`  
> `                <p>`  
> `                    <button type="submit">Submit</button>`  
> `                </p>`  
> `            </form>`  
> `            <div id="weatherdetail" class="weatherdetail" style="display: none;width: 840px">`  
> `                <div>`  
> `                    <div>`  
> `                        <span class="temperature" id="temperature"> </span>`  
> `                        <span class="weatherinfov1" id="temperature_units"></span>`  
> `                    </div>`  
> `                    <div>`  
> `                        <span class="weatherinfov1" style="font-size: 36px;" id="location"> </span>`  
> `                        <br>`  
> `                        <span class="weatherinfov1" style="font-size: 24px;" id="cordinates"></span>`  
> `                        <p>`  
> `                    </div>`  
> `                </div>`  
> `                <div style="display: flex;">`  
> `                    <div style="flex: 1;">`  
> `                        <span class="weatherinfov2">Wind: </span>`  
> `                        <span class="weatherinfov1" id="windspeed"></span>`  
> `                        <span class="weatherinfov1" id="speed_units"> </span>`  
> `                    </div>`  
> `                    <div style="flex: 1;">`  
> `                        <span class="weatherinfov2">Visibility: </span>`  
> `                        <span class="weatherinfov1" id="visibility"></span>`  
> `                        <span class="weatherinfov1" id="distance_units"></span>`  
> `                    </div>`  
> `                </div>`  
> `                <div style="display: flex;">`  
> `                    <div style="flex: 1;">`  
> `                        <span class="weatherinfov2">UV Index: </span>`  
> `                        <span class="weatherinfov1" id="uv"></span>`  
> `                    </div>`  
> `                    <div style="flex: 1;">`  
> `                        <span class="weatherinfov2">Conditions: </span>`  
> `                        <span class="weatherinfov1" id="condition"></span>`  
> `                    </div>`  
> `                </div>`  
> `            </div>`  
> `        </div>`  
> `    </div>`  
> `</div>`  
>   
> `<script>`  
> `    document.getElementById("cityForm").addEventListener("submit", function (event) {`  
> `        event.preventDefault(); // Prevent form submission`  
> `        var weatherDiv = document.getElementById("weatherdetail");`  
> `        weatherDiv.style.display = "none";`  
>   
> `        var location = document.getElementById("locationInput").value;`  
>   
> `        var _url = "<Cloud flow URL>";`  
>   
> `      var data = {};`  
> `      data["Location"] = location;`  
>   
> `        var payload = {};`  
> `        payload.eventData = JSON.stringify(data);`  
> `        shell`  
> `            .ajaxSafePost({`  
> `                type: "POST",`  
> `                url: _url,`  
> `                data: payload`  
> `            })`  
> `            .done(function (response) {`  
> `                const result = JSON.parse(response);`  
> `                document.getElementById("temperature").innerHTML = result["temperature"];`  
> `                document.getElementById("windspeed").innerHTML = result["wind_speed"];`  
> `                document.getElementById("visibility").innerHTML = result["visibility_distance"];`  
> `                document.getElementById("uv").innerHTML = result["uv_index"];`  
> `                document.getElementById("location").innerHTML = result["location"];`  
> `                document.getElementById("condition").innerHTML = result["conditions"];`  
> `                document.getElementById("temperature_units").innerHTML = result["temperature_units"];`  
> `                document.getElementById("speed_units").innerHTML = result["speed_units"];`  
> `                document.getElementById("distance_units").innerHTML = result["distance_units"];`  
> `                document.getElementById("cordinates").innerHTML = parseFloat(result["latitude"]).toFixed(2) + ', ' + parseFloat(result["longitude"]).toFixed(2);`  
> `                weatherDiv.style.display = "block";`  
> `            })`  
> `            .fail(function () {`  
> `                alert("failed");`  
> `            });`  
> `    });`  
> `</script>`
>
> ![](./media/image30.png)

6.  **Reemplace** el **URL** con el que copió anteriormente.

> ![](./media/image31.png)

7.  **Guarde** el code al seleccionar CTRL + S.

8.  Vuelva al Power Pages portal y seleccione **Sync** en design studio.

> ![](./media/image32.png)

Tarea 4: Pruebe el flow integration

Para probar el flow integration functionality:

1.  Seleccione **Preview** \> **Desktop** para abrir el site.

> ![](./media/image33.png)

2.  Introduzca un código postal o ciudad en el cuadro de texto
    **Location** por ejemplo **Seattle**.

3.  Seleccione el botón **Submit**.

> ![](./media/image34.png)

Conclusión:

En este laboratorio, los participantes integran Power Automate con un
Power Pages site, mejorando sus habilidades en la creación del website,
cloud flow development, y la personalización del webpage. Han aprendido
a diseñar una interfaz fácil que recupera y muestra datos meteorológicos
dinámicos mediante Power Automate. Al probar el flow integration, los
participantes también dessarrollan habilidades de troubleshooting,
habilitándoles a crear aplicaciones interactivas dentro de Power
Platform.
