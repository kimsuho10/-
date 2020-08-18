# ioBroker 이미지 for Raspberry Pi2 / 3 / 4 Buster 20191127
2
​
삼
## Erzeugen einer µ-SD Karte
4
Raspberry Pi2, Pi3, Pi3 B + 또는 Pi4에 대한 SD-Karten 이미지를 죽입니다. 
5
​
6
Raspberry Pi4 mit 4GB RAM erzeugt, sollte aber에 대한 Das Image wurde auf einem 
7
auch auf allen genannten laufen. Es ist für 8 GB Karten und größer passend. Eine 16 GB ist jedoch die empfohlene Mindestgröße.
8
16GB Karten sind sowieso empfohlen damit nicht immer die selben Zellen beschrieben werden.
9
​
10
Das Image wird entpackt und anschließend mit Hilfe des Programms Balena Etcher auf die SD-Karte geschrieben. Etcher는 verschiedene Betriebssysteme에 대한 정보를 제공합니다.
11
​
12
## Bestandteile des 이미지
13
Das Image enthält das Raspbian lite, basierend auf Debian 10“Buster”vom 26.09.2019 nach download von http://www.raspberrypi.org/downloads .
14
​
15
Zusätzlich wurden noch Pakete, die für einige Adapter notwendig sind, installiert.
16
​
17
Folgender 사용자 ist angelegt :
18
​
19
* 사용자 : `pi` ,
20
* 암호 : `라즈베리`
21
​
22
Node-js ist in der Version 10.17.0 installiert sowie natürlich iobroker über den installer mit dem js-controller ** v2.1.1 ** nach Stand vom 27.11.2019.
23
​
24
Es handelt sich um eine ** Minimalinstallation ** , die nur den admin, den Info- und den discovery-Adapter ** enthält.
25
Weitere Adapter sowie deren Instanzen müssen noch angelegt und konfiguriert werden.
26
​
27
Das Anlegen von weiteren Adaptern und deren Instanzen wird [hier] (/tutorial/adapter.md) beschrieben.
28
​
29
** 힌 웨이스! **
30
Die folgende Anleitung wurde nach bestem Wissen mit den Informationen zum Zeitpunkt der Erstellung des Images erstellt. Durch 업데이트 von Paketen oder des
31
kann sich da jederzeit etwas ändern.
32
​
33
Das Image ist für Deutschland lokalisiert. Bei Nutzung in anderen Umgebungen bitte entsprechend anpassen. ( `sudo raspi-config` ; 4.) 현지화 옵션)
34
 
35
​
36
## Nach dem ersten Start
37
Nach dem ersten Starten des Rapberry Pi bitte mit`sudo raspi-config` folgende Einstellungen vornehmen :
38
​
39
* Punkt 1 : `Change User passwort` (Eigenes Passwort für den User`Pi` vergeben)
40
​
41
* PUNKT 2 : '네트워크 옵션 -Hostname` (. Namen 데 라즈베리 파이 ggf. ändern Vorgabe 경악 `raspberrypi` )
42
wenn der Hostname geändert wird, bitte anschließend in der Konsole im Installationsverzeichnis`iobroker host this` eingeben
43
​
44
* Punkt 7 : `고급 옵션 – 파일 시스템 확장` (Erweitern des root-filesystems bis zur maximalen Größe der verwendeten SD-Karte)
45
​
46
* ggf. noch unter Punkt 4 : `현지화 옵션` Anpassungen vornehmen. Die Voreinstellungen gelten für Deutschland
47
 
48
​
49
 
50
​
51
## 시스템 업데이트
52
Da zum Zeitpunkt des 다운로드 bereits einige Zeit seit der Erstellung des 이미지 vergangen sein kann, sollte man als erstes das System auf den neuesten Stand bringen.
53
​
