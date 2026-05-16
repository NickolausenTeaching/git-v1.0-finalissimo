
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

<br/>
<br/>

<small class="text-muted">
    <a href="https://creativecommons.org/licenses/by-sa/4.0/">
    Copyleft 2026 — CC-BY-SA
    </a>
</small>

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
(Centralized Versioning Control System)

<img class="w-50 exclude" src="imgs/centralized.png"/>

{{% /col %}}
{{% col %}}
### Distribuito
(Distributed Versioning Control System)

<img class="w-50 exclude" src="imgs/distributed.png"/>

{{% /col %}}
{{% /multicol %}}

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
  <img class="exclude card-img-top" src="imgs/cvs.png" alt="Card image cap">
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
  <img class="exclude card-img-top" src="imgs/svn.png" alt="Card image cap">
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
  <img class="exclude card-img-top w-50 mx-auto mb-5" src="imgs/git.svg" alt="Card image cap">
  <small>
    Jason Long, CC BY 3.0 <https://creativecommons.org/licenses/by/3.0>, via Wikimedia Commons
  </small>
  
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
  <img class="exclude card-img-top w-50 mx-auto" src="https://upload.wikimedia.org/wikipedia/commons/f/f1/Bazaar-passo-2_-_Copia.png?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original" alt="Card image cap">
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

{{% section %}}

## <strong><i class="bi bi-git"></i></strong> **Git**

{{% multicol %}}
{{% col %}}

<img src="https://upload.wikimedia.org/wikipedia/commons/0/01/LinuxCon_Europe_Linus_Torvalds_03_%28cropped%29.jpg?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original" class="w-50"/>

<small>

Krd (photo)Von Sprat (crop/extraction), CC BY-SA 3.0 <https://creativecommons.org/licenses/by-sa/3.0>, via Wikimedia Commons

</small>

<i class="display-3 bi bi-tux"></i>

{{% /col %}}
{{% col %}}

- DVCS più **conosciuto** e **utilizzato**
- Software **libero** e **open-source**
- Sviluppato nell'arco di 2 settimane da **Linus Torvalds**.
    - sviluppatore, tra le altre cose, del kernel **Linux**
    - dopo uno sgradito cambio di licenza di BitWarden, sistema precedentemente utilizzato per versionare Linux

<br class="my-3">

{{% callout title="Nice to know" %}}

Il nome "*Git*" non è un acronimo! In inglese, è un "insulto leggero" che Torvalds usa per descrivere sé stesso.

{{% /callout %}}

{{% /col %}}
{{% /multicol %}}

---
 
Strumento che permette la collaborazione e la gestione di progetti di **tutte le dimensioni**.

<br>

```mermaid
      gitGraph
        commit
        branch hotfix
        checkout hotfix
        commit
        branch develop
        checkout develop
        commit id:"ash" tag:"abc"
        branch featureB
        checkout featureB
        commit type:HIGHLIGHT
        checkout main
        checkout hotfix
        commit type:NORMAL
        checkout develop
        commit type:REVERSE
        checkout featureB
        commit
        checkout main
        merge hotfix
        checkout featureB
        commit
        checkout develop
        branch featureA
        commit
        checkout develop
        merge hotfix
        checkout featureA
        commit
        checkout featureB
        commit
        checkout develop
        merge featureA
        branch release
        checkout release
        commit
        checkout main
        commit
        checkout release
        merge main
        checkout develop
        merge release
```

---

## Cominciamo dalle **basi**

{{% /section %}}

---

## Tassonomia di Git

{{% callout %}}

Da ora in poi ci riferiamo al **progetto** su cui lavoriamo con il termine di **repository**. 

{{% /callout %}}

---


Qualora, durante lo sviluppo di un progetto volessi salvarne lo stato, dovrei catturarne uno *snapshot*.

<br>

{{% multicol %}}
{{% col %}}

{{% callout %}}

Nella tassonomia di Git, ci si riferisce a questa pratica con il termine "**commit**".

{{% /callout %}}

{{% /col %}}

{{% col %}}

<img class="w-50" src="imgs/commit.png" />

{{% /col %}}

{{% /multicol %}}

---

## Storico di un progetto

Stiamo lavorando su un progetto all'avanguardia: 

### `PrimeSequence.kt`

---

{{% section %}}
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

---

{{% multicol %}}
{{% col class="d-flex flex-column align-items-center justify-content-center" %}}

## Remote

{{% callout type="cite" src="Risposta di Nouflam Ibrahim, stackoverflow.com" srcLink="https://stackoverflow.com/questions/5617211/what-is-git-remote-add-and-git-push-origin-master/5617350#5617350" %}}
To communicate with the outside world, Git uses what are called "**remotes**". These are repositories other than the one on your local disk which you can push your changes into (so that other people can see them) or pull from (so that you can get others changes)
{{% /callout %}}

{{% /col %}}
{{% col %}}

![](imgs/remote.png)

{{% /col %}}
{{% /multicol %}}

---

{{% section %}}
### Step 1: Creazione di un remote

{{% callout %}}
<strong><i class="bi bi-gitlab"></i></strong> Utilizzeremo **GitLab**.
{{% /callout %}}

---

![GitLab Home](imgs/gitlab-home.png)

1. Andiamo su [**biagio.ispascalcomandini.it/gitlab/**]()

---

![New Repo option](imgs/new-repo-menu.png)

<br/> 

2. Clicchiamo su "**New project/repository**"

---

![New Project Page](imgs/new-project-page.png)

3. Inseriamo i dati della nostra repository (qui chiamata "**Project**")

---

![New Project Created](imgs/new-project-created.png)

4. Abbiamo creato il **remote**!

{{% /section %}}

---

### Step 2: Collegamento del remote al repository locale

```mermaid
flowchart RL

subgraph somesite.com/repo.git
  direction RL
  HEAD{{"HEAD"}}
  master(master)
  serverless(feat/serverless)

  C10([10]) --> C9([9]) --> C8([8]) --> C7([7]) --> C6([6]) --> C5([5]) --> C4([4]) --> C3([3]) --> C2([2]) --> C1([1])
  C12([12]) --> C11([11]) --> C7

  master -.-> C10
  serverless -.-> C12

  HEAD -.-> C10
  HEAD --"fas:fa-link"--o master
end

subgraph local
  direction RL
  origin[(origin)]

  HEADL{{"HEAD"}}
  masterl(master)

  CL10([10]) --> CL9([9]) --> CL8([8]) --> CL7([7]) --> CL6([6]) --> CL5([5]) --> CL4([4]) --> CL3([3]) --> CL2([2]) --> CL1([1])

  masterl -.-> CL10
  masterl ==o master

  HEADL -.-> CL10
  HEADL --"fas:fa-link"--o masterl
end

origin ==o somesite.com/repo.git

class local,somesite.com/repo.git repo;
class origin remote;
class HEAD,HEADL head;
class master,masterl,bug22,serverless branch;
class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10,C11,C12,C13,CL1,CL2,CL3,CL4,CL5,CL6,CL7,CL8,CL9,CL10,CL11,CL12,CL13 commit;
```