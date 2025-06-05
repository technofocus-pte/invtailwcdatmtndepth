# **Laboratório 5 - Criação e análise do processo de reembolso de contas a pagar**

**Objetivo:** O objetivo deste laboratório é criar e analisar um
processo de reembolso de contas a pagar usando os recursos do Power
Automate Process Mining. Os participantes aprenderão a importar dados de
um arquivo CSV, criar um novo processo e utilizar o aplicativo de
desktop Process Mining para analisar os key performance indicators
(KPIs) e outras métricas para obter insights sobre a eficiência e o
desempenho do processo de reembolso de contas a pagar.

**Tempo estimado:** 30 minutos

### Tarefa 1: Criar um processo

1.  Navegue até **+++https://make.powerautomate.com/+++.** Se
    solicitado, faça login com suas credenciais de locatário do
    Office 365. Selecione **United States** como country/region e, em
    seguida, selecione **Get started**.

- ![](./media/image1.png)

2.  Selecione seu environment – **Dev One**.

- ![](./media/image2.png)

3.  No painel de navegação à esquerda, selecione **More** **Process
    mining**.

- ![](./media/image3.png)

4.  Na seção **Create new process**, selecione **Start here**.

- ![](./media/image4.png)

5.  Na tela **Create a new process**, insira um nome para o processo –
    **Processmining**, depois selecione **Import data**, selecione
    **Data flow** e em seguida clique em **Continue**. (Opcional) Insira
    uma descrição para o seu processo.

- ![](./media/image5.png)

6.  Caso seja necessário **choose where to export**, escolha **PowerBi
    embedded** na lista **Choose your destination** e prossiga clicando
    em **Continue**

- ![](./media/image6.png)

### Tarefa 2: Importar dados

1.  Na tela **Choose a data source**, selecione **Text/CSV**.

- ![](./media/image7.png)

2.  Em **Connection settings**, selecione **Upload file (Preview)**.

- ![](./media/image8.png)

3.  Selecione **Browse**.

- ![](./media/image9.png)

4.  Localize e selecione
    **SampleData_AP_Refunds_Financial_EventLog.csv**. Local: **C:Files**

5.  Selecione **Open**.

- ![](./media/image10.png)

6.  Se for solicitado que você se autentique, selecione **Sign in** e
    siga as instruções. (Configure o bloqueador de pop-ups para
    permitir)

- ![](./media/image11.png)

7.  Select **Next**.

- ![](./media/image12.png)

8.  Visualize os dados do arquivo e selecione **Next**.

- ![](./media/image13.png)

9.  Quando visualizar o power query, que permite transformar seus dados,
    selecione **Next**.

- ![](./media/image14.png)

10. Corresponda o **Attribute Name** dos dados de exemplo ao **Attribute
    Type** de forma apropriada.

- ![](./media/image15.png)

11. Neste exemplo, os atributos de dados que você irá alterar são
    **InvoiceValue**, **Resource**, **StartTimestamp**, **EndTimestamp**, **CaseId**,
    e **ActivityName** conforme indicado abaixo.

- **InvoiceValue** – Financial per case (first event)

  **Resource** – Resourse

  **StartTimestamp** – Event Start

  **EndTimestamp** – Event End

  **CaseId** – Case ID

  **ActivityName** - Activity

  ![](./media/image16.png)

12. Quando **terminar**, o mapeamento de atributos deverá ficar
    semelhante à captura de tela a seguir.

- ![](./media/image17.png)

13. Selecione **Save and analyze**. A análise pode levar alguns minutos
    para ser concluída.

- ![](./media/image18.png)

14. Quando o **processo de análise estiver concluído**, você verá um
    mapa do processo e um painel com outras informações sobre o seu
    processo. No painel, você pode visualizar várias métricas que o
    ajudarão a **analisar o seu processo**.

- ![](./media/image19.png)

### 

### Tarefa 3: Analisar um processo

Vamos levar a análise do nosso processo além dos KPIs. Usaremos o
aplicativo desktop Power Automate Process Mining, onde você pode editar
e analisar seus processos criados na funcionalidade de process mining.

1.  Na barra superior, clique em **Download process Mining app**.

- ![](./media/image20.png)

2.  Dê um duplo clique no arquivo instalador do
    **PowerAutomateProcessMining App** na pasta Downloads.

- ![](./media/image21.png)

3.  Clique em **Install**.

- ![](./media/image22.png)

4.  Após instalar o Processmining app, o app será iniciado
    automaticamente; se não, por favor, inicie o app manualmente. Depois
    de abrir o app, selecione **English** como idioma e clique em **Next
    Step**.

- ![](./media/image23.png)

5.  Selecione todas as **caixas de seleção** conforme mostrado na imagem
    e clique em **Next**.

- ![](./media/image24.png)

6.  Então, clique no botão **Apply and mine**.

- ![](./media/image25.png)

7.  Depois, selecione o botão **Use**, que irá direcionar para a janela
    de login.

- ![](./media/image26.png)

8.  Digite seu ID de locatário administrador e clique no botão **Sign
    In.**

- ![](./media/image27.png)

9.  Digite seu ID de locatário administrador e clique no botão **Sign
    In**.

- ![](./media/image28.png)

10. Se aparecer um pop-up dizendo “Stay signed in to all your apps”,
    selecione **No, sign in to this app only**.

- ![](./media/image29.png)

11. Na barra de ferramentas do Power Automate Process Mining app,
    selecione o ambiente – **Dev One** no canto superior direito.

- ![](./media/image30.png)

12. Pesquise pelo processo que você criou com a funcionalidade de
    process mining no Power Automate (**Processmining**).

13. Selecione **Default** para exibir a visualização padrão. Você está
    pronto para usar os recursos avançados do Process Mining desktop
    app.

- ![](./media/image31.png)

  > Obserrvação: Se aparecer uma mensagem relacionada a **Model size is
  > too large for your PC configuration** e oferecer as opções Yes e No
  > para execução, selecione **Yes**.

  ![](./media/image32.png)

14. Na barra de ferramentas do painel **Customize**, selecione
    **Frequency** (o primeiro ícone), e então selecione **Case count**
    no menu suspenso **Metric**.

- ![](./media/image33.png)

> O process map exibe o número de casos do processo que incluem a
> atividade especificada em cada nó.

15. No painel **Customize**, selecione **Performance** (ícone de
    relógio) e, em seguida, selecione **Mean duration** no menu
    suspenso.

- ![](./media/image34.png)

  > Perceba que a etapa **Refund with special voucher** tem uma mean
  > duration longa em comparação com as outras etapas.

  ![](./media/image35.png)

16. No painel **Customize**, selecione **Finance** (ícone da folha de
    papel) e depois selecione **Mean** no menu suspenso **Metric**.

- ![](./media/image36.png)

  > Perceba que a mesma etapa **Refund with Special Voucher** envolve
  > apenas $631.11 em valor de fatura, que é menos da metade da maioria
  > das outras etapas.

  ![](./media/image37.png)

17. Select **Save**.

- ![](./media/image38.png)

### Conclusão:

Neste laboratório, os participantes criaram e analisaram um processo de
reembolso de contas a pagar utilizando as capacidades de Power Automate
Process Mining. Ao importar dados em CSV, eles construíram um process
map detalhado e um dashboard, permitindo examinar os key performance
indicators (KPIs) e métricas do processo. Através do Power Automate
Process Mining desktop app, os participantes realizaram uma análise mais
profunda, identificando ineficiências, como longas durações e valores
menores de fatura em etapas específicas. Este laboratório demonstrou
como o Process Mining pode ajudar as organizações a otimizar fluxos
financeiros, melhorar a eficiência e agilizar operações de contas a
pagar
