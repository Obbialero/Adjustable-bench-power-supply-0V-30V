# ⚡ Alimentatore da Banco Regolabile (0–20V / 5A) con XL4016

![Versione](https://img.shields.io/badge/version-2.1-blue)  
![Data](https://img.shields.io/badge/data-22%2F05%2F2024-lightgrey)

Un alimentatore da banco regolabile progettato completamente da zero, capace di fornire una tensione variabile da **1.25V a 20V** con una corrente massima di **5A continui**. Il progetto si basa su un convertitore **AC-DC**, seguito da un regolatore **DC-DC step-down (buck)** con **XL4016**.

Tutto il circuito è integrato su un singolo PCB progettato in **EasyEDA**, senza l'uso di moduli prefabbricati.

---

## 📌 Specifiche Tecniche

| Caratteristica                | Valore                             |
|------------------------------|------------------------------------|
| **Ingresso**                 | 220V AC                            |
| **Tensione DC interna**      | 32V DC max                         |
| **Uscita regolabile**        | 1.25V – 20V                        |
| **Corrente massima**         | 5A continui                        |
| **Efficienza tipica**        | >80%                               |
| **Tipologia di conversione** | AC-DC + DC-DC Step-Down (Buck)     |
| **PCB**                      | Progettato con EasyEDA             |

---

## 📦 Distinta Base (BOM)

Consulta la [distinta base completa (BOM.csv)](./hardware/BOM.csv) per la lista dettagliata dei componenti utilizzati, inclusi codici, valori e note tecniche.

---

## 📊 Schema a Blocchi

![Schema a blocchi](./docs/schema_a_blochi.png)

---

## 🔢 Calcolo della Tensione di Uscita

La tensione di uscita è regolata tramite un partitore resistivo composto da **R1**, **P1** e **R2**, secondo la formula:

Vout = 1.25V × (1 + (R1 + P1) / R2)

yaml
Copia
Modifica

### Valori Tipici:

- **R1** = 10kΩ  
- **R2** = 2kΩ  
- **P1** = 10kΩ (trimmer variabile)  
- **Range ottenuto**: ~ **1.25V – 20V**

---

## 🛠️ Raccomandazioni per il PCB

- **Tracce AC**: separate da quelle DC, larghezza ≥ 2mm, isolamento > 3mm
- **Tracce DC ad alta corrente**: larghezza ≥ 2.5mm per garantire 5A continui
- **Piano di massa esteso**, idealmente su entrambi i lati del PCB
- **Via termiche** sotto dissipatori e convertitori per una migliore dissipazione
- **Condensatori C1 e C3**: il più vicino possibile al pin VIN
- **Zona AC**: serigrafata, contrassegnata con simboli ⚡ e fisicamente isolata
- **Ventola e dissipatori**: fortemente consigliati per correnti > 3A

---

## 🔍 Monitoraggio (Opzionale)

| Componente       | Descrizione                            |
|------------------|----------------------------------------|
| **M1**           | Volt-Amperometro digitale              |
| **R3**           | Resistenza di shunt 0.1Ω / 5W          |
| **Connettori**   | Banana jack isolati per uscita         |

---

## 🧱 Sicurezza e Meccanica

- **Contenitore ignifugo e ventilato** (ABS V0 o alluminio dissipante)
- **Protezione lato AC**: fusibile, piste isolate, terminali coperti
- **Cablaggi AC**: solo con guaina in silicone
- **Ventilazione forzata**: obbligatoria per correnti > 3A
- **Zone AC marcate** con simboli ⚡ e distanze di sicurezza appropriate

---

## 📂 File Inclusi

- `README.md` – Documentazione del progetto  
- `schema_blocchi.pdf` – Schema a blocchi  
- `alimentatore_xl4016.brd / .sch` – File EasyEDA (PCB e schema elettrico)  
- `distinta_base.xlsx` – Distinta base dettagliata  
- `BOM.csv` – Lista sintetica dei componenti

---

## 🖼️ Immagini e PCB

### 🔧 Schema Elettrico

![Schematic](./docs/PNG_AC-DC/Schematic_AC-DC-V1.0.png)

### 📐 Layout PCB - 2D

![PCB](./docs/PNG_AC-DC/PCB_AC-DC-V1.0.png)

### 🖥️ Vista 3D del PCB Assemblato

![3D PCB](./docs/PNG_AC-DC/3D-PCB-AC-DC-V1.0.png)

---

## 🔍 Componenti Esterni

| Componente                         | Link                                   | Quantità |
|------------------------------------|----------------------------------------|----------|
| **Volt-Amperometro Digitale**      | [Amazon](https://www.amazon.it/dp/B01MUC149K) | 1        |
| **Interruttore a bilanciere**      | [TEMU](https://www.temu.com/g-601099550024059.html) | 2        |

---

## ⚠️ Avvertenze

> ⚡ **ATTENZIONE: Questo progetto lavora con tensioni di rete (220V AC).**  
> È necessaria **estrema cautela** durante il montaggio e l'utilizzo.  
> Riservato a utenti esperti.  
> Isolare tutte le parti AC, utilizzare un contenitore sicuro e ventilato.

---

## 📬 Contatti

Per domande o suggerimenti:  
**Andrea Obbialero** – [https://obbialero.github.io/](https://obbialero.github.io/)

---

## 📘 Licenza

Questo progetto è distribuito con licenza **MIT**.  
È liberamente utilizzabile per scopi personali, educativi e commerciali, a condizione di fornire attribuzione.

---