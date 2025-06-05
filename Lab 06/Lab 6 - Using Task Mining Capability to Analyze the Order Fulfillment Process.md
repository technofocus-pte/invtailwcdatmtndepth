# Laboratoire 6 - Utilisation de la fonctionnalité d'exploration de tâches pour analyser le processus d'exécution des commandes

**Objectif :** Le laboratoire se concentre sur l'utilisation des
fonctionnalités d'exploration de tâches de Power Automate pour analyser
et optimiser le processus d'exécution des commandes. Les participants
apprendront à importer une solution contenant des enregistrements
d'échantillons, à explorer les fonctionnalités d'exploration de tâches
et à effectuer une analyse de processus pour identifier les goulets
d'étranglement. De plus, le laboratoire couvre l'automatisation des
étapes du processus et l'utilisation de l'analytique pour obtenir des
informations sur l'efficacité du processus.

**Temps estimé :** 30 minutes

### Tâche 1 : Se préparer à l'exploitation minière des tâches

1.  **Connectez-vous** à Power Automate à l'aide de
    +++**https://make.powerautomate.com**/+++ avec vos informations
    d'identification Office 365 tenant.

2.  Sélectionnez votre environnement – **Dev One**.

- ![](./media/image1.png)

### Tâche 2 : Importer une solution

1.  Dans le volet de navigation de gauche, sélectionnez **Solutions** ,
    puis dans la barre d'outils en haut, sélectionnez **Import
    solution**.

- ![](./media/image2.png)

2.  Sélectionnez **Parcourir**.

- ![](./media/image3.png)

3.  Sélectionnez le **fichier Processmining.zip** dans C :Files et
    ouvrez-le.

- ![](./media/image4.png)

4.  Sélectionnez **Next**.

- ![](./media/image5.png)

5.  Sélectionnez **Import** et attendez que la solution soit importée.

- ![](./media/image6.png)

### Tâche 3 : Voir des exemples d'enregistrements

1.  Une fois que vous avez importé le fichier .zip, dans le volet de
    navigation de gauche, sélectionnez **Process mining,** puis
    sélectionnez **Processus de soumission de** **factures**.

- ![](./media/image7.png)

2.  Si vous accédez à l'onglet Analyses, reculez d'un pas. Revenez au
    processus de **soumission de factures** en le sélectionnant dans le
    fil d'Ariane en haut de la page.

- ![](./media/image8.png)

3.  Vous pouvez voir certains des enregistrements existants sous
    **Enregistrements**.

- ![](./media/image9.png)

4.  Pour vous assurer de voir la liste complète des enregistrements
    existants, sélectionnez **See all**.

### Tâche 4 : Explorer les fonctionnalités

Vous verrez les fonctionnalités suivantes :

- **Nouvel enregistrement** : créez un nouvel enregistrement.

- **Analytique** : consultez la carte des processus et les informations

- **Analyser** : Analysez un processus.

- **Créer des noms d'activité** : créez des noms d'activité pour votre
  processus.

- **Supprimer le processus** : supprimez votre processus.

&nbsp;

- ![](./media/image10.png)

### Tâche 5 : Analyser un processus

Lorsque vous analysez un processus, la fonctionnalité d'exploration de
processus analyse les enregistrements existants pour identifier les
goulots d'étranglement au sein du processus d'entreprise.

1.  Sélectionnez **Analyser**.

- > **Remarque :** L'analyse ne prendra que quelques minutes. Au cours
  > de ce processus, un message d'état s'affiche sous le bouton **New
  > recording** .

  ![](./media/image11.png)

2.  Si vous rencontrez une erreur pendant l'étape d'analyse,
    sélectionnez **Analyser** pour déclencher à nouveau cette action.

3.  Une fois que c'est fait, vous voyez le **statut Analyse du
    processus** passer à **Analysé**. Sélectionnez **Analytics** pour
    afficher la carte de processus et les informations.

- ![](./media/image12.png)

  > **Remarque :** Cette étape peut prendre quelques minutes après
  > l'analyse.

### Tâche 6 : Mise en page Analytics

Cette section explique ce que vous pouvez faire sur l' **écran
Analytics**.

![](./media/image13.png)

![](./media/image14.png)

**Légende:**

1.  **Automatiser les activités** : pour rationaliser le processus
    d'automatisation, vous pouvez utiliser la **fonctionnalité
    Automatiser les activités**. Cette fonctionnalité détecte si
    l'utilisateur a effectué des actions à l'aide d'une application qui
    dispose d'actions Power Automate, telle que Microsoft Outlook ou
    Excel. Lors de la sélection **des activités Automatiser**, un
    brouillon de processus Power Automate contenant les actions
    pertinentes est généré. L'utilisateur peut ensuite modifier et
    personnaliser le processus de brouillon pour créer le processus
    automatisé final.

2.  **Légende** : informations supplémentaires sur le rapport, qui les
    aident à mieux comprendre les visualisations et les données
    présentées.

3.  **Processus** : informations détaillées sur le processus analysé, y
    compris la carte du processus, l'analyse temporelle de chaque
    variante et de chaque auteur d'enregistrement.

4.  **Application** : informations sur les applications utilisées dans
    les enregistrements. Il s'agit notamment des applications utilisées
    par les auteurs, de la fréquence à laquelle elles ont été utilisées
    et des transitions entre elles. Ce rapport explique quels
    connecteurs doivent être utilisés lors de la mise en œuvre de
    l'automatisation du processus et où utiliser potentiellement les
    flux de bureau, car il n'existe aucun connecteur.

### Tâche 7 : Relations entre les étapes du processus d'entreprise

Vous voyez les différentes étapes du processus d'entreprise et leurs
durées associées. Ces étapes comprennent :

- Télécharger la pièce jointe de la facture à partir de l'e-mail (48
  secondes)

- Ouvrir la liste des factures Excel (11,5 secondes)

- Ouvrir la facture à partir de OneDrive (21 secondes)

- Saisir les détails de la facture (53,6 secondes)

- Enregistrer et soumettre (9 secondes)

- Notifier l'équipe de la soumission (26.67 secondes)

&nbsp;

- ![](./media/image15.png)

### Tâche 8 : Afficher les données d'analyse

1.  Examinez les principales données d'analyse. Le temps moyen de
    traitement est de 1,47 minute sur cinq enregistrements.

- ![](./media/image16.png)

2.  Analysez d'autres tableaux de bord de mesures basées sur le temps.

- > **Activité par temps moyen en secondes** : Notez que **Saisir les
  > détails de la facture** et **Télécharger la facture** prennent le
  > plus de temps.

  ![](./media/image17.png)

  > **Enregistrement en temps moyen en min** : Remarquez que certaines
  > personnes (**Preston Morales** et **Shakti Menon**) prennent plus de
  > temps que d'autres.

  ![](./media/image18.png)

3.  Sélectionnez l' onglet **Application** pour voir les détails sur les
    applications utilisées.

- Le chargement des rapports peut prendre un certain temps.

  - En fournissant des informations sur les applications utilisées dans
    un processus d'entreprise, leur fréquence d'utilisation et le temps
    passé sur chaque application, ce rapport est crucial pour obtenir
    des informations sur le processus.

  - Par exemple, le tableau de bord montre qu'une application de
    facturation héritée, Outlook et Excel contribuent de manière
    significative au temps passé et aux actions des applications.

  - Prenez le temps de vous familiariser avec les différents rapports.

  ![](./media/image19.png)

4.  Revenez à la carte des processus en sélectionnant **Processus**.

5.  Regardez la fonction d'activités automatisées. À partir de la carte
    des processus, vous pouvez voir que la capacité d'exploration des
    processus a mis en évidence plusieurs activités comme candidates
    potentielles pour l'automatisation en fonction des applications.

6.  Commencez à créer un flux pour l'automatisation en sélectionnant
    **Automatiser les activités** en haut.

- ![](./media/image20.png)

  Un onglet s'ouvre dans le navigateur et affiche le concepteur de flux.
  Les actions recommandées qui correspondent aux activités de la carte
  de processus s'affichent automatiquement dans le panneau de droite.
  Par exemple, plusieurs connecteurs de messagerie vous sont suggérés
  afin d'automatiser l'activité Télécharger la **pièce jointe de la
  facture à partir de l'activité de messagerie**.

  ![](./media/image21.png)

### Conclusion:

Dans cet atelier, les participants ont utilisé les fonctionnalités
d'exploration de tâches de Power Automate pour analyser et optimiser le
processus d'exécution des commandes. En important une solution
prédéfinie avec des exemples d'enregistrements, ils ont exploré les
principales fonctionnalités de l'exploration de tâches, notamment
l'analyse des processus, l'identification des goulets d'étranglement et
la génération de recommandations d'automatisation. Les participants ont
appris à évaluer l'efficacité des processus grâce à des analyses
détaillées du temps passé dans diverses tâches et applications. Le
laboratoire a mis en évidence comment l'exploration de tâches peut
rationaliser les processus métier en identifiant les opportunités
d'automatisation, améliorant ainsi l'efficacité opérationnelle et
réduisant les charges de travail manuelles dans le processus d'exécution
des commandes.
