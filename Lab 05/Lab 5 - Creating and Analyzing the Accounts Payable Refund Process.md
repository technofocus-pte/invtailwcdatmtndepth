# **Laboratoire 5 - Création et analyse du processus de remboursement des comptes fournisseurs**

**Objectif :** L'objectif de ce laboratoire est de créer et d'analyser
un processus de remboursement des comptes fournisseurs à l'aide des
fonctionnalités de Power Automate Process Mining. Les participants
apprendront à importer des données à partir d'un fichier CSV, à créer un
nouveau processus et à utiliser l'application de bureau Process Mining
pour analyser les indicateurs clés de performance (KPI) et d'autres
mesures afin d'obtenir des informations sur l'efficacité et les
performances du processus de remboursement des comptes fournisseurs.

**Temps estimé :** 30 minutes

### Tâche 1 : Créer un processus

1.  Allez à +++**https://make.powerautomate.com/**+++. Si vous y êtes
    invité, connectez-vous avec vos informations d'identification de
    Office 365 tenant. Sélectionnez **États-Unis** comme pays/région,
    puis sélectionnez **Get started**.

- ![](./media/image1.png)

2.  Sélectionnez votre environnement – **Dev One**.

- ![](./media/image2.png)

3.  Dans le volet de navigation de gauche, sélectionnez **Plus** 🡪
    **Exploration de processus**.

- ![](./media/image3.png)

4.  Dans la **section Créer un processus**, sélectionnez **Start here**.

- ![](./media/image4.png)

5.  Dans l' **écran Créer un processus**, entrez un nom de processus :
    +++**Processmining**+++, puis sélectionnez **Importer des données**,
    **Data flow**, puis sélectionnez **Continuer**. (Facultatif) Entrez
    une description pour votre processus.

- ![](./media/image5.png)

6.  Si vous êtes invité à **choisir l'emplacement d'exportation**,
    sélectionnez **PowerBi intégré** dans la **liste déroulante**
    Choisir votre destination, puis sélectionnez **Continuer**.

- ![](./media/image6.png)

### Tâche 2 : Importer des données

1.  Dans l' écran **Choisir une source de données**, sélectionnez
    **Texte/CSV**.

- ![](./media/image7.png)

2.  Sous l' en-tête **Paramètres de connexion,** sélectionnez **Upload
    file (Preview)**.

- ![](./media/image8.png)

3.  Sélectionnez **Browse**.

- ![](./media/image9.png)

4.  Recherchez et sélectionnez
    **SampleData_AP_Refunds_Financial_EventLog.csv**. Emplacement :
    **C :Files**

5.  Sélectionnez **Open**.

- ![](./media/image10.png)

6.  Si vous êtes invité à vous authentifier, sélectionnez Se
    **connecter** et suivez les instructions. (Configurez le bloqueur de
    fenêtres contextuelles pour autoriser.)

- ![](./media/image11.png)

7.  Sélectionnez **Next**.

- ![](./media/image12.png)

8.  Prévisualisez les données du fichier et sélectionnez **Next**.

- ![](./media/image13.png)

9.  Lorsque vous voyez la requête puissante, qui vous permet de
    transformer vos données, sélectionnez **Next**.

- ![](./media/image14.png)

10. Faites correspondre le **nom de l'attribut** des exemples de données
    au **type d'attribut,** le cas échéant.

- ![](./media/image15.png)

11. Dans cet exemple, les attributs de données que vous allez modifier
    sont **InvoiceValue**, **Resource**, **StartTimestamp**,
    **EndTimestamp**, **CaseId** et **ActivityName**, comme suit.

- **InvoiceValue** – Financial per case (first event)

  **Ressource** – Ressources

  **StartTimestamp** – Event start

  **EndTimestamp** – Event End

  **CaseId** – Case ID

  **ActivityName** - Activity

  ![](./media/image16.png)

12. Lorsque vous avez **terminé**, le mappage d'attributs doit
    ressembler à la capture d'écran suivante.

- ![](./media/image17.png)

13. Sélectionnez **Save and analyze**. L'exécution de l'analyse peut
    prendre quelques minutes.

- ![](./media/image18.png)

14. Une fois le **processus d' analyse terminé**, vous verrez une carte
    de processus et un tableau de bord avec d'autres informations sur
    votre processus. Sur le tableau de bord, vous pouvez afficher de
    nombreuses mesures qui vous aideront à **analyser votre processus.**

- ![](./media/image19.png)

### Tâche 3 : Analyser un processus

Poussons l'analyse de notre processus au-delà des KPI. Nous utiliserons
l'application de bureau Power Automate Process Mining, qui vous permet
de modifier et d'analyser vos processus créés dans la fonctionnalité
d'exploration de processus.

1.  Dans la barre supérieure, cliquez sur le processus de téléchargement
    de l' **application Mining**.

- ![](./media/image20.png)

2.  Double-cliquez sur **le fichier d'installation de l'application
    PowerAutomateProcessMining** dans Téléchargements.

- ![](./media/image21.png)

3.  Cliquez sur **Install**.

- ![](./media/image22.png)

4.  Après avoir installé l'application Processmining, l'application est
    automatiquement lancée, si ce n'est pas le cas, veuillez lancer
    l'application manuellement. Après avoir lancé l'application,
    sélectionnez **l'anglais** comme langue et cliquez sur **Next
    step**.

- ![](./media/image23.png)

5.  Cochez toutes les **cases** comme indiqué dans l'image et cliquez
    sur **Next**.

- ![](./media/image24.png)

6.  Cliquez ensuite sur le bouton **Apply and mine**.

- ![](./media/image25.png)

7.  Sélectionnez ensuite le bouton **Use** , il naviguera vers la
    fenêtre de connexion.

- ![](./media/image26.png)

8.  Entrez votre ID de locataire administrateur et cliquez sur le bouton
    **Sign in** .

- ![](./media/image27.png)

9.  Entrez ensuite votre mot de passe de locataire administrateur et
    cliquez sur **Sign in**.

- ![](./media/image28.png)

10. Si une fenêtre contextuelle s'affiche indiquant ‘Stay signed in to
    all your apps’, sélectionnez **Non, connectez-vous à cette
    application uniquement**.

- ![](./media/image29.png)

11. Dans la barre d'outils de l'application Power Automate Process
    Mining, sélectionnez l'environnement **Dev** **One** en haut à
    droite.

- ![](./media/image30.png)

12. Recherchez le processus que vous avez créé avec la fonctionnalité
    d'exploration de processus dans Power Automate (**Processmining**).

13. Sélectionnez **default** pour afficher la vue par défaut. Vous êtes
    prêt à utiliser les fonctionnalités avancées de l'application de
    bureau Process Mining.

- ![](./media/image31.png)

  > Remarque : Si un message s'affiche lié à La taille du **modèle est
  > trop grande pour la configuration de votre PC** et que vous donnez
  > les options Oui et Non pour l'exécution, sélectionnez **Yes**.

  ![](./media/image32.png)

14. Dans la barre d'outils du panneau **Personnaliser**, sélectionnez
    **Fréquence** (première icône), puis Nombre **de cas** dans le
    **menu déroulant** Mesure.

- ![](./media/image33.png)

  > La carte de processus affiche le nombre de cas du processus qui
  > incluent l'activité spécifiée à chaque nœud.

15. Dans le panneau **Personnaliser**, sélectionnez Performances (icône
    d'horloge), puis sélectionnez **Durée moyenne** dans le menu
    déroulant.

- ![](./media/image34.png)

  > Notez que l' étape **de remboursement avec un bon d'achat spécial**
  > a une durée moyenne longue par rapport aux autres étapes.

  ![](./media/image35.png)

16. Dans le panneau **Personnaliser**, sélectionnez **Finance** (l'icône
    de la feuille de papier), puis sélectionnez **Moyenne** dans le
    **menu déroulant** Mesure.

- ![](./media/image36.png)

  > Notez que la même étape de **remboursement avec bon spécial**
  > n'implique que 631,11 $ de valeur de facture, ce qui représente
  > moins de la moitié de la plupart des autres étapes.

  ![](./media/image37.png)

17. Sélectionnez **Save**.

- ![](./media/image38.png)

### Conclusion:

Dans ce laboratoire, les participants ont créé et analysé un processus
de remboursement des comptes fournisseurs à l'aide des fonctionnalités
d'exploitation Power Automate Process Mining. En important des données
CSV, ils ont construit une carte de processus et un tableau de bord
détaillés, ce qui leur a permis d'examiner les indicateurs clés de
performance (KPI) et les mesures de processus. Grâce à l'application de
bureau Power Automate Process Mining, les participants ont effectué une
analyse plus approfondie, identifiant les inefficacités telles que les
longues durées et les faibles valeurs de facturation à des étapes
spécifiques. Ce laboratoire a démontré comment le Process Mining peut
aider les organisations à optimiser les flux de travail financiers, à
améliorer l'efficacité et à rationaliser les opérations des comptes
fournisseurs.
