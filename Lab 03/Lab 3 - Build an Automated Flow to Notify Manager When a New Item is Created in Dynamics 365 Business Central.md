# Lab 3 - Erstellen eines automatisierten Flows, um den Manager zu benachrichtigen, wenn ein neues Element in Dynamics 365 Business Central erstellt wird

**Ziel:** In diesem Lab lernen die Teilnehmer, wie sie einen
automatisierten Flow in Power Automate erstellen, der eine
E-Mail-Benachrichtigung sendet, wenn ein neues Element in Microsoft
Dynamics 365 Business Central erstellt wird. Durch das Befolgen eines
strukturierten Prozesses werden die Teilnehmer mit dem Auslösen von
Flows auf der Grundlage von Business Central-Daten, dem Sammeln
relevanter Artikelinformationen, dem Anwenden bedingter Logik und dem
Ausführen von Aktionen zum Senden von E-Mail-Benachrichtigungen vertraut
gemacht. Diese praktische Erfahrung wird die Teilnehmer in die Lage
versetzen, Power Automate zur Verbesserung von Geschäftsprozessen und
Benachrichtigungen zu nutzen.

**Geschätzte Zeit:** 15 Minuten

### Aufgabe 1: Registrieren Sie sich in Microsoft Dynamic 365 Business Central

1.  Navigieren Sie zu
    +++**https://www.microsoft.com/en-us/dynamics-365/products/business-central**+++
    und klicken Sie auf **Try for Free.**

- ![](./media/image1.png)

2.  Geben Sie Ihre Office 365-Tenant-ID ein, und klicken Sie auf
    **Next**.

- ![](./media/image2.png)

3.  Klicken Sie dann auf **Sign in** und geben Sie die
    Anmeldeinformationen ein.

- ![](./media/image3.png)

4.  Wählen Sie **United States** als Land oder Region aus, geben Sie
    Ihre **Telefonnummer** ein, und wählen Sie dann **Get started** aus.

- ![](./media/image4.png)

5.  Klicken Sie dann auf **Get Started** , um auf Business Central
    zuzugreifen.

- ![](./media/image5.png)

6.  Wählen Sie die Schaltfläche **Skip Survey** aus, um fortzufahren.

- ![](./media/image6.png)

7.  Sie werden zur Startseite von Dynamics 365 Business Central
    weitergeleitet.

- ![](./media/image7.png)

### Aufgabe 2: Starten von Power Automate

1.  Öffnen Sie einen neuen Tab neben Dynamic 365 Business Central und
    navigieren Sie in Ihrem Browser zu
    +++**https://make.powerautomate.com/**++.

- ![](./media/image8.png)

2.  Wenn Sie dazu aufgefordert werden, geben Sie die **Microsoft
    365-Tenant-ID** in das entsprechende Feld ein, und klicken Sie auf
    die Schaltfläche **Next**.

- ![](./media/image9.png)

3.  Geben Sie das **Passwort** in das entsprechende Feld ein und klicken
    Sie auf **Sign in.**

- ![](./media/image10.png)

4.  Wählen Sie in der oberen Navigationsleiste die Umgebung **Dev One**
    aus.

- ![](./media/image11.png)

5.  Klicken Sie im linken Menü auf **+Create**.

- ![](./media/image12.png)

6.  Wählen Sie die Kachel **Automated cloud flow** aus.

- ![](./media/image13.png)

### Aufgabe 3: Erstellen des Auslösers auf der Grundlage von Business Central-Daten

1.  Geben Sie im Feld **Flow-Name** +++ **Email notification for new
    furniture** +++ ein.

- ![](./media/image14.png)

2.  Geben Sie in **Choose your flow’s trigger search bar** “**Business
    Central**” ein. Scrollen Sie nach unten, um die Auslöser anzuzeigen,
    und wählen Sie den Auslöser **When a record is created (V3)** aus.

3.  Klicken Sie auf **Create**.

- ![](./media/image15.png)

4.  Geben Sie die Details des Auslösers ein:

    1.  **Umgebungsname**: Geben Sie +++**PRODUCTION**+++ ein.

    2.  **Firmenname**: Wählen Sie **CRONUS USA, Inc.** aus der Liste.

    3.  **Tabellenname**: Wählen Sie **Items** aus.

- ![](./media/image16.png)

### Aufgabe 4: Erfassen von Daten aus Business Central

1.  Klicken Sie auf **die Schaltfläche +** **Add** und wählen Sie **Add
    an action** aus.

- ![](./media/image17.png)

2.  Geben Sie im Fenster **Add an action** +++**Dynamics 365 Business
    Central**+++ in das Suchfeld ein und wählen Sie die Aktion **Get
    record (V3)** aus.

- ![](./media/image18.png)

3.  Geben Sie die folgenden Informationen ein:

    1.  **Umgebung**: +++PRODUKTION+++.

    2.  **Firmenname**: Wählen Sie **CRONUS USA, Inc.**. aus

    3.  **Tabellenname**: Wählen Sie **Items** aus.

    4.  **Zeilen-ID**: Wählen Sie das **Row-ID**-Token aus dem
        dynamischen Inhalt aus.

- ![](./media/image19.png)

### Aufgabe 5: Machen Sie die Bedingung

1.  Klicken Sie auf die **Schaltfläche +** unter “Get record”und wählen
    Sie **Add an action** aus.

- ![](./media/image20.png)

2.  Geben Sie in der Suchleiste **Add an action** “**Control**”ein.
    Wählen Sie die Aktion **Condition** aus.

- ![](./media/image21.png)

3.  Legen Sie die Bedingung fest:

    1.  Wählen Sie im ersten Feld **Choose a value** das Token **Item
        Category Code** aus Dynamischer Inhalt aus.

    2.  Behalten Sie die Option **is equal to**.

    3.  Geben Sie im zweiten Feld **Choose a value** +++**FURNITURE**+++
        ein.

- ![](./media/image22.png)

### Aufgabe 6: Erstellen einer Aktion basierend auf der Bedingung

1.  Klicken Sie im Fenster **" If yes or True "**-Bedingung auf **" Add
    an action ".**

- ![](./media/image23.png)

2.  Suchen Sie im Fenster “Add an action”nach +++**office 365
    outlook**+++ und klicken Sie auf “See more”. Wählen Sie im Office
    365 Outlook-Trigger die Option **Send an Email (V2)** aus.

- ![](./media/image24.png)

  ![](./media/image25.png)

3.  Geben Sie die E-Mail-Details ein:

    1.  **An:** Geben Sie "Admin" ein, und wählen Sie **Mod Admin** aus
        dem Vorschlag aus, d. h. die E-Mail-ID des Office 365-Tenants,
        die Sie in diesem Lab verwenden.

    2.  **Betreff**: Geben Sie +++ **New furniture released** +++ ein.

    3.  **Körper**:

        1.  Fügen Sie den Text **New** **furniture** hinzu.

        2.  Fügen Sie die Token-**Number** aus dem dynamischen Inhalt
            hinzu.

        3.  Fügen Sie das Token **displayName** aus dynamischem Inhalt
            hinzu.

        4.  Fügen Sie den Text +++ **has just released.**+++

- ![](./media/image26.png)

4.  Klicken Sie auf **Save** , um Ihren Flow abzuschließen.

- ![](./media/image27.png)

### Aufgabe 7: Testen des Flows

1.  Klicken Sie in der oberen Leiste auf die Schaltfläche **Test**.

- ![](./media/image28.png)

2.  Wählen Sie den **Manual** Prozess aus und klicken Sie dann auf
    **Test**.

- ![](./media/image29.png)

3.  Navigieren Sie zurück zur **Business Central-Website** und gehen Sie
    in der oberen Leiste zu **Sales** 🡪 **Items**.

- ![](./media/image30.png)

4.  Klicken Sie auf die **Schaltfläche + New**

- ![](./media/image31.png)

5.  Wählen Sie **ITEM** aus, und klicken Sie dann auf **OK**.

- ![](./media/image32.png)

6.  Wählen Sie im Feld Artikelkategoriecode die Option **FURNITURE**
    aus, und schreiben Sie in das Feld Description **Office Chair.**

- ![](./media/image33.png)

7.  Klicken Sie auf die Schaltfläche **Save**.

- ![](./media/image34.png)

8.  Klicken Sie im Power Automate-Portal auf **App-Launcher** in der
    oberen linken Ecke. Wählen Sie **Outlook** aus, und dann können Sie
    sehen, dass die automatische Antwort in der vom MOD-Administrator
    bereitgestellten **E-Mail** empfangen wird.

- ![](./media/image35.png)

### Schlussfolgerung:

Am Ende dieses Labs haben die Teilnehmer erfolgreich einen
automatisierten E-Mail-Benachrichtigungsflow in Power Automate für neue
Elemente in Business Central erstellt. Sie haben praktische Erfahrungen
im Einrichten von Triggers, Aktionen und Bedingungen gesammelt, die für
die Automatisierung von Workflows unerlässlich sind. Die Teilnehmer
werden auch verstehen, wie sie Daten aus Business Central effektiv
sammeln und bearbeiten können, um die Kommunikation zu rationalisieren
und die Produktivität in ihren jeweiligen Organisationen zu steigern.
Dieses Wissen wird als Grundlage für die weitere Erforschung der Power
Automate-Funktionen bei der Automatisierung verschiedener
Geschäftsprozesse dienen.
