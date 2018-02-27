#---
#title: "Overview Libre Solar"
#excerpt: ""
#permalink: /solarbox/libre_solar_overview/
#---

In diesem Kapitel wollen wir ersteinmal ganz allgemein erklären um was es sich bei Libre Solar handelt, welche Komponenten darin enthalten sind und für welche Anwendungen es genutzt werden kann.

Libre Solar ist ein Open Hardware Projekt für den Aufbau eines lokalen Energienetzes auf Basis von regenerativen Energiequellen. Libre Solar beinhaltet die benötigten elektrischen Platinen, welche zwischen Energieerzeuger (Solarpanele), Energiespeicher (Batterien) und der Last (elektrische Geräte, die wir mit Strom versorgen möchten) zusammengeschaltet werden. Damit kann ein modulares Gesamtsystem aufgebaut, je nach Leistungs- und Speicherbedarf, können mehrere Platinen miteinander verschaltet werden.


## Kurzbeschreibung der Komponenten

![roadmap](/media_files/pcb_MPPT_charger_20A_rendered.png)

Folgende Komponenten sind Bestandteil des Libre Solar Projekts
- **MPPT** (Maximum Power Point Tracker)
- **BMS** (Battery-Management-System)
- **CAN2Wifi** (Kommunikations-Gateway)

### MPPT
Das MPPT Modul stellt einen Solarladeregler dar. Dieser speist die elektrische Leistung aus den Solarpanels (Hinweis: es können dabei nicht nur Solarpanels als Quelle genutzt werden, sondern auch Kleinwindanlagen oder Fahrradgeneratoren) in den angeschlossenen Batteriespeicher. Ein direktes Anschließen von Solarpanels an eine Batterien, würde die Batterie nach kurzer Zeit zerstören, da keinerlei Überwachung der Spannungen und Ströme erfolgt und damit die Betriebsvorschriften der Batterie nicht eingehalten werden. Daher ist ein Laderegler zwingend erforderlich.

Die Besonderheit eines MPPT Ladereglers ist die optimale Leistungsentnahme eines Solarmoduls. Dies wird durch das Nachverfolgen (Tracking) der Spannungs/Stromkennlinie realisiert.
Eine genaue Beschreibung des MPPT Verfahrens ist unter folgendem Wikipedia Artikel -[Maximum Power Point Tracking](https://de.wikipedia.org/wiki/Maximum_Power_Point_Tracking)- zu finden.
Der Vorteil dieses Verfahrens ist der wesentlich höhere Wirkungsgrad von 95% bis 99%. Zum Vergleich haben einfache Laderegler ohne MPPT Funktion, die einen Wirkungsgrad von ca. XX.


Die grundlegenden Aufgaben des Libre Solar MPPT Ladereglers sind:
- Verhindern des Überladens durch Überspannung
- Verhindern von Überstrom durch Begrenzung des Ladestromes
- PV short circuit
- PV reverse polarity
- Battery reverse polarity (destructive, fuse is blown)
- Stabilisierung der Ausgangsspannung auf einem Spannungslevel

Der verbaute Mikrocontroller erlaubt durch einfache Softwareanpassung das Anschließen von verschiedenen Energiequellen und Energiespeichern.

### BMS
Das BMS Modul ist optional notwendig sobald Lithium Ionen Batterien verwendet werden.
Bei Lithium Ionen Batterien weisen eine hohe Energiedichte aus, also die Energiegehalt pro kg. Somit eignen sie sich besonders gut für mobile Anwendungen, wie etwas in der Elektromobilität oder im Consumerbereich. Die Akkus in unseren Handy sind ebenfalls Lithium Ionen Batterien.
Ein Nachteil dieses Batterientyps ist die Empfindlichkeit gegenüber Überspannung und Tiefenentladung. Daher benötigen sie eine vorgeschaltete elektrische Schaltung, die diese Überwachungsfunktionen abdeckt, ein sog. Batteriemanagementsystem (BMS).

Neben den Sicherheitsfunktionen führt das BMS Modul ein Balancing der angeschlossenen Batterien durch. Dies ist notwendig sobald mehr als eine Batteriezelle in Reihe geschaltet wird. Durch Lade- und Entladeprozesse kann die Kapazität zwischen den einzelnen Batteriezellen voneinander wegdriften. Dieser Effekt führt auf Dauer zu einer geringer Lebensdauer der Batterien und zu einer geringerer Energieaufnahme. Durch das Balancing wird diesem Effekt entgegengewirkt indem durch Ausgleichströme zwischen den Zellen die Kapazität angeglichen wird (balance).
Eine genaue Beschreibung des Balancing Verfahren kann unter folgendem Wkipedia Artikel - [Balancer](https://de.wikipedia.org/wiki/Balancer) - eingesehen werden.

### CAN2Wifi
Das CAN2Wifi Modul stellt ein Kommunikationsgateway mit dessen Hilfe Daten aus den beiden anderen Modulen (MPPT und BMS) via [CAN Bus](https://en.wikipedia.org/wiki/CAN_bus) aufbereitet und durch eine Umsetzung auf W-Lan über ein Webinterface visualisiert werden können.
Dadurch ergeben sich viele Möglichkeiten im Bereich Internet of Things (IoT). Ein Beispiel für die Visualisierung von Energiedaten ist das Open Hardwareprojekt [Open Energy Monitor](https://openenergymonitor.org/).

Eine Beispieldarstellung der Energiewerte ist im folgendem Bild zu sehen.

![OEM](/media_files/introduction_openenergymonitor.png)
