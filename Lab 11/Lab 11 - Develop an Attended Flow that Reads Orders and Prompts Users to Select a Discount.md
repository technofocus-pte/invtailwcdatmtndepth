# Laboratório 11 – Desenvolver um Fluxo Assistido que Lê Pedidos e Solicita que os Usuários Selecionem um Desconto

**Objetivo:** o objetivo deste laboratório é desenvolver um **fluxo
assistido no Power Automate Desktop** que automatize o processo de
leitura de pedidos a partir de um arquivo Excel e solicite que os
usuários apliquem um desconto com base em determinadas condições. Os
participantes criarão um fluxo que lê os dados, verifica se o valor do
pedido excede um determinado limite e, em seguida, solicita ao usuário a
decisão de aplicar ou não um desconto, com a opção de inserir o valor do
desconto. O fluxo, então, atualizará a planilha do Excel com o desconto
aplicado.

**Tempo estimado:** 25 minutos

### Tarefa 1: Criar o fluxo do Power Automate Desktop

1.  Abra **Power automate desktop** e faça logon com a **credencial de
    locatário do Office 365**.

2.  Escolha o ambiente **Contoso** e clique em **+ New then Flow** e
    comece a criar um novo fluxo.

- ![](./media/image1.png)

3.  Insira +++**Message Box Communication**+++ como flow name e confirme
    se o Power Fx enabled (versão prévia) está desativada. Em seguida,
    clique no botão **Create**.

- ![](./media/image2.png)

4.  Comece solicitando que o usuário selecione um arquivo do Excel.
    Adicione a ação +++**Display select file dialog**+++ e configure o
    campo Filtro de arquivo para permitir apenas arquivos xlsx.

- ![](./media/image3.png)

5.  Insira o **Dialog Title** como +++**Select Excel**+++, insira o
    local da pasta em **initial** **folder** como +++ C: Files+++ Filtre
    como **\*.xlsx** e clique no botão **Save**.

- ![](./media/image4.png)

6.  Antes de ler qualquer dado do arquivo selecionado, é necessário
    abri-lo usando a ação **Launch Excel.** Adicione a ação **Launch
    Excel** a partir da lista de ações. Em seguida, configure a seguinte
    opção:

    - Launch Excel: **add open the following document**

    - Document path: +++**%SelectedFile%**+++

    - Clique no botão salve

- ![](./media/image5.png)

7.  Para ler os dados do arquivo Excel, adicione a ação **Read from
    Excel worksheet.**  
    Insira **%ExcelInstance%** no campo Excel instance e selecione **All
    available values from worksheet** no campo Retrieve. Clique no botão
    **Save**.

- ![](./media/image6.png)

8.  Adicione a ação **Get first free column/row from Excel worksheet**
    para obter a primeira coluna e linha livres na planilha do Excel.  
    Insira **%ExcelInstance%** no campo Excel instance e, em seguida,
    clique no botão **Save**.

- ![](./media/image7.png)

9.  Adicione a ação Set Variable, nomeie-a como **Counter** e
    inicialize-a com o valor **1**, em seguida clique no botão Save**.**

- ![](./media/image8.png)

10. Adicione a ação **Display input dialog** e configure os seguintes
    campos.

    - **Input Dialog Title**: +++**Header**+++

    - **Input Dialog Message**: +++**Enter the Header**+++

    - **Default Value**: +++**Discount**+++

    - Clique no botão **save**.

- ![](./media/image9.png)

11. Adicione a ação **Write to Excel worksheet** a partir das ações e
    configure-a com os seguintes detalhes:

    - **Excel instance**: %ExcelInstance%

    - **Value to write**: +++**%UserInput%**+++

    - **Write role**: On specific cell

    - **Column**: +++**9**+++

    - **Row**: +++**%Counter%**+++

    - Clique no botão **save**.

- ![](./media/image10.png)

12. Adicione a ação **For each** para iterar sobre os dados recuperados
    e insira +++**%ExcelData%**+++ no campo Value to iterate. Em
    seguida, clique no botão **Save**.

- ![](./media/image11.png)

13. Para verificar o valor da coluna **Gross** (coluna G ou a sexta
    coluna na planilha — no Excel, o nome da coluna é "6"), adicione a
    ação **Convert text to number**. Configure o campo text to convert
    como +++**%CurrentItem\[6\]%**+++ e, em seguida, clique no botão
    Save.

- ![](./media/image12.png)

14. Adicione uma ação **If** para verificar se o valor excede 100.000 e
    configure-a com os seguintes detalhes:

    - **First operand**: +++**%TextAsNumber%**+++

    - **Operator**: Greater than or equal to (\>=)

    - **Second Operand**: +++**100000**+++

- ![](./media/image13.png)

15. Adicione a ação **Display message** dentro do bloco **If**, para
    fornecer as informações necessárias ao usuário e solicitar que ele
    escolha entre **Yes** ou **No**. Em seguida, clique no botão
    **Save**. Preencha os seguintes detalhes:

    - **Message Box title**: +++**Add discount**+++
    - **Message to display**:
      - +++**Product:** %CurrentItem\[2\]%+++
      - +++**Units**: %CurrentItem\[3\]%+++
      - +++**Gross:** %TextAsNumber%+++
    - **Message box button**: Yes – No

- ![](./media/image14.png)

16. Adicione uma segunda ação **If** abaixo da ação **Display message**
    para verificar qual botão foi pressionado na etapa anterior:

- **First** **operand**: +++%ButtonPressed3%+++

- **Operator:** Equal to (=)

- **Second operand:** +++Yes+++

 

- ![](./media/image15.png)

17. *Dentro do segundo* **If**, adicione a ação **Display Input
    Dialog***.**  
    ***Insira os parâmetros abaixo nos campos correspondentes e clique
    no botão **Save**.

Input dialog title: +++Discount Value+++

Input dialog message: +++Enter the Discount Value+++

![](./media/image16.png)

18. Adicione a ação **Write to Excel worksheet** logo abaixo da segunda
    ação **If** e preencha os seguintes detalhes:

- **Excel instance:** +++%ExcelInstance%+++

- **Value to writer**: +++%UserInput2%+++

- **Write mode:** On specific cell

- **Column:** +++9+++

- **Row:** +++%Counter%+++

&nbsp;

- ![](./media/image17.png)

20. No **Final** do primeiro bloco **If**, adicione a ação **Increase
    Variable**, adicione o nome da variável como **%Counter%**,
    configure Increase by para **1** e clique no botão Save.

> ![](./media/image18.png)

21. Na barra superior, **salve** o fluxo para o teste.

- ![](./media/image19.png)

# Tarefa 2: Testar o fluxo

1.  Clique no botão **Run** para executar o teste.

> ![](./media/image20.png)

2.  A primeira pasta da planilha será aberta, selecione o **arquivo
    excel** dela.

> ![](./media/image21.png)

3.  A janela Header será exibida; como definimos o **Discount** como
    padrão, clique no botão **OK**.

> ![](./media/image22.png)

4.  A janela **Add Discount** aparecerá, indicando que este produto tem
    valor superior a **100.000.** Selecione **Yes** ou **No**. Neste
    teste, selecionamos **Yes** (**yes**, concedemos desconto neste
    produto).

> ![](./media/image23.png)

5.  Em seguida, insira o **Discount Value** para o teste, inserimos
    **10000** e clicamos em **ok**.

> ![](./media/image24.png)

6.  Na Planilha, o valor do desconto é atualizado.

![](./media/image25.png)

7.  O loop está em execução **contínua** para todos os produtos.

### Conclusão:

Neste laboratório, os participantes desenvolveram um fluxo assistido no
Power Automate Desktop que lê dados de pedidos de um arquivo Excel,
verifica se o valor do pedido excede um limite definido e solicita ao
usuário que aplique um desconto.  
O fluxo automatiza de forma eficiente o processo de tomada de decisão,
permitindo que os usuários interajam com o fluxo por meio de prompts e
insiram os valores de desconto.  
Este laboratório oferece experiência prática na automação de tarefas
envolvendo Excel, entradas do usuário e lógica condicional, capacitando
os participantes a otimizar processos de negócios similares usando o
Power Automate Desktop.
