# Laboratório 07 - Criar um fluxo para encaminhar solicitações de suporte técnico para diferentes caixas de e-mail com base no idioma

**Objetivo:** o objetivo deste laboratório é orientar os participantes
no processo de criação de um fluxo do Power Automate que encaminha as
solicitações de suporte técnico para diferentes caixas de entrada com
base na detecção de idioma. O fluxo se integra aos recursos do GPT para
resumir os e-mails recebidos e automatizar o processo de encaminhamento
com base em acionadores específicos, ajudando a otimizar os fluxos de
trabalho de comunicação dentro da organização.

**Tempo estimado:** 15 minutos

### Tarefa 1: Criar um fluxo para encaminhar as solicitações do Suporte Técnico para diferentes caixas de e-mail com base no idioma

1.  Faça login na **conta de administrador locatário do Office 365 em**
    +++**https://make.powerautomate.com/using**+++

2.  Selecione **Templates** no painel de navegação à esquerda, digite
    **+++Summarize emails using GPT+++** na caixa de pesquisa no topo e
    selecione o fluxo quando ele aparecer.

- ![](./media/image1.png)

3.  Em seguida, o template mostra quais conexões serão usadas neste
    fluxo. Se elas não tiverem uma marca de seleção verde ao lado,
    corrija a conexão selecionando ‘Sign in’ ao lado da conexão e depois
    selecione **Continue**.

- ![](./media/image2.png)

4.  Selecione o acionador, **when a new email arrives (V3)**. O painel
    de propriedades será aberto à esquerda com uma notificação para
    atualizar o parâmetro Subject Filter. Atualmente, o **Subject
    Filter** é AI Builder.

5.  Atualize o Subject Filter para **Project Kick-off.**

- ![](./media/image3.png)

6.  Selecione a ação **Create text with a GPT using a prompt** para que
    o painel de propriedades seja aberto à esquerda. No painel de
    propriedades, o campo Prompt exibe **AI Summarize**.

7.  Selecione **Test prompt** para abrir as configurações de Prompt.

- ![](./media/image4.png)

8.  O template possui um prompt predefinido que o GPT utilizará, mas
    você pode atualizar e testar um novo prompt nesta janela. Siga a
    próxima etapa para atualizar o prompt.

9.  Para testar um prompt, insira os dados de amostra fornecidos na
    seção **Input**. Em seguida, selecione **Test prompt** na parte
    inferior da seção Prompt. Você pode ver a resposta na seção Prompt
    response.

- +++Once upon a time in the quaint town of Eldoria, nestled between
  rolling hills and dense forests, lived a young girl named Elara. Her
  days were spent exploring the mystical woods that bordered the town,
  and whispers of ancient tales filled her imagination.+++

  ![](./media/image5.png)

10. Para este exercício, deixaremos tudo como estava quando abrimos o
    Prompt Settings.

11. **Save** o fluxo no canto superior direito. Agora podemos executar o
    fluxo.

![](./media/image6.png)

> Observação: ignore se você vir o aviso: A ação ‘Create text with GPT
> não possui uma ação de aprovação de conteúdo após ela.

### Tarefa 2: Testar o fluxo

1.  Envie um e-mail do ID de locatário do MOD Admin ou do seu ID de
    e-mail para o ID de locatário do MOD Admin com o assunto **Project
    Kick-off** and the following in the body of the email:

- Dear Team,

      I hope this email finds you well. We are excited to announce the
      kick-off of our new project, "Phoenix". The initial meeting is scheduled
      for Monday, June 1st, at 10 AM via Zoom. Please come prepared with any
      questions or suggestions. Your input is vital for the project's success.

      Kindly confirm your attendance by the end of the day tomorrow. Looking
      forward to a productive session and a successful project launch.

      Best regards,

      Miriam Graham

      Project Manager

      Contoso

2.  Você receberá uma mensagem no Teams com um resumo do e-mail. No
    canto inferior direito, você encontrará um link para acessar seu
    fluxo.

- ![](./media/image7.png)

3.  Esta unidade utiliza um GPT para resumir os e-mails recebidos. As
    informações de detecção da AI podem ser imprecisas. Certifique-se
    sempre de verificar as informações do GPT.

### Conclusão:

Neste laboratório, os participantes criaram com sucesso um fluxo do
Power Automate para otimizar as solicitações de suporte técnico,
encaminhando e-mails com base na detecção de idioma e usando o GPT para
resumir o conteúdo. Ao integrar a automação ao fluxo de trabalho de
e-mail, o laboratório demonstrou como gerenciar com eficiência a
comunicação entre várias equipes ou departamentos com base em
acionadores de idioma. O exercício também mostrou como usar o GPT no
Power Automate para aumentar a produtividade e reduzir a classificação
manual. Essa solução ajuda as organizações a melhorar a eficiência do
fluxo de trabalho e reduzir o tempo de resposta às solicitações de
suporte técnico.

.
