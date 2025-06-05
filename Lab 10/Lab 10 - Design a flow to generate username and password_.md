# Laboratório 10 - Projetar um fluxo para gerar nome de usuário e senha

**Objetivo:** o objetivo deste laboratório é criar e testar um fluxo do
Power Automate Desktop que gere um nome de usuário e uma senha aleatória
com base na entrada do usuário. Ao concluir este laboratório, os
participantes aprenderão a projetar e automatizar um fluxo usando ações
do Power Automate Desktop, incluindo manipulação de texto e geração de
texto aleatório.

**Tempo estimado:** 20 minutos

# Tarefa 1: Criar um fluxo do Power Automate Desktop

1.  Faça login e abra o **Power Automate Desktop com o locatário do
    Office 365** e escolha um environment (**Contoso**). No canto
    superior esquerdo, selecione **+ New flow.**

- ![](./media/image1.png)

2.  Digite o Flow name +++**Generate Username and Password**+++,
    confirme se o **Power Fx** está desligado e clique em **Create**.

- ![](./media/image2.png)

3.  Na barra de pesquisa Actions à esquerda, pesquise a ação
    +++**Display input dialog**+++ e dê um duplo clique na ação para
    selecioná-la.

- ![](./media/image3.png)

4.  Defina a propriedade **Input dialog title** como **+++Name
    Input+++** e a propriedade **Input dialog message** como **+++Please
    enter your first and last name (for example, Adele Vance)+++**. Essa
    ação exibe uma mensagem que solicita a entrada do usuário. Clique no
    botão **Save**.

- ![](./media/image4.png)

5.  Na barra de Actions à esquerda, pesquise a ação +++**Split text**+++
    e dê um duplo clique na ação para selecioná-la.

- ![](./media/image5.png)

6.  No campo **Text to split** da ação Split text, insira
    +++**%UserInput%**+++ e, em seguida, clique em **Save.**

- ![](./media/image6.png)

7.  Na barra de Actions à esquerda, pesquise a ação +++**Change text
    case**+++ e dê um duplo clique na ação para selecioná-la.

- ![](./media/image7.png)

8.  No campo Text to convert, insira +++**%TextList\[0\]%**+++.

9.  Com o índice de uma variável do tipo lista, forneça o primeiro item
    da lista, que é o primeiro nome. Defina a propriedade Convert to
    para **Lower case** e, em seguida, clique em **Save**.

- ![](./media/image8.png)

10. Na barra de Actions à esquerda, pesquise a ação +++**Change text
    case**+++ e dê um duplo clique na ação para selecioná-la.

- ![](./media/image9.png)

11. No campo de ação **Text to convert**, insira
    +++**%TextList\[1\]%**+++.

12. Com o índice de uma variável do tipo lista, forneça o primeiro item
    da lista, que é o primeiro nome. Defina a propriedade Convert to
    para **Lower case** e, em seguida, clique em **Save**.

- ![](./media/image10.png)

13. Na barra de Actions à esquerda, pesquise a ação +++**Get
    subtext**+++ e dê um duplo clique na ação para selecioná-la.

- ![](./media/image11.png)

14. No campo Original text, insira +++**%TextWithNewCase%**+++. Na seção
    Start index, defina Character position como +++**0**+++

15. Na seção Length, defina Number of chars como +++**1**+++. Essa
    configuração obtém o primeiro caractere da cadeia de texto.

16. Clique em **Save**.

- ![](./media/image12.png)

17. Para gerar uma senha aleatória, adicione a ação **Create random
    text**. As propriedades da ação podem ser mantidas nos valores
    padrão. Em seguida, clique no botão **Save**.

- ![](./media/image13.png)

18. Na barra de Actions à esquerda, pesquise a ação +++**Display
    message**+++ e dê um duplo clique na ação para selecioná-la.

- ![](./media/image14.png)

19. No campo **Message box title**, digite +++**Username & Password**+++
    e, no campo **Message to display**, insira o seguinte conteúdo:

- +++Hello, %UserInput%, your username is: %SubText%%TextWithNewCase2% Your temporary password is: %RandomText%+++

20. O nome de usuário (primeira letra do primeiro nome, combinada com o
    sobrenome) é exibido e o resultado da ação **Generate random text**
    aparece como a senha do usuário. Clique no botão **Save**.

- ![](./media/image15.png)

21. O **fluxo concluído** deve ser semelhante à figura a seguir.

- ![](./media/image16.png)

# Tarefa 2: Testar o fluxo

1.  Clique no botão **Run** para testar o fluxo.

- ![](./media/image17.png)

2.  Digite o **First and Last Name** para fins de teste e clique no
    botão **Ok**.

- ![](./media/image18.png)

3.  A **saída final** do caso de teste ficará semelhante ao exemplo
    abaixo uma vez concluída.

- ![](./media/image19.png)

**Conclusão:** neste laboratório, os participantes projetaram e testaram
com êxito um fluxo do Power Automate Desktop que gera um nome de usuário
e uma senha aleatória com base na entrada do usuário. Ao utilizar ações
de manipulação de texto, como dividir, alterar maiúsculas e minúsculas e
gerar texto aleatório, os participantes ganharam experiência prática na
automação de tarefas específicas do usuário. O fluxo demonstra como
criar dinamicamente um nome de usuário e uma senha usando recursos
básicos do Power Automate Desktop. Este laboratório estabelece as bases
para a criação de fluxos de automação mais complexos em tarefas futuras.
