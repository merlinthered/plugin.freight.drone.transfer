# Frachtaustausch per Drohne: Remake

![Frachtdrohne](http://img3.imagebanana.com/img/d9ibkjf/frachtdrohne.jpg)

Dieses Skript ermöglicht den funktionierenden Frachtaustausch per Drohne.
Das Kommando befindet sich unter den Handelsbefehlen und unterscheidet sich vom EGO-Skript durch die gelbe Farbe.

Die Handhabung ist gleich dem EGOSOFT-Skript. Das Verhalten jedoch etwas anders.

Korrespondierender Thread im Egosoft-Forum: [[SCR] [17.03.09] Frachtaustausch per Drohne](http://forum.egosoft.com/viewtopic.php?p=2801714)

## Beschreibung:
Mit dem Frachtaustausch per Drohne ist es möglich, Waren über große Strecken hinweg zwischen Schiffen und Stationen sowie zwischen Schiffen untereinander auszutauschen. Aufgrund der Nutzung von intergalaktischen Handelssoftware-Standards ist es nun auch möglich, die Drohnen an fremden Stationen ein- und verkaufen zu lassen. Durch ihre Größe bedingt können Frachtdrohnen nur von großen Schiffen eingesetzt werden.

## Voraussetzungen:
* Schiff der Grosschiffklasse (außer M8) - Es macht keinen Sinn, Frachtdrohnen auf Schiffen einzusetzen, die kleiner als die Drohne sind...
* Handelssoftware Mk2
* Frachtdrohne

## Installation/Update:
* Den Inhalt des Ordners "t" in den "X3 TC\t" Ordner kopieren
* Den Inhalt des Ordners "scripts" in den "X3 TC\scripts" Ordner kopieren
* Wenn die String-Library von ChemODur bereits installiert ist, kann diese Version ruhig darübergeschrieben werden. Sie enthält ein paar kleine fixes für deutsche Buchstaben.


## Deinstallation:
* Im Spiel alle laufenden Frachttransfere abbrechen (den Drohnen einen anderen Befehl geben oder einsammeln)
* Speichern
* X3 verlassen und die Dateien des Skripts aus dem "scripts" Ordner löschen (s. "Verwendete Dateien")
* Die t-Datei aus dem "t" Ordner löschen (s. "Verwendete Dateien")

## Verhalten:
Wenn mehr Waren eingestellt werden, als eine Drohne transportieren kann, werden mehrere Drohnen gestartet und die Waren auf diese aufgeteilt.
Eine Drohne läd von dem Schiff, von dem sie gestartet wird, so viele eingestellte Waren ein, wie sie kann, und fliegt los. Am Ziel angekommen läd sie diese Waren aus. Ist dies nicht auf einmal möglich, wartet sie, bis wieder Frachtraum im Ziel frei wird, um den Rest zu transferieren.
Ist dies geschehen, läd sie so viel Ware wie eingestellt ein. Ist im Ziel nicht genug Ware vorhanden, wartet die Drohne, bis der Vorrat des Ziels wieder aufgestockt wird! Bei der Auswahl der Waren, die vom Ziel zurück transportiert werden sollen, wird daher auch nicht darauf geachtet, ob es überhaupt die eingestellte Menge vorrätig hat.
Wenn die gesamte eingestellte Menge der Fracht eingeladen wurde, macht sich die Drohne auf dem Weg zurück. Dann läd sie ihre Waren aus, sobald sie innerhalb der Transporterreichweite des Schiffes angekommen ist. Ist auf dem Schiff, das die Drohe gestartet hat, nicht genug Frachtraum frei, läd die Drohne so viel aus, wie sie kann, und folgt dem Schiff in 5 km Abstand bis sie in der Lage war, alles auszuladen. Dann fliegt sie zum Schiff, um eingesammelt zu werden. Dies passiert jetzt auch automatisch, sobald die Drohne in der Nähe des Schiffs ist. Besitzer von M2 und anderen Schiffen ohne Dockingplätzen müssen die Drohne also jetzt nicht mehr von Hand einsammeln.

## Bekannte Probleme:
Es kann vorkommen, dass die Drohnen nicht die genaue Menge der Waren transportieren, die eingestellt war. Das hat damit zu tun, dass bei der Auswahl der Waren nicht beachtet wird, dass der verfügbare Frachtraum auf mehrere Drohnen aufgeteilt werden muss. 
Hat man z.B. drei Drohnen an Bord, haben diese einen gesamten Frachtraum von 2400 Einheiten.
Wenn man jetzt eine Ware damit transportieren will, die z.B. 600 Einheiten groß ist, dann ist es bei der Auswahl der Waren ohne weiteres möglich, 4 davon einzustellen, da ja 4*600 genau in 2400 reinpasst. Wenn die Waren jetzt auf die Drohnen aufgeteilt werden, ist aber nur der Transport von 3 Einheiten Ware möglich, da auf eine Drohne jeweils nur eine Einheit der Ware passt. In dem Fall werden die Drohnen ohne Warnung einfach nur 3 Einheiten transportieren. Hier ist also etwas mitdenken gefragt.
_Anm: Dieser Fall ist bisher noch nicht ausreichend getestet_

## Verwendete Dateien:

`t\8222-L044.xml`
`t\8222-L049.xml`
`t\8910-L007.xml` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`t\8910-L044.xml` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`t\8910-L049.xml` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377

`scripts\lib.chem.strings.xml` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`scripts\plugin.freight.drone.delivery.xml`
`scripts\plugin.freight.drone.gui.xml`
`scripts\setup.freight.drone.move.xml`
`scripts\plugin.freight.drone.target.xml`
`scripts\plugin.freight.drone.transfer.xml`
`scripts\plugin.freight.drone.wares.xml`
`scripts\setup.freight.drone.transfer.xml`

## Verwendete Ressourcen:

### Kommandoslot
`COMMAND_TYPE_TRADE_22 (422)` ->"COMMAND_DRONE_WARE_EXCHANGE"

### Sprachdatei 
`8222-L044.xml (page id=8222)`
`8222-L049.xml (page id=8222)`
`8910-L007.xml (page id=8910)` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`8910-L044.xml (page id=8910)` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377
`8910-L049.xml (page id=8910)` <-------String Library von ChemODur!! http://forum.egosoft.com/viewtopic.php?t=233377

## Changelog:

### 17.03.2009: v beta 07

- Das aufrufen des Kommandos beendet jetzt keine anderen auf dem Schiff laufenden Kommandos mehr.
- Bei der Warenauswahl wird jetzt auch der aktuelle Lagerstand, die Transportklasse und das Volumen jeder Ware angezeigt.
- String-Library von ChemODur zum Formatieren verwendet.

### 13.03.2009: v beta 06

- Frachtdrohnen laden nun keine installierten Waren mehr ein.

### 13.03.2009: v beta 05

- Die Skriptversion wird nun im Hauptfenster des Frachtaustauschs oben rechts angezeigt. (Ja, mir ist langweilig)

### 11.03.2009: v beta 04

- Wenn die Drohne an fremden Stationen einkaufen geschickt wird, wartet sie, bis der Spieler genug Geld hat, anstatt den Rest einfach einzuladen, ohne zu bezahlen.

### 09.03.2009: v beta 03

- Englischen Sprachsupport hinzugefügt

### 09.03.2009: v beta 02

- Bestätigungston "Kommando akzeptiert" hinzugefügt

- Verhalten der Drohne beim Anflug beweglicher Ziele verbessert, wenn diese den Sektor wechseln

- Problem bei der Warenauswahl behoben, wenn man bei der Eingabe der Anzahl mit Esc abgebrochen hat

- Problem behoben, durch das mehr Drohnen gestartet wurden, als im Frachtraum vorhanden waren

- Problem behoben, wodurch die erste Ware eines Schiffs/einer Station nicht in der Auswahlliste angezeigt wurde


### 07.03.2009: v beta 01

- Erstausgabe
