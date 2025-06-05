# 實驗 4 - 創建一個自動化流程來調用 MSN Weather 應用程序並在站點頁面上顯示當前天氣詳細信息

**目標：** 本實驗室的目標是指導參與者完成將 Power Automate 雲端流與
Power Pages 站點集成的過程。參與者將學習如何使用模板創建 Power Page
網站，設置雲端流以從
MSN天氣服務獲取當前天氣數據，並構建顯示此天氣信息的自定義網頁。在實驗結束時，參與者將獲得
Power Pages 和 Power Automate
的實踐經驗，使他們能夠創建響應用戶輸入的動態和交互式 Web 應用程序。

**預計時間：** 25 分鐘

### 任務 1：登錄並創建 Power Page 網站

1.  使用 **+++https://make.powerpages.microsoft.com/+++** 轉到 Power
    Pages。

2.  確保您位於開發人員環境 – **Dev One** 中，然後單擊 **Get started**。

- ![](./media/image1.png)

3.  選擇 **Skip** 在 **Tell us about yourself** 頁面。

- ![](./media/image2.png)

4.  在 **Create a site** 頁面上，向下滾動並選擇 **Start with a
    template** 。

- ![](./media/image3.png)

5.  單擊 **Starter layout 1**。

- ![](./media/image4.png)

6.  在 **Stater layout 1** 頁面上，選擇 **Choose this template**。

- ![](./media/image5.png)

7.  在尊重字段中輸入站點名稱 **+++contoso+++**，然後單擊 **Done**
    按鈕創建網站。

- ![](./media/image6.png)

### 任務 2：創建雲端流

1.  您可以看到，您已導航到您的網站。如果您看到有關**Introducing Copilot
    in Power
    Pages**，請選擇**Next**，直到您到達最後一步，然後選擇**Done**。

- ![](./media/image7.png)

> **注意：** 您可以關閉 **Enable site copilot** 彈出窗口。

![](./media/image8.png)

2.  流向左導航欄，選擇 設置，然後選擇 **Cloud flow。**

- ![](./media/image9.png)

3.  從頂部欄中選擇 **+ Create new**流。

- ![](./media/image10.png)

4.  在搜索欄中搜索 Power Pages，然後向下滾動並選擇 **When Power Pages
    call a flow trigger。**

- ![](./media/image11.png)

5.  選擇 **+ Add an input**。

- ![](./media/image12.png)

6.  選擇 **Text**。

- ![](./media/image13.png)

7.  添加名稱作為 **Location** ，然後單擊 + 新建步驟。

- ![](./media/image14.png)

8.  搜索 **+++MSN Weather+++**。

9.  選擇 **Get current weather**作。

- ![](./media/image15.png)

10. 將光標聚焦在 **Location**輸入文本 選擇 **Location** 參數 當 **When
    Power Pages calls a flow **。

- ![](./media/image16.png)

11. 選擇 **+ New step**，搜索 Power Pages，選擇將 **Return value(s) to
    Power Pages**作。

- ![](./media/image17.png)

12. 選擇 **+ Add**和輸出， **選擇文本**，輸入 **+++Pressure+++**
    作為標題。

- ![](./media/image18.png)

13. 在 Pressure value to respond 部分中，選擇動態內容 **Pressure**。

- ![](./media/image19.png)

14. 重複作以使用文本類型創建以下輸出步驟:

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

15. 將流命名為 **+++Get current weather+++**。

- ![](./media/image21.png)

16. 選擇 **Save** ，然後關閉 flow 部分

- ![](./media/image22.png)

17. 在 **“Roles”** 下選擇 “+ **Add roles** ”，選擇 **“ Anonymous
    Users”**，然後選擇 **“ Add**”。

- ![](./media/image23.png)

18. 點擊 **Save** 按鈕。

- ![](./media/image24.png)

19. **複製** **URL**。

- ![](./media/image25.png)

> **注意：** 這是用於連接到關聯 Cloud Flow 的唯一 URL。稍後將使用此 URL
> 調用當前天氣流。

### 任務 3：創建頁面以顯示 MSN 天氣數據

1.  選擇 Pages workspace，選擇 **+ Page。**

- ![](./media/image26.png)

2.  如果 **Describe a page to create it** 窗口，然後選擇 **Other ways to
    add a page。**

- ![](./media/image27.png)

3.  將頁面命名為 **+++Todays_weather_report+++**，然後單擊 **Add**
    按鈕。

![](./media/image28.png)

4.  選擇 **Edit code** 以打開 Visual Studio Code，然後單擊 **Open Visual
    Studio Code。**

- ![](./media/image29.png)

5.  **注意：** 如果彈出窗口顯示“擴展'Power Platform Tools'想要使用
    Microsoft 登錄”，請選擇 **“Allow**”。

- ![](./media/image30.png)

6.  **粘貼** 此代碼:

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

7.  將 **URL** **替換**為您在上一步中複製的 URL。

- ![](./media/image32.png)

8.  通過選擇 CTRL + S **保存**代碼。

9.  返回 Power Pages 門戶，然後選擇在 Design Studio 中**Sync**。

- ![](./media/image33.png)

### 任務 4：測試流集成

要測試 Flow 集成功能，請執行以下作：

1.  選擇 **Preview** \> **Desktop** 以打開站點。

- ![](./media/image34.png)

2.  在 **Location** 文本框中輸入郵政編碼或城市 ，例如 **Seattle**。

3.  選擇 **Submit** 按鈕。

- ![](./media/image35.png)

### 結論：

在此實驗室中，參與者成功地將 Power Automate 與 Power Pages
站點集成，增強了他們在網站創建、雲端流開發和網頁自定義方面的技能。他們學會了設計一個用戶友好的界面，該界面使用
Power Automate
檢索和顯示動態天氣數據。通過測試流集成，參與者還培養了故障排除技能，使他們能夠有效地在
Power Platform 中創建交互式應用程序。
