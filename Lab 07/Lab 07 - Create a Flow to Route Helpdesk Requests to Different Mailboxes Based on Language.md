# Laboratoire 0 7 : création d'un flux pour acheminer les demandes d'assistance vers différentes boîtes aux lettres en fonction de la langue

**Objectif :** L'objectif de ce laboratoire est de guider les
participants tout au long du processus de création du Power Automate
flow qui achemine les demandes d'assistance vers différentes boîtes aux
lettres en fonction de la détection de la langue. Le flux s'intègre aux
capacités de GPT pour résumer les e-mails entrants et automatiser le
processus de routage en fonction de déclencheurs spécifiques, ce qui
permet de rationaliser les flux de communication au sein de
l'organisation.

**Temps estimé :** 15 minutes

### Tâche 1 : Créer un flux pour acheminer les demandes d'assistance vers différentes boîtes aux lettres en fonction de la langue

1.  Connectez-vous au compte office 365 admin tenant
    **+++https://make.powerautomate.com/using+++.**

2.  Sélectionnez **Modèles** dans le volet de navigation de gauche,
    entrez +++**Summarize emails using GPT** +++ dans la zone de
    recherche en haut et sélectionnez le flux lorsqu'il apparaît.

- ![](./media/image1.png)

3.  Ensuite, le modèle vous montre quelles connexions seront utilisées
    dans ce flux. S'ils n'ont pas de coche verte à côté d'eux, corrigez
    la connexion en sélectionnant « Se connecter » à côté de la
    connexion, puis sélectionnez **Continue**.

- ![](./media/image2.png)

4.  Sélectionnez le déclencheur à l**'arrivée d'un nouvel e-mail (V3).**
    Le panneau des propriétés s'ouvre à partir de la gauche avec une
    note pour mettre à jour le paramètre Filtre de sujet. Actuellement,
    le **filtre Objet** est AI Builder.

5.  Mettez à jour le filtre d'objet sur **Project Kick-off**.

- ![](./media/image3.png)

6.  Sélectionnez l' action **Créer du texte avec un GPT à l'aide d'une
    invite** pour que le panneau des propriétés s'ouvre sur la gauche.
    Dans le panneau des propriétés, le champ de prompt affiche **AI
    Summarize**.

7.  Sélectionnez **Test prompt** pour ouvrir les paramètres du prompt.

- ![](./media/image4.png)

8.  Le modèle dispose de prompt prédéfini que le GPT utilisera, mais
    vous pouvez mettre à jour et tester un nouveau prompt dans cette
    fenêtre. Suivez l'étape suivante pour mettre à jour le prompt.

9.  Pour tester le prompt, entrez des exemples de données donnés dans la
    **section Entrée**. Sélectionnez ensuite **Test prompt** en bas de
    la section Prompt. Vous pouvez voir la réponse dans la section
    Réponse prompt.

- +++Il était une fois dans la ville pittoresque d'Eldoria, nichée entre
  des collines vallonnées et des forêts denses, une jeune fille nommée
  Elara. Elle passait ses journées à explorer les bois mystiques qui
  bordaient la ville, et des murmures de contes anciens remplissaient
  son imagination.+++

  ![](./media/image5.png)

10. Pour cet exercice, nous allons tout laisser tel qu'il était lorsque
    nous avons ouvert les paramètres de prompt.

11. **Save** le flux dans le coin supérieur droit. Nous pouvons
    maintenant exécuter le flux.

![](./media/image6.png)

> Remarque : Ignorez si vous voyez l'avertissement donné : ‘Create text
> with GPT using a prompt’ n'est pas suivie d'une action d'approbation
> de contenu.

### Tâche 2 : Tester le flow

1.  Envoyez un e-mail à partir de l'identifiant de MOD Admin’s tenant id
    ou de votre adresse e-mail à l'ID de MOD Admin’s tenant id avec pour
    objet Project **Kick-off** et ce qui suit dans le corps de l'e-mail
    :

- Chère équipe, 

      j'espère que cet e-mail vous trouve bien. Nous sommes ravis d'annoncer le
      lancement de notre nouveau projet, “Phoenix”. La première réunion est prévue
      pour le lundi 1er juin à 10 h via Zoom. Veuillez vous préparer avec des
      questions ou des suggestions. Votre contribution est essentielle à la réussite du projet.

      Veuillez confirmer votre présence avant la fin de la journée de demain. Dans l'attente
      d'une session productive et d'un lancement de projet réussi.

      Cordialement,Miriam

       Graham

      Chef de projet

      Contoso

2.  Vous recevrez un message dans Teams avec un résumé de l'e-mail. Dans
    le coin inférieur droit, vous pouvez trouver un lien pour accéder à
    votre flux.

- ![](./media/image7.png)

3.  Cette unité utilise un GPT pour résumer les e-mails entrants. Les
    informations de détection de l'IA peuvent être inexactes.
    Assurez-vous toujours de vérifier les informations du GPT.

### Conclusion:

Dans ce laboratoire, les participants ont réussi à créer un Power
Automate flow pour rationaliser les demandes d'assistance en acheminant
les e-mails en fonction de la détection de la langue et en utilisant GPT
pour résumer le contenu. En intégrant l'automatisation dans le flux de
travail des e-mails, le laboratoire a montré comment gérer efficacement
la communication entre plusieurs équipes ou départements en fonction de
déclencheurs linguistiques. L'exercice a également montré comment
utiliser GPT dans Power Automate pour améliorer la productivité et
réduire le tri manuel. Cette solution aide les organisations à améliorer
l'efficacité du flux de travail et à réduire le temps de réponse aux
demandes du service d'assistance.
