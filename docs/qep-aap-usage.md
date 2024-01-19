# Webserver Deployment

Als kleines Projekt sollt ihr *automatisiert* einen Webserver in einem Container erstellen. Um die Automatisierung auszuführen nutzen wir die *Ansible Automation Platform* (kurz *AAP*), bzw. ihr *Open Source* Pendant *AWX*. Die AAP ist ein Web-UI für die einfache Ausführung von Ansible Automatisierung.

## 1. Projekt erstellen

In der AAP Oberfläche auf der linken Seite unter *Resources* den Punkt *Projects* wählen.  
Klickt oben auf den Button *Add*, es öffnet sich eine Maske mit Eingabe-Feldern. Ihr müsst lediglich die mit einem roten Sternchen markierten Felder zwingend ausfüllen, alles weitere ist optional.

Gebt eurem Projekt einen Namen, z.B. `QeP Demo`.

Wählt aus der Liste **Source Control Credential Type** den Punkt **Git**, es werden dadurch weitere Felder angezeigt.

Im Feld **Source Control URL** tragt ihr die folgende Adresse ein:

```text
https://github.com/TimGrt/automation-demo
```

!!! tip
    Ihr könnt die Adresse rechts mit einem kleinen Button (*Copy to Clipboard*) kopieren.

Bei den *Checkboxen* unter **Options** wählt ihr **Update Revision on Launch** aus.

Abschließend wählt ihr unten den Button **Save**. 

??? info "**Wozu das Ganze?**"
    Ein *Project* in der AAP zeigt auf ein *Repository*, quasi einen (versionskontrollierten) Ordner mit allem *Code* für die Automatisierung.  
    In unserem Fall liegt der gesamte *Code* für die Ansible Automatisierung in einem (öffentlich zugänglichen) *Github* Repository, die AAP zieht sich also den Code aus diesem Ordner und sorgt (durch die Auswahl der Checkbox) dafür, dass vor jeder Ausführung der Automatisierung der aktuellste Stand geladen wird.

## 2. Job Template erstellen

Nachdem der Code für die Automatisierung in der AAP verfügbar ist, wollen wir ihn auch ausführen können. Dazu wird ein *Job Template* erstellt.  

In der AAP Oberfläche auf der linken Seite unter *Resources* den Punkt *Templates* wählen.  
Klickt oben auf den Button *Add*, es öffnet sich eine Maske mit Eingabe-Feldern. Ihr müsst wieder lediglich die mit einem roten Sternchen markierten Felder zwingend ausfüllen, alles weitere ist optional.

Die folgende Tabelle zeigt alle Felder welche ihr befüllen müsst:

| Feld          | Inhalt                 |
| ------------- | ---------------------- |
| **Name**      | `Webserver Deployment` |
| **Job Type**  | `Run`                  |
| **Inventory** | `Workshop Inventory`   |
| **Project**   | `QeP Demo`             |
| **Playbook**  | `welcome.yml`          |

Speichert euer Jpb Template mit dem Button **Save**.

??? info "**Wozu das Ganze?**"  
    In unserem Fall liegt der gesamte *Code* für die Ansible Automatisierung in einem (öffentlich zugänglichen) *Github* Repository, die AAP zieht sich also den Code aus diesem Ordner und sorgt (durch die Auswahl der Checkbox) dafür, dass vor jeder Ausführung der Automatisierung der aktuellste Stand geladen wird.
