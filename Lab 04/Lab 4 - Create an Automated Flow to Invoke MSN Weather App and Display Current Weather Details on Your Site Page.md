# Laboratório 4 - Crie um Fluxo Automatizado para Acionar o Aplicativo MSN Weather e Exibir Detalhes do Clima Atual na Página do Seu Site

**Objetivo:** O objetivo deste laboratório é orientar os participantes
pelo processo de integração de um fluxo de nuvem no Power Automate a um
site do Power Pages. Os participantes aprenderão a criar um site no
Power Page usando modelos, configurar um fluxo de nuvem para buscar
dados meteorológicos atuais do serviço MSN Weather e criar uma página da
Web personalizada que exiba essas informações meteorológicas. Ao final
do laboratório, os participantes ganharão experiência prática com o
Power Pages e o Power Automate, permitindo que eles criem aplicativos
Web dinâmicos e interativos que respondem à entrada do usuário.

**Tempo estimado:** 25 minutos

### Tarefa 1: Acessar e criar o site do Power Page

1.  Vá para o Power Pages usando
    +++**https://make.powerpages.microsoft.com/**+++.

2.  Certifique-se se você está no ambiente do desenvolvedor – **Dev
    One** e clique em **Get Started**.

- ![](./media/image1.png)

3.  Selecione **Skip** na página **Tell us a little about yourself**.

- ![](./media/image2.png)

4.  Em **Create a site**, desça e selecione **Start with a template**.

- ![](./media/image3.png)

5.  Clique em **Starter layout 1**.

- ![](./media/image4.png)

6.  Na página **Starter Layout 1**, selecione **Choose this template**.

- ![](./media/image5.png)

7.  Insira o nome do site como +++**contoso**+++ no campo respectivo e
    clique no botão **Done** para criar o site.

- ![](./media/image6.png)

### Tarefa 2: Criar fluxo na nuvem

1.  Você pode ver que está navegando para o seu site. Se você vir um
    pop-up sobre **Introducing Copilot in Power Pages**, selecione
    **Next** até chegar à última etapa e selecione **Done**.

- ![](./media/image7.png)

  **Observação:** você pode fechar o pop-up **Enable site Copilot**.

![](./media/image8.png)

2.  Na barra de navegação esquerda, selecione Set up, e, em seguida,
    selecione **Cloud Flow.**

- ![](./media/image9.png)

3.  Selecione **+ Create new flow** na barra superior.

- ![](./media/image10.png)

4.  Selecione Power Pages na barra de pesquisa, role para baixo e
    selecione **When Power Pages call a flow trigger.**

- ![](./media/image11.png)

5.  Selecione **+ Add an input**.

- ![](./media/image12.png)

6.  Escolha **Text**.

- ![](./media/image13.png)

7.  Adicione um nome como **Location** e clique em + New step.

- ![](./media/image14.png)

8.  Pesquise +++**MSN Weather**+++.

9.  Selecione a ação **Get current weather**.

> ![](./media/image15.png)

10. Posicione o cursor no campo de texto **Location input**. Selecione o
    parâmetro **Location** em **When Power Pages calls a flow** dentro
    do conteúdo dinâmico.

> ![](./media/image16.png)

11. Selecione **+ New step**, pesquise por Power Pages, e selecione a
    ação **Return value(s) to Power Pages**.

> ![](./media/image17.png)

12. Selecione **+ Add an output**, escolha **Text** e digite
    +++**Pressure**+++ como título.

> ![](./media/image18.png)

13. Na seção Pressure value to respond, escolha o conteúdo dinâmico
    **Pressure**.

> ![](./media/image19.png)

14. Repita para criar as seguintes etapas de saída usando o tipo de
    texto:

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

15. Nomeie o fluxo +++**Get current weather**+++.

> ![](./media/image21.png)

16. Selecione **Save** e feche a seção de fluxo

> ![](./media/image22.png)

17. Selecione **+ Add roles** em Roles, escolha o papel **Anonymous
    Users**, e clique em **Add**.

> ![](./media/image23.png)

18. Clique no botão **Save**.

> ![](./media/image24.png)

19. **Copie** a **URL**.

> ![](./media/image25.png)

- **Observação:** essa é a URL exclusiva usada para se conectar ao fluxo
  de nuvem associado. Você usará essa URL posteriormente para chamar o
  fluxo meteorológico atual.

### Tarefa 3: Criar uma página para exibir dados meteorológicos do MSN

1.  Selecione Pages no workspace, depois selecione **+ Page.**

> ![](./media/image26.png)

2.  Se **Describe a page to create it** for exibida, selecione **Other
    ways to add a page**.

> ![](./media/image27.png)

3.  Nomeie a página **+++Todays_weather_report+++** e, em seguida,
    clique no botão **Add**.

![](./media/image28.png)

4.  Selecione **Edit code** para abrir o Visual Studio Code e, em
    seguida, clique em **Open Visual Studio Code.**

> ![](./media/image29.png)
>
> **Observação:** Se aparecer um pop-up dizendo 'The extension ‘Power
> Platform Tools’ wants to sign in using Microsoft’, selecione
> **Allow**.
>
> ![](./media/image30.png)

5.  **Cole** este código:

> <style>
>         div.weatherdetail {
>             border: 1px solid #F3F2F1;
>             border-radius: 12px;
>             box-shadow: 0px 1.2px 3.6px rgba(0, 0, 0, 0.1), 0px 6.4px 14.4px rgba(0, 0, 0, 0.13);
>             padding: 24px;
>         }
>         .weather label {
>             font-family: 'Nunito';
>             font-style: normal;
>             font-weight: 600;
>             font-size: 18px;
>             color: #323130;
>         }
>         .weather button {
>             font-family: 'Segoe UI';
>             padding: 8px 16px;
>             font-size: 16px;
>             background-color: #6219D9;
>             color: white;
>             border: none;
>             border-radius: 4px;
>             cursor: pointer;
>             outline: none;
>         } 
>         div.weather {
>             display: flex;
>             flex-direction: column;
>             align-items: flex-start;
>             padding: 100px;
>             gap: 36px;
>             width: 840px;
>         }
>         span.temperature {
>             font-family: Segoe UI;
>             font-size: 96px;
>             font-style: normal;
>             font-weight: 600;
>             color: #6219d9;
>         }
>         span.weatherinfov1 {
>             font-family: Segoe UI;
>             font-size: 28px;
>             font-style: normal;
>             font-weight: 400;
>             color: #201f1e;
>         }
>         span.weatherinfov2 {
>             font-family: Segoe UI;
>             font-size: 24px;
>             font-style: normal;
>             font-weight: 600;
>             color: #a19f9d;
>         }
>     </style>
>
>     <div class="row sectionBlockLayout text-left" style="display: flex; flex-wrap: wrap; margin: 0px; min-height: auto; padding: 8px;">
>         <div class="container" style="display: flex; flex-wrap: wrap;">
>             <div class="col-md-12 columnBlockLayout weather" style="flex-grow: 1; display: flex; flex-direction: column; min-width: 310px; word-break: break-word; padding: 0 180px; margin: 60px 0px;">
>                 <h1>What's the weather?</h1>
>                 <form id="cityForm">
>                     <label for="locationInput">Enter a location to find out</label>
>                     <br>
>                     <input type="text" style="width: 840px; border: 1px solid #D2D0CE;" id="locationInput" required />
>                     <p>
>                     <p>
>                         <button type="submit">Submit</button>
>                     </p>
>                 </form>
>                 <div id="weatherdetail" class="weatherdetail" style="display: none;width: 840px">
>                     <div>
>                         <div>
>                             <span class="temperature" id="temperature"> </span>
>                             <span class="weatherinfov1" id="temperature_units"></span>
>                         </div>
>                         <div>
>                             <span class="weatherinfov1" style="font-size: 36px;" id="location"> </span>
>                             <br>
>                             <span class="weatherinfov1" style="font-size: 24px;" id="cordinates"></span>
>                             <p>
>                         </div>
>                     </div>
>                     <div style="display: flex;">
>                         <div style="flex: 1;">
>                             <span class="weatherinfov2">Wind: </span>
>                             <span class="weatherinfov1" id="windspeed"></span>
>                             <span class="weatherinfov1" id="speed_units"> </span>
>                         </div>
>                         <div style="flex: 1;">
>                             <span class="weatherinfov2">Visibility: </span>
>                             <span class="weatherinfov1" id="visibility"></span>
>                             <span class="weatherinfov1" id="distance_units"></span>
>                         </div>
>                     </div>
>                     <div style="display: flex;">
>                         <div style="flex: 1;">
>                             <span class="weatherinfov2">UV Index: </span>
>                             <span class="weatherinfov1" id="uv"></span>
>                         </div>
>                         <div style="flex: 1;">
>                             <span class="weatherinfov2">Conditions: </span>
>                             <span class="weatherinfov1" id="condition"></span>
>                         </div>
>                     </div>
>                 </div>
>             </div>
>         </div>
>     </div>
>
>     <script>
>         document.getElementById("cityForm").addEventListener("submit", function (event) {
>             event.preventDefault(); // Prevent form submission
>             var weatherDiv = document.getElementById("weatherdetail");
>             weatherDiv.style.display = "none";
>
>             var location = document.getElementById("locationInput").value;
>
>             var _url = "<Cloud flow URL>";
>
>           var data = {};
>           data["Location"] = location;
>
>             var payload = {};
>             payload.eventData = JSON.stringify(data);
>             shell
>                 .ajaxSafePost({
>                     type: "POST",
>                     url: _url,
>                     data: payload
>                 })
>                 .done(function (response) {
>                     const result = JSON.parse(response);
>                     document.getElementById("temperature").innerHTML = result["temperature"];
>                     document.getElementById("windspeed").innerHTML = result["wind_speed"];
>                     document.getElementById("visibility").innerHTML = result["visibility_distance"];
>                     document.getElementById("uv").innerHTML = result["uv_index"];
>                     document.getElementById("location").innerHTML = result["location"];
>                     document.getElementById("condition").innerHTML = result["conditions"];
>                     document.getElementById("temperature_units").innerHTML = result["temperature_units"];
>                     document.getElementById("speed_units").innerHTML = result["speed_units"];
>                     document.getElementById("distance_units").innerHTML = result["distance_units"];
>                     document.getElementById("cordinates").innerHTML = parseFloat(result["latitude"]).toFixed(2) + ', ' + parseFloat(result["longitude"]).toFixed(2);
>                     weatherDiv.style.display = "block";
>                 })
>                 .fail(function () {
>                     alert("failed");
>                 });
>         });
>     </script>
>
> ![](./media/image31.png)

6.  **Substitua** a **URL** pela qual você copiou na etapa anterior.

> ![](./media/image32.png)

7.  **Salve** o código selecionando CTRL + S.

8.  Volte ao portal do Power Pages e selecione **Sync** no design
    studio.

> ![](./media/image33.png)

### Tarefa 4: Testar a integração de fluxo

Para testar a funcionalidade de integração de fluxo:

1.  Selecione **Preview** \> **Desktop** para abrir o site.

> ![](./media/image34.png)

2.  Insira um CEP ou cidade na caixa de texto **Location,** por exemplo,
    **Seattle**.

3.  Selecione o botão **Submit**.

> ![](./media/image35.png)

### Conclusão:

Neste laboratório, os participantes integraram com sucesso o Power
Automate a um site Power Pages, aprimorando suas habilidades na criação
de sites, desenvolvimento de fluxo de nuvem e personalização de páginas
da Web. Eles aprenderam a projetar uma interface amigável que recupera e
exibe dados meteorológicos dinâmicos usando o Power Automate. Ao testar
a integração do fluxo, os participantes também desenvolveram habilidades
de solução de problemas, capacitando-os a criar aplicativos interativos
no Power Platform de forma eficaz.
