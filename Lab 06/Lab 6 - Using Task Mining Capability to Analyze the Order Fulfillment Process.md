# Laboratório 6 - Usando o Recurso de Task Mining para Analisar o Processo de Atendimento de Pedidos

**Objetivo**: o laboratório foca na utilização dos recursos de task
mining do Power Automate para analisar e otimizar o processo de
atendimento de pedidos. Os participantes aprenderão a importar uma
solução contendo gravações de exemplo, explorar os recursos do task
mining e realizar análises de processo para identificar obstáculos. Além
disso, o laboratório aborda a automação de etapas do processo e o uso de
análises para obter insights sobre a eficiência do processo.

**Tempo estimado:** 30 minutos

### Tarefa 1: Prepare-se para o task mining

1.  **Faça login** no Power Automate usando
    +++**https://make.powerautomate.com/**+++ com suas credenciais de
    locatário do Office 365.

2.  Selecione seu environment – **Dev One**.

- ![](./media/image1.png)

### Tarefa 2: Importar uma solução

1.  No painel de navegação à esquerda, selecione **Solutions** e então
    na barra de ferramentas no topo, selecione **Import solution**.

- ![](./media/image2.png)

2.  Selecione **Browse**.

- ![](./media/image3.png)

3.  Selecione o arquivo **Processmining.zip** file em C:Files e abra-o.

- ![](./media/image4.png)

4.  Selecione **Next**.

- ![](./media/image5.png)

5.  Selecione **Import** e aguarde a importação da solução.

- ![](./media/image6.png)

### Task 3: Visualizar gravações de exemplo

1.  Após importar com sucesso o arquivo .zip, no painel de navegação à
    esquerda, selecione **Process mining** e então selecione o **Invoice
    submission process**.

- ![](./media/image7.png)

2.  Se você navegar até a guia Analytics, depois dê um passo para trás.
    Volte para o **Invoice submission process** selecionando-o nos
    breadcrumbs no topo da página.

- ![](./media/image8.png)

3.  Você pode ver algumas das gravações existentes em **Recordings**.

- ![](./media/image9.png)

4.  Para garantir que você veja a lista completa de gravações
    existentes, selecione **See all**.

### Task 4: Explorar os recursos

Você verá os seguintes recursos:

- **New recording:** criar uma nova gravação.

- **Analytics: v**er o mapa do processo e insights.

- **Analyze:** analisar um processo.

- **Create activity names:** criar nomes de atividades para seu
  processo.

- **Delete process:** excluir seu processo.

&nbsp;

- ![](./media/image10.png)

### 

### Tarefa 5: Analisar um processo

Ao analisar um processo, a funcionalidade de process mining analisa os
registros existentes para identificar quaisquer obstáculos dentro do
processo de negócios.

1.  Selecione **Analyze**.

- > **Observação:** a análise levará alguns minutos para ser concluída.
  > Durante esse processo, uma mensagem de status será exibida abaixo do
  > botão **New recording**.

  ![](./media/image11.png)

2.  Se você encontrar um erro durante a etapa de análise, selecione
    **Analyze** para acionar essa ação novamente.

3.  Quando estiver concluído, você verá o **Process analysis status**
    mudar para **Analyzed**. Selecione **Analytics** para ver o mapa do
    processo e os insights.

- ![](./media/image12.png)

  > **Observação:** essa etapa pode levar alguns minutos para ser
  > concluída após a análise ter sido realizada.

### Tarefa 6: Layout da página de análises

Esta seção explica o que você pode fazer na tela **Analytics**.

![](./media/image13.png)

![](./media/image14.png)

**Legenda:**

1.  **Automate activities:** para simplificar o processo de automação,
    você pode usar o recurso **Automate activities**. Esse recurso
    detecta se o usuário executou ações usando um aplicativo que possui
    ações disponíveis no Power Automate, como Microsoft Outlook ou
    Excel. Ao selecionar **Automate activities**, um rascunho de
    processo do Power Automate contendo as ações relevantes é gerado. O
    usuário pode então modificar e personalizar o processo de rascunho
    para criar o processo automatizado final.

2.  **Legend**: Informações adicionais sobre o relatório, ajudando a
    entender melhor as visualizações e os dados apresentado.

3.  **Process**: Informações detalhadas sobre o processo analisado,
    incluindo o mapa do processo, análises de tempo para cada variante e
    para cada autor da gravação.

4.  **Application**: Informações sobre os aplicativos usados nas
    gravações. Isso inclui quais aplicativos foram utilizados pelos
    autores, com que frequência foram usados e quais foram as transições
    entre eles. Esse relatório explica quais connectors devem ser usados
    ao implementar a automação do processo e onde potencialmente
    utilizar desktop flows, caso não exista um connector disponível.

### Tarefa 7: Relações entre as etapas do processo de negócios

Você pode ver as várias etapas do processo de negócios e suas
respectivas durações. Essas etapas incluem:

- Download invoice attachment from email (48 segundos)

- Open Excel invoice list (11.5 segundos)

- Open invoice from OneDrive (21 segundos)

- Enter invoice details (53.6 segundos)

- Save and submit (9 segundos)

- Notify team of submission (26.67 segundos)

&nbsp;

- ![](./media/image15.png)

### Tarefa 8: Visualizar dados analíticos

1.  Observe os principais dados analíticos. O tempo médio do processo é
    de 1,47 minutos em cinco gravações.

- ![](./media/image16.png)

2.  Analise outros painéis de métricas baseados em tempo.

- > **Activity by average time in sec**: Observe que **Enter invoice
  > details** e **Download invoice** estão levando mais tempo.

  ![](./media/image17.png)

  > **Recording by average time in min**: Observe que algumas pessoas
  > (Preston Morales e Shakti Menon) estão levando mais tempo do que
  > outras.

  ![](./media/image18.png)

  3\. Selecione a guia **Application** para ver detalhes sobre quais
  aplicações foram usadas. Pode demorar um pouco para carregar os
  relatórios.

  - Ao fornecer informações sobre as aplicações utilizadas em um
    processo de negócio, a frequência de uso e o tempo gasto em cada
    aplicação, este relatório é fundamental para obter insights sobre o
    processo.

  - Por exemplo, o painel mostra que um aplicativo legado de
    faturamento, o Outlook e o Excel têm contribuições significativas no
    tempo gasto e nas ações por aplicação.

  - Dedique um tempo para se familiarizar com os diferentes relatórios.

  ![](./media/image19.png)

4.  Volte para o mapa do processo selecionando **Process**.

5.  Observe o recurso de atividades automatizadas. A partir do mapa do
    processo, é possível ver que a funcionalidade de process mining
    destacou várias atividades como potenciais candidatas à automação,
    com base nas aplicações utilizadas.

6.  Comece a criar um fluxo de automação selecionando **Automate
    activities** na parte superior.

- ![](./media/image20.png)

  Uma guia abre no navegador e exibe o designer de fluxo. As ações
  recomendadas que correspondem às atividades do mapa do processo
  aparecem automaticamente no painel à direita. Por exemplo, vários
  email connectors são sugeridos para você usar a fim de automatizar a
  atividade **Download invoice attachment from email**.

  ![](./media/image21.png)

### Conclusão:

Neste laboratório, os participantes utilizaram os recursos de task
mining do Power Automate para analisar e otimizar o processo de
atendimento de pedidos. Ao importar uma solução pré-configurada com
gravações de exemplo, eles exploraram os principais recursos do task
mining, incluindo a análise de processos, identificação de obstáculos e
geração de recomendações de automação. Os participantes aprenderam a
avaliar a eficiência do processo por meio de análises detalhadas sobre o
tempo gasto em várias tarefas e aplicações. O laboratório destacou como
o task mining pode simplificar processos de negócios ao identificar
oportunidades de automação, melhorando a eficiência operacional e
reduzindo o trabalho manual no processo de atendimento de pedidos.
