## Dal DevOps al Platform Engineering nel Mondo Java: Perché Jakarta EE È un Vantaggio Competitivo (di Angelo Rubini)

L'articolo nasce da una serie di letture e riflessioni sull'argomento DevOps, Platform Engineering e jakarta ee.
Negli ultimi anni, il movimento DevOps ha permesso ai team di sviluppo di assumersi responsabilità sull’intero ciclo di vita delle applicazioni. Ma questa autonomia ha portato anche un aumento del carico cognitivo, spesso al punto da rallentare l’innovazione e compromettere la sostenibilità operativa dei team.

Il Platform Engineering nasce come risposta a questa complessità, riflettendo principi ormai riconosciuti nel settore: **si focalizza sulla creazione di una piattaforma interna (IDP) che standardizza, automatizza e semplifica tutto ciò che non è sviluppo puro, trattando la delivery del software come un prodotto a sé stante con l'obiettivo primario di migliorare la Developer Experience (DevEx)**. Questa piattaforma restituisce velocità ai team e valore al business, riducendo il carico cognitivo sugli sviluppatori applicativi.

Nel mondo Java enterprise, due paradigmi si confrontano:

* **Spring Boot con Uber JAR:** flessibile, autonomo, ma infrastrutturalmente "nudo".
* **Jakarta EE (ex Java EE):** tradizionale, ma già dotato di una logica di piattaforma integrata.

Questo articolo mostra come Platform Engineering e Jakarta EE insieme siano un alleato potente per accelerare il time-to-market, ridurre i costi e aumentare la sostenibilità tecnologica, sfruttando i vantaggi intrinseci di Jakarta EE in termini di piattaforma integrata, riduzione del carico cognitivo e facilità di standardizzazione.

### DevOps, Carico Cognitivo e Java

Il DevOps ha portato a una rivoluzione positiva: gli sviluppatori non si limitano più a scrivere codice, ma lo rilasciano, lo monitorano e lo mantengono in esercizio.

Tuttavia, in ambienti complessi – come quelli Java – questo modello può trasformarsi in un boomerang:

* Deploy, configurazioni YAML, Docker, Helm, monitoring, sicurezza: tutto ricade sul team.
* Ogni progetto ricostruisce l’infrastruttura di base.
* La coerenza tra ambienti, la compliance e la qualità diventano fragili.
* **La manutenzione e l'evoluzione del runtime, inclusi gli aggiornamenti delle librerie di sistema e la gestione delle patch di sicurezza, sono a carico diretto del team di sviluppo.**

L’effetto collaterale? Gli sviluppatori spendono sempre più tempo in attività non core, il che rallenta la delivery e genera costi non visibili ma elevatissimi.

### Platform Engineering: Sollevare il Team, Spingere il Business

Il Platform Engineering mira a creare un layer di astrazione tra l’applicazione e l’infrastruttura. L’obiettivo non è togliere controllo, ma semplificare, standardizzare e accelerare.

Con una Internal Developer Platform (IDP), idealmente costruita su fondamenta che già offrono servizi centralizzati come nel caso di Jakarta EE, i team ottengono:

* Deploy self-service in pochi click o comandi.
* Configurazioni centralizzate e standardizzate, facilitate dalla natura stessa dell'application server Jakarta EE quando questo è il fondamento.
* Tooling integrato: logging, tracing, alerting, gestione dei segreti.
* Risorse condivise, come database, code di messaggi, storage, spesso gestite centralmente in un ambiente Jakarta EE.
* Ambienti riproducibili, sicuri, e compliant, grazie agli standard e alle policy applicate a livello di piattaforma.
* La gestione della piattaforma sottostante, inclusi gli aggiornamenti del runtime, le patch di sicurezza dell'application server e l'aggiornamento delle librerie di sistema, è centralizzata e gestita dai team di Platform o Operations, sollevando i team di sviluppo da questa responsabilità.

Il risultato? Meno tempo perso, meno errori, più velocità di rilascio e un business che vede il valore prima.

### Java: Spring Boot Uber JAR vs Jakarta EE

Ecco dove il mondo Java presenta due filosofie opposte.

🧱 **Spring Boot con Uber JAR**

* Ogni servizio è autosufficiente, ma anche autoresponsabile.
* Il team gestisce: build, Docker, deploy, sicurezza, configurazioni, osservabilità, tuning JVM, ecc.
* **La gestione del runtime e l'aggiornamento delle librerie integrate nell'Uber JAR sono responsabilità dirette del team di sviluppo per ogni singolo servizio.** Questo include l'identificazione delle vulnerabilità, la compatibilità tra librerie e l'esecuzione dei test di regressione a ogni aggiornamento.
* Nessuna “piattaforma” nativa: la devi costruire da zero, implicando un significativo investimento in tempo e risorse per replicare funzionalità che altri paradigmi offrono out-of-the-box.
* Elevato carico cognitivo + rischio di duplicazione di sforzi, proprio perché ogni team deve farsi carico dell'intero stack operativo e infrastrutturale. Ogni microservizio tende ad avere la sua configurazione individuale e la standardizzazione e sicurezza devono essere implementate e costruite manualmente.

📇 **Jakarta EE**

* Basato su un application server che fornisce nativamente una piattaforma integrata con: Runtime, pooling di risorse (come connessioni DB e thread), sicurezza, logging, risorse JNDI, ecc. – servizi essenziali che sollevano i team da compiti infrastrutturali complessi e riducono le responsabilità DevOps dirette.
* **La manutenzione e l'aggiornamento dell'application server, che include la gestione del runtime e l'aggiornamento centralizzato delle librerie di sistema e delle patch di sicurezza, sono delegati ai team di Platform o Operations. Questo consente ai team di sviluppo di concentrarsi sulla business logic.**
* Configurazioni centralizzate e dichiarative (es. tramite web.xml, annotazioni, o console di gestione del server), che semplificano la gestione e la coerenza tra ambienti.
* Un’architettura piattaformata per design, che riduce drasticamente il carico cognitivo del team di sviluppo.
* Il team si concentra sulla business logic, mentre l’application server si occupa del contesto operativo. Questo si traduce in una netta riduzione delle responsabilità DevOps dirette per gli sviluppatori applicativi.
* Più predisposto alla standardizzazione, automazione e controllo centralizzato, grazie alle sue funzionalità integrate di sicurezza (JAAS, ruoli definiti a livello server) e gestione delle risorse. Questo facilita anche una velocità di onboarding superiore per nuovi progetti e membri del team, che possono contare su template e profili e risorse già configurate.
* La sua struttura intrinsecamente orientata ai servizi condivisi e standardizzati rende Jakarta EE particolarmente adatta all'integrazione in una IDP, richiedendo meno customizzazioni e sforzi di standardizzazione attiva rispetto ad approcci che partono da una base più 'nuda'.

💡 Jakarta EE è, di fatto, un precursore naturale del Platform Engineering, fornendo out-of-the-box molti degli elementi che una piattaforma interna si prefigge di offrire.

### Tabella Comparativa: DevOps e Platform Engineering in Java

| Aspetto                      | Spring Boot (Uber JAR)                                                                                                 | Jakarta EE                                                                                                                                                            |
| :--------------------------- | :--------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Piattaforma integrata        | ❌ No – Ogni team costruisce la propria                                                                                 | ✅ Sì – Application server fornisce runtime e servizi di base                                                                                                            |
| Responsabilità DevOps        | Molte: build, runtime, configurazione, sicurezza, monitoring, **aggiornamento librerie/runtime** | Limitate: concentrate sulla logica applicativa. **Aggiornamento librerie/runtime gestito centralmente.** |
| Facilità di integrazione IDP | Bassa: richiede tool custom e standardizzazione attiva                                                                 | Alta: già strutturato per ambienti condivisi e standardizzati                                                                                                          |
| Carico cognitivo del team    | Elevato: ogni aspetto operativo è gestito dal team, **inclusa la gestione del runtime e delle librerie.** | Basso: la piattaforma si occupa della maggior parte delle problematiche operative, **inclusi gli aggiornamenti del runtime e delle librerie di sistema.** |
| Scalabilità e microservizi   | Naturale, ma richiede molta infrastruttura e gestione individuale per ogni servizio                                      | Nativamente supportata: architettura modulare (es. EJB, WAR, EAR), separazione e distribuzione dei componenti                                                           |
| Configurazione centralizzata | No, ogni microservizio ha la sua configurazione (o richiede config server esterni)                                     | Sì, tramite container di risorse condivise, JNDI, e descrittori di deployment a livello server                                                                         |
| Standardizzazione e sicurezza| Manuale e da costruire per ogni progetto                                                                               | Integrata e configurabile a livello di server (JAAS, policy, ecc.)                                                                                                    |
| Velocità di onboarding       | Lenta – ogni nuovo servizio parte da zero infrastrutturalmente                                                         | Veloce – usa template, profili e risorse già configurate a livello di piattaforma                                                                                      |

### Scalabilità e Microservizi

🧱 **Spring Boot con Uber JAR**

Offre un approccio nativamente compatibile con i microservizi, con deploy autonomi e runtime embedded. Tuttavia, richiede uno sforzo infrastrutturale importante per ogni singolo servizio: dal build system, alla gestione del deploy, alla configurazione, all’osservabilità. La gestione indipendente del runtime e delle dipendenze incluse nell'Uber JAR per ogni microservizio aumenta il carico operativo e il rischio di disallineamenti tra i vari servizi.

📇 **Jakarta EE**

Contrariamente a un pregiudizio diffuso, Jakarta EE è da sempre modulare e scalabile, sin dai tempi di J2EE. La sua architettura non solo supporta la scalabilità ma la promuove in modo strutturato e centralizzato.

I moduli EJB, i WAR indipendenti, e le EAR che incapsulano più componenti erano già un modello di architettura distribuita e componentizzata.

L’application server consente la separazione tra moduli di business, risorse condivise (come pool di connessioni, code JMS) e logica remota, con responsabilità chiaramente definite, un aspetto cruciale per una sana architettura a microservizi gestita tramite una piattaforma. La gestione centralizzata del runtime e delle librerie di sistema a livello di application server semplifica notevolmente l'aggiornamento e la manutenzione dell'infrastruttura sottostante per tutti i microservizi deployati su di esso.

Con le evoluzioni recenti (es. MicroProfile, che estende Jakarta EE per i microservizi), Jakarta EE può convivere efficacemente anche con ambienti cloud-native, offrendo una base solida e standardizzata per la costruzione di microservizi che beneficiano di una gestione centralizzata del ciclo di vita e delle risorse.

📌 Il modello Jakarta EE non solo supporta la scalabilità, ma lo fa in modo strutturato, centralizzato e con responsabilità separate – esattamente ciò che oggi chiamiamo “platform-aware architecture”, riducendo la necessità di costruire da zero molte delle fondamenta richieste da un approccio a microservizi in contesti di Platform Engineering.

### L’evoluzione del Platform Engineering nel Mondo Java

| Era                 | Architettura          | Caratteristiche                                    |
| :------------------ | :-------------------- | :------------------------------------------------- |
| J2EE (anni 2000)    | Application Server    | Modularità, EJB, EAR, Configurazione centralizzata |
| Java EE (2010-2018) | Runtime standardizzato| CDI, REST, JPA, EJB Lite, Sicurezza, Transazioni   |
| Jakarta EE (2019+)  | Cloud-ready           | MicroProfile, JSON-P/B, OpenAPI, Health, Metrics   |
| Platform Eng. (oggi)| Internal Dev Platform | Self-service, standard, DX, Automazione, velocità  |
|                     | su Jakarta EE         |                                                    |

Questa progressione mostra come Jakarta EE abbia posto solide basi architetturali, e come oggi il Platform Engineering le valorizzi ulteriormente per ottenere agilità, governance e scalabilità senza sacrificare la robustezza enterprise.

### Conclusione: Jakarta EE + Platform Engineering = Valore

Non solo Jakarta EE è compatibile con un approccio Platform Engineering: è storicamente uno dei primi esempi concreti di architettura enterprise con separazione dei ruoli, componentizzazione e scalabilità.

A differenza di Spring Boot, dove tutto va costruito e la gestione del runtime e delle librerie è delegata a ogni singolo team, Jakarta EE fornisce un ecosistema integrato e pronto all’uso – con vantaggi tangibili in termini di piattaforma nativa, riduzione del carico cognitivo, configurazioni centralizzate, standardizzazione e sicurezza integrate, e una più rapida integrazione in IDP – che Platform Engineering può semplicemente rendere più accessibile, automatizzato e self-service. In questo modello, la manutenzione del runtime e l'aggiornamento delle librerie di sistema diventano una responsabilità centralizzata dei team di piattaforma, liberando gli sviluppatori per concentrarsi sulla logica di business.

♻ DevOps ha dato autonomia.
🛠️ Platform Engineering restituisce efficienza.
💡 Jakarta EE ti dà un vantaggio strategico, oggi più che mai.
