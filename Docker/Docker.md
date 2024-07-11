# Docker

**Docker** è una piattaforma di containerizzazione open-source che consente agli sviluppatori di automatizzare la distribuzione di applicazioni all'interno di container leggeri e portabili. I container contengono tutto il necessario per eseguire un'applicazione, inclusi il codice, le librerie, le dipendenze e le configurazioni.

### Caratteristiche principali di Docker

1. **Isolamento**: Ogni container è isolato dagli altri, garantendo che le applicazioni non interferiscano tra loro.
2. **Portabilità**: I container Docker possono essere eseguiti su qualsiasi ambiente che supporti Docker, indipendentemente dal sistema operativo sottostante.
3. **Efficienza**: I container condividono il kernel del sistema operativo host, il che li rende più leggeri e veloci rispetto alle macchine virtuali tradizionali.
4. **Scalabilità**: Docker consente di scalare le applicazioni in modo rapido e semplice, sia orizzontalmente che verticalmente.
5. **Automazione**: Docker facilita l'automazione del ciclo di vita delle applicazioni, dalla creazione all'implementazione e gestione.

### Componenti principali di Docker

1. **Docker Engine**: È il cuore di Docker e include il runtime e le API per creare e gestire i container.
2. **Docker Images**: Un'immagine Docker è un modello di sola lettura utilizzato per creare i container. Le immagini possono essere versionate e condivise attraverso Docker Hub o altri registri di immagini.
3. **Docker Containers**: Sono istanze eseguibili delle immagini Docker. Un container esegue un'applicazione isolata dal sistema operativo host e da altri container.
4. **Docker Hub**: È un servizio di registrazione di immagini Docker, che consente di trovare, scaricare e pubblicare immagini Docker.
5. **Docker Compose**: Uno strumento per definire e gestire applicazioni multi-container. Utilizza un file YAML per configurare i servizi, le reti e i volumi richiesti dall'applicazione.

### Utilizzi comuni di Docker

1. **Sviluppo e Test**: Docker consente agli sviluppatori di creare ambienti di sviluppo coerenti con i loro ambienti di produzione, facilitando il processo di sviluppo e test.
2. **Distribuzione Continua**: Docker si integra facilmente con le pipeline di CI/CD (Continuous Integration/Continuous Deployment), automatizzando il processo di build, test e distribuzione delle applicazioni.
3. **Microservizi**: Docker è spesso utilizzato per implementare architetture a microservizi, dove ogni servizio è eseguito all'interno di un container isolato.
4. **Applicazioni Legacy**: Docker può essere utilizzato per containerizzare applicazioni legacy, facilitando la loro migrazione e gestione nei nuovi ambienti cloud.

### Vantaggi di Docker

1. **Consistenza tra ambienti**: Garantisce che il software si comporti allo stesso modo in diversi ambienti (sviluppo, test, produzione).
2. **Efficienza delle risorse**: Utilizza meno risorse rispetto alle macchine virtuali tradizionali.
3. **Velocità di Avvio**: I container possono essere avviati in pochi secondi, migliorando i tempi di sviluppo e distribuzione.
4. **Isolamento**: Migliora la sicurezza isolando le applicazioni tra loro e dal sistema operativo host.



## Comandi di Base di Docker

Ecco una guida dettagliata sui comandi di base di Docker, compresi quelli per avviare il demone Docker, ottenere aiuto, e visualizzare le informazioni di sistema.

#### 1. Avviare il demone Docker

Per avviare il demone Docker, è necessario che Docker sia installato sul sistema. Su sistemi basati su Unix (come Linux e macOS), il demone Docker viene generalmente avviato come servizio. Su Windows, Docker Desktop gestisce automaticamente il demone.

- **Linux/Unix:**
  ```sh
  sudo systemctl start docker
  ```

  Se stai usando una distribuzione che non usa `systemd`, puoi usare:
  ```sh
  sudo service docker start
  ```

  Per avviare Docker manualmente (anche se di solito è gestito come servizio di sistema):
  ```sh
  sudo dockerd
  ```

- **Windows/MacOS:**
  Avvia Docker Desktop, che avvierà automaticamente il demone Docker.

#### 2. Ottenere aiuto con Docker

Per ottenere aiuto con Docker e visualizzare una lista di tutti i comandi disponibili, puoi usare il comando seguente:
```sh
docker --help
```

Puoi anche ottenere aiuto per qualsiasi sottocomando Docker specifico. Ad esempio, per ottenere aiuto con il comando `docker run`, puoi eseguire:
```sh
docker run --help
```

#### 3. Visualizzare informazioni di sistema

Per visualizzare informazioni di sistema su Docker, inclusi i dettagli sulla versione, i contenitori, le immagini e altre informazioni utili, puoi usare:
```sh
docker info
```



## Comandi Docker per la Gestione delle Immagini

Docker fornisce una serie di comandi per la creazione, gestione e rimozione delle immagini. Ecco una guida dettagliata su questi comandi:

#### 1. Costruire un'immagine da un Dockerfile

Per costruire un'immagine Docker da un Dockerfile nella directory corrente, usa il comando seguente. Il flag `-t` permette di assegnare un nome (e facoltativamente un tag) all'immagine.
```sh
docker build -t <image_name> .
```

#### 2. Costruire un'immagine da un Dockerfile senza usare la cache

Se vuoi costruire un'immagine ignorando la cache, puoi utilizzare il flag `--no-cache`:
```sh
docker build -t <image_name> . --no-cache
```

#### 3. Elencare le immagini locali

Per visualizzare una lista di tutte le immagini Docker presenti localmente sul tuo sistema, usa il comando:
```sh
docker images
```

#### 4. Eliminare un'immagine

Per eliminare un'immagine specifica, usa il comando `rmi` seguito dal nome o dall'ID dell'immagine:
```sh
docker rmi <image_name>
```

#### 5. Rimuovere tutte le immagini inutilizzate

Per eliminare tutte le immagini Docker che non sono utilizzate da nessun container, usa il comando:
```sh
docker image prune
```



## Gestione delle Immagini Docker con Docker Hub

Docker Hub è un servizio di registrazione cloud-based che consente di condividere, distribuire e gestire le immagini Docker. Ecco una guida dettagliata su come effettuare il login, pubblicare, cercare e scaricare immagini da Docker Hub.

#### 1. Effettuare il login su Docker Hub

Per effettuare il login su Docker Hub, usa il comando `docker login` seguito dall'opzione `-u` per specificare il tuo nome utente. Ti verrà richiesta la password.

```sh
docker login -u <username>
```

#### 2. Pubblicare un'immagine su Docker Hub

Per pubblicare un'immagine su Docker Hub, usa il comando `docker push` seguito dal nome utente e dal nome dell'immagine nel formato `<username>/<image_name>`. Assicurati di aver eseguito il login su Docker Hub prima di eseguire questo comando.

```sh
docker push <username>/<image_name>
```

#### 3. Cercare un'immagine su Docker Hub

Per cercare un'immagine su Docker Hub, usa il comando `docker search` seguito dal nome dell'immagine che desideri trovare. Questo comando restituisce una lista di immagini che corrispondono al nome cercato.

```sh
docker search <image_name>
```

#### 4. Scaricare un'immagine da Docker Hub

Per scaricare un'immagine da Docker Hub, usa il comando `docker pull` seguito dal nome dell'immagine.

```sh
docker pull <image_name>
```



## Gestione dei Container Docker

Docker fornisce una serie di comandi per creare, eseguire, gestire e monitorare i container. Ecco una guida dettagliata su questi comandi.

#### 1. Creare ed eseguire un container da un'immagine, con un nome personalizzato

Per creare ed eseguire un container da un'immagine Docker, assegnando un nome personalizzato al container, usa il comando:
```sh
docker run --name <container_name> <image_name>
```

#### 2. Eseguire un container e pubblicare le porte del container sull'host

Per eseguire un container e pubblicare le porte del container sull'host, usa il comando `-p`:
```sh
docker run -p <host_port>:<container_port> <image_name>
```

#### 3. Eseguire un container in background

Per eseguire un container in background (modalità detached), usa il comando `-d`:
```sh
docker run -d <image_name>
```

#### 4. Avviare o fermare un container esistente

Per avviare un container esistente, usa il comando:
```sh
docker start <container_name> (or <container-id>)
```

Per fermare un container esistente, usa il comando:
```sh
docker stop <container_name> (or <container-id>)
```

#### 5. Rimuovere un container fermo

Per rimuovere un container che è stato fermato, usa il comando:
```sh
docker rm <container_name>
```

#### 6. Aprire una shell all'interno di un container in esecuzione

Per aprire una shell all'interno di un container in esecuzione, usa il comando `exec` con le opzioni `-it`:
```sh
docker exec -it <container_name> sh
```

#### 7. Ottenere e seguire i log di un container

Per ottenere e seguire i log di un container, usa il comando `logs` con l'opzione `-f`:
```sh
docker logs -f <container_name>
```

#### 8. Ispezionare un container in esecuzione

Per ispezionare un container in esecuzione e ottenere informazioni dettagliate su di esso, usa il comando:
```sh
docker inspect <container_name> (or <container_id>)
```

#### 9. Elencare i container attualmente in esecuzione

Per elencare i container attualmente in esecuzione, usa il comando:
```sh
docker ps
```

#### 10. Elencare tutti i container Docker (in esecuzione e fermati)

Per elencare tutti i container Docker, inclusi quelli fermati, usa il comando:
```sh
docker ps --all
```

#### 11. Visualizzare le statistiche sull'uso delle risorse

Per visualizzare le statistiche sull'uso delle risorse dei container, usa il comando:
```sh
docker container stats
```



## Comandi Dockerfile: Descrizione e Utilizzo
Un Dockerfile è un file di testo che contiene una serie di istruzioni per automatizzare la creazione di un'immagine Docker. Ogni istruzione nel Dockerfile genera un layer nell'immagine, che viene poi eseguito quando viene creato un container dall'immagine.

Ecco una descrizione dettagliata dei comandi principali utilizzati nei Dockerfile:

1. **FROM**: Specifica l'immagine di base per la build. Ogni Dockerfile deve iniziare con una istruzione `FROM`.
   ```Dockerfile
   FROM ubuntu:20.04
   ```

2. **COPY**: Copia i file o le directory dal contesto di build del Dockerfile al filesystem del container.
   ```Dockerfile
   COPY myfile.txt /app/myfile.txt
   ```

3. **ADD**: Simile a `COPY`, ma può anche estrarre archivi compressi (come tar) e scaricare URL.
   ```Dockerfile
   ADD myarchive.tar.gz /app/
   ADD http://example.com/file /app/file
   ```

4. **RUN**: Esegue un comando all'interno del container durante il processo di build. È comunemente usato per installare pacchetti o eseguire script.
   ```Dockerfile
   RUN apt-get update && apt-get install -y python3
   ```

5. **CMD**: Imposta il comando predefinito da eseguire quando un container viene avviato dall'immagine. Può essere sovrascritto con `docker run`.
   ```Dockerfile
   CMD ["python3", "app.py"]
   ```

6. **USER**: Imposta l'utente predefinito che eseguirà i comandi successivi all'interno del container.
   ```Dockerfile
   USER appuser
   ```

7. **WORKDIR**: Imposta la directory di lavoro predefinita per i comandi `RUN`, `CMD`, `ENTRYPOINT`, `COPY` e `ADD`.
   ```Dockerfile
   WORKDIR /app
   ```

8. **ENV**: Imposta una variabile d'ambiente.
   ```Dockerfile
   ENV APP_ENV=production
   ```

9. **EXPOSE**: Informa Docker che il container ascolterà sulla(s) porta(e) specificata(e) durante il runtime.
   ```Dockerfile
   EXPOSE 80
   ```

10. **ENTRYPOINT**: Configura un container in modo che si comporti come un eseguibile. Differisce da `CMD` perché non può essere sovrascritto facilmente con `docker run`.
    ```Dockerfile
    ENTRYPOINT ["python3", "app.py"]
    ```
