# Laboratoire 11 - Développer un flux assisté qui lit les commandes et prompt les utilisateurs à sélectionner une remise

**Objectif :** L'objectif de cet atelier est de développer un **flux
Power Automate Desktop assisté** qui automatise le processus de lecture
des commandes à partir d'un fichier Excel et prompt les utilisateurs à
appliquer une remise en fonction de certaines conditions. Les
participants créeront un flux qui lit les données, vérifie si le montant
de la commande dépasse un seuil spécifique et invite l'utilisateur à
décider d'appliquer ou non une remise, avec la possibilité de saisir la
valeur de la remise. Le flux mettra ensuite à jour la feuille Excel avec
la remise appliquée.

**Temps estimé :** 25 minutes

### Tâche 1 : Créer le Power Automate desktop flow

1.  Ouvrez **Power Automate desktop** et connectez-vous avec **les
    informations d'identification de Office 365 tenant**.

2.  Choisissez l'environnement **Contoso** et cliquez sur + **New then
    Flow** et commencez à créer un flux.

- ![](./media/image1.png)

3.  Entrez +++**Message Box Communication**+++ comme nom de flux et
    vérifiez que l'activation de Power Fx (préversion) est désactivée.
    Cliquez ensuite sur le bouton **Create**.

- ![](./media/image2.png)

4.  Commencez par inviter l'utilisateur à sélectionner un fichier Excel.
    Ajoutez l'action +++ **Display select file dialog**+++ et configurez
    le champ Filtre de fichier pour n'autoriser que les fichiers xlsx.

- ![](./media/image3.png)

5.  Entrez le titre de la **boîte de dialogue** comme +++**Select
    Excel**+++, Entrez l'emplacement du dossier dans le **dossier
    initial** comme +++ C : Fichiers+++ Filtre comme **\*.xlsx** puis
    cliquez sur le bouton **Save**.

- ![](./media/image4.png)

6.  Avant de lire les données du fichier sélectionné, vous devez le
    lancer à l'aide de l' **action Lancer Excel**. Ajoutez **Lancer
    Excel** à partir de l'action. Configurez ensuite le paramètre
    suivant.

    - Lancez Excel : **ouvrez le document suivant**

    - Chemin d'accès au document : +++** %SelectedFile %**+++

    - Cliquez sur le bouton Enregistrer

- ![](./media/image5.png)

7.  Pour lire les données du fichier Excel, ajoutez l' action **Lire à
    partir de la feuille de calcul Excel** Entrez **%ExcelInstance %**
    dans l'instance Excel et sélectionnez **Toutes les valeurs
    disponibles de la feuille de calcul** dans le champ Récupérer.
    Cliquez sur le bouton **ESave.**

- ![](./media/image6.png)

8.  Ajoutez l' action **Obtenir la première colonne/ligne gratuite à
    partir de la feuille de calcul Excel** pour récupérer la première
    colonne et ligne libre dans la feuille de calcul Excel. Entrez
    **%ExcelInstance %** dans l'instance Excel, puis cliquez sur le
    bouton **Save**.

- ![](./media/image7.png)

9.  Ajoutez une variable définie à partir de l'action nommée
    **Compteur** et initialisez-la à **1,** puis cliquez sur
    enregistrer.

- ![](./media/image8.png)

10. Ajoutez **la boîte de dialogue** d'affichage de saisie à partir de
    l'action et configurez les champs suivants.

    - **Titre de la boîte de dialogue de saisie** : +++**Header**+++

    - **Message de la boîte de dialogue de saisie** : +++**Enter the
      Header**+++

    - **Valeur par défaut** : +++**Discount**+++

    - Cliquez sur le bouton **Save**.

- ![](./media/image9.png)

11. Ajoutez la **feuille de calcul Écrire dans Excel** à partir des
    actions et configurez-la avec les détails suivants :

    - **Instance Excel** : %ExcelInstance %

    - **Valeur à écrire** : +++** %UserInput %**+++

    - **Rôle d'écriture** : Sur une cellule spécifique

    - **Colonne** : +++**9**+++

    - **Ligne** : +++** %Counter%**+++

    - Cliquez sur le bouton **Save**.

- ![](./media/image10.png)

12. Ajoutez une **boucle For each** pour l'action permettant d'itérer
    dans les données récupérées et ajoutez la section
    +++** %ExcelData%**+++ dans la valeur à itérer. Cliquez ensuite sur
    enregistrer.

- ![](./media/image11.png)

13. Pour vérifier la valeur de la colonne **Brute** (colonne G ou
    sixième colonne de la feuille de calcul, dans la feuille le nom de
    la colonne est “6“), ajoutez l'action convertir **le texte en
    nombre**. Configurez le texte pour convertir en
    +++** %CurrentItem\[6\] %**+++, puis cliquez sur le bouton
    Enregistrer.

- ![](./media/image12.png)

14. Ajoutez une **action If** pour vérifier s'il dépasse 100 000 et
    configurez-le comme indiqué ci-dessous :

    - **Premier opérande** : +++** %TextAsNumber %**+++

    - **Opérateur** : supérieur ou égal à (\>=)

    - **Deuxième opérande** : +++**100000**+++

- ![](./media/image13.png)

15. Ajoutez l' action **Afficher le message** sous **Si**, pour fournir
    les informations nécessaires à l'utilisateur et l'inviter à choisir
    **Yes** ou **No**. Cliquez ensuite sur le bouton **Enregistrer**.
    Entrez les détails suivants dans le it :

    - **Titre de la boîte de message** : +++**Add discount**+++
    - **Message à afficher** :
      - +++Produit : %CurrentItem\[2\] %+++
      - +++Units : %CurrentItem\[3\] %+++
      - +++G**ross** : %TextAsNumber %+++
    - **Bouton de la boîte de message** : Oui – Non

- ![](./media/image14.png)

16. Ajoutez une deuxième action **If** sous Afficher l'action du message
    pour vérifier quel bouton a été enfoncé à l'étape précédente. Entrez
    les détails suivants dans les champs respectés :

- **Premier opérande** : +++ %ButtonPressed3 %+++

- **Opérateur :** Égal à (=)

- **Deuxième opérande :** +++Yes+++

 

- ![](./media/image15.png)

17. Sous la deuxième action Si ajouter **une boîte de dialogue d'entrée
    d'affichage**. Ajoutez le paramètre ci-dessous dans le champ et
    cliquez sur le bouton **Save**.

Titre de la boîte de dialogue de saisie : +++Discount value+++

Message de la boîte de dialogue de saisie : +++Enter the discount
value+++

![](./media/image16.png)

18. Ajoutez l**'action Écrire dans la feuille de calcul Excel** sous la
    deuxième action **IF** et entrez-y les détails suivants :

- **Instance Excel :** +++ %ExcelInstance %+++

- **Valeur pour l'auteur** : +++ %UserInput2 %+++

- **Mode d'écriture :** Sur cellule spécifique

- **Colonne :** +++9+++

- **Ligne :** +++ %Counter%+++

&nbsp;

- ![](./media/image17.png)

20. Sous Première **IF End,** ajoutez l'action **Augmenter la
    variable,** ajoutez le nom de la variable en tant que
    **%Counter %,** Augmentez de **1,** puis cliquez sur le bouton
    Enregistrer.

> ![](./media/image18.png)

21. À partir de la barre supérieure, **Save** le flux pour le test.

- ![](./media/image19.png)

# Tâche 2 : Tester le flux

1.  Cliquez sur le bouton **Run** pour exécuter le test.

> ![](./media/image20.png)

2.  Le premier dossier de feuille s'ouvrira, sélectionnez le **fichier
    Excel** à partir de celui-ci.

> ![](./media/image21.png)

3.  La fenêtre d'en-tête apparaîtra, lorsque nous définissons la
    **remise** par défaut, cliquez sur le bouton **OK**.

> ![](./media/image22.png)

4.  La fenêtre **Ajouter une remise** apparaît, qui indique que ce
    produit est supérieur à **100000**, sélectionnez **oui** ou **non**.
    Dans ce test, nous sélectionnons **oui** (**oui**, nous accordons
    une réduction sur ce produit.)

> ![](./media/image23.png)

5.  Entrez ensuite la valeur de la **remise** Pour le test, nous entrons
    **10000,** puis cliquez sur **OK**.

> ![](./media/image24.png)

6.  Dans la feuille, la valeur de la remise est mise à jour.

![](./media/image25.png)

7.  La boucle tourne **en continu** pour tous les produits.

### Conclusion:

Dans ce laboratoire, les participants ont développé un Power Automate
Desktop flow assisté qui lit les données de commande à partir d'un
fichier Excel, vérifie si le montant de la commande dépasse un seuil
défini et prompt l'utilisateur à appliquer une remise. Le flux
automatise efficacement le processus de prise de décision en permettant
aux utilisateurs d'interagir avec le flux par le biais de prompts et de
saisir des valeurs de remise. Cet atelier fournit une expérience
pratique de l'automatisation des tâches impliquant Excel, les entrées
utilisateur et la logique conditionnelle, permettant aux participants de
rationaliser des processus métier similaires à l'aide de Power Automate
Desktop.
