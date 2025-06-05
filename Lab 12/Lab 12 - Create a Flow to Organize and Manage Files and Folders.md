# Lab 12 - Erstellen eines Flows zum Organisieren und Verwalten von Dateien und Ordnern

**Ziel:** Das Ziel dieses Labs besteht darin, den Prozess des Sicherns
von Dateien aus einem bestimmten Ordner auf dem Desktop mithilfe von
**Power Automate Desktop** zu automatisieren. Die Teilnehmer erstellen
einen Flow, der Dateien aus einem Ordner mit dem Namen **Contoso_Files**
kopiert, sie in einen neu erstellten Sicherungsordner verschiebt und
einen Zeitstempel an die Sicherungsdatei anhängt. Dieses Lab bietet
praktische Erfahrungen in der Automatisierung von
Dateiverwaltungsaufgaben, einschließlich des Erstellens von Ordnern, des
Kopierens von Dateien und des Umbenennens von Dateien mit dynamischen
Datums- und Zeitformaten.

**Geschätzte Zeit:** 20 Minuten

### Aufgabe 1: Erstellen eines Ordners und Desktop-Flows

1.  Erstellen Sie einen Ordner auf Ihrem Desktop, und benennen Sie ihn
    in **Contoso_Files** um.

- ![](./media/image1.png)

2.  Wählen Sie **Report.txt**-Datei aus dem **Ordner C:\***, **und
    verschieben Sie** die .txt\*\*-Datei im Ordner **Contoso_Files**.

- ![](./media/image2.png)

3.  Öffnen Sie den Power Automate-Desktop, und **melden Sie** **sich**
    mit den **Office 365 tenant credential** **an**. Wählen Sie in der
    oberen Leiste die Umgebung **Contoso** aus.

- ![](./media/image3.png)

4.  Klicken Sie auf + **New flow** in der oberen linken Ecke und
    beginnen Sie mit der Erstellung eines neuen Flows.

- ![](./media/image4.png)

5.  Geben Sie +++**Backup File Flow**+++ als Flow-Namen ein und
    aktivieren Sie das Kontrollkästchen der **Power Fx enable
    (Preview).** Klicken Sie dann auf **Create**

- ![](./media/image5.png)

6.  Suchen Sie in der linken Navigationsleiste **"Actions**" nach der
    Aktion **+++Get special folder+++** zum Arbeitsbereich. Wählen Sie
    die Aktion aus, indem Sie darauf doppelklicken, um sie dem Flow
    hinzuzufügen.

- ![](./media/image6.png)

7.  Klicken Sie dann auf die Schaltfläche **Save**, um die
    Standardeinstellung der Schaltfläche zu speichern.

- ![](./media/image7.png)

8.  Suchen Sie in der linken Navigationsleiste für **Actions** nach der
    Aktion **+++Get files in folder+++** zum Arbeitsbereich. Wählen Sie
    die Aktion aus, indem Sie darauf doppelklicken, um sie dem Flow
    hinzuzufügen.

- ![](./media/image8.png)

9.  Fügen Sie die Aktion **Get files in folder** hinzu, um das Feld
    Ordner auf +++\*\*C:\_Files+++ zu setzen.**Mit dieser Einstellung
    wird der Ordner ausgewählt, den Sie zuvor auf dem Desktop erstellt
    haben.** Klicken Sie dann auf die Schaltfläche **Save**\*\*.

- ![](./media/image9.png)

10. Suchen Sie in der linken Navigationsleiste **"Actions**" nach der
    Aktion **+++Create folder+++** zum Arbeitsbereich. Wählen Sie die
    Aktion aus, indem Sie darauf doppelklicken, um sie dem Flow
    hinzuzufügen.

- ![](./media/image10.png)

11. Geben Sie im Feld **Create new folder** in der Aktion „Ordner
    erstellen“+++\*\*C:\*+++ Geben Sie im Feld **New folder name
    Contoso_Backup** ein. Nachdem Sie die Informationen eingegeben
    haben, klicken Sie auf die Schaltfläche **Save**.

- ![](./media/image11.png)

12. Suchen Sie in der linken Navigationsleiste für **Actions** nach der
    Aktion +++**Copy file(s)** in den Arbeitsbereich. Wählen Sie die
    Aktion aus, indem Sie darauf doppelklicken, um sie dem Flow
    hinzuzufügen.

- ![](./media/image12.png)

13. Legen Sie das Feld **File(s) to Copy** auf **+++=Files+++,** das
    Feld **Destination Folder** auf +++\*\*C:\_Backup+++ und **die
    Dropdown-Option** **+++If File(s) Exists+++** auf Overwrite fest**.
    Klicken Sie nach der Einrichtung auf die** Schaltfläche
    **Save**\*\*.

- ![](./media/image13.png)

14. Suchen Sie in der linken Navigationsleiste **"Actions**" nach der
    Aktion +++**Rename file(s)** +++ (Aktion) zum Arbeitsbereich. Wählen
    Sie die Aktion aus, indem Sie darauf doppelklicken, um sie dem Flow
    hinzuzufügen.

- ![](./media/image14.png)

15. Legen Sie das Feld **Files(s) to rename,** auf
    +++\*\*C:\_Backup.txt+++ fest. Wählen Sie im Dropdown-Menü **Rename
    scheme** die Option Date/time hinzufügen aus **.** Legen Sie die
    Dropdown-Option **Separator** auf **Nothing**\*\* und die Option
    **DateTime Format** auf +++**dd.MM.yy_HH.mm**+++ fest. Klicken Sie
    nach der Einrichtung auf die Schaltfläche **Save**.

- ![](./media/image15.png)

16. Der abgeschlossene **Flow** sollte dem folgenden Screenshot ähneln.

- ![](./media/image16.png)

### Aufgabe 2: Testen des Flows

1.  Nachdem der Ausführungsablauf abgeschlossen ist, befindet sich auf
    Ihrem Desktop ein neuer Ordner mit dem Namen “Backup Files”. Der
    Ordner enthält den gesamten Inhalt des Ordners mit dem Namen
    "Important" und eine zusätzliche Textdatei mit dem Namen "Backup
    Log", an deren Dateiname das Datum und die Uhrzeit der letzten
    Ausführung des Flows angehängt sind.

- ![](./media/image17.png)

  ![](./media/image18.png)

### Schlussfolgerung:

In diesem Lab haben die Teilnehmer erfolgreich einen Power Automate
Desktop-Flow erstellt, um die Organisation und Verwaltung von Dateien
und Ordnern zu automatisieren. Durch das Sichern von Dateien aus einem
bestimmten Ordner mit dem Namen Contoso_Files in einen neu erstellten
Sicherungsordner erhielten die Teilnehmer praktische Erfahrungen in
wichtigen Dateiverwaltungsaufgaben, einschließlich der Ordnererstellung,
des Kopierens von Dateien und der dynamischen Dateiumbenennung mit
Zeitstempeln. In diesem Lab wird die Effektivität von Power Automate
Desktop bei der Optimierung von Dateiorganisationsprozessen, der
Reduzierung des manuellen Aufwands und der Sicherstellung der sicheren
Sicherung wichtiger Dateien hervorgehoben. Die Teilnehmer verließen die
Veranstaltung mit praktischem Wissen, wie sie die Automatisierung für
eine effiziente Dateiverwaltung nutzen und ihre Produktivität bei
alltäglichen Aufgaben steigern können.
