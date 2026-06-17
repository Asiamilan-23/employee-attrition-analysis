# Progetto Employee Attrition

> Progetto di fine corso — Introduzione alla Data Science e al Pensiero Computazionale — 2025/2026

---

## Membri del Gruppo

| Nome |   Cognome   | Matricola |
|-------|------------|-----------|
| Paolo | Magnanelli |  1231652  |
| Asia  |    Milan   |  1217247  |

---

## Descrizione del Progetto
Questo progetto analizza il fenomeno dell’attrition dei dipendenti, ovvero l’abbandono dell’azienda, utilizzando tecniche di data analysis e machine learning. Attraverso l’analisi del dataset Employee Attrition, vengono individuati i principali fattori che influenzano la decisione di lasciare il lavoro, e vengono poi costruiti diversi modelli di classificazione per prevedere i dipendenti a rischio.  

---

## Descrizione del Dataset

- **Nome dataset:** Employee Attrition 
- **Dimensioni:** 1470 righe x 35 colonne
- **Periodo di riferimento:** non specificato
- **Variabile target:** Attrition (Yes = lascia, No = rimane)
- **Features principali:** Age, MonthlyIncome, JobSatisfaction, WorkLifeBalance, OverTime, TotalWorkingYears, YearsAtCompany, JobRole, Department

> Il dataset contiene informazioni su dipendenti relative a caratteristiche demografiche, lavorative ed economiche. Non sono presenti valori mancanti, mentre alcune variabili costanti (come EmployeeCount, Over18 e StandardHours) sono state rimosse in fase 2 (analisi del dataset). Sono stati osservati alcuni outlier nelle variabili numeriche (es. reddito o anni di esperienza), ma questi risultano coerenti con situazioni reali e non sono stati eliminati.

---

## Obiettivo

L’obiettivo del progetto è analizzare e prevedere il fenomeno dell’**attrition dei dipendenti**. In particolare, si tratta di un problema di classificazione binaria, in cui si vuole predire se un dipendente lascerà l’azienda (Yes) oppure rimarrà (No). Attraverso l’analisi dei dati e la costruzione di modelli di machine learning, il progetto mira a:
- individuare i principali fattori che influenzano l’attrition;
- confrontare diversi modelli predittivi.

---
