# Iaas

**Infrastructure as a Service (IaaS)** è un modello di distribuzione cloud in cui un fornitore di servizi cloud gestisce e fornisce agli utenti infrastrutture IT virtualizzate tramite Internet. Questa infrastruttura può includere server virtuali, storage, reti e altri elementi fondamentali dell'IT.

### Benefici dell'IaaS

1. **Scalabilità**: Puoi scalare le risorse in base alle esigenze del momento.
2. **Agilità**: Accesso rapido alle risorse IT senza dover gestire l'hardware fisico.
3. **Elasticità**: Capacità di aumentare o ridurre le risorse in modo dinamico.
4. **Costi ridotti**: Pagamento per l'uso effettivo delle risorse, evitando investimenti in hardware costoso.
5. **Accesso globale**: Infrastrutture distribuite globalmente per ridurre la latenza e migliorare la disponibilità.
6. **Automazione**: Strumenti per automatizzare il provisioning e la gestione delle risorse.

### Componenti dell'IaaS

1. **Server virtuali**: Macchine virtuali su cui eseguire applicazioni e processi.
2. **Storage**: Spazio di archiviazione per dati e file.
3. **Rete**: Connessioni tra server e utenti o tra i componenti dell'infrastruttura.

### Principali fornitori di IaaS

1. **Amazon Web Services (AWS)**: Ampia gamma di servizi e funzionalità.
2. **Microsoft Azure**: Integrato con le soluzioni Microsoft e ampiamente supportato.
3. **Google Cloud Platform (GCP)**: Innovativo con un forte focus su IA e machine learning.
4. **IBM Cloud**: Concentrato su soluzioni aziendali e ibride.
5. **Oracle Cloud**: Orientato a servizi gestiti e applicazioni enterprise.

### Considerazioni chiave

1. **Requisiti di sicurezza**: Valutare le politiche di sicurezza e conformità del provider.
2. **Costi**: Monitorare e pianificare i costi delle risorse utilizzate.
3. **Performance**: Valutare la latenza, la disponibilità e la velocità delle risorse.
4. **Supporto**: Disponibilità e qualità del supporto tecnico.
5. **Integrazione**: Capacità di integrare l'IaaS con i sistemi IT esistenti.

### Implementazione di IaaS

1. **Identificazione delle esigenze**: Definire le risorse necessarie e i requisiti di prestazione.
2. **Scelta del provider**: Selezionare il provider che meglio soddisfa le esigenze specifiche.
3. **Provisioning**: Configurare e implementare le risorse necessarie.
4. **Gestione**: Monitorare, ottimizzare e gestire le risorse per garantire prestazioni ottimali e costi controllati.

## Amazon EC2

Amazon Elastic Compute Cloud (Amazon EC2) è uno dei servizi chiave offerti da Amazon Web Services (AWS) nell'ambito dell'Infrastructure as a Service (IaaS). EC2 consente agli utenti di eseguire macchine virtuali (chiamate istanze) su infrastrutture cloud gestite da AWS. 

### Caratteristiche principali di Amazon EC2

1. **Istanze**: Amazon EC2 consente agli utenti di creare e gestire istanze virtuali di server in base alle proprie esigenze. Le istanze possono essere avviate, interrotte e terminatate in modo flessibile.

2. **Scalabilità**: Le istanze EC2 possono essere scalate verticalmente (aumentando le risorse di CPU, memoria, ecc.) e orizzontalmente (aggiungendo più istanze).

3. **Selezione delle istanze**: AWS offre una vasta gamma di tipi di istanze con diverse capacità di CPU, memoria, storage e networking per soddisfare diverse esigenze di applicazione.

4. **Storage**: EC2 supporta varie opzioni di storage, tra cui Amazon Elastic Block Store (EBS) per storage persistente e Amazon EC2 Instance Store per storage temporaneo su disco locale.

5. **Networking**: Fornisce opzioni avanzate di rete, come la possibilità di creare reti virtuali isolate (Virtual Private Cloud - VPC), configurare subnet, definire gruppi di sicurezza e gestire indirizzi IP elastici.

6. **Gestione**: AWS Management Console fornisce un'interfaccia grafica per la gestione delle istanze EC2, mentre è anche possibile utilizzare API e strumenti della riga di comando per l'automazione e la gestione.

7. **Sicurezza**: EC2 implementa misure di sicurezza avanzate come crittografia dei dati in transito e a riposo, controllo degli accessi basato su ruoli (IAM), firewall (Security Groups), e altre funzionalità di sicurezza avanzate.

### Utilizzi comuni di Amazon EC2

1. **Hosting di applicazioni web**: Molte applicazioni web e siti web vengono ospitati su istanze EC2 per la loro scalabilità e flessibilità.

2. **Sviluppo e test**: Gli sviluppatori possono utilizzare istanze EC2 per sviluppare, testare e distribuire applicazioni senza dover investire in hardware fisico.

3. **Big Data**: EC2 è spesso utilizzato per eseguire analisi di big data su grandi set di dati, sfruttando le capacità di calcolo e di storage scalabili.

4. **Applicazioni enterprise**: Le aziende possono eseguire applicazioni aziendali, database e altri servizi critici su EC2, beneficiando della robustezza e dell'affidabilità del servizio.

## Amazon S3

Amazon Simple Storage Service (S3) è un servizio di storage oggetti offerto da Amazon Web Services (AWS), progettato per fornire scalabilità, durabilità, e facilità di gestione dei dati nel cloud.

### Caratteristiche principali di Amazon S3

1. **Storage Scalabile**: Amazon S3 consente di archiviare quantità praticamente illimitate di dati in formato oggetto, organizzati in bucket (contenitori) all'interno di una regione AWS.

2. **Durabilità e Disponibilità**: Amazon S3 è progettato per offrire una durabilità dei dati del 99.999999999% (11 9's), garantendo che i dati siano altamente protetti e disponibili.

3. **Accesso Sicuro**: Supporta l'accesso sicuro ai dati tramite controllo degli accessi, politiche di sicurezza e crittografia sia in transito che a riposo.

4. **Gestione dei Dati**: Fornisce un'interfaccia semplice per caricare e scaricare dati, nonché per gestire i permessi di accesso ai dati.

5. **Versioning**: Supporta il versioning dei file, consentendo di mantenere più versioni di un oggetto nel tempo e recuperare versioni precedenti.

6. **Lifecycle Policies**: Consente di definire politiche di lifecycle per automatizzare la gestione dei dati, ad esempio il trasferimento automatico dei dati meno frequentemente accessati a classi di storage meno costose.

7. **Integrazione**: Integrato con molti altri servizi AWS come Amazon EC2, AWS Lambda, Amazon Glacier, Amazon CloudFront, e altri, facilitando lo sviluppo di applicazioni scalabili e resilienti.

### Utilizzi comuni di Amazon S3

1. **Hosting di Siti Web Statici**: Amazon S3 può essere utilizzato per ospitare siti web statici, beneficiando della distribuzione globale tramite Amazon CloudFront per migliorare le prestazioni.

2. **Backup e Archiviazione**: Molte organizzazioni utilizzano Amazon S3 per il backup e l'archiviazione di dati critici, sfruttando la durabilità e la scalabilità offerte.

3. **Analisi dei Big Data**: Amazon S3 è spesso utilizzato come data lake per l'archiviazione di grandi quantità di dati strutturati e non strutturati, utilizzati per analisi di big data.

4. **Condivisione di Contenuti**: È possibile condividere file e contenuti pubblici o privati utilizzando URL prefirmati, consentendo l'accesso controllato ai dati.

### Sicurezza e Gestione dei Dati

Amazon S3 offre opzioni avanzate per la sicurezza dei dati, inclusi controlli di accesso basati su politiche (IAM), crittografia dei dati sia in transito che a riposo utilizzando SSL/TLS e AES-256, e monitoraggio delle attività attraverso AWS CloudTrail.

## Amazon IAM 

Amazon IAM (Identity and Access Management) è un servizio di gestione degli accessi offerto da Amazon Web Services (AWS), progettato per consentire ai clienti di gestire in modo sicuro l'accesso alle risorse AWS. Ecco una guida dettagliata su Amazon IAM:

### Caratteristiche principali di Amazon IAM

1. **Gestione degli Utenti e delle Credenziali**: IAM consente di creare e gestire utenti e gruppi di utenti in AWS. Gli utenti possono essere forniti con credenziali di accesso (username e password) o con accesso temporaneo tramite token.

2. **Controllo degli Accessi Basato su Ruoli (RBAC)**: IAM utilizza un modello di controllo degli accessi basato su ruoli, che permette di definire i permessi (autorizzazioni) necessari per ogni utente, gruppo o servizio. I ruoli possono essere assegnati in modo granulare per garantire che gli utenti ottengano solo l'accesso necessario per svolgere il proprio lavoro.

3. **Politiche di Accesso**: Le politiche di accesso IAM sono documenti JSON che definiscono i permessi. Possono essere associate a utenti, gruppi o ruoli per specificare quali azioni AWS sono consentite o negate.

4. **Multi-Factor Authentication (MFA)**: IAM supporta l'autenticazione a più fattori per aumentare la sicurezza, richiedendo un secondo fattore di autenticazione oltre alla password standard.

5. **Audit e Monitoraggio**: IAM registra le attività degli utenti e fornisce informazioni dettagliate sui cambiamenti apportati ai permessi. Queste informazioni possono essere analizzate tramite AWS CloudTrail.

6. **Integrazione con Servizi AWS**: IAM è integrato con molti altri servizi AWS, consentendo di gestire facilmente l'accesso ai servizi e di applicare le stesse politiche di sicurezza in tutto l'ambiente AWS.

### Utilizzi comuni di Amazon IAM

1. **Gestione degli Utenti**: IAM consente di creare e gestire utenti per l'accesso a specifici servizi o risorse AWS.

2. **Controllo degli Accessi**: Le politiche IAM permettono di controllare in modo preciso quali azioni possono eseguire gli utenti su quali risorse AWS.

3. **Gestione dei Ruoli**: IAM permette di definire ruoli con permessi specifici e assegnarli a utenti o servizi, facilitando l'automazione e il controllo degli accessi.

4. **Sicurezza Reforzata**: L'utilizzo di MFA e la definizione precisa delle politiche IAM contribuiscono a migliorare la sicurezza dell'ambiente AWS.

### Sicurezza e Conformità

IAM implementa misure di sicurezza avanzate per proteggere l'accesso ai dati e alle risorse, inclusa la crittografia delle credenziali, l'accesso condizionale basato su IP, e il monitoraggio dettagliato delle attività.

