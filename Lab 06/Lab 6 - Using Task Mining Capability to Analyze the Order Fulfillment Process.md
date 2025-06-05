**ラボ６：タスクマイニング機能を使用して注文処理プロセスを分析する**

**目的：**このラボでは、Power
Automateのタスクマイニング機能を活用して、注文処理プロセスを分析・最適化することに焦点を当てます。参加者は、サンプル録画を含むソリューションをインポートする方法、タスクマイニング機能の活用方法、そしてボトルネックを特定するためのプロセス分析の実行方法を学習します。さらに、プロセスステップの自動化と、分析を用いたプロセス効率に関する洞察の獲得についても解説します。

**所要時間：** 30分

**タスク１：タスクマイニングを準備する**

1.  Office 365 tenant
    credentialsで+++\*\*[*https://make.powerautomate.com/\*\*+++*](https://make.powerautomate.com/**+++)を使用してPower
    Automate にサインインします。

2.  環境を選択しますー**Dev One。**

> ![](./media/image1.png)

**タスク２：ソリューションをインポートする**

1.  左側のナビゲーション ウィンドウで**Solutions**を選択し、上部のツール
    バーで**Import solution**を選択します。

> ![](./media/image2.png)

2.  **Browse**を選択します。

> ![](./media/image3.png)

3.  **Processmining.zip**ファイルを選択して開きます。

> ![](./media/image4.png)

4.  **Next**を選択します。

> ![](./media/image5.png)

5.  **Import**を選択し、ソリューションがインポートされるまで待ちます。

> ![](./media/image6.png)

**タスク３：サンプル録音を表示する**

1.  .zip fileを正常にインポートしたら、左側のナビゲーション
    ペインで**Process mining**を選択し、**Invoice submission
    process**プロセスを選択します。

> ![](./media/image7.png)

2.  アナリティクスタブに移動した場合は、1つ前のステップに戻ってください。ページ上部のbreadcrumbsリストから**Invoice
    submission process**を選択して、元の画面に戻ります。

> ![](./media/image8.png)

3.  既存の録音の一部は、**Recordings**で確認できます。

> ![](./media/image9.png)

4.  既存の録画のリスト全体を表示するには、**See all**を選択します。

**タスク４：機能を探索する**

次の機能が表示されます：

- **New recording**: Create a new recording.

- **Analytics**: See the process map and insights

- **Analyze**: Analyze a process.

- **Create activity names**: Create activity names for your process.

- **Delete process**: Delete your process

> ![](./media/image10.png)

**タスク５：プロセスを分析する**

プロセスを分析すると、プロセス
マイニング機能によって既存の記録が分析され、ビジネス
プロセス内のボトルネックが特定されます。

1.  **Analyze**を選択します。

> **注意：**分析には数分かかる場合があります。分析中は、**New
> recording**ボタンの下にステータスメッセージが表示されます。
>
> ![](./media/image11.png)

2.  分析段階でエラーが発生した場合は、**Analyze**を選択してこのアクションを再度トリガーします。

3.  完了すると、**Process analysis
    status**が**Analyzed**に変わります。**Analytics**を選択すると、プロセスマップと分析情報が表示されます。

> ![](./media/image12.png)
>
> **注意：**分析の実行後、この手順が完了するまでに数分かかる場合があります。

**タスク６：アナリティクスページのレイアウト**

**Analytics**で実行できる操作について説明します。

![](./media/image13.png)

![](./media/image14.png)

**凡例：**

1.  **Automate activities：自動化プロセスを効率化するために、Automate
    activities**機能を使用できます。この機能は、Microsoft
    OutlookやExcelなど、Power
    Automateアクションが利用可能なアプリケーションを使用してユーザーがアクションを実行したかどうかを検出します。**Automate
    activities**を選択すると、関連するアクションを含むPower Automate
    processの下書きが生成されます。ユーザーは下書きプロセスを修正およびカスタマイズして、最終的な自動化プロセスを作成できます。

2.  **Legend**：レポートに関する追加情報。提示された視覚化とデータをよりよく理解するのに役立ちます。

3.  **Process**：プロセス
    マップ、各バリアントおよび各記録作成者の時間分析など、分析されたプロセスに関する詳細情報。

4.  **Application**：録画に使用されたアプリに関する情報。これには、作成者が使用したアプリ、使用頻度、アプリ間の遷移が含まれます。このレポートでは、プロセスの自動化を実装する際にどのコネクタを使用すべきか、また既存のコネクタがない場合にデスクトップフローを使用できる可能性のある箇所について説明します。

**タスク7：ビジネスプロセスステップの関係**

ビジネスプロセスにおける様々なステップと、それに関連する所要時間が表示されます。これらのステップには以下が含まれます。

- Download invoice attachment from email (48 seconds)

- Open Excel invoice list (11.5 seconds)

- Open invoice from OneDrive (21 seconds)

- Enter invoice details (53.6 seconds)

- Save and submit (9 seconds)

- Notify team of submission (26.67 seconds)

> ![](./media/image15.png)

**タスク８：分析データを表示する**

1.  上位の分析データをご覧ください。5件の記録のうち、平均処理時間は1.47分です。

> ![](./media/image16.png)

2.  その他の時間ベースのメトリック ダッシュボードを分析します。

> **average time in sec**:**によるアクティビティ**: **Enter invoice
> details**と**Download
> invoice** に最も時間がかかっていることに注意してください。
>
> ![](./media/image17.png)
>
> **Recording by average time in min**：一部の人 (**Preston
> Morales** and **Shakti Menon**)
> が他の人たちよりも時間がかかっていることに注目してください。
>
> ![](./media/image18.png)

3.  使用されたアプリケーションの詳細を表示するには、**Application**タブを選択します。

> レポートの読み込みにはしばらく時間がかかる場合があります。

- このレポートは、ビジネス
  プロセスで使用されるアプリケーション、その使用頻度、各アプリケーションに費やされた時間に関する情報を提供することで、プロセスに関する洞察を得るために重要です。

- たとえば、ダッシュボードには、従来の請求アプリ、Outlook、Excel
  が、アプリケーションによる時間とアクションに大きく貢献していることが示されます。

- 時間をかけてさまざまなレポートに慣れてください。

> ![](./media/image19.png)

4.  **Process**を選択してプロセス マップに戻ります。

5.  自動化されたアクティビティ機能をご覧ください。プロセスマップから、プロセスマイニング機能によって、アプリケーションに基づいて自動化の候補となるアクティビティがいくつかハイライト表示されていることがわかります。

6.  上部の**Automate
    activities**を選択して、自動化のフローの作成を開始します。

> ![](./media/image20.png)
>
> ブラウザにタブが開き、フローデザイナーが表示されます。プロセスマップのアクティビティに一致する推奨アクションが右側のパネルに自動的に表示されます。例えば、**Download
> invoice attachment from
> email** アクティビティを自動化するために、いくつかのメールコネクタが提案されます。
>
> ![](./media/image21.png)

**結論：**

このラボでは、参加者はPower
Automateタスクマイニング機能を活用して、受注処理プロセスを分析・最適化しました。サンプル録画を含む構築済みソリューションをインポートすることで、プロセス分析、ボトルネックの特定、自動化に関する推奨事項の生成といったタスクマイニングの主要な機能を学習しました。参加者は、様々なタスクやアプリケーションに費やされた時間の詳細な分析を通じて、プロセス効率を評価する方法を学びました。ラボでは、タスクマイニングが自動化の機会を特定することでビジネスプロセスを合理化し、最終的には業務効率を向上させ、受注処理プロセスにおける手作業の負荷を軽減する方法を具体的に説明しました。
