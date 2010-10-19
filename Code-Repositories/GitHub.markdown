# Code-Repositories #
## GitHub ##
### Versionsverwaltung ###
Ein typisches Einsatzgebiet von Versionsverwaltungssystemen befindet sich im Umfeld der Software-Entwicklung, um Quellcode an den mehrere Personen arbeiten zu organisieren. Es lassen sich die &Auml;nderungen an jeder einzelnen Datei &uuml;ber die Zeit nachverfolgen.
Einige dieser Versionsverwaltungssysteme sind auch als Open Source Software verf&uuml;gbar.
Ein wichtiges Merkmal der Versionsverwaltung liegt in der Koordinierung des gemeinsamen Zugriffs auf eine Datei.
### zent###
### Git ###
Git ist ein Open Source verteiltes Versionsverwaltungssystem, dass &uuml;ber  einen gerichteten azyklischen Graph (DAG) implementiert wird. Es werden vollst&auml;ndige Abbilder aller Dateien &uuml;bertragen und k&ouml;nnen bearbeitet werden. Damit ist jeder <code>checkout</code> gleichzeitig ein vollst&auml;ndiges Backup des gesamten Repositories. So wird die Notwendigkeit eines eigenst&auml;ndigen Servers zum Austausch der Daten umgangen. 
Git ist kostenlos und ein Open Source verteiltes Versionsverwaltungs System,  das entwickelt wurde um alles vom kleinen Projekt bis zu sehr gro&szlig;en Projekten performant und effizent zu versionieren. 
### Schnelleinstieg ###
Die Grundschritte um ein Projekt zu erzeugen und unter Versionsverwaltung zu stellen, werden im folgenden beschrieben. Unter der Projektseite <code>http://git-scm.com</code> k&ouml;nnen die Git Release bezogen werden. Neben den Unix-Programm, existiert auch eine Version f&uuml;r Windows. Damit wird die <code>git</code> Befehlskommando verf&uuml;gbar. Der erste Schritt besteht in der Einrichtung eines Repositories, also eines Verzeichnis das unter Versionsverwaltung gestellt wird. Dazu wird der Befehl <code>git init</code> aus dem Verzeichnis das unter Versionsverwaltung gestellt werden soll ausgef&uuml;hrt. Mit dem Befehl <code>git add .</code> werden alle Dateien aus dem Verzeichnis zur Versionsverwaltung zugef&uuml;gt. Es k&ouml;nnen nun gezielt Dateien mit in die Versionsverwaltung aufgenommen werden, indem hinter dem add der Dateiname oder Dateimasken angegeben werden.&Uml;ber den Befehl <code>git commit %lt;Dateimaske%gt; -m "Kommentar"</code> k&ouml;nnen die Inhalte aktualisert werden. Nat&uuml;rlcih lassen sich &uuml;ber den Befehl `git rm &lt;Dateimanske&gt;` Dateien aus der Versionsverwaltung wieder entfernen.
Damit ist der erste schnelle Einstieg erfolgt. Es ist ein neues Repositories erzeugt, neue Dateien wurden zugef&uuml;gt und die Inhalte das erste Git &uuml;bertragen. Dies entspricht auch der arbeitsweise eines eines lokalen oder zentralen Versionsverwaltungssystem. Der neue Ansatz liegt eines verteilten Versionsverwaltungssystem ist oben bereits angesprochen wurden. Es werden nicht mehr die textuellen Differenzen zweier Version abgespeichert, sondern eine komplette Kopie der Arbeitsversion angelegt. Auf den ersten Blick erscheint das als Verschwendung von Ressourcen, es wird sich aber zeigen, dass dieser Ansatz sehr flexibel ist und &uuml;ber die M&ouml;glichkeiten von zentralen Systemen, wie Subversion, weitere Verbesserungen anbietet.
Der n&auml;chste Schritt im Verst&auml;ndnis von Grit liegt in der M&ouml;glichkeit Klone anzulegen. Dazu verwendet man den Befehl <code>git clone</code> und nicht wie bei zentralen Systemen `checkout`. Damit wird eine vollst&auml;ndige Kopie aller Dateien vom aktuelle Stand lopiert, also geklont. Aus diesem Dateibestand kann jeder Klon, den Datenbestand des Gesamtsystems zum Zeitpunkt des klonens wieder herstellen. Dies stellt eine Kernidee der verteilten Versionsverwaltung dar, somit existiert die im zentralen Versionsveraltungssystem erforderliche Rolle des Servers nicht mehr. Jeder Klon kann auch als Server fungiern und seperat weitere &Auml;nderungen aufnehmen. 
Durch das Klonen eines Git erh&auml;lt man eine vollst&auml;ndige Arbeitskopie an der man seine &Auml;nderungen ausf&uuml;hrt und nachdem der Zustand erreicht ist, indem die Daten wieder zur&uuml;ckgespielt werden sollen, auch &uuml;bertr&auml;gt. Diese &Auml;nderungen werden als Snapshots oder Commits bezeichnet. Dabei handelt es sich um eine vollst&auml;ndige Kopie des Arbeitsverzeichnis, das an einen anderen Server komplett &uuml;bertragen wird. Der Server wird die Dateien mit dem bereits im Repository enthaltenen Dateien abgleichen. Dabei wird zwischen den M&ouml;glichkeiten ge&auml;ndert, gel&ouml;scht, verschoben, unver&auml;ndert und neu unterschieden.
Ist eine Datei unver&auml;ndert, wird der Server dies durch einen Verweis auf den letzten &Auml;nderungsstand ersetzen. Eine gel&ouml;schte Datei wird ohne Verweis auf die Altdaten &uuml;bernommen, damit wird diese Datei nicht mehr hergestellt. Eine neue Datei wird nun auch neu angelegt und eine ge&auml;nderte Datei wird ebenfalls neu angelegt. Das Verschieben einer Datei wird als l&ouml;schen und neuanlegen &uuml;bersetzt und wie beschrieben ausgef&uuml;hrt. Jedes `commit` oder `Snapshot` legt einen neuen Knoten im gerichtetenen azyklischen Graphen (DAG) an und wird als Nachfolger des geclonten Knoten eingef&uuml;gt.
&Uml;ber den Befehl `git status` kann &uuml;berpr&uuml;ft werden, ob es zwischen der lokalen Arbeitskopie und der auf dem Server unterhaltenen Git &Auml;nderungen gibt. Dabei werden Dateien die sich nicht auf dem Server Git aber in der Arbeitskopie befinden hingewiesen. Diese k&ouml;nnen dann &uuml;ber `git add` zugef&uuml;gt werden. Nat&uuml;rlich werden auch alle ge&auml;nderte oder gel&ouml;schte Dateien angezeigt. Die Ausgabe des Befehls listet diese Dateie in der Sektion ge&auml;ndert nicht akualisierte Dateien auf, wenn sich der Inhalt nicht ge&auml;ndert hat, die datei aber zwischenzeitlich bearbeitet wurde. Sonst werden ge&auml;nderte Dateien unter der Sketion: &Auml;nderungen die &Uml;bertragen werden aufgef&uuml;hrt.
Damit wird zwischen den &Auml;nderungen der lokalen Arbeitskopie und den freigegebenen &Auml;nderungen zum abgleich mit dem Server Grit unterschieden. Dies wird als `Staging Area` bezeichnet. Somit ist der `git status` Befehl ein sehr wichtiges Informationswerkzeug.
Den Vergleich zwischen den Version kann &uuml;ber den Befehl `git diff` angefordert werden. Dabei wird der Unix diff Befehl verwendet, um die Unterschiede der Dateien herauszustellen. Zus&auml;tzlich kann durch die Intergration der Git Tools in Eclipse der Quellcode komfortabel verglichen werden.
Es wird unterschieden zwischen den &Auml;nderungen in der lokalen Arbeitskopie und den freigegbenen &Auml;nderungen, die als `staging area` bezeichnet werden. Diese freigegebenen &Auml;nderungen k&ouml;nnen aus der `staging area` &uuml;ber den Befehl `git commit` an einen beliebigen als Git Server gesendet werden. &Uml;ber den Paramter `git commit -m "Kommentar"` kann ein Kommentar mit vorgegeben werden, ohne die Angabe wird ein Editor Fenster zur Eingabe eines Kommentras ge&ouml;ffnet.
Um alle &Auml;nderungen ohne die Kommposition in eine `staging area` zu &uuml;bernehmen kann man den Befehl `git commit -a -m "Kommentar"` verwenden. Eine ausf&uuml;hrliche &Uml;bersicht aller Git Kommandos liefert der Befehl `git help`. Dort kann man &uuml;ber `git help log` weitere Informationen &uuml;ber die Versionsgeschichte oder weitere hier noch nicht ausgef&uuml;hrten Befehle erhalten.

### Arbeiten mit externen Repositories ###
Es wurde bereits ausgef&uuml;hrt, das es sich bei `Git` um ein verteiles Versionsverwaltungssystem handelt. Ein Vorzug liegt in der Aufl&uml;sung des zentralen Servers, wie er f&uuml;r `Subversion` eingesetzt wird. Jeder Klon kann im verteilten Versionsverwaltungssystem, wie `Git`, mit jedem anderen Repositoriy Daten austauschen. &Uuml;ber den Befehl `git remote` k&uml;nnen weitere Git Repositories bekannt gemacht werden. &Uuml;ber den Befehl `git fetch &gt;remoteGit&lt;` k&uml;nnen Daten aus dem remoteGit bezogen werden, die im eigenen Git noch nicht verf&uuml;gbar sind. Das eigene Git, also die Arbeitskopie, wird &uuml;ber den Namen origin angesprochen und durch den Befehl `git fetch origin` werden alle relevanten Neuerungen des Original Gits bezogen. Standardm&auml;&szlig;ig werden die geklonten Gits als origin benannt und mit dem master, dem Repository das geklont wurde, logisch verbunden. Es folgt dem Branch und kann durch die kurzschreibweise `git pull` die Daten aus dem `master Git` in das `origin Git` &uuml;bernehmen.

Nachdem verstanden wurde, wie die Daten von anderen Repositories  bezogen wurde, wird nun die Frage nach untersucht, wie Daten von der lokalen Arbeitskopie an entfernte Gits &uuml;bertragen werden kann. Der einfach Weg Daten aus dem `origin Git` an das `master Git` zu transferieren, liegt in der Verwendung des Befehls `git push origin master`.
Das funktioniert nur dann, wenn Schreibrechte f&uuml;r das jeweilige Repository gegeben sind und niemand anders in der Zwischenzeit irgendwelche &Auml;nderungen an den gleichen Dateien hochgeladen hat. Wenn zwei Leute ein Repository zur gleichen Zeit klonen, dann zuerst der eine seine &Auml;nderungen hochl&auml;dt und der zweite anschlie&szlig;end versucht, das gleiche zu tun, dann wird sein Versuch korrekterweise abgewiesen. In dieser Situation mu&szlig; man neue &Auml;nderungen zun&auml;chst herunterladen und mit seinen eigenen zusammenf&uuml;hren, um sie dann erst hochzuladen. 

### Tagging ###
In den meisten Versionsverwaltungssystemen existiert die M&uml;glichkeit Markierungen (Tags) zu setzen. Die ist sehr hilfreich, um Programmversionen explizit zu spezifizieren. In Git kann man &uuml;ber den Befehl `git tag` diese Markierungen anzeigen lassen und &uuml;ber den Parameter `git tag -a v &gt;version&lt;` solche Markierungen setzen. Dies ist sogar nachtr&auml;glich m&uml;glich.

### Git Branching ###
In dem verteilten Versionverwaltungssystem Git wird intern ein gerichteter azyklischen Graph genutzt, um die einzelnen Sichten auf das Dateisystem zu verwalten. Somit l&auml;&szlig;t sich sehr elegant das erstellen von Zweigen (Branching), um von der Hauptlinie abzuzweigen erreichen. Es wird ein Pr&uuml;fsumme &uuml;ber das erzeugte Commit(Snapshot) &uuml;ber eine Einwegefunktion (Hashcode) als Datei mit dem 40 Zeichen langen SHA-1 Code. Andere Versionsverwaltungssystem bilden die komplette Struktur aller Dateien als echte physikalische Kopie der Abzweigepunkte und ben&uml;tigen dadurch wesentlich mehr Ressource.
Dieses Branching wird von Git als leistungsstarke Erweiterung gesehen. Es wird ermutigt, viele Branches zu erzeugen. Jedes Teilproblem kann ein eigener Branch sein, der unabh&auml;nig von den anderen Zeigen bearbeitet werden kann. Die L&uml;sung kann seperat in den Master als eigenst&auml;ndiger Branch gef&uuml;hrt werden.
Zus&auml;tzlich kann durch den Befehl `git merge &gt;branch&lt;` der Zweig wieder mit in die Hauptlinie zur&uuml;ck &uuml;berf&uuml;hrt werden und auf wunsch &uuml;ber den Befehl `git branch -d &gt;branch&lt;` kann der erzeugte Verzweigungspunkt wieder entfernt werden.


 

### Social Coding ###
### GitHub ###

Hosting f&uuml;r Open Source Projekte:

* JQuery
* Erlang
* Linux Mint
* PHP
* Rails - Ruby on Rails
* Erlang / OTP
* node.js
* Protoype
* MooTools
* Diaspora
* three20
* script.aculo.us
* MaNGOS
* ProGit
* Git
* YUI 3
* Django
* web.py
* cappucino
* Lift Web
* phpBB
* Groovy
* TinyMCE
* Greasemonkey
* und viele mehr




