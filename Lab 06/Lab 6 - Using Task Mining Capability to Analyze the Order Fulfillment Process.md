# Lab 6 - Verwenden der Task-Mining-Funktion zur Analyse des Auftragsabwicklungsprozesses

**Ziel:** Das Lab konzentriert sich auf die Nutzung von Power Automate
Task Mining-Funktionen, um den Auftragsabwicklungsprozess zu analysieren
und zu optimieren. Die Teilnehmer lernen, wie sie eine Lösung mit
Beispielaufzeichnungen importieren, Task-Mining-Funktionen erkunden und
Prozessanalysen durchführen, um Engpässe zu identifizieren. Darüber
hinaus befasst sich das Lab mit der Automatisierung von Prozessschritten
und dem Einsatz von Analytics, um Einblicke in die Prozesseffizienz zu
gewinnen.

**Geschätzte Zeit:** 30 Minuten

### Aufgabe 1: Bereiten Sie sich auf das Task-Mining vor

1.  **Melden Sie sich** bei Power Automate mit
    +++**https://make.powerautomate.com/**+++ mit Ihren Office
    365-Tenantanmeldeinformationen **an**.

2.  Wählen Sie Ihre Umgebung aus – **Dev One**.

- ![](./media/image1.png)

### Aufgabe 2: Importieren einer Lösung

1.  Wählen Sie im Navigationsbereich auf der linken Seite **Solutions**
    und dann in der Symbolleiste oben **Import solution** aus.

- ![](./media/image2.png)

2.  Wählen Sie **Browse** aus.

- ![](./media/image3.png)

3.  Wähle die **Processmining.zip** Datei aus C:Files aus und öffne sie.

- ![](./media/image4.png)

4.  Wählen Sie **Next** aus.

- ![](./media/image5.png)

5.  Wählen Sie **Import** aus, und warten Sie, bis die Lösung importiert
    wurde.

- ![](./media/image6.png)

### Aufgabe 3: Anzeigen von Beispielaufzeichnungen

1.  Nachdem Sie die .zip Datei erfolgreich importiert haben, wählen Sie
    im Navigationsbereich auf der linken Seite **Process Mining** und
    dann den **Invoice submission process** aus.

- ![](./media/image7.png)

2.  Wenn Sie zur Registerkarte "Analytics" navigieren, gehen Sie einen
    Schritt zurück. Kehren Sie zum **Invoice Submission Process** zurück
    , indem Sie ihn aus den Breadcrumbs oben auf der Seite auswählen.

- ![](./media/image8.png)

3.  Einige der vorhandenen Aufzeichnungen können Sie unter
    **Recordings** sehen.

- ![](./media/image9.png)

4.  Um sicherzustellen, dass Sie die gesamte Liste der vorhandenen
    Aufzeichnungen sehen, wählen Sie **See all** aus.

### Aufgabe 4: Erkunden der Funktionen

Sie sehen die folgenden Funktionen:

- **New recording**: Erstellen Sie eine neue Aufnahme.

- **Analytics**: Sehen Sie sich die Prozesslandkarte und Einblicke an

- **Analyze**: Analysieren Sie einen Prozess.

- **Create activity names**: Erstellen Sie Aktivitätsnamen für Ihren
  Prozess.

- **Delete process**: Löschen Sie Ihren Prozess.

&nbsp;

- ![](./media/image10.png)

### Aufgabe 5: Analysieren eines Prozesses

Wenn Sie einen Prozess analysieren, analysiert die Process
Mining-Funktion vorhandene Aufzeichnungen, um Engpässe innerhalb des
Geschäftsprozesses zu identifizieren.

1.  Wählen Sie **Analyze** aus.

- > **Hinweis:** Die Analyse dauert einige Minuten. Während dieses
  > Vorgangs wird unter der Schaltfläche **New recording** eine
  > Statusmeldung angezeigt.

  ![](./media/image11.png)

2.  Wenn während der Analysephase ein Fehler auftritt, wählen Sie
    **Analyze** aus, um diese Aktion erneut auszulösen.

3.  Sobald dies erledigt ist, ändert sich der **Process analysis
    status** in **Analyzed**. Wählen Sie **Analytics** aus, um die
    Prozesslandkarte und die Erkenntnisse anzuzeigen.

- ![](./media/image12.png)

  > **Hinweis:** Es kann einige Minuten dauern, bis dieser Schritt
  > abgeschlossen ist, nachdem die Analyse durchgeführt wurde.

### Aufgabe 6: Seitenlayout für Analytics

In diesem Abschnitt wird erläutert, was Sie auf dem
**Analytics**-Bildschirm tun können.

![](./media/image13.png)

![](./media/image14.png)

**Legende:**

1.  **Automatisieren von Aktivitäten**: Um den Automatisierungsprozess
    zu optimieren, können Sie die Funktion **" Automate activities** "
    verwenden. Diese Funktion erkennt, ob der Benutzer Aktionen mit
    einer Anwendung ausgeführt hat, für die Power Automate-Aktionen
    verfügbar sind, z. B. Microsoft Outlook oder Excel. Bei der Auswahl
    von **Automatisieren von** **Aktivitäten** wird ein Power
    Automate-Prozessentwurf generiert, der die relevanten Aktionen
    enthält. Der Benutzer kann dann den Entwurfsprozess ändern und
    anpassen, um den endgültigen automatisierten Prozess zu erstellen.

2.  **Legende**: Zusätzliche Informationen zum Bericht, die ihnen
    helfen, die präsentierten Visualisierungen und Daten besser zu
    verstehen.

3.  **Prozess**: Detaillierte Informationen über den analysierten
    Prozess, einschließlich der Prozesslandkarte, der Zeitanalyse für
    jede Variante und jeden Aufzeichnungsautor.

4.  **Anwendung**: Informationen über die Apps, die in Aufzeichnungen
    verwendet werden. Dazu gehört, welche Apps von Autoren verwendet
    wurden, wie oft sie verwendet wurden und welche Übergänge zwischen
    ihnen bestanden. In diesem Bericht wird erläutert, welche
    Konnektoren bei der Implementierung der Automatisierung für den
    Prozess verwendet werden sollten und wo Desktop-Flows möglicherweise
    verwendet werden können, da kein Konnektor vorhanden ist.

### Aufgabe 7: Beziehungen zu Geschäftsprozessschritten

Sie sehen die verschiedenen Schritte im Geschäftsprozess und die
zugehörigen Dauern. Zu diesen Schritten gehören:

- Laden Sie den Rechnungsanhang aus einer E-Mail herunter (48 Sekunden)

- Excel-Rechnungsliste öffnen (11,5 Sekunden)

- Rechnung aus OneDrive öffnen (21 Sekunden)

- Geben Sie die Rechnungsdetails ein (53,6 Sekunden)

- Speichern und absenden (9 Sekunden)

- Team über die Einreichung benachrichtigen (26,67 Sekunden)

&nbsp;

- ![](./media/image15.png)

### Aufgabe 8: Anzeigen von Analyticsdaten

1.  Schauen Sie sich die wichtigsten Analyticsdaten an. Die
    durchschnittliche Verarbeitungszeit beträgt 1,47 Minuten bei fünf
    Aufnahmen.

- ![](./media/image16.png)

2.  Analysieren Sie andere zeitbasierte Metrik-Dashboards.

- > **Activity by average time in sec**: Beachten Sie, dass **Enter
  > invoice details** und das **Download invoice** die meiste Zeit in
  > Anspruch nehmen.

  ![](./media/image17.png)

  > **Recording by average time in min**: Beachten Sie, dass einige
  > Personen (**Preston Morales** und **Shakti Menon**) sich mehr Zeit
  > nehmen als andere.

  ![](./media/image18.png)

3.  Wählen Sie die Registerkarte **Application** aus, um Details zu den
    verwendeten Anwendungen anzuzeigen.

- Es kann eine Weile dauern, bis die Berichte geladen sind.

  - Durch die Bereitstellung von Informationen über die in einem
    Geschäftsprozess verwendeten Anwendungen, ihre Nutzungshäufigkeit
    und die für jede Anwendung aufgewendete Zeit ist dieser Bericht von
    entscheidender Bedeutung, um Einblicke in den Prozess zu gewinnen.

  - Das Dashboard zeigt beispielsweise, dass eine ältere
    Rechnungsstellungs-App, Outlook und Excel einen erheblichen Beitrag
    zur aufgewendeten Zeit und zu den Aktionen von Anwendungen leisten.

  - Nehmen Sie sich Zeit, um sich mit den verschiedenen Berichten
    vertraut zu machen.

  ![](./media/image19.png)

4.  Kehren Sie zur Prozesslandkarte zurück, indem Sie **Process**
    auswählen.

5.  Schauen Sie sich die Funktion für automatisierte Aktivitäten an. In
    der Prozesslandkarte können Sie sehen, dass die Process
    Mining-Funktion mehrere Aktivitäten als potenzielle Kandidaten für
    die Automatisierung basierend auf Anwendungen hervorgehoben hat.

6.  Beginnen Sie mit der Erstellung eines Flows für die Automatisierung,
    indem Sie oben **Automate activities** auswählen.

- ![](./media/image20.png)

  Im Browser wird eine Registerkarte geöffnet, auf der der Flow-Designer
  angezeigt wird. Die empfohlenen Aktionen, die den Aktivitäten aus der
  Prozesslandkarte entsprechen, werden automatisch im rechten Bereich
  angezeigt. Es werden beispielsweise mehrere E-Mail-Konnektoren
  vorgeschlagen, die Sie verwenden können, um die Aktivität **" Download
  invoice attachment from email** " zu automatisieren .

  ![](./media/image21.png)

### Schlussfolgerung:

In diesem Lab nutzten die Teilnehmer die Task-Mining-Funktionen von
Power Automate, um den Auftragsabwicklungsprozess zu analysieren und zu
optimieren. Durch den Import einer vorgefertigten Lösung mit
Beispielaufzeichnungen untersuchten sie die wichtigsten Funktionen des
Task Mining, einschließlich der Prozessanalyse, der Identifizierung von
Engpässen und der Generierung von Automatisierungsempfehlungen. Die
Teilnehmer lernten, wie sie die Prozesseffizienz durch detaillierte
Analysen der für verschiedene Aufgaben und Anwendungen aufgewendeten
Zeit bewerten können. Das Lab hob hervor, wie Task Mining
Geschäftsprozesse rationalisieren kann, indem es
Automatisierungsmöglichkeiten identifiziert, letztendlich die
betriebliche Effizienz verbessert und den manuellen Arbeitsaufwand im
Auftragsabwicklungsprozess reduziert.
