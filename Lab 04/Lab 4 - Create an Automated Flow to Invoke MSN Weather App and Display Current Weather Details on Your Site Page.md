# 实验 4 - 创建一个自动化流程来调用 MSN Weather 应用程序并在站点页面上显示当前天气详细信息

**目标：** 本实验室的目标是指导参与者完成将 Power Automate 云端流与
Power Pages 站点集成的过程。参与者将学习如何使用模板创建 Power Page
网站，设置云端流以从
MSN天气服务获取当前天气数据，并构建显示此天气信息的自定义网页。在实验结束时，参与者将获得
Power Pages 和 Power Automate
的实践经验，使他们能够创建响应用户输入的动态和交互式 Web 应用程序。

**预计时间：** 25 分钟

### 任务 1：登录并创建 Power Page 网站

1.  使用 **+++https://make.powerpages.microsoft.com/+++** 转到 Power
    Pages。

2.  确保您位于开发人员环境 – **Dev One** 中，然后单击 **Get started**。

- ![](./media/image1.png)

3.  选择 **Skip** 在 **Tell us about yourself** 页面。

- ![](./media/image2.png)

4.  在 **Create a site** 页面上，向下滚动并选择 **Start with a
    template** 。

- ![](./media/image3.png)

5.  单击 **Starter layout 1**。

- ![](./media/image4.png)

6.  在 **Stater layout 1** 页面上，选择 **Choose this template**。

- ![](./media/image5.png)

7.  在尊重字段中输入站点名称 **+++contoso+++**，然后单击 **Done**
    按钮创建网站。

- ![](./media/image6.png)

### 任务 2：创建云端流

1.  您可以看到，您已导航到您的网站。如果您看到有关**Introducing Copilot
    in Power
    Pages**，请选择**Next**，直到您到达最后一步，然后选择**Done**。

- ![](./media/image7.png)

> **注意：** 您可以关闭 **Enable site copilot** 弹出窗口。

![](./media/image8.png)

2.  流向左导航栏，选择 设置，然后选择 **Cloud flow。**

- ![](./media/image9.png)

3.  从顶部栏中选择 **+ Create new**流。

- ![](./media/image10.png)

4.  在搜索栏中搜索 Power Pages，然后向下滚动并选择 **When Power Pages
    call a flow trigger。**

- ![](./media/image11.png)

5.  选择 **+ Add an input**。

- ![](./media/image12.png)

6.  选择 **Text**。

- ![](./media/image13.png)

7.  添加名称作为 **Location** ，然后单击 + 新建步骤。

- ![](./media/image14.png)

8.  搜索 **+++MSN Weather+++**。

9.  选择 **Get current weather**作。

- ![](./media/image15.png)

10. 将光标聚焦在 **Location**输入文本 选择 **Location** 参数 当 **When
    Power Pages calls a flow **。

- ![](./media/image16.png)

11. 选择 **+ New step**，搜索 Power Pages，选择将 **Return value(s) to
    Power Pages**作。

- ![](./media/image17.png)

12. 选择 **+ Add**和输出， **选择文本**，输入 **+++Pressure+++**
    作为标题。

- ![](./media/image18.png)

13. 在 Pressure value to respond 部分中，选择动态内容 **Pressure**。

- ![](./media/image19.png)

14. 重复作以使用文本类型创建以下输出步骤:

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

15. 将流命名为 **+++Get current weather+++**。

- ![](./media/image21.png)

16. 选择 **Save** ，然后关闭 flow 部分

- ![](./media/image22.png)

17. 在 **“Roles”** 下选择 “+ **Add roles** ”，选择 **“ Anonymous
    Users”**，然后选择 **“ Add**”。

- ![](./media/image23.png)

18. 点击 **Save** 按钮。

- ![](./media/image24.png)

19. **复制** **URL**。

- ![](./media/image25.png)

> **注意：** 这是用于连接到关联 Cloud Flow 的唯一 URL。稍后将使用此 URL
> 调用当前天气流。

### 任务 3：创建页面以显示 MSN 天气数据

1.  选择 Pages workspace，选择 **+ Page。**

- ![](./media/image26.png)

2.  如果 **Describe a page to create it** 窗口，然后选择 **Other ways to
    add a page。**

- ![](./media/image27.png)

3.  将页面命名为 **+++Todays_weather_report+++**，然后单击 **Add**
    按钮。

![](./media/image28.png)

4.  选择 **Edit code** 以打开 Visual Studio Code，然后单击 **Open Visual
    Studio Code。**

- ![](./media/image29.png)

5.  **注意：** 如果弹出窗口显示“扩展'Power Platform Tools'想要使用
    Microsoft 登录”，请选择 **“Allow**”。

- ![](./media/image30.png)

6.  **粘贴** 此代码:

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

7.  将 **URL** **替换**为您在上一步中复制的 URL。

- ![](./media/image32.png)

8.  通过选择 CTRL + S **保存**代码。

9.  返回 Power Pages 门户，然后选择在 Design Studio 中**Sync**。

- ![](./media/image33.png)

### 任务 4：测试流集成

要测试 Flow 集成功能，请执行以下作：

1.  选择 **Preview** \> **Desktop** 以打开站点。

- ![](./media/image34.png)

2.  在 **Location** 文本框中输入邮政编码或城市 ，例如 **Seattle**。

3.  选择 **Submit** 按钮。

- ![](./media/image35.png)

### 结论：

在此实验室中，参与者成功地将 Power Automate 与 Power Pages
站点集成，增强了他们在网站创建、云端流开发和网页自定义方面的技能。他们学会了设计一个用户友好的界面，该界面使用
Power Automate
检索和显示动态天气数据。通过测试流集成，参与者还培养了故障排除技能，使他们能够有效地在
Power Platform 中创建交互式应用程序。
