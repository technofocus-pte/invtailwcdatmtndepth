# Laboratoire 2 - Création de l’ Inventory Management App

**Objectif :** L'objectif de ce laboratoirer est de guider les
participants dans la création d'une application fonctionnelle de gestion
d'inventaire à l'aide de Microsoft Power Apps et de Copilot. Les
participants apprendront à configurer leur environnement Dataverse, à
concevoir des écrans d'applications, à gérer des données et à
automatiser les flux de travail de réapprovisionnement des stocks avec
Power Automate.

**Temps estimé :** 40 min

## Exercice 1 : Créer un Inventory Management App

### Tâche 1 : Vérification de votre environnement Dataverse

1.  Ouvrez un navigateur et accédez à
    +++**https://admin.powerplatform.microsoft.com+++.** Connectez-vous
    avec votre compte office 365 admin.

2.  Sélectionnez **Environnements** dans le volet de navigation de
    gauche. L' **environnement de développement** doit avoir été créé
    pour vous, comme illustré dans l'image ci-dessous. (Cet
    environnement est créé automatiquement dès que vous fournissez la
    licence Microsoft Power App pour développeur à l'aide de vos comptes
    administrateurs. Le nom de l'environnement sera différent pour
    chaque compte administrateur.)

- ![](./media/image1.png)

3.  Utilisez le même environnement de développement pour exécuter tous
    les exercices de cet atelier.

> **Remarque** : L**'environnement de développement Dev One** est
> utilisé dans cet atelier. Le nom de l'environnement peut être
> différent pour différents utilisateurs. Veillez à sélectionner votre
> environnement de développement.

### Tâche 2 : Créer un inventory management app à l'aide de Copilot.

1.  Ouvrez un navigateur et accédez à la connexion
    +++**https://make.powerapps.com**+++ avec un compte de 365 admin
    tenant.

2.  Cliquez sur l'environnement dans le coin supérieur droit et
    sélectionnez **votre environnement de développement** (Dev one est
    un environnement de développement utilisé dans ce guide de
    laboratoire)

- ![](./media/image2.png)

3.  Entrez l'invite ci-dessous et cliquez sur le bouton **Enter** .

- +++**build a candy inventory management app**+++

  ![](./media/image3.png)

4.  Sélectionnez la vignette **Démarrer avec le copilote**

- ![](./media/image4.png)

5.  Entrez l'invite ci-dessous et cliquez sur **Générer** pour créer un
    tableau à l'aide de Copilot

- +++**Candy Inventory management**+++

  ![](./media/image5.png)

6.  Copilot génère les tables comme indiqué dans l'image ci-dessous.

- ![](./media/image6.png)

7.  Cliquez sur trois points à côté de Candy, puis cliquez sur
    **Afficher les données.**

- ![](./media/image7.png)

8.  Les données de la table Candy doivent contenir des données comme
    indiqué dans l'image ci-dessous.

- ![](./media/image8.png)

9.  Cliquez sur **Supplier –\> View data** et explorez les données, puis
    fermez la fenêtre d'affichage.

- ![](./media/image9.png)

10. Mettez à jour l'un des identifiants de messagerie du fournisseur
    avec votre identifiant de messagerie professionnel/personnel

- ![](./media/image10.png)

11. Cliquez sur **Commander –\> Afficher les données**

- ![](./media/image11.png)

12. Cliquez ci-dessous dans la zone de texte et cliquez sur Entrée.
    Cette colonne est nécessaire pour notifier lorsque la quantité est
    passée en dessous du point de réapprovisionnement.

- +++**Add reorder point column to Candy table**+++

  ![](./media/image12.png)

13. Ajoutez la colonne candyInStock avec le type Number. Si la quantité
    est inférieure aux points de réapprovisionnement, la colonne
    Quantité automatisera l'ajout avec candyInStock.

- +++**Add** candyInStock\*\* column to Candy table with sample stock
  count\*\*+++

  ![](./media/image13.png)

14. Le tableau a été mis à jour avec la colonne point de
    réapprovisionnement et la colonne Bonbons en stock

- ![](./media/image14.png)

15. Cliquez sur le bouton **Save and open app**

- ![](./media/image15.png)

16. Vous **avez fini de travailler ?** , cliquez sur **Save and open
    app** **l'application** et attendez que l'application soit créée.

- ![](./media/image16.png)

  ![](./media/image17.png)

17. Ignorez la fenêtre d'accueil.

- ![](./media/image18.png)

18. L'application est créée et doit ressembler à l'image ci-dessous.

- ![](./media/image19.png)

19. Cliquez sur le bouton **Save** et entrez le nom de **MSCandy
    Inventory management app**, puis cliquez sur le bouton **Save**.

- ![](./media/image20.png)

  ![](./media/image21.png)

20. Explorez l'application. Cliquez sur **l'écran Candy** dans
    l'arborescence. Vous pouvez mettre à jour l'étiquette de l'écran
    pour la gestion de l'inventaire de **bonbons**

- ![](./media/image22.png)

21. Explorez l'écran Fournisseur et mettez-le à jour selon vos besoins.

- ![](./media/image23.png)

### Tâche 3 : Créer un écran de qualité bonbon

1.  Cliquez sur **Nouvel écran** et sélectionnez Template **vierge** .

- ![](./media/image24.png)

2.  Sélectionnez le nouvel écran et faites un clic droit sur
    **Renommer**

- ![](./media/image25.png)

4.  Nommez l'écran comme +++**Candy quality screen**+++

- ![](./media/image26.png)

3.  Cliquez sur la zone Écran et sélectionnez **Créer une nouvelle table
    (aperçu)**

- ![](./media/image27.png)

4.  Cliquez sur **Nouvelle table –\> Ajouter des colonnes et des
    données.**

- ![](./media/image28.png)

5.  Cliquez sur **Nouvelle colonne -\> Modifier la colonne.**

- ![](./media/image29.png)

6.  Entrez le nom d'affichage comme **Candy ID**, puis cliquez sur le
    bouton **Update**.

- ![](./media/image30.png)

7.  Cliquez sur la colonne Nouveau et entrez les détails ci-dessous,
    puis cliquez sur **Enregis**.

    - **Nom d'affichage :** Nom du bonbon

    - **Type de données :** Choix

    - **Obligatoire :** Oui.

    - **Choix :** ajoutez les choix ci-dessous

      - Barre chocolatée

      - Oursons en gélatine

      - Bonbons

      - Sucette

      - Sour Patch Enfants

- ![](./media/image31.png)

8.  Cliquez sur Nouvelle colonne et ajoutez une colonne avec les détails
    ci-dessous, puis cliquez sur **Save**.

    - **Nom d'affichage :** Qualité des bonbons
    - **Type de données :** Choix
    - **Obligatoire :** Oui
    - **Choix :** étiquettes
      - Défectueux
      - Non défectueux

- ![](./media/image32.png)

> **Remarque :** Vous pouvez ajouter d'autres colonnes en fonction des
> besoins de votre application.

10. Modifiez le nom de la table et mettez-le à jour avec +++**Candy
    Quality check**+++. ![](./media/image33.png)

11. Cliquez sur **Enregistrer et quitter -\> Enregistrer et quitter**.
    ![](./media/image34.png)

12. Vous reviendrez à la page de l'application Power Apps. Sélectionnez
    l'écran nouvellement ajouté et cliquez sur Insérer et sélectionnez
    **Modifier le formulaire** comme indiqué dans l'image ci-dessous.
    ![](./media/image35.png)

13. Cliquez sur le conteneur et sélectionnez la table de source de
    données comme +++ **Candy Qualities
    table**+++.![](./media/image36.png)

14. Vous devriez voir le formulaire comme ci-dessous l'image.
    ![](./media/image37.png)

15. Ajustez le tableau au milieu de la page. Cliquez sur **Insérer-\>
    l'étiquette de texte.** ![](./media/image38.png)

16. Ajustez l'étiquette du texte et entrez le texte comme suit :
    +++**Candy Quality check+++** et mettez à jour les styles du texte.
    ![](./media/image39.png)

17. Sélectionnez le **formulaire**. Cliquez sur **Insérer** et
    sélectionnez **Boutton**. ![](./media/image40.png)

18. Faites glisser le bouton d'envoi et placez-le au milieu du
    conteneur. Sélectionnez le bouton et remplacez le texte des
    propriétés par **Submit**, comme illustré dans l'image ci-dessous.
    ![](./media/image41.png)

19. Sélectionnez le bouton **Submit**, puis sélectionnez **la fonction
    OnSelect,** puis entrez la fonction ci-dessous.

> **Remarque :** Form4 dans la formule doit être remplacé par le nom de
> votre formulaire SubmitForm(Form4) ; NewForm(Formulaire4).

![](./media/image42.png)

20. Sélectionnez le conteneur, sous Propriétés, sélectionnez **Mode par
    défaut** sur **Nouveau**. ![](./media/image43.png)

21. Cliquez sur **Save**, puis sur le bouton **Preview app** comme
    indiqué dans l'image ci-dessous. ![](./media/image44.png)

22. Entrez les détails de Candy, puis cliquez sur le bouton Soumettre.
    ![](./media/image45.png)

23. Revenez à votre table de qualité Candy dans l'environnement
    Dataverse et vous devriez voir l'enregistrement ajouté ci-dessus.
    ![](./media/image46.png)

24. Fermez la fenêtre d'aperçu.

## Exercice 2 : Création d'un flux Power Automate pour réapprovisionner le stock.

### Tâche 1 : Créer un Power Automate flow pour déclencher l'e-mail de réapprovisionnement

1.  Revenez à l'onglet Power Automate et cliquez sur **My flows** -\>
    **New flow -cloud flow.** ![](./media/image47.png)

2.  Entrez le nom du flux comme suit : +++**Candy Restock Flow**+++.
    Recherchez +++ **When a row**+++ est et sélectionnez l' **action
    Lorsqu'une ligne est ajoutée ou modifiée** de Dataverse , puis
    cliquez sur **Create**. ![](./media/image48.png)

3.  Sélectionnez l'action et définissez les paramètres ci-dessous.

    - Changer de type ; Ajouté ou modifié
    - Table Nam : Bonbons
    - Portée : Organisation ![](./media/image49.png)

4.  Ajouter une action après une action **“ lors de l'ajout, de la
    modification ou de la suppression d'une ligne “.**
    ![](./media/image50.png)

5.  Recherchez **Condition** et sélectionnez **l'action Condition du
    contrôle** . ![](./media/image51.png)

6.  Cliquez sur Choisir la valeur et sélectionnez choisir dans l'action
    dynamique de l'étape précédente. ![](./media/image52.png)

7.  Recherchez la colonne +++**Quantity**+++ et sélectionnez-la.
    ![](./media/image53.png)

8.  Sélectionnez une condition **inférieure à** et cliquez sur Saisir
    les données de l'action précédente. ![](./media/image54.png)

9.  Recherchez la colonne +++**Reorder points**+++ et sélectionnez-la.
    ![](./media/image55.png)

10. **Ajoutez une action** sous **la condition**
    Vrai.![](./media/image56.png)

11. Sélectionnez l'action +++**Approvals**+++. ![](./media/image57.png)

12. Sélectionnez +++**Start and wait for an Approvals**+++.
    ![](./media/image58.png)

13. Sélectionnez le type d'approbation comme suit : +++**Approve/Reject
    – First to Respond** +++. Entrez le titre comme : +++ **Approve to
    Restock** +++ - et cliquez sur le bouton Dynamique pour sélectionner
    les données de l'étape précédente. ![](./media/image59.png)

14. Recherchez **Candy Name+++ et sélectionnez-le.**
    ![](./media/image60.png)

15. Entrez les détails ci-dessous.

- Attribué à : Votre adresse e-mail professionnelle.

      Détails :Salut

       Monsieur, 

      est en rupture de stock - pour que les clients puissent passer une commande. Veuillez approuver le
      réapprovisionnement.  

      Merci

> **Remarque :** Vous pouvez personnaliser la section des détails selon
> vos besoins.

![](./media/image61.png)

16. **Ajoutez une action** après **l'action d'approbation** .
    ![](./media/image62.png)

17. Recherchez +++**condition**+++ et sélectionnez **Contrôle –
    Condition**. ![](./media/image63.png)

18. Cliquez sur Choisir une valeur et sélectionnez **Résultat** dans
    Démarrer et attendez une action d'approbation.
    ![](./media/image64.png)

19. Sélectionnez la condition égale **à** et entrez la valeur
    **Approuver**. ![](./media/image65.png)

20. Sous **Condition Vrai** , **ajoutez une action**.
    ![](./media/image66.png)

21. Recherchez **Mettre à jour la ligne** et sélectionnez-la dans la
    section **Microsoft Dataverse**. ![](./media/image67.png)

22. Sélectionnez votre **table Candy** et cliquez sur **Row Id** pour
    sélectionner l'action dynamique. ![](./media/image68.png)

23. Recherchez une colonne d'identificateur unique dans votre table et
    sélectionnez-la. ![](./media/image69.png)

24. Cliquez sur le menu déroulant Paramètres avancés et sélectionnez
    **la colonne Quantité**. ![](./media/image70.png)

25. Entrez la fonction ci-dessous (que vous tapez dans votre
    application) et réduisez l'action.

- > **Remarque :** La fonction ci-dessous ne fonctionne pas pour vous,
  > car le nom de votre schéma de colonne peut être différent. Accédez à
  > la colonne de table -\> et copiez le nom du schéma.

  +++add(triggerBody() ?\[' cr8a3_Quantity'\],triggerBody() ?
  \['cr8a3_CandyInStock'\])+++

  ![](./media/image71.png)

26. Cliquez sur le bouton **the save** pour enregistrer le flux Power
    Automate. ![](./media/image72.png)

### Tâche 2 : Tester le flow de réapprovisionnement

1.  Revenez à l' onglet **PowerApps** et cliquez sur l'écran Candy dans
    l'arborescence de gauche et sélectionnez **Play**.

- > **Remarque :** Vous pouvez mettre à jour le titre de l'écran

  ![](./media/image73.png)

2.  Sélectionnez le bonbon et cliquez sur **Edit**.
    ![](./media/image74.png)

3.  Entrez la **valeur** Quantité **inférieure aux points de
    réapprovisionnement** et **validez** les modifications.
    ![](./media/image75.png)

4.  Revenez à l'onglet Power Automate flow et cliquez sur Mes flux \>
    Votre flux. ![](./media/image76.png)

5.  Le débit est en cours d'exécution et est à l'état.
    ![](./media/image77.png)

6.  Ouvrez un nouvel onglet et accédez à +++**https://outlook.com**+++
    et connectez-vous avec votre compte d'administrateur Office 365.
    Vous devriez avoir reçu un e-mail pour vous réapprovisionner.
    **Approve** et **Submit**. ![](./media/image78.png)

- ![](./media/image79.png)

7.  Le flux est maintenant couronné de succès. ![](./media/image80.png)

- ![](./media/image81.png)

8.  Revenez à PowerApps et vérifiez la quantité de produit ci-dessus. Il
    aurait dû être mis à jour (Bonbons en stock + Quantité lorsque c'est
    moins que le point de réapprovisionnement) ![](./media/image82.png)

### Conclusion:

À la fin de cet atelier, les participants seront en mesure de vérifier
leur environnement Dataverse, de créer une application de gestion des
stocks à l'aide de Copilot, de concevoir un écran de contrôle de la
qualité Candy avec des champs personnalisés et d'implémenter des Power
Automate flow pour déclencher des demandes de réapprovisionnement en
fonction des niveaux de stock. De plus, ils acquerront des compétences
dans le test et la validation des flux de travail automatisés afin
d'assurer des mises à jour précises des stocks après les processus
d'approbation. Cette approche structurée permettra aux participants
d'exploiter efficacement les capacités de Power Apps et de Power
Automate, améliorant ainsi leurs compétences en matière de développement
d'applications et d'automatisation des processus.
