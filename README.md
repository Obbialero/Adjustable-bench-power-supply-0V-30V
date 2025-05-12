# ⚡ Alimentatore da Banco Regolabile AC-DC Buck XL4016

**Versione:** 2.1  
**Autore:** Obbialero Andrea  
**Data:** 22/05/2024  

## 📌 Descrizione del Progetto

Questo progetto consiste nella realizzazione di un alimentatore da banco regolabile, basato su un convertitore **AC-DC + Buck DC-DC XL4016**, in grado di fornire **una tensione regolabile da 1.25V a 20V** e una **corrente continua massima di 5A**. Tutto il circuito è stato progettato **su un singolo PCB**, senza l'utilizzo di moduli prefabbricati.

---

## 🔧 Specifiche Tecniche

| Caratteristica                  | Valore                           |
|--------------------------------|----------------------------------|
| **Ingresso**                   | 220V AC                          |
| **Tensione DC Interna**        | 32V DC max                       |
| **Uscita Regolabile**          | 1.25V – 20V                      |
| **Corrente Massima**           | 5A continui                      |
| **Efficienza Tipica**          | >80% (totale)                    |
| **Tipologia di Conversione**   | AC-DC + DC-DC Step-Down (Buck)   |
| **PCB**                        | Progettato da zero               |

---

## 📦 Distinta Base (BOM)

Consulta la [Distinta Base completa (BOM.csv)](./BOM.csv) per tutti i componenti utilizzati, comprensivi di codici, valori e note tecniche.


---

## 🔌 Schema a Blocchi

                  ┌────────────┐
     220V AC ─────▶   [F0]     │   Fusibile AC
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │  [BR1]     │   Ponte Raddrizzatore
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │  [C0]      │   Filtro Elettrolitico 400V
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │  [U0]      │   AC-DC Switching (32V DC)
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │ [C0b]      │   Condensatore di uscita
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │  [F1]      │   Fusibile DC
                  └────┬───────┘
                       │
                  ┌────▼───────┐
                  │  [S1]      │   Interruttore ON/OFF
                  └────┬───────┘
                       │
                  ┌────▼──────────────┐
                  │   XL4016 Buck     │
                  │   Converter       │
                  └────┬──────────────┘
                       │
      ┌────────────────┼──────────────────────┐
      ▼                ▼                      ▼
 [L1] Induttore   [D1] Diodo Schottky   [C1–C5] Condensatori
                                              (Filtro & Bootstrap)
                                              
                    ▼
                 [P1] Potenziometro
                       │
                    [M1] Volt/Amperometro Digitale
                       │
                     OUT+ / OUT-

---

## 🔢 Calcolo Tensione di Uscita

La tensione di uscita è regolata tramite il partitore resistivo R1, P1 e R2:

VOUT = 1.25V × (1 + (R1 + P1) / R2)

yaml
Copia
Modifica

- **R1** = 10kΩ  
- **R2** = 2kΩ  
- **P1** = 10kΩ (variabile)  
- **Range ottenuto** ≈ **1.25V – 20V**

---

## 🛠️ Raccomandazioni PCB

- **Tracce AC**: separate da quelle DC, ≥2mm di larghezza, isolamento >3mm
- **Tracce DC (alta corrente)**: ≥2.5mm per 5A
- **Piano di massa esteso** con via termiche per dissipazione
- **C1/C3**: montati il più vicino possibile a VIN
- **Zona AC**: marcata, serigrafata e fisicamente separata
- **Dissipatori e ventola**: necessari per >3A continui

---

## 🔍 Monitoraggio (Opzionale)

| Componente  | Descrizione                       |
|------------|-----------------------------------|
| **M1**     | Volt/Amperometro digitale          |
| **R3**     | Shunt 0.1Ω / 5W                    |
| **Banana Jack** | Uscite sicure per strumenti |

---

## 🧱 Sicurezza e Meccanica

- **Contenitore ignifugo e ventilato** (ABS V0 o alluminio)
- **Protezione lato AC**: fusibile, isolamento piste
- **Copertura terminali AC**, cavi con guaina in silicone
- **Ventilazione forzata obbligatoria** per correnti >3A
- **Marcature zona AC** con simboli ⚡ e distanze di sicurezza

---

## 📂 File Inclusi

- `README.md` – Documentazione del progetto
- `schema_blocchi.pdf` – Schema a blocchi (da includere)
- `alimentatore_xl4016.brd / .sch` – File PCB 
- `distinta_base.xlsx` – BOM dettagliata

---

## 📸 Immagini e PCB

*(Inserire immagini reali del prototipo o rendering del PCB se disponibili)*

---



## ⚠️ Avvertenze

> ⚡ **ATTENZIONE: Questo progetto lavora con tensione di rete (220V AC).**  
> Si raccomanda estrema cautela durante il montaggio e l'uso. Solo per utenti esperti.  
> Isolare sempre le parti AC e assicurarsi che il contenitore sia adeguato e ventilato.

---

## 📬 Contatti

Per domande o suggerimenti:  
**Andrea Obbialero** – https://obbialero.github.io/

---

## 📘 Licenza

Questo progetto è rilasciato sotto licenza **MIT**.  
Libero per uso personale, educativo e commerciale con attribuzione.
