# Lab 07 - Erstellen eines Flows zum Weiterleiten von Helpdesk-Anfragen an verschiedene Postfächer basierend auf der Sprache

**Ziel:** Das Ziel dieses Labs besteht darin, die Teilnehmer durch den
Prozess der Erstellung eines Power Automate-Flows zu führen, der
Helpdeskanforderungen basierend auf der Spracherkennung an verschiedene
Postfächer weiterleitet. Der Flow lässt sich in GPT-Funktionen
integrieren, um eingehende E-Mails zusammenzufassen und den
Routing-Prozess basierend auf bestimmten Triggers zu automatisieren, was
zur Optimierung der Kommunikationsabläufe innerhalb des Unternehmens
beiträgt.

**Geschätzte Zeit:** 15 Minuten

### Aufgabe 1: Erstellen eines Flows zum Weiterleiten von Helpdesk-Anfragen an verschiedene Postfächer basierend auf der Sprache

1.  Melden Sie sich beim +++**https://make.powerautomate.com/using**+++
    **Office 365-admin tenant account** an.

2.  Wählen Sie im linken Navigationsbereich **Templates** aus, geben Sie
    +++ **Summarize emails using GPT** +++ in das Suchfeld oben ein und
    wählen Sie den Flow aus, wenn er angezeigt wird.

- ![](./media/image1.png)

3.  Als Nächstes zeigt Ihnen die Vorlage, welche Verbindungen in diesem
    Flow verwendet werden. Wenn neben der Verbindung kein grünes Häkchen
    angezeigt wird, reparieren Sie die Verbindung, indem Sie neben der
    Verbindung "Sign in" und dann **"Continue"** auswählen.

- ![](./media/image2.png)

4.  Wählen Sie den Trigger aus, **when a new email arrives (V3).** Das
    Eigenschaftenfenster wird von links mit einem Hinweis zum
    Aktualisieren des Parameters Subject Filter geöffnet. Derzeit ist
    der **Subject filter** AI Builder.

5.  Aktualisieren Sie den Betrefffilter auf **Project Kick-off**.

- ![](./media/image3.png)

6.  Wählen Sie die Aktion **Create text with a GPT using a prompt** aus,
    damit das Eigenschaftenfenster auf der linken Seite geöffnet wird.
    Im Eigenschaftenbereich wird im Promptsfeld **AI Summarize**
    angezeigt.

7.  Wählen Sie **Test prompt** aus, um die Promptseinstellungen zu
    öffnen.

- ![](./media/image4.png)

8.  Die Vorlage verfügt über eine vordefinierte Prompt, die von GPT
    verwendet wird, aber Sie können in diesem Fenster eine neue Prompt
    aktualisieren und testen. Befolgen Sie den nächsten Schritt, um die
    Prompt zu aktualisieren.

9.  Um eine Prompt zu testen, geben Sie die angegebenen Beispieldaten in
    den Abschnitt **Input** ein. Wählen Sie dann unten im Abschnitt
    Prompt die Option **Test prompt** aus. Sie können die Antwort im
    Abschnitt Prompt response sehen.

- +++ Once upon a time in the quaint town of Eldoria, nestled between
  rolling hills and dense forests, lived a young girl named Elara. Her
  days were spent exploring the mystical woods that bordered the town,
  and whispers of ancient tales filled her imagination.+++

  ![](./media/image5.png)

10. Für diese Übung lassen wir alles so, wie es war, als wir die
    Promptseinstellungen geöffnet haben.

11. **Speichern Sie** den Flow in der oberen rechten Ecke. Jetzt können
    wir den Flow ausführen.

![](./media/image6.png)

> Hinweis: Ignorieren, wenn die angegebene Warnung angezeigt wird: Nach
> der Aktion " Create text with GPT using a prompt " folgt keine Aktion
> zur Inhaltsgenehmigung.

### Aufgabe 2: Testen des Flows

1.  Senden Sie eine E-Mail von der Tenant-ID des MOD-Administrators oder
    Ihrer E-Mail-ID an die Tenant-ID des MOD-Administrators mit dem
    Betreff **Project Kick-off** und folgendem Inhalt der E-Mail:

- Dear Team,

      I hope this email finds you well. We are excited to announce the
      kick-off of our new project, "Phoenix". The initial meeting is 

> scheduled
>     for Monday, June 1st, at 10 AM via Zoom. Please come prepared with any
>     questions or suggestions. Your input is vital for the project's success.
>
>     Kindly confirm your attendance by the end of the day tomorrow. Looking
>     forward to a productive session and a successful project launch.
>
>     Best regards,
>
>     Miriam Graham
>
>     Project Manager
>
>     Contoso

2.  Sie erhalten eine Nachricht in Teams mit einer Zusammenfassung der
    E-Mail. In der unteren rechten Ecke finden Sie einen Link, über den
    Sie zu Ihrem Flow gelangen können.

- ![](./media/image7.png)

3.  In dieser Lektion wird ein GPT verwendet, um eingehende E-Mails
    zusammenzufassen. AI-Erkennungsinformationen können ungenau sein.
    Stellen Sie immer sicher, dass Sie die Informationen aus dem GPT
    überprüfen.

### Schlussfolgerung:

In diesem Lab haben die Teilnehmer erfolgreich einen Power Automate-Flow
erstellt, um Helpdesk-Anfragen zu optimieren, indem sie E-Mails
basierend auf der Spracherkennung weiterleiten und GPT verwenden, um den
Inhalt zusammenzufassen. Durch die Integration der Automatisierung in
den E-Mail-Workflow demonstrierte das Lab, wie die Kommunikation
zwischen mehreren Teams oder Abteilungen auf der Grundlage von
Sprach-Triggers effizient verwaltet werden kann. In der Übung wurde auch
gezeigt, wie GPT in Power Automate verwendet werden kann, um die
Produktivität zu steigern und die manuelle Sortierung zu reduzieren.
Diese Lösung hilft Unternehmen, die Effizienz von Workflow zu verbessern
und die Reaktionszeit für Helpdesk-Anfragen zu verkürzen.
