# BSU Docker Konfiguration

[Docker](https://www.docker.com) ist eine virtualisierungssoftware, mithilfe dessen sich Software unabhängig von Betriebssystem bereitstellen lässt. Docker vereinfacht die Bereitstellung von Anwendungen, weil sich Container, die alle nötigen Pakete enthalten, leicht als Dateien transportieren und installieren lassen. Container gewährleisten die Trennung und Verwaltung der auf einem Rechner genutzten Ressourcen.

## Docker Image

Das [Docker Image](https://www.ionos.de/digitalguide/server/knowhow/docker-image/) bildet hierbei, die Blaupause womit beliebig viele Container erzeugt werden können. Das Image umfasst dabei alle Konfigurationen des Containers. (Ports, Volumen, etc..) Diese Konfigurationen werden in einem [Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) festgehalten. Das Kommando um aus einem Dockerfile ein Docker Image zu generieren ist [Docker build](https://docs.docker.com/engine/reference/commandline/build/)

```bash
docker build [Docker Image]:[Tag] [Pfad zum Docker File]
```

## Docker Container

Im [Docker Container](https://www.docker.com/resources/what-container/) lebt dann der Prozess der die Anwendung ausführt. Nachdem ein Docker Image erstellt wurde, lassen sich nun beliebig viele Docker Container aus diesem Image erzeugen. Hierbei kann man sich nun auf einem beliebigen System befinden, welches Docker installiert hat. Um einen Container zu erzeugen benutzt man das Kommando [Docker run](https://docs.docker.com/engine/reference/run/)

```bash
docker run -p [Eingangasport]:[Ausgangsport] [Docker Image]:[Tag]
```

![Aufbau](https://camo.githubusercontent.com/05c83871e6821f36653540156ec459eaa3d45359/68747470733a2f2f646f63732e646f636b65722e636f6d2f656e67696e652f696d616765732f6172636869746563747572652e737667)

## Docker Compose

Mithilfe von [Docker compose](https://docs.docker.com/compose/) lassen sich mehrere Container auf einmal erzeugen. Die `docker-compose.yml` definiert hierbei, wie dies geschehen soll. Die Datei beschreibt unter anderem welcher Port zu welchem Container weitergeleitet werden soll, welche Container unteinander kommunizieren sollen und was für gemeinsamer Speicher genutzt wird. Um nun alle Container zu starten benötigt man nur ein Kommando [Docker compose up](https://docs.docker.com/engine/reference/commandline/compose_up/).

> Dabei muss man sich im Verzeichnis der `docker-compose.yml` befinden.

```bash
docker-compose up
```

Mit [Docker compose down](https://docs.docker.com/engine/reference/commandline/compose_down/) fährt man alle Container wieder herunter.

```bash
docker-compose down
```
