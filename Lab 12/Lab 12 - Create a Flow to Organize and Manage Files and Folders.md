# Laboratório 12 – Criar um fluxo para organizar e gerenciar arquivos e pastas

**Objetivo:** o objetivo deste laboratório é automatizar o processo de
backup de arquivos de uma pasta designada na área de trabalho usando o
**Power Automate Desktop**. Os participantes criarão um fluxo que copia
arquivos de uma pasta chamada **Contoso_Files**, move-os para uma pasta
de backup recém-criada e acrescenta um carimbo de data/hora ao arquivo
de backup. Este laboratório oferece experiência prática na automação de
tarefas de gerenciamento de arquivos, incluindo a criação de pastas,
cópia de arquivos e renomeação com formatos dinâmicos de data e hora.

**Tempo estimado:** 20 minutos

### Tarefa 1: Criar pasta e fluxo da área de trabalho

1.  Crie uma pasta em sua área de trabalho e renomeie como
    **Contoso_Files.**

- ![](./media/image1.png)

2.  **Selecione** o arquivo **Report.txt** na **pasta C:\* e mova o**
    arquivo **.txt\*\*** para a pasta **Contoso_Files.**

- ![](./media/image2.png)

3.  Abra o Power automate Desktop e **faça login** com a **credencial de
    locatário do Office 365**. Escolha o ambiente **Contoso** na barra
    superior.

- ![](./media/image3.png)

4.  Clique em **+ New flow** no canto superior esquerdo e comece a criar
    um novo fluxo.

- ![](./media/image4.png)

5.  Digite **+++Backup File Flow+++** como nome do flow e selecione a
    caixa de seleção **Power Fx enable (Preview)**. Depois, clique em
    **Create**.

- ![](./media/image5.png)

6.  Na barra de navegação **Actions** à esquerda, pesquise pela ação
    **+++Get special folder+++** no workspace. Selecione a ação dando um
    duplo clique para adicioná-la ao fluxo.

- ![](./media/image6.png)

7.  Em seguida, clique no botão **Save** para salvar a configuração
    padrão do botão.

- ![](./media/image7.png)

8.  Na barra de navegação **Actions** à esquerda, pesquise pela ação
    **+++Get files in folder +++** no workspace. Selecione a ação dando
    um duplo clique para adicioná-la ao fluxo.

- ![](./media/image8.png)

9.  Adicione a ação **Get files in folder** para definir o campo
    **Folder** como +++\*\*C:\_Files**+++**. **Esta configuração
    selecionará a pasta que você criou anteriormente na área de
    trabalho. Depois, clique no** botão Save\*\*.

- ![](./media/image9.png)

10. Na barra de navegação **Actions** à esquerda, pesquise pela ação
    +++**Create Folder**+++ no workspace. Selecione a ação dando um
    duplo clique para adicioná-la ao fluxo.

- ![](./media/image10.png)

11. No campo **Create new folder into** da ação **Create folder**,
    digite +++C:\*+++. No campo **New folder name**, digite
    **Contoso_Backup**. Após inserir as informações, clique no botão
    **Save**.

- ![](./media/image11.png)

12. Na barra de navegação **Actions** à esquerda, pesquise pela ação
    +++**Copy file(s)**+++ no workspace. Selecione a ação dando um duplo
    clique para adicioná-la ao fluxo.

- ![](./media/image12.png)

13. Defina o campo **File(s) to Copy** como **+++ =Files +++**, o campo
    **Destination Folder** como +++ C:\_Backup **+++**, **e a opção do
    menu suspenso** **+++** If File(s) Exists **+++** **como**
    Overwrite**. Após a configuração, clique no** botão Save\*\*.

- ![](./media/image13.png)

14. Na barra de navegação **Actions** à esquerda, pesquise pela ação
    +++**Rename file(s)**+++ no workspace. Selecione a ação dando um
    duplo clique para adicioná-la ao fluxo.

> ![](./media/image14.png)

15. Defina o campo **File(s) to rename** como
    +++\*\*C:\_Backup.txt**+++. No** **menu suspenso** Rename scheme**,
    selecione a opção** Add datetime**. Defina a opção do menu
    suspenso** Separator **como** Nothing\*\* e a opção **DateTime
    Format** como **+++dd.MM.yy_HH.mm+++.** Após a configuração, clique
    no botão Save**.**

- ![](./media/image15.png)

16. O fluxo **concluído** deve ser semelhante à captura de tela a
    seguir.

- ![](./media/image16.png)

### Tarefa 2: Testar o fluxo

1.  Após a conclusão da execução do fluxo, uma nova pasta chamada Backup
    Files será criada na sua área de trabalho. Essa pasta conterá todo o
    conteúdo da pasta chamada Important e um arquivo de texto adicional
    chamado Backup Log, que terá anexada ao nome do arquivo a última
    data e hora em que o fluxo foi executado.

- ![](./media/image17.png)

  ![](./media/image18.png)

### Conclusão:

Neste laboratório, os participantes criaram com sucesso um fluxo no
Power Automate Desktop para automatizar a organização e o gerenciamento
de arquivos e pastas.  
Ao fazer backup de arquivos a partir de uma pasta designada chamada
Contoso_Files para uma nova pasta de backup criada, os participantes
adquiriram experiência prática em tarefas essenciais de gerenciamento de
arquivos, incluindo criação de pastas, cópia de arquivos e renomeação
dinâmica de arquivos com carimbos de data e hora.  
Este laboratório destaca a eficácia do Power Automate Desktop na
otimização dos processos de organização de arquivos, redução do esforço
manual e garantia de backup seguro de arquivos importantes.
