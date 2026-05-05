
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

<img class="exclude" src="imgs/micky-mouse.png"/>

{{% /section %}}

---

# Sistemi di versionamento

{{% callout type="note" %}}

**Version control**, also known as source control, is the practice of tracking and managing changes to software code.

[[Atlassian - What is version control]](https://www.atlassian.com/git/tutorials/what-is-version-control)
{{% /callout %}}

---

## Benefici chiave


{{% fragment %}}
### **#1. Tracciabilità completa**

È possibile tracciare la cronologia completa delle modifiche apportate ad un progetto.
{{% /fragment %}}

{{% fragment %}}
### **#2. Ripristino semplice**

È possibile tornare a versioni precedenti del mio progetto senza danni collaterali.
{{% /fragment %}}

{{% fragment %}}
### **#3. Collaborazione sicura** 

Possibilità a membri del team di lavorare su ramificazioni diverse del progetto, in modo da evitare sovrapposizioni e da suddividere agilmente i compiti.
{{% /fragment %}}

---

## Tipologie di sistemi di versionamento

{{% multicol %}}
{{% col %}}
### Centralizzato
{{% /col %}}
{{% col %}}
### Distribuito
{{% /col %}}
{{% /multicol %}}

<img class="w-50 exclude" src="imgs/centralized-vs-distributed.png"/>