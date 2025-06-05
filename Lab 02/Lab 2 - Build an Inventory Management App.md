**ラボ 2-在庫管理アプリを構築する**

**目的：**このラボの目的は、Microsoft Power Apps と Copilot
を使用して、機能的な在庫管理アプリケーションを作成する方法を参加者に指導することです。参加者は、データバース環境の設定、アプリ画面の設計、データ管理、そして
Power Automate
を使用した在庫補充ワークフローの自動化について学習します。

**所要時間：** 40分

**演習１：庫管理アプリを構築する**

**タスク １：データバース環境を検証する**

1.  ブラウザを開き、+++\*\* に移動します。office 365 admin
    accountでサインインします。

2.  左側のナビゲーションで**Environments**を選択します。下の画像のように、**Developer
    environment**が作成されているはずです。（この環境は、管理者アカウントを使用してMicrosoft
    Power App for　Developer
    ライセンスを提供するとすぐに自動的に作成されます。環境名は管理者アカウントごとに異なります。）

> ![](./media/image1.png)

3.  このラボのすべての演習を実行するには、同じ開発者環境を使用します。

**注意**：このラボでは**Dev
One**開発環境を使用します。環境名はユーザーごとに異なる場合があります。必ずご自身の開発環境を選択してください。

**タスク ２：Copilot を使用して在庫管理アプリを作成します。**

1.  ブラウザを開き、++++\*\* 、Office 365 admin tenant
    accountでサインインします。

2.  右上隅の環境をクリックし、**your developer**環境を選択します (Dev
    環境は、このラボ ガイドで使用される開発者環境です。)

> ![](./media/image2.png)

3.  以下のプロンプトを入力し、**the Enter**ボタンをクリックします。

> +++**build a candy inventory management app**+++
>
> ![](./media/image3.png)

4.  **Start with Copilot**タイルを選択します。

> ![](./media/image4.png)

5.  以下のプロンプトを入力し、**Generate**をクリックして、Copilot
    の助けを借りてテーブルを作成します。

> +++**Candy Inventory management**+++
>
> ![](./media/image5.png)

6.  、Copilotは下の画像に示すようにテーブルを生成します。

> ![](./media/image6.png)

7.  Candy の横にある 3 つのドットをクリックし、**View
    data**をクリックします。

> ![](./media/image7.png)

8.  Candy テーブルのデータは次の画像に示すとおりになります。

> ![](./media/image8.png)

9.  **Supplier --\> View
    data** をクリックしてデータを調べ、表示ウィンドウを閉じます。

> ![](./media/image9.png)

10. サプライヤーのメールIDの1つを仕事用/個人用のメールidに更新します。

> ![](./media/image10.png)

11. **Order --\> View data**をクリックします**。**

> ![](./media/image11.png)

12. 以下のプロンプトをテキストボックスに入力し、Enterをクリックしてください。この列は、数量が再注意文ポイントを下回った場合に通知するために必要です。

> +++**Add reorder point column to Candy table**+++
>
> ![](./media/image12.png)

13. 数値型でcandyInStock列を追加します。数量が再注意文ポイントより少ない場合、数量列にcandyInStockが自動的に追加されます。

> +++**Add candyInStock column to Candy table with sample stock
> count**+++
>
> ![](./media/image13.png)

14. 表は再発注意点の列とCandy in Stock columnで更新されました。

> ![](./media/image14.png)

15. **Save and open app**ボタンをクリックします。

> ![](./media/image15.png)

16. **「Done working?」**ウィンドウで、**Save and open
    app**をクリックし、アプリが作成されるのを待ちます。

> ![](./media/image16.png)
>
> ![](./media/image17.png)

17. welcomeウィンドウをスキップします。

> ![](./media/image18.png)

18. アプリが作成され、下の画像のようになります。

> ![](./media/image19.png)

19. **save**ボタンをクリックし、**MSCandy Inventory management
    app**という名前を入力して、**Save**ボタンをクリックします。

> ![](./media/image20.png)
>
> ![](./media/image21.png)

20. アプリを探索してみます。ツリービューから**the Candy
    screen**をクリックします。画面のラベルを**Candy Inventory
    management**に更新できます。

> ![](./media/image22.png)

21. サプライヤー画面を確認し、要件に応じて更新します。

> ![](./media/image23.png)

**タスク３：candy品質スクリーンを作成する**

1.  **New Screen**をクリックし、**Blank**のテンプレートを選択します。

> ![](./media/image24.png)

2.  新しい画面を選択し、右クリックして**Rename**を選択します。

> ![](./media/image25.png)

3.  画面に+++**Candy quality screen**+++という名前を付けます。

> ![](./media/image26.png)

4.  画面領域をクリックし、**Create a new table(preview)**を選択します。

> ![](./media/image27.png)

5.  **New table --\> Add columns and data**をクリックします。

> ![](./media/image28.png)

6.  **New column -\> Edit column**をクリックします。

> ![](./media/image29.png)

7.  表示名を**Candy
    ID** として入力し、**Update**ボタンをクリックします。

> ![](./media/image30.png)

8.  「新しい列」をクリックし、以下の詳細を入力して、**Save**をクリックします。

    - **Display Name:** Candy Name

    - **Data Type:** Choice

    - **Required:** Yes.

    - **Choices:** add below choices

      - Chocolate Bar

      - Gummy Bears

      - Jellybeans

      - Lollipop

      - Sour Patch Kids

> ![](./media/image31.png)

9.  新しい列をクリックし、以下の詳細を含む列を追加して、**Save**をクリックします。

    - **Display Name:** Candy Quality

    - **Data type:** Choice

    - **Required:** Yes

    - **Choice:** labels

      - Defective

      - Nondefective

> ![](./media/image32.png)

**注意:**アプリの要件に応じて列を追加できます。

10. テーブル名を編集し、+++**Candy Quality
    check**+++で更新します。![](./media/image33.png)

11. **Save and exit -\> Save and
    exit**をクリックします。![](./media/image34.png)

12. Power Apps app
    pageに戻ります。新しく追加された画面を選択し、挿入をクリックして、下の画像のように**Edit
    form**を選択します。![](./media/image35.png)

13. コンテナーをクリックし、データ ソース テーブルとして+++**Candy
    Qualities table**+++を選択します。![](./media/image36.png)

14. 下の画像のようなフォームが表示されます。![](./media/image37.png)

15. 表をページの中央に合わせます。**Insert-\> Text
    label**をクリックします。 ![](./media/image38.png)

16. テキスト ラベルを調整し、テキストを次のように入力し、+++**Candy
    Quality
    check**+++としてテキストのスタイルを更新します。![](./media/image39.png)

17. **Form**を選択します。**Insert**をクリックし、**Button**を選択します。![](./media/image40.png)

18. 送信ボタンをドラッグしてコンテナの中央に配置します。下の画像を参照にしてボタンを選択し、**properties**のテキストを**Submit**に変更します。![](./media/image41.png)

19. **Submit**ボタンを選択し、
    **OnSelect**関数を選択して、以下の関数を入力します。

**注意:**数式内の Form4 は、フォーム名SubmitForm ( Form4 ); NewForm
(Form4) に置き換える必要があります。

![](./media/image42.png)

20. コンテナーを選択し、プロパティで、**Default**モードを**New**を選択します。![](./media/image43.png)

21. **Save**をクリックし、下の画像に示すように**Preview
    app**ボタンをクリックします。![](./media/image44.png)

22. Candyの詳細を入力し、Submitボタンをクリックします。![](./media/image45.png)

23. Dataverse 環境の Candy
    品質テーブルに戻ると、上記に追加されたレコードが表示されます。![](./media/image46.png)

24. プレビューウィンドウを閉じます。

**演習 2: 在庫を補充するための Power Automate フローを作成する。**

**タスク１：再入荷メールをトリガーする Power Platform フローを作成する**

1.  Power Automate タブに戻り、**My flows** -\> **New flow -\Automated
    cloud flow**をクリックします。![](./media/image47.png)

2.  フロー名を+++**Candy Restock Flow**+++と入力します。+++**When a
    row**+++を検索し、Dataverse の**When a row is added or
    modified**アクションを選択して、**Create**をクリックします。![](./media/image48.png)

3.  アクションを選択し、以下のパラメータを設定します。

    - Change Type; Added or Modified

    - Table Nam: Candies

    - Scope: Organization ![](./media/image49.png)

4.  **when a row is added, modified or
    deleted**のアクションの後にアクションを追加します。![](./media/image50.png)

5.  **Condition**を検索し、**Control’s
    Condition**アクションを選択します。![](./media/image51.png)

6.  値の選択をクリックし、前のステップから選択動的アクションを選択します。![](./media/image52.png)

7.  +++**Quantity**+++列を検索して選択します。![](./media/image53.png)

8.  **is less
    than**条件を選択し、前のアクションからデータを入力をクリックします。![](./media/image54.png)

9.  +++**Reorder
    points**+++列を検索して選択します。![](./media/image55.png)

10. **True**条件で**Add an
    action**を追加します。![](./media/image56.png)

11. +++**Approvals**+++アクションを選択します。![](./media/image57.png)

12. +++**Start and wait for an
    Approvals**+++を選択します。 ![](./media/image58.png)

13. +++**Approve/Reject – First to
    Respond**+++として選択します。タイトルを+++**Approve to
    Restock**+++と入力し、ダイナミックボタンをクリックして前の手順のデータを選択します。![](./media/image59.png)

14. **Candy Name**+++を検索して選択します。![](./media/image60.png)

15. 以下の詳細を入力してください。

16. Assigned to: Your work email id.

17. 

18. Details:

19. 

20. Hi Sir,

21. 

22. is out of stock - for customers to place an order. Please approve to

23. restock.

24. 

25. Thanks

**注意:**必要に応じて詳細セクションをカスタマイズできます。

![](./media/image61.png)

16. **approval**アクションの後に**Add an
    action**をします。![](./media/image62.png)

17. +++**condition**+++を検索し、**Control –
    Condition**を選択します。![](./media/image63.png)

18. Choose
    valueをクリックし、Startから**Outcome**を選択して、承認アクションを待ちます。![](./media/image64.png)

19. 条件として**is equal
    to**を選択し、値として**Approve**を入力します。![](./media/image65.png)

20. **True**条件で**add an action**をします。![](./media/image66.png)

21. **Update Row**を検索し、**Microsoft
    Dataverse**セクションから選択します。![](./media/image67.png)

22. **Candy**テーブルを選択し、**Row
    Id**をクリックして動的アクションを選択します。![](./media/image68.png)

23. テーブルから一意の識別子列を検索して選択します。![](./media/image69.png)

24. **Advanced
    Parameters**ドロップダウンをクリックし、**Quantity**列を選択します。![](./media/image70.png)

25. 以下の関数（自分でアプリに入力する）を入力し、アクションを折りたたみます。

> **注意:　**列のスキーマ名が異なる場合、以下の関数は機能しません。table
> --\> columnに移動し、スキーマ名をコピーしてください。
>
> +++add(triggerBody()?\['cr8a3_Quantity'\],triggerBody()?\['cr8a3_CandyInStock'\])+++
>
> ![](./media/image71.png)

26. Power Automate フローを保存するには、**the
    Save**ボタンをクリックします。 ![](./media/image72.png)

**タスク２：補充フローをテストする**

1.  **PowerApps**タブに戻り、左側のツリー
    ビューから**Candy**画面をクリックして、**play**を選択します。

> **注意:**画面のタイトルを更新できます
>
> ![](./media/image73.png)

2.  Candyを選択し、**Edit**をクリックします。![](./media/image74.png)

3.  **Quantity**の値として**less than reorder
    points**を入力し、変更を**commit**にします。![](./media/image75.png)

4.  Power Automate フロー タブに戻り、My flows -\> Your flow
    をクリックします。![](./media/image76.png)

5.  フローは実行されており、条件を満たしています。![](./media/image77.png)

6.  新しいタブを開いて++++ 、office 365 admin
    accountでサインインしてください。在庫補充に関するメールが届いているはずです。**Approve**して**submit**してください。![](./media/image78.png)

> ![](./media/image79.png)

7.  フローは成功しました。![](./media/image80.png)

> ![](./media/image81.png)

8.  PowerAppsに戻り、上記の商品数量を確認してください。更新されているはずです（在庫数キャンディー+再発注意点を下回った場合の数量）。![](./media/image82.png)

**結論：**

このラボの終了までに、参加者はデータバース環境の検証、Copilotを活用した在庫管理アプリの構築、カスタムフィールドを使用したキャンディの品質チェック画面の設計、在庫レベルに基づいて補充リクエストをトリガーするPower
Automateフローの実装を行えるようになります。さらに、承認プロセス後の在庫更新の精度を確保するために、自動化されたワークフローのテストと検証のスキルも習得します。この体系的なアプローチにより、参加者はPower
AppsとPower
Automateの機能を効果的に活用し、アプリ開発とプロセス自動化のスキルを向上させることができます。
