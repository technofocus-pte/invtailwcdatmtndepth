# Laboratório 3 - Crie um Fluxo Automatizado para Notificar o Gerente Quando um Novo Item for Criado no Dynamics 365 Business Central

**Objetivo:** Neste laboratório, os participantes aprenderão a criar um
Fluxo Automatizado no Power Automate que envia uma notificação por email
sempre que um novo item é criado no Microsoft Dynamics 365 Business
Central. Seguindo um processo estruturado, os participantes irão se
familiarizar com o acionamento de fluxos com base nos dados do Business
Central, coletando informações relevantes sobre itens, aplicando lógica
condicional e executando ações para enviar alertas por email. Essa
experiência prática capacitará os participantes a aproveitar o Power
Automate para aprimorar processos de negócios e notificações.

**Tempo estimado:** 15 minutos

### Tarefa 1: Inscrever-se no Microsoft Dynamic 365 Business Central

1.  Navegue até
    **+++https://www.microsoft.com/en-us/dynamics-365/products/business-central+++**
    e clique em **Try for Free.**

- ![](./media/image1.png)

2.  Insira sua ID de locatário do Office 365 e clique em **Next**.

- ![](./media/image2.png)

3.  Em seguida, clique em **Sign In** e insira as credenciais.

- ![](./media/image3.png)

4.  Selecione **United States** como country or region, insira seu
    **phone number** e selecione **Get Started**.

- ![](./media/image4.png)

5.  Em seguida, clique em **Get Started** para acessar o Business
    Central.

- ![](./media/image5.png)

6.  Selecione o botão **Skip survey** para continuar.

- ![](./media/image6.png)

7.  Você será direcionado para a página inicial do Dynamics 365 Business
    Central.

- ![](./media/image7.png)

### Tarefa 2: Iniciar o Power Automate

1.  Abra uma nova guia ao lado do Dynamic 365 Business Central e navegue
    até **+++https://make.powerautomate.com/+++** no navegador.

- ![](./media/image8.png)

2.  Se solicitado, insira a **ID de locatário do Microsoft 365** no
    campo respeitado e clique no botão **Next**.

- ![](./media/image9.png)

3.  Digite o **password** no campo correspondente e clique em **Sign
    in.**

- ![](./media/image10.png)

4.  Na barra de navegação superior, selecione o Environment **Dev One.**

- ![](./media/image11.png)

5.  Clique em **+ Create** no menu à esquerda.

- ![](./media/image12.png)

6.  Selecione o bloco **Automated cloud flow**.

- ![](./media/image13.png)

### Tarefa 3: Crie um Trigger baseado nos dados do Business Central

1.  Na caixa **Flow name**, insira +++**Email notification for new
    furniture**+++.

- ![](./media/image14.png)

2.  Na barra de pesquisa **Choose your flow’s trigger**, insira
    **Business Central**. Role para baixo para exibir os triggers e
    selecione **When a record is created (V3)**.

3.  Clique em **Create**.

> ![](./media/image15.png)
>
> 4\. Preencha os detalhes do acionador:

1.  **Environment name**: insira +++**PRODUCTION**+++.

2.  **Company name**: selecione **CRONUS USA, Inc.** da lista.

&nbsp;

1.  **Table name**: selecione **Items**.

> ![](./media/image16.png)

### Tarefa 4: Coletar dados do Business Central

1.  Clique no botão **+ Add** e selecione **Add an action**.

> ![](./media/image17.png)

4.  Na janela **Add an action**, digite +++**Dynamics 365 Business
    Central**+++ na caixa de pesquisa e escolha a ação **Get record
    (V3)**.![](./media/image18.png)

&nbsp;

1.  Insira as seguintes informações:

    1.  **Environment**: +++**PRODUCTION**+++.

    2.  **Company name**: Selecione **CRONUS USA, Inc.**.

    3.  **Table name**: Selecione **items**.

    &nbsp;

    1.  **Row ID**: Selecione a **Row ID** da linha no conteúdo
        Dinâmico.

> ![](./media/image19.png)

### Tarefa 5: Criar a condição

1.  Clique no **botão** **+** abaixo de Get record e selecione **Add an
    action**.

> ![](./media/image20.png)

5.  Na barra de pesquisa **Add an action**, insira **Control**. Escolha
    a ação **Condition**.![](./media/image21.png)

&nbsp;

1.  Defina a condição:

    1.  Na primeira caixa **Choose a value**, selecione o token **Item
        Category Code** em Dynamic content.

    2.  Mantenha a opção **is equal to**.

    3.  Na segunda caixa **Choose a value**, insira
        +++**FURNITURE**+++.![](./media/image22.png)

### Tarefa 6: Criar uma ação com base na condição

1.  Na janela **If yes or True** condition, clique em **Add an
    action**.![](./media/image23.png)

&nbsp;

6.  Pesquise por +++**office 365 outlook**+++ na janela Add an action e
    clique em ver mais. No trigger do Office 365 Outlook, selecione
    **Send an Email (V2).**![](./media/image24.png)

> ![](./media/image25.png)

7.  Preencha os detalhes do e-mail:

    1.  **To**: Insira 'Admin' e selecione **Mod Admin** na sugestão, ou
        seja, ID de email do locatário do Office 365 que você está
        usando neste laboratório.

    2.  **Subject**: Digite +++**New furniture released**+++.

    3.  **Body**:

        1.  Adicione o texto **New Furniture**.

        2.  Adicione a token **Number** a partir do conteúdo Dinâmico.

        3.  Adicione a token **displayName** a partir do conteúdo
            Dinâmico.

        4.  Adicione o texto +++**has just released.**+++

> ![](./media/image26.png)

2.  Clique em **Save** para finalizar seu fluxo.

> ![](./media/image27.png)

### Tarefa 7: Testar o fluxo

1.  Na barra superior, clique no botão **Test**.

> ![](./media/image28.png)

2.  Selecione o processo **Manual** e clique em **Test**.

> ![](./media/image29.png)

3.  Navegue de volta para o **site do** **Business Central** e, na barra
    superior, vá para **Sales Items**.

> ![](./media/image30.png)

4.  Clique no botão **+ New**

> ![](./media/image31.png)

5.  Selecione **ITEM** e clique em **OK**.

> ![](./media/image32.png)

6.  No campo Item Category Code, selecione **FURNITURE** e, no campo
    Description, escreva **Office Chair.**

> ![](./media/image33.png)

7.  Clique no botão **Save**.

> ![](./media/image34.png)

8.  No portal Power Automate, clique em **App launcher** localizado no
    canto superior esquerdo. Selecione **Outlook** e você poderá ver que
    a resposta automática é recebida no **e-mail** do MOD Admin
    fornecido.

> ![](./media/image35.png)

### Conclusão:

Ao final deste laboratório, os participantes terão criado com êxito um
fluxo de notificações por email automatizado no Power Automate para
novos itens no Business Central. Eles terão adquirido experiência
prática configurando triggers, ações e condições, que são habilidades
essenciais para automatizar um workflow. Os participantes também
entenderão como coletar e manipular dados do Business Central de forma
eficaz, permitindo a simplificação de comunicações e o aumento da
produtividade em suas respectivas organizações. Esse conhecimento
servirá como base para uma maior exploração dos recursos do Power
Automate na automação de vários processos de negócios.
