# AWS

Questi passaggi guidano nella configurazione di un ambiente di lavoro su AWS, dall'archiviazione dei file su S3, alla gestione delle istanze EC2, fino all'uso della CLI per trasferire e gestire file.

### Step 1 – Creare un Bucket su S3

Un bucket è un contenitore in cui puoi memorizzare oggetti, che possono essere file, immagini, documenti, ecc.
1. **S3 -> Bucket -> Crea bucket**
2. Specificare il nome del Bucket e la regione (noi useremo quella di
Parigi: eu-west-3)
3. Lasciare «ACL disabilitate»
4. Lasciare «Blocca tutti gli accessi pubblici»
5. Cliccare su «Crea bucket»

   ![image](https://github.com/gstella03/Cloud-Computing/assets/167904147/c67e9926-6012-4ab6-bc41-eaa6a2300111)


### Step 2 – Creare una Coppia di chiavi su EC2

Un bucket è un contenitore in cui puoi memorizzare oggetti, che possono essere file, immagini, documenti, ecc.
1. Verificare di essere nella regione di Parigi
2. **EC2 -> Rete e sicurezza -> Coppie di chiavi -> Crea una coppia di chiavi**
2. Specificare il nome della coppia di chiavi
3. Selezionare il formato .pem
4. Cliccare su «Crea una coppia di chiavi»
5. È importante tenere traccia del percorso del file .pem scaricato, in
quanto ci servirà in seguito

![image](https://github.com/gstella03/Cloud-Computing/assets/167904147/09a121cd-f33d-4b0c-a9a6-ef939e8f6b28)


### Step 3 – Creare un’istanza EC2

Un'istanza EC2 è una macchina virtuale che può eseguire applicazioni su AWS.
1. **EC2 -> Istanze -> Avvia un’istanza**
2. Specificare il nome dell’istanza
3. Scegliere l’immagine Amazon Linux 2
4. Selezionare il tipo di istanza t2.micro (verificare che sia presente la
scritta «Idoneo al piano gratuito»)
5. Selezionare la coppia di chiavi creata precedentemente
6. Lasciare il resto delle impostazioni inalterate
7. Verificare la correttezza della configurazione nel «Riepilogo»
8. Cliccare su «Avvia istanza»

![image](https://github.com/gstella03/Cloud-Computing/assets/167904147/c76a0be9-a895-49ee-984b-b2bfade99048)

### Step 4 – Accedere da Terminale

1. Aprire un terminale nella directory contenente il file delle chiavi dell'istanza EC2 (es.
chiavi.pem) e digitare i seguenti comandi:
  - su Linux:
      ```
      chmod 400 chiavi.pem
      ```
      (Se ottenete un errore provate con sudo per tutti i comandi compresi i successivi)
  - Su Windows (da powershell):
      ```
      icacls.exe chiavi.pem /reset
      icacls.exe chiavi.pem /grant:r "$($env:username):(r)"
      icacls.exe chiavi.pem /inheritance:r
      ```
3. Accedere tramite ssh all’istanza EC2:
   ```
   ssh –i chiavi.pem ec2-user@<IPv4_EC2_INST>
   ```

### Step 5 – Caricare e gestire file tra S3 e EC2 tramite AWS CLI

AWS CLI è un'interfaccia a riga di comando per interagire con i servizi AWS.
1. Caricare sul bucket S3 un file qualsiasi (preferibilmente uno testuale)
2. Tramite il terminale dell’istanza provare a scaricare il file con il comando:
  ```
  aws s3 mv s3://<BUCKET>/<FILE> <LOCAL_PATH>
  ```

### Step 6 – Creare un Ruolo IAM

IAM (Identity and Access Management) permette di gestire accessi e permessi agli utenti e servizi AWS.
Per accedere al bucket S3 dalle istanze EC2 è necessario creare un
Ruolo IAM per concedere l’accesso.
1. **IAM -> Ruoli -> Crea ruolo**
2. Selezionare «Servizio AWS» come «Tipo di entità attendibile»
3. Come «Caso d’uso» selezionare «EC2»
4. Cliccare su «Successivo»
5. Selezionare la policiy «AmazonS3FullAccess»
6. Cliccare su «Successivo» e inserire il nome del ruolo

### Step 7 – Aggiungere il Ruolo IAM all’istanza EC2

Associa il ruolo IAM alla tua istanza EC2 per concedere i permessi necessari.
1. EC2 -> Istanze
2. Selezionare l’istanza
3. Operazioni -> Sicurezza- > Modifica il ruolo IAM
4. Selezionare il ruolo creato precedentemente
5. Riprovare il comando aws

### Esercizio – Caricare un file su S3 da EC2

Partendo da un file esistente in locale trovare il modo di caricarlo
tramite ssh nell’istanza. Poi tramite terminale caricare il file
dall’istanza al bucket S3.
   ```
   scp –i chiavi.pem <FILE> ec2-user@<IPv4_EC2_INST>:<REMOTE_PATH>
   aws s3 mv <FILE> s3://<BUCKET>
   ```
### Esercizio – Sorting su EC2

Creare uno script in bash sull’istanza EC2 che:
1. scarica un file dal bucket S3 formato da una lista non ordinata di
interi, uno per riga;
2. li ordina;
3. carica la lista ordinata su S3.
   
 ```
 aws s3 mv s3://<BUCKET>/numbers.txt ./numbers.txt
 sort -n -o numbers.txt numbers.txt
 aws s3 mv ./numbers.txt s3://<BUCKET>/numbers.txt
 ```
