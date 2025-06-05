# Laboratoire 3 - Création d'un Automated Flow pour informer le gestionnaire lorsqu'un nouvel élément est créé dans Dynamics 365 Business Central

**Objectif :** Dans ce laboratoire, les participants vont apprendre à
créer un automated flow dans Power Automate qui envoie une notification
par e-mail chaque fois qu'un nouvel élément est créé dans Microsoft
Dynamics 365 Business Central. En suivant un processus structuré, les
participants se familiariseront avec le déclenchement de flux basés sur
les données Business Central, la collecte d'informations pertinentes sur
les éléments, l'application d'une logique conditionnelle et l'exécution
d'actions pour envoyer des alertes par e-mail. Cette expérience pratique
permettra aux participants d'exploiter Power Automate pour améliorer les
processus métier et les notifications.

**Temps estimé :** 15 minutes

### Tâche 1 : S'inscrire à Microsoft Dynamic 365 Business Central

1.  Naviguez jusqu'à
    +++**https://www.microsoft.com/en-us/dynamics-365/products/business-central**+++
    et cliquez sur **Essayer** **gratuitement.**

- ![](./media/image1.png)

2.  Entrez votre Office 365 tenant ID et cliquez sur **Next**.

- ![](./media/image2.png)

3.  Cliquez ensuite sur Se **connecter** et entrez les informations
    d'identification.

- ![](./media/image3.png)

4.  Sélectionnez **États-Unis** comme pays ou région, entrez votre
    **numéro de téléphone**, puis sélectionnez **Commencer**.

- ![](./media/image4.png)

5.  Cliquez ensuite sur **Get started** pour accéder à Business Central.

- ![](./media/image5.png)

6.  Sélectionnez le bouton **Skip Survey** pour continuer.

- ![](./media/image6.png)

7.  Vous serez redirigé vers la page d'accueil de Dynamics 365 Business
    Central.

- ![](./media/image7.png)

### Tâche 2 : Démarrer Power Automate

1.  Ouvrez un nouvel onglet à côté de Dynamic 365 Business Central et
    accédez à +++**https://make.powerautomate.com**/+++ dans votre
    navigateur.

- ![](./media/image8.png)

2.  Si vous y êtes invité, entrez **Microsoft 365 tenant id** dans le
    champ respecté et cliquez sur le bouton **Next**.

- ![](./media/image9.png)

3.  Entrez le **mot de passe** dans le champ respecté et cliquez sur
    **Sign in.**

- ![](./media/image10.png)

4.  Dans la barre de navigation supérieure, sélectionnez l'environnement
    **Dev One.**

- ![](./media/image11.png)

5.  Cliquez sur **+Create** dans le menu de gauche.

- ![](./media/image12.png)

6.  Sélectionnez la vignette **Automated cloud flow**.

- ![](./media/image13.png)

### Tâche 3 : Créer le déclencheur basé sur les données Business Central

1.  Dans la zone **Nom du flux**, entrez +++**Email notification for new
    furniture**+++.

- ![](./media/image14.png)

2.  Dans **Choisir la barre de recherche du déclencheur de votre flux**,
    entrez **Business Central**. Faites défiler l'écran vers le bas pour
    afficher les déclencheurs et sélectionnez le déclencheur **Lors de
    la création d'un enregistrement (V3).**

3.  Cliquez sur **Create** .

- ![](./media/image15.png)

4.  Remplissez les détails du déclencheur :

    1.  **Nom de l'environnement** : Entrez +++**PRODUCTION**+++.

    2.  **Nom de l'entreprise** : Sélectionnez **CRONUS USA, Inc.** dans
        la liste.

    3.  **Nom de la table** : sélectionnez **items**.

- ![](./media/image16.png)

### Tâche 4 : Collecter des données à partir de Business Central

1.  Cliquez sur **+ button** ajouter, puis sélectionnez **Add an
    action**.

- ![](./media/image17.png)

2.  Dans la fenêtre **Ajouter une action**, tapez +++**Dynamics 365
    Business Central**+++ dans la zone de recherche et choisissez
    l'action Obtenir l'**enregistrement (V3).**

- ![](./media/image18.png)

3.  Entrez les informations suivantes :

    1.  **Environnement** : +++**PRODUCTION**+++.

    2.  **Nom de l'entreprise** : Sélectionnez **CRONUS USA, Inc.**.

    3.  **Nom de la table** : sélectionnez **Items**.

    4.  **Row id** : sélectionnez le jeton **Row id** dans Contenu
        dynamique.

- ![](./media/image19.png)

### Tâche 5 : Fabriquer la condition

1.  Cliquez sur le **bouton +** sous Obtenir l'enregistrement et
    sélectionnez **Ajouter une action**.

- ![](./media/image20.png)

2.  Dans la **barre de recherche** Ajouter une action, entrez
    **Contrôle**. Sélectionnez l' **action Condition**.

- ![](./media/image21.png)

3.  Définissez la condition :

    1.  Dans la première zone **Choisir une valeur**, sélectionnez le
        jeton Code de catégorie d'article dans Contenu dynamique.

    2.  Gardez l' **option est égale à**.

    3.  Dans la deuxième zone **Choisir une valeur**, entrez +++
        **FURNITURE**+++.

- ![](./media/image22.png)

### Tâche 6 : Créer une action basée sur la condition

1.  Dans la **fenêtre Si oui ou Vrai**, cliquez sur **Ajouter une
    action**.

- ![](./media/image23.png)

2.  Recherchez +++**office 365 outlook**+++ dans la fenêtre Ajouter une
    action et cliquez sur voir plus. Dans le déclencheur Office 365
    Outlook, sélectionnez **Envoyer un e-mail (V2).**

- ![](./media/image24.png)

  ![](./media/image25.png)

3.  Remplissez les détails de l'e-mail :

    1.  **À** : Entrez « Admin » et sélectionnez **Mod Admin dans** la
        suggestion, c'est-à-dire l'ID de messagerie du locataire Office
        365 que vous utilisez dans cet atelier.

    2.  **Objet** : Entrez +++**New furniture released**+++.

    3.  **Body** :

        1.  Ajouter le texte **Nouveaux meubles**.

        2.  Ajoutez le numéro de jeton à partir du contenu dynamique.

        3.  Ajoutez le jeton **displayName** à partir du contenu
            dynamique.

        4.  Ajouter le texte +++**has just released.**+++

- ![](./media/image26.png)

4.  Cliquez sur **Save** pour finaliser votre flux.

- ![](./media/image27.png)

### Tâche 7 : Tester le flux

1.  Dans la barre supérieure, cliquez sur le bouton **Test.**

- ![](./media/image28.png)

2.  Sélectionnez le **processus manuel**, puis cliquez sur **Test**.

- ![](./media/image29.png)

3.  Revenez au **site Web de Business Central** et, à partir de la barre
    supérieure, accédez à **Ventes** 🡪 **Articles**.

- ![](./media/image30.png)

4.  Cliquez sur le **bouton + Nouveau**

- ![](./media/image31.png)

5.  Sélectionnez **ÉLÉMENT**, puis cliquez sur **OK**.

- ![](./media/image32.png)

6.  Dans le champ Code de catégorie d'article, sélectionnez
    **FURNITURE** et dans le champ Description, écrivez **Chaise de
    bureau.**

- ![](./media/image33.png)

7.  Cliquez sur le bouton **Save**.

- ![](./media/image34.png)

8.  Sur le portail Power Automate, cliquez sur **Lanceur
    d'applications** situé dans le coin supérieur gauche. Sélectionnez
    **Outlook,** puis vous pouvez voir que la réponse automatique est
    reçue sur l'e-mail fourni par l'administrateur MOD.

- ![](./media/image35.png)

### Conclusion:

À la fin de ce laboratoire, les participants auront réussi à créer un
flux de notification par e-mail automatisé dans Power Automate pour les
nouveaux éléments dans Business Central. Ils auront acquis une
expérience pratique dans la mise en place de déclencheurs, d'actions et
de conditions, qui sont des compétences essentielles pour
l'automatisation des flux de travail. Les participants comprendront
également comment collecter et manipuler efficacement les données de
Business Central, ce qui leur permettra de rationaliser les
communications et d'améliorer la productivité dans leurs organisations
respectives. Ces connaissances serviront de base à l'exploration plus
approfondie des capacités de Power Automate dans l'automatisation de
divers processus métier.
