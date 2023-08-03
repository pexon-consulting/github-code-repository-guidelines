# Github Code-Repository Guidelines

## Table of Content

<!-- toc -->

- [1 Einführung](#1-einfuhrung)
- [2 Git Repository](#2-git-repository)
  * [2.1 Readme Datei](#21-readme-datei)
  * [Projektbescheibung](#projektbescheibung)
  * [Badges](#badges)
  * [Quickstart-Guide](#quickstart-guide)
  * [Link zu weiteren Ressourcen](#link-zu-weiteren-ressourcen)
  * [Acknowledgements](#acknowledgements)
  * [Kontaktdaten](#kontaktdaten)
  * [2.2 Git Branching-Strategie](#22-git-branching-strategie)
    + [2.2.1 Allgemeine Regeln](#221-allgemeine-regeln)
    + [2.2.2 Hauptbranch](#222-hauptbranch)
    + [2.2.3 Sekundärbranches](#223-sekundarbranches)
  * [2.3 Tags, Releases und Versionierung](#23-tags-releases-und-versionierung)
    + [2.3.1 Tags und Releases](#231-tags-und-releases)
    + [2.3.2 Versionierung](#232-versionierung)
- [3 Source Code und Code Commits](#3-source-code-und-code-commits)
  * [3.1 Source Code Quality & Style](#31-source-code-quality--style)
  * [3.2 Code Commits](#32-code-commits)
    + [3.2.1 Commit Nachrichtne](#321-commit-nachrichtne)
  * [2.2 Dokumentation](#22-dokumentation)
  * [2.3 Practices](#23-practices)
  * [2.4 Git Commit Regeln](#24-git-commit-regeln)
  * [Lizenz](#lizenz)
  * [2.3 Clean Code](#23-clean-code)
- [3 Organisation](#3-organisation)

<!-- tocstop -->

## 1 Einführung

Alle Pexonians sind herzlich eingeladen, interessante Open-Source Projekte zu gestalten und diese in unserer GitHub Organisation zu veröffentlichen.  
Unsere Firma strebt danach, fesselnde Technologien zu kreieren, einzusetzen und zu fördern.  
Unser Ziel ist es, sämtliche Entwickler zu unterstützen und zu ermutigen, Neues zu schaffen.  
Dieses Dokument fungiert als Richtlinie für unsere Code-Qualität und die Struktur unserer Repositories.  
Es soll die Zusammenarbeit während der Entwicklung erleichtern und die Veröffentlichung der Projekte auf einen einheitlichen Standard bringen.  
Projekte können eigenständige Programme, Frameworks, Libraries, Plugins, Extentions, Dokumente und vieles weiteres sein.  Im folgenden Dokument werde sie alle kollektiv als "Projekt" bezeichent.

## 2 Git Repository

### 2.1 Readme Datei

Die Readme-Datei stellt eines der wesentlichsten Dokumente innerhalb eines Git-Repositories dar.  
In sowohl open- als auch in Closed-Source-Anwendungen fungiert sie als primärer Anlaufpunkt für Entwicklerinnen und Entwickler, die sich mit dem Code auseinandersetzen müssen.  
Daher ist es von außerordentlicher Wichtigkeit, dass die Readme-Datei ein umfassendes Dokument bildet, das sämtliche wesentlichen Informationen zum Projekt enthält.  
Es sollte nicht das Hauptziel sein, dass die Readme-Datei die gesamte Dokumentation widerspiegelt.  
Trotzdem sollte sie genügend Wissen vermitteln, um die meisten Fragen der Entwicklergemeinschaft zu beantworten.  

***Folgende Punkte müssen in der Readme Datei zu finden sein:***

### Projektbescheibung

Am Anfang der Readme-Datei befindet sich eine knappe Zusammenfassung, die als "Executive Summary" für das Projekt und das Repository fungiert.  
In nur wenigen Sätzen soll der Leser einen groben Überblick darüber erhalten, worum es bei dem Projekt geht und welche Inhalte in diesem Repository zu finden sind.  

### Badges

An zweiter Stelle sollten Projekt-Badges ("Shields") zu finden sein.  
Dieses Badges geben einen Überblick über verschiedene Attribute des Repositories geben.  
Zu diesen Badges gehören unter anderem:

- Code Coverage
- Build Status
- Latest Version
- Code Lizenz

Shields können über den Folgen Links generiert werden: [shields.io](https://shields.io/)

### Quickstart-Guide

Der Quickstart-Guide stellt eines der zentralen Elemente innerhalb der Readme-Datei dar.  
Er umreißt die Schritte, die ein Nutzer befolgen muss, um das Projekt usw. nutzen zu können.  
Bei der Erstellung des Quickstart-Guides ist es von besonderer Bedeutung, die Perspektive des Nutzers einzunehmen.  
Das bedeutet, der Verfasser des Leitfadens sollte sich in die Lage einer Person versetzen, die noch keinerlei Interaktion mit dem Code hatte und bei Null beginnt.  
Folglich müssen klare Informationen bereitgestellt werden, wie das Projekt genutzt werden kann, welche Vorbedingungen erfüllt sein müssen, ob spezifische Konfigurationen angepasst werden müssen und so weiter.  
Idealerweise mündet der Leitfaden in einem "Hello World!"-Beispiel. Das bedeutet, er sollte so weit gehen, bis der Nutzer das Projekt usw. gestartet hat und ein einfaches Ergebnis sieht.  

### Link zu weiteren Ressourcen

In diesem Abschnitt der Readme sollen weiteren Ressourcen verlinkt werden, welche die Nutzung des Projekts unterstützen.
Dazu gehören unter anderem Verweise zu einer Wiki oder eine Demo.

### Acknowledgements

Anerkenntnisse jeglicher Form haben hier ihren Platz.  
Dazu gehören Punkte wie Danksagungen an wichtige Contributor, Sponsoren, usw.

### Kontaktdaten

Hier einen Verweis mit dem Nutzer and Hilfe kommen können, wenn sie diese benötigen. Dies kann eine E-Mail (nicht empfohlen) oder ein Link zur Issue Page sein.

### 2.2 Git Branching-Strategie

Jedes Repository folgt der gleichen Branching-Strategie. 

#### 2.2.1 Allgemeine Regeln

Alle Branches sollten über eine Pipeline verfügen, welche Tests durchführt und Code Qualität mithilfe von SonarQube prüft. Sollte dies aus technischen Gründen nicht möglich sein entfällt diese Regel.   

#### 2.2.2 Hauptbranch

Die Strategie sieht als Default-Branch den Branch `main` vor.  
Auf den `main`-Branch darf nicht direkt gepushed werden, besonders nicht via. Force-Push.  
Alle Code Changes auf den `main`-Branches muss via Pull Request erfolgen.  
Pull Requests auf den `main`-Branch brauchen das Approval des Code Owners.  
Wenn eine Pipeline für den `main`-Branch existiert, darf ein PR nur gemerged werden, wenn die PR-Pipeline fehlerfrei durchgelaufen ist.
Der `main`-Branch soll zu jeden zeitpunkt eine stabile, produktionsreife Version des Programs beinhalten.  
Bei einer Projekt-Versionsnummer <1.0 muss der `main`-Branch die vorherige Regeln nicht einhalten, sollte jedoch den stabilsten Zustand, der möglich ist, wiederspiegeln.  
Mehr Informationen zur Versionierung um entsprechenden Kapitel.  

#### 2.2.3 Sekundärbranches

Ein Nebenbranch muss einen der folgenden Namen haben:  

- `dev`
- `feature/*`
- `bugfix/*`
- `hotfix/*`
- `concept/*`

**Sollte ein Branch mit einem Ticket assoziiert sein, so muss ein Sekundärbranch einen der folgenden Namen haben:**  

- `feature/<ticket_nr>/*`
- `bugfix/<ticket_nr>/*`
- `hotfix/<ticket_nr>/*`
- `concept/<ticket_nr>/*`

Ein PR auf einen Sekundärbranch dürfen nur von Branch-Owner angenommen werden.  
Branch-Owner ist die Person, die den ältesten Commit auf dem entsprechenden Branch getätigt hat.  
Branch-Owner bei Branches, welche mit Tickets assoziiert sind, ist die Person, die das Ticket bearbeitet.  
Ausgenommen hierbei ist der `dev`-Branch.

### 2.3 Tags, Releases und Versionierung

#### 2.3.1 Tags und Releases

Den Contributern ist frei überlassen ob und in welchem Abstand releases veröffentlicht werden.  
Um ein Release zu erstellen wird ein bestimmter Commit mit einem Git Tag versehen.  
Releases können nur vom Stand des `main`-Branches erstellt werden.  
Sollten aus anderen Branches Releases erstellt werden, so müssen sie mit dem Postfix `-unstable` markiert werden.  

#### 2.3.2 Versionierung
Stabile Releases (Releases vom `main`-Branch) folgen der standard [Semver](https://semver.org/)-Konvention `MAJOR.MINOR.PATCH`  
Dabei stehen `MAJOR`, `MINOR` und `PATCH` für positive Ganzzahlen und dürfen keine vorstehende "0" haben.  
Inkrementiere ...

- ... MAJOR, bei breaking changes.
- ... MINOR, bei non-breaking changes.
- ... PATCH, bei non-breaking bug fixes.


## 3 Source Code und Code Commits

Dieser Abschnitt listet das Regelwerk auf, welches von jedem Entwickler eines Projektes in dieser Organisation zu befolgen ist.  

### 3.1 Source Code Quality & Style

***Als grundsätzliche Regelt gilt: Für jede Programmiersprache sind die "Best Practices" der entsprechenden Sprache einzuhalten.***  

Hier eine Referenz zu den Best Practices verschiedener Sprachen:  

**Java**: [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)  
**Python**: [PEP 8 Style Guide](https://peps.python.org/pep-0008/), [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html), [The Hitchhiker's Guide to Python](https://docs.python-guide.org/)  
**JavaScript**: [JavaScript: The Right Way](http://jstherightway.org/), [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html), [W3C Javascript Best Practices](https://www.w3.org/wiki/JavaScript_best_practices)  
**TypeScript**: [AWS Follow TypeScript best practices](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-cdk-typescript-iac/typescript-best-practices.html), [Typescript Do's and Don'ts](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html)  
**HTML**: [HTML Style Guide](https://www.w3schools.com/html/html5_syntax.asp)  
**CSS**: [Organizing your CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Organizing)  
**GoLang**: [Effective Go](https://go.dev/doc/effective_go), [GoLang best Practices](https://golangdocs.com/golang-best-practices)

Weitere Guides zu diesen und weiteren Sprachen, Frameworks und Tools sind zu finden im folgenden Repository: [Awesome Guidelines](https://github.com/Kristories/awesome-guidelines)

### 3.2 Code Commits

#### 3.2.1 Commit Nachrichtne
Commit Titel müssen kurz und kompakt sein. Dabei müssen sie die wichtigsten Changes im Commit nennnen.   
Commit Beschreibungen dürfen tiefer ins Detail gehen.  
Commit Beschreibungen sind optional aber empfohlen.  
Commit Titel und Beschreibungen dürfen entweder Deutsch oder Englisch sein, jedoch muss pro Branch eine Sprache eingehalten werden.  
Sowohl Titel als auch Beschreibung werden im Imperativ geschrieben.

Alle Nachrichten folgen dem Schema:

    <ticket_nr>: <Commit_Titel>  

    <Commit_Beschreibung>

### 2.2 Dokumentation

- Git Dokumentationstools verwenden

### 2.3 Practices

- Release Strategy
- Tages
- Artefakte
- Github Actions
- Package Management

### 2.4 Git Commit Regeln

- Git Authorship
- Commit Messages folgen Schema (evtl. Husky miteinbauen)
- Rebase > Merge
- Squash before Merge

### Lizenz

Für unsere Open Source Projekte nutzen wir Grundsätzlich die [GPL3 Lizenz](https://www.tldrlegal.com/license/gnu-general-public-license-v3-gpl-3).  
Diese ist in jeder Codebase beizulegen.  
Abweichende Lizenzen sind je nach Projekt aus verschiedenen Gründen auch nutzbar. 

### 2.3 Clean Code

- Clean Code Guidelines der jew. Sprache beachten
- Pexon Prefered Code Format für Sprache beachten

## 3 Organisation
