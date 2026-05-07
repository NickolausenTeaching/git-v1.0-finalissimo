
+++

title = "Introduzione a Git"
description = "Lezione introduttiva per STA-i"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

##### Istituto Tecnico Tecnologico "Blaise Pascal" **@** Cesena 

# Version Control Systems: **Git**
## "**g**lobal **i**nformation **t**racker"
<small>
{{% markdown %}}

or ~"**g**oddamn **i**diotic **t**ruckload of sh*t"~

{{% /markdown %}}
</small>

A cura di Luca Casadei, Nicholas Magi

<small>
e con il prezioso contributo di Luca Pulga
</small>

<br/>

{{% pdf %}}

---

{{% section %}}

## Fino ad ora - pt. 01

![](imgs/versioning-filesystem.png)

---

## Fino ad ora - pt. 02

![](imgs/versioning-email.png)

---


![](imgs/versioning-gdocs.png)

### Fino ad ora - pt. 03

---

<i style="font-size: 15rem" class="bi bi-emoji-dizzy-fill"></i>

{{% /section %}}

---

# Sistemi di versionamento

{{% callout type="note" %}}

**Version control**, also known as source control, is the practice of tracking and managing changes to software code.

[[Atlassian - What is version control]](https://www.atlassian.com/git/tutorials/what-is-version-control)
{{% /callout %}}

---

## Benefici principali


{{% fragment %}}
### **#1. Tracciabilità completa**

È possibile tracciare la cronologia completa delle modifiche apportate ad un progetto.
{{% /fragment %}}

{{% fragment %}}
### **#2. Ripristino semplice**

È possibile tornare a versioni precedenti del progetto senza causare danni collaterali.
{{% /fragment %}}

{{% fragment %}}
### **#3. Collaborazione agevolata** 

I membri del team possono lavorare su ramificazioni diverse del progetto, così da evitare sovrapposizioni e da suddividere agilmente i compiti.
{{% /fragment %}}

---

## Tipologie di sistemi di versionamento

{{% multicol %}}
{{% col %}}
### Centralizzato
[Centralized Versioning Control System]

{{% /col %}}
{{% col %}}
### Distribuito
[Distributed Versioning Control System]

{{% /col %}}
{{% /multicol %}}

<img class="w-50 exclude" src="imgs/centralized-vs-distributed.png"/>

---

{{% section %}}
## **CVCS**

### **C**entralized **V**ersioning **C**ontrol **S**ystem

Esiste un **unico progetto centrale**, e ogni sviluppatore lavora su una copia dell'ultima versione del codice.

---

| **<u>Caratteristica</u>**        | **<u>Descrizione</u>**           |
| ------------- |:-------------|
| **Progetto centrale**      | Tutti i file di un progetto sono salvati in una località centralizzata. |
| **Storico delle versioni**      | Lo storico delle versioni del progetto è centrale (vive insieme al progetto).      |
| **Collaborazione in tempo reale** | Gli sviluppatori lavorano sulla stessa codebase, accedendo alla stessa versione del progetto e ricevendo gli stessi aggiornamenti dai colleghi.      |
| **Installazione semplice** | I CVCS sono relativamente semplici da installare e inizializzare. |

---

### CVCS Popolari

{{% multicol %}}
{{% col %}}

<div class="card p-5">
  <img class="exclude card-img-top" src="https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.yolinux.com%2FTUTORIALS%2Fimages%2FtkCVS-Browse.png&f=1&nofb=1&ipt=215528fab5d306e483e0896d8cb10657aae4d9022d4f707d6dfafc916f88686a" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>Concurrent Versions System</strong>
    <p class="card-text">
        Sviluppato negli anni '80, ancora in utilizzo. Presenta alcune limitazioni critiche, risolte da sistemi sviluppati successivamente.
    </p>
    <small class="mt-3">
       <a href="https://web.archive.org/web/20140709051732/http://ximbiot.com/cvs/manual/"> 
       Scopri di più [Documentazione ufficiale] 
       </a>
    </small>
  </div>
</div>

{{% /col %}}
{{% col %}}

<div class="card p-5">
  <img class="exclude card-img-top" src="https://subversion.apache.org/images/svn-name-banner.svg" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>Apache Subversion</strong>
    <p class="card-text">
        Creato per risolvere le criticità di CVS. Server centralizzato, deve essere mantenuta una connessione costante per poter lavorare. 
    </p>
    <small class="mt-3">
        <a href="https://subversion.apache.org/">
        Scopri di più [Documentazione ufficiale]
        </a>
    </small>
  </div>
</div>

{{% /col %}}
{{% col %}}

<div class="card p-5">
  <img class="exclude card-img-top" src="https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fpngimg.com%2Fuploads%2Fibm%2Fibm_PNG19658.png&f=1&nofb=1&ipt=94b9b5d5e7e6af83e3b0c72316b8ca09124cacbd0a1c738be28d97c11a217934" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>IBM Rational ClearCase</strong>
    <p class="card-text">
        Sistema molto robusto utilizzato nelle aziende enterprise. Funzionalità avanzate per ambienti di sviluppo complessi.
    </p>
    <small class="mt-3">
        <a href="https://www.ibm.com/docs/en/clearcase">
        Scopri di più [Documentazione ufficiale]
        </a>
    </small>
  </div>
</div>

{{% /col %}}
{{% /multicol %}}
{{% /section %}}

---

{{% section %}}

## **DVCS**

### **D**ecentralized **V**ersioning **C**ontrol **S**ystem

Ogni sviluppatore lavora su una **copia del progetto** di riferimento, disponendo sul proprio dispositivo di tutto lo storico delle modifiche di quest'ultimo. 

---

| **<u>Caratteristica</u>**        | **<u>Descrizione</u>**           |
| ------------- |:-------------|
| **Progetti completamente locali**      | Tutti i file di un progetto sono salvati in locale. Possibilità di lavorare offline. |
| **Diramazioni dello sviluppo**      | I DVCS facilitano la diramazione dello sviluppo, permettendo di lavorare in maniera isolata su una funzionalità per poi riconciliarla con la codebase principale.      |
| {{% cross %}} **Nessun *Single Point Of Failure*** | Se il progetto centrale dovesse essere perso, lo si può facilmente ricostruire partendo dalle copie a disposizione di chi ci stava lavorando.      |
| **Collaborazione** | I DVCS permettono, attraverso un meccanismo di *pull/push* (vedremo tra poco), una collaborazione "decentralizzata". |

---

### DVCS Popolari

{{% multicol %}}
{{% col %}}

<div class="card p-5">
  <img class="exclude card-img-top w-50 mx-auto" src="https://www.mercurial-scm.org/_static/logo-square-dark.svg" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>Mercurial</strong>
    <small class="mt-3">
       <a href="https://www.mercurial-scm.org/"> 
       Scopri di più [Documentazione ufficiale] 
       </a>
    </small>
  </div>
</div>

{{% /col %}}
{{% col %}}

<div class="card p-5 border-warning">
  <img class="exclude card-img-top w-50 mx-auto" src="https://git-scm.com/images/logo@2x.png" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>Git</strong>
    <small class="mt-3">
        <a href="https://git-scm.com/">
        Scopri di più [Documentazione ufficiale]
        </a>
    </small>
  </div>
</div>
<br/>
{{% callout type="tip" %}}

$\uparrow$

Noi approfondiamo questo!
{{% /callout %}}

{{% /col %}}
{{% col %}}

<div class="card p-5">
  <img class="exclude card-img-top w-50 mx-auto" src="https://duckduckgo.com/i/23196d99ae092af9.png" alt="Card image cap">
  <div class="card-body d-flex flex-column">
    <strong>GNU Bazaar</strong>
    <small class="mt-3">
        <a href="https://documentation.help/Bazaar-help/tutorial.html">
        Scopri di più [Documentazione]
        </a>
    </small>
  </div>
</div>

{{% /col %}}
{{% /multicol %}}

---

## Da qui in poi iniziamo a parlare di **Git**.

{{% /section %}}

---

## <strong><i class="bi bi-git"></i></strong> **Git**

{{% multicol %}}
{{% col %}}

<img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.arstechnica.net%2Fwp-content%2Fuploads%2F2015%2F08%2FLinuxCon_Europe_Linus_Torvalds_05-2048x2048.jpg&f=1&nofb=1&ipt=750346aa0b0ac25ece9ab4b18a13b5613062d4b87d199a7d0ea009de3bb2ceed" class="w-75"/>

<i class="display-3 bi bi-tux"></i>

{{% /col %}}
{{% col %}}

- DVCS più **conosciuto** e **utilizzato**
- Software **libero** e **open-source**
- Sviluppato nell'arco di 2 settimane da **Linus Torvalds**.
    - sviluppatore, tra le altre cose, del kernel **Linux**
    - dopo un cambio di licenza sgradito di BitWarden, sistema precedentemente utilizzato per versionare Linux

<br class="my-3">

{{% callout title="Nice to know" %}}

Il nome "*Git*" non è un acronimo! In inglese, è un "insulto leggero" che Torvalds usa per descrivere sé stesso.

{{% /callout %}}

{{% /col %}}
{{% /multicol %}}

---

## Tassonomia di Git

{{% callout %}}

Da ora in poi ci riferiamo al **progetto** su cui lavoriamo con il termine di **repository**. 

{{% /callout %}}

---

Qualora, durante lo sviluppo di un progetto volessi salvarne lo stato, dovrei catturarne uno *snapshot*.

<br>

{{% callout %}}

Nella tassonomia di Git, ci si riferisce a questa pratica con il termine "**commit**".

{{% /callout %}}

---

{{% section %}}
## Storico di un progetto

Stiamo lavorando su un progetto all'avanguardia: 

### `PrimeSequence.kt`

---

### Step 0: Creazione di una **repository**

- Per poter permettere a `Git` di tracciare l'evoluzione di un progetto, occorre inizializzare la **repository** su cui andremo a lavorare.

<br>

{{% callout %}}
Se volessimo lavorare in CLI, scriveremmo:
`git init`
{{% /callout %}}

<br/>
{{% callout %}}

<small>

CLI $\rightarrow$ "Command Line Interface", *interfaccia a riga di comando*

</small>

{{% /callout %}}

---

```mermaid
gitGraph
   commit id: "Initial commit"
```

---

```mermaid
gitGraph
   commit id: "Initial commit"
   commit id: "First tests"
```

---

```mermaid
gitGraph
   commit id: "Initial commit"
   commit id: "First tests"
   commit id: "Method `isPrime`..."
```

---

```mermaid
gitGraph
   commit id: "Initial commit"
   commit id: "First tests"
   commit id: "Method `isPrime`..."
   commit id: "..."
```

---

```mermaid
gitGraph
   commit id: "Initial commit"
   commit id: "First tests"
   commit id: "Method `isPrime`..."
   commit id: "..."
   commit id: "Finished!" type: HIGHLIGHT
```

{{% /section %}}