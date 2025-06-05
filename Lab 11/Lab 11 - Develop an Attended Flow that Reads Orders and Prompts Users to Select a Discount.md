# Lab 11 – Entwickeln eines beaufsichtigten Flows, der Bestellungen liest und Benutzer auffordert, einen Rabatt auszuwählen

**Ziel:** Das Ziel dieses Labs besteht darin, einen **attended Power
Automate Desktop-Flow** zu entwickeln, der den Prozess des Lesens von
Bestellungen aus einer Excel-Datei automatisiert und Benutzer
auffordert, einen Rabatt basierend auf bestimmten Bedingungen
anzuwenden. Die Teilnehmer erstellen einen Flow, der Daten liest, prüft,
ob der Bestellbetrag einen bestimmten Schwellenwert überschreitet, und
den Benutzer auffordert, zu entscheiden, ob ein Rabatt angewendet werden
soll, mit der Option, den Rabattwert einzugeben. Der Flow aktualisiert
dann die Excel-Tabelle mit dem angewendeten Rabatt.

**Geschätzte Zeit:** 25 Minuten

### Aufgabe 1: Erstellen eines Power Automate-Desktopflows

1.  Öffnen Sie **Power Automate Desktop,** und melden Sie sich mit
    **Office 365 tenant credential** an.

2.  Wählen Sie die Umgebung **Contoso** aus , klicken Sie auf **+ New
    then Flow**, und beginnen Sie mit der Erstellung eines neuen Flows.

- ![](./media/image1.png)

3.  Geben Sie +++**Message Box Communication**+++ als Flow-Name ein, und
    bestätigen Sie, dass Power Fx enable (Preview) deaktiviert ist.
    Klicken Sie dann auf **Create**.

- ![](./media/image2.png)

4.  Beginnen Sie damit, den Benutzer aufzufordern, eine Excel-Datei
    auszuwählen. Fügen Sie die Aktion **+++Display select file
    dialog+++** hinzu und konfigurieren Sie das Feld Dateifilter so,
    dass nur xlsx-Dateien zugelassen werden.

- ![](./media/image3.png)

5.  Geben Sie **Dialog Title** als +++**Select Excel**+++ ein, geben Sie
    den Speicherort des Ordners im **initial folder** als +++ C:
    Files+++ Filtern als **\*.xlsx** ein und klicken Sie dann auf die
    Schaltfläche **Save.**

- ![](./media/image4.png)

6.  Bevor Sie Daten aus der ausgewählten Datei lesen können, müssen Sie
    sie mit der Aktion **Launch Excel** starten. Fügen Sie **Launch
    Excel** aus der Aktion hinzu. Konfigurieren Sie dann die folgende
    Einstellung.

    - Starten Sie Excel: **add open the following document**

    - Dokumentpfad: +++**%SelectedFile%**+++

    - Klicken Sie auf die Schaltfläche **Save**

- ![](./media/image5.png)

7.  Um die Daten aus der Excel-Datei zu lesen, fügen Sie die Aktion
    **Read from Excel worksheet** Geben Sie **%ExcelInstance%** in der
    Excel-Instanz ein und wählen Sie **All available values from
    worksheet** im Feld „Retrieve“ aus. Klicken Sie auf die Schaltfläche
    **Save**

- ![](./media/image6.png)

8.  Fügen Sie die Aktion **Get first free column/row from Excel
    worksheet** hinzu, um die erste freie Spalte und Zeile im
    Excel-Arbeitsblatt abzurufen. Geben Sie **%ExcelInstance%** in die
    Excel-Instanz ein und klicken Sie dann auf die Schaltfläche
    **Save**.

- ![](./media/image7.png)

9.  Fügen Sie eine Set-Variable aus der Aktion mit dem Namen **Counter**
    hinzu, initialisieren Sie sie auf **1** und klicken Sie dann auf
    **Save**.

- ![](./media/image8.png)

10. Fügen Sie das **Display input dialog** aus der Aktion hinzu und
    konfigurieren Sie die folgenden Felder.

    - **Input Dialog Title**: **+++Header+++**

    - **Input Dialog Message**: **+++Enter the Header+++**

    - **Default Value**: **+++Discount+++**

    - Klicken Sie auf die Schaltfläche **Save**

- ![](./media/image9.png)

11. Fügen Sie **“Write to Excel worksheet"** aus Aktionen hinzu, und
    konfigurieren Sie es mit den folgenden Details:

    - **Excel instance**: %ExcelInstance%

    - **Value to write**: +++**%UserInput%**+++

    - **Write role**: In einer bestimmten Zelle

    - **Column**: +++9+++

    - **Row**: +++**%Counter**+++

    - Klicken Sie auf die Schaltfläche **Save**

- ![](./media/image10.png)

12. Fügen Sie eine **For each**-Schleife für die Aktion hinzu, um die
    abgerufenen Daten zu durchlaufen, und fügen Sie den Abschnitt
    +++**%ExcelData%**+++ in den Wert hinzu, um zu iterieren. Klicken
    Sie dann auf Save.

- ![](./media/image11.png)

13. Um den Wert der Spalte **Gross** (Spalte G oder die sechste Spalte
    im Arbeitsblatt, im Blatt ist der Name der Spalte "6") zu
    überprüfen, fügen Sie die Aktion **convert text to number** hinzu .
    Konfigurieren Sie den Text so, dass er als
    +++**%CurrentItem\[6\]%**+++ konvertiert wird, und klicken Sie dann
    auf die Schaltfläche Save.

- ![](./media/image12.png)

14. Fügen Sie eine **If** Aktion hinzu , um zu überprüfen, ob sie
    100.000 überschreitet, und konfigurieren Sie sie wie folgt Details:

    - **First operand**: +++**%TextAsNumber%**+++

    - **Operator**: Greater than or equal to (\>=)

    - **Second Operand**: +++**100000**+++

- ![](./media/image13.png)

15. Fügen Sie unter **If** die Aktion **Display message** hinzu**,** um
    dem Benutzer die erforderlichen Informationen bereitzustellen und
    ihn aufzufordern**, Yes** oder **No** auszuwählen. Klicken Sie dann
    auf die Schaltfläche **Save**. Geben Sie das folgende Detail in das
    it ein:

    - **Message Box title**: **+++Add discount+++**
    - **Message to display**:
      - +++**Product:** %CurrentItem\[2\]%+++
      - **+++Units:** %CurrentItem\[3\]%+++
      - **+++Gross:** %TextAsNumber%+++
    - **Message box button:** Yes – No

- ![](./media/image14.png)

16. Fügen Sie unter der Aktion „Nachricht anzeigen“ eine zweite
    „**If**“-Aktion hinzu, um zu prüfen, welcher Button im vorherigen
    Schritt gedrückt wurde. Geben Sie die folgenden Details in die
    entsprechenden Felder ein:

- **First Operand**: +++%ButtonPressed3%+++

- **Operator:** Equal to (=)

- **Second Operand:** +++Yes+++

 

- ![](./media/image15.png)

17. Fügen Sie unter der zweiten Aktion If " **Add Display Input Dialog**
    " den unten angegebenen Parameter in das Feld ein und klicken Sie
    auf die Schaltfläche **Save**.

Input dialog title: +++Discount Value+++

Input dialog message: +++Enter the Discount Value+++

![](./media/image16.png)

18. Fügen Sie unter der zweiten **IF**-Aktion die Aktion **Write to
    excel worksheet** hinzu , und geben Sie das folgende Detail ein:

- **Excel instance:** +++% ExcelInstance%+++

- **Value to writer**: +++%UserInput2%+++

- **Write mode:** Auf einer bestimmten Zelle

- **Column:** +++9+++

- **Row:** +++%Counter%+++

&nbsp;

- ![](./media/image17.png)

20. Fügen Sie unter Erstes **IF End** die Aktion **Increase Variable**
    hinzu, fügen Sie den Variablennamen als **%Counter%** , erhöhen Sie
    um **1** und klicken Sie dann auf die Schaltfläche **Save**.

> ![](./media/image18.png)

21. **Save** in der oberen Leiste den Flow für den Test.

- ![](./media/image19.png)

# Aufgabe 2: Testen des Flows

1.  Klicken Sie auf die Schaltfläche **Run**, um den Test auszuführen.

> ![](./media/image20.png)

2.  Der erste Blattordner wird geöffnet, wählen Sie die **excel file**
    daraus aus.

> ![](./media/image21.png)

3.  Das Kopffenster wird angezeigt, wenn wir den **Discount** als
    Standard festlegen, klicken Sie auf die Schaltfläche **OK**.

> ![](./media/image22.png)

4.  Es erscheint das Fenster **"Add Discount**", das anzeigt, dass
    dieses Produkt mehr als **100000** ist, wählen Sie **yes** oder
    **No**. In diesem Test wählen wir **yes**(**yes,** wir geben Rabatt
    auf dieses Produkt.)

> ![](./media/image23.png)

5.  Geben Sie dann den **Discount Value** ein: Für den Test geben wir
    **10000** ein und klicken dann auf **OK**.

> ![](./media/image24.png)

6.  Im Blatt wird der Rabattwert aktualisiert.

![](./media/image25.png)

7.  Die Schleife läuft für alle Produkte **kontinuierlich**.

### Schlussfolgerung:

In diesem Lab entwickelten die Teilnehmer einen beaufsichtigten Power
Automate Desktop-Flow, der Bestelldaten aus einer Excel-Datei liest,
überprüft, ob der Bestellbetrag einen festgelegten Schwellenwert
überschreitet, und den Benutzer auffordert, einen Rabatt anzuwenden. Der
Flow automatisiert den Entscheidungsprozess effizient, indem er es
Benutzern ermöglicht, über Prompts mit dem Flow zu interagieren und
Rabattwerte einzugeben. Dieses Lab bietet praktische Erfahrungen in der
Automatisierung von Aufgaben mit Excel, Benutzereingaben und bedingter
Logik und ermöglicht es den Teilnehmern, ähnliche Geschäftsprozesse mit
Power Automate Desktop zu optimieren.
