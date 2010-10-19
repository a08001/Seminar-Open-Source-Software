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
Um alle &Auml;nderungen ohne die Kommposition in eine `staging area` zu &uuml;bernehmen kann man den Befehl `git commit -a -m "Kommentar"` verwenden. Eine ausf&uuml;hrliche &Uml;bersicht aller Git Kommandos liefert der Befehl `git help`. Dort kann man &uuml;ber `git help log` weitere Informationen &uuml;ber die Versionsgeschichte erhalten.

<code>git add</code>

<code></code>

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




