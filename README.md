# Progetto Employee Attrition

> Progetto di fine corso — Introduzione alla Data Science e al Pensiero Computazionale — 2025/2026

---

## Membri del gruppo

| Nome |   Cognome   | Matricola |
|-------|------------|-----------|
| Paolo | Magnanelli |  1231652  |
| Asia  |    Milan   |  1217247  |

---

## Descrizione del progetto
Questo progetto analizza il fenomeno dell’attrition dei dipendenti, ovvero l’abbandono dell’azienda, utilizzando tecniche di data analysis e machine learning. Attraverso l’analisi del dataset `Employee Attrition`, questo progetto analizza il fenomeno dell’attrition dei dipendenti, ovvero l’abbandono dell’azienda, utilizzando tecniche di data analysis e machine learning.

---

## Descrizione del dataset

- **Nome dataset:** Employee Attrition 
- **Dimensioni:** 1470 righe x 35 colonne (26 numeriche, 9 categoriche)
- **Periodo di riferimento:** non specificato
- **Variabile target:** `Attrition` (`Yes` = lascia, `No` = rimane)
- **Features principali:** `Age`, `MonthlyIncome`, `JobSatisfaction`, `WorkLifeBalance`, `OverTime`, `TotalWorkingYears`, `YearsAtCompany`, `JobRole`, `Department`

> Il dataset contiene informazioni su dipendenti relative a caratteristiche demografiche, lavorative ed economiche. Non sono presenti valori mancanti, mentre alcune variabili costanti (come `EmployeeCount`, `Over18` e `StandardHours`) sono state rimosse in fase 2 (analisi del dataset). Sono stati osservati alcuni outliers nelle variabili numeriche (es. reddito o anni di esperienza), ma questi risultano coerenti con situazioni reali e non sono stati eliminati.

---

## Obiettivo

L’obiettivo del progetto è analizzare e prevedere il fenomeno dell’**attrition dei dipendenti**. In particolare, si tratta di un problema di classificazione binaria, in cui si vuole predire se un dipendente lascerà l’azienda (`Yes`) oppure rimarrà (`No`). Attraverso l’analisi dei dati e la costruzione di modelli di machine learning, il progetto mira a:
- individuare i principali fattori che influenzano l’`Attrition`;
- confrontare diversi modelli predittivi.

---
## Tecnologie utilizzate
- Python  
- pandas, numpy → gestione dati  
- matplotlib, seaborn → visualizzazione  
- scikit-learn → modelli di machine learning  
- Google Colab → ambiente di sviluppo  
- GitHub → gestione del codice e versionamento  
- Copilot, Claude → supporto nello sviluppo e nella revisione
  
---
## Analisi dei dati
L'analisi esplorativa è strutturata in due fasi principali:
### 1.  *Fase 2 — Descrizione e comprensione del dataset*
- [ ] **Statistiche descrittive**: panoramica su dimensioni, tipi di variabili e statistiche di riepilogo (`df.info()`, `df.describe()`).
- [ ] **Gestione dei valori mancanti**: verifica tramite `df.isna().sum()` dove nessun valore mancante è stato rilevato.
- [ ] **Identificazione variabili costanti**: rilevate e rimosse 3 colonne non informative (`EmployeeCount`, `Over18`, `StandardHours`), che presentano un unico valore in tutto il dataset.
- [ ] **Analisi della distribuzione della variabile target**: `Attrition` risulta sbilanciata (~84% `No` vs ~16% `Yes`: class imbalance); visualizzata con grafico countplot.
- [ ] **Rilevazione degli outliers**: analisi tramite boxplot su `MonthlyIncome`, `YearsAtCompany` e `TotalWorkingYears`. Gli outliers identificati rappresentano situazioni realistiche (come dipendenti senior/dirigenziali) e non errori di rilevazione. Sono stati mantenuti nel dataset.
- [ ] **Analisi delle correlazioni**: heatmap delle correlazioni tra variabili numeriche. Correlazioni più forti tra `MonthlyIncome` e `JobLevel` (~0.95), tra `TotalWorkingYears` e `JobLevel` (~0.78). Alcune variabili legate all’anzianità lavorativa risultano fortemente correlate tra loro (correlazione tra 0.71 e 0.77).



### 2.  *Fase 3 — Analisi esplorativa e grafici rispetto al target*
- [ ] **Analisi della distribuzione delle variabili**: distribuzione dell'età (`Age`) per gruppo di `Attrition` (histplot + KDE); distribuzione congiunta esperienza–reddito (scatterplot + kdeplot 2D).
- [ ] **Grafici**: barplot, boxplot, countplot, heatmap, catplot, scatterplot con densità bivariata per esplorare le relazioni tra features e attrition.

>*Domande analitiche affrontate*:
> - `OverTime` è fortemente associato all'`Attrition`: ~31% di abbandono tra chi fa straordinari contro il ~10% tra chi non ne fa.
> - I dipendenti che lasciano hanno un `MonthlyIncome` mediano più basso.
> - Il reddito varia significativamente per `JobRole` (da `Sales Representative` a `Manager/Research Director`).
> - Un `WorkLifeBalance` scarso è associato a un'`Attrition` più alta.
> - Il rischio di abbandono si concentra nei dipendenti giovani e con poca esperienza in azienda (fascia 18–25 anni, nuovi: ~42%).
> - Il numero di aziende in cui si è precedentemente lavorato non mostra relazioni evidente con l'`Attrition`.

---
## Modelli Utilizzati

| Modello | Tipo | Libreria |
|---------------------------|-------------------------|--------------|
| **Regressione Logistica** (con e senza standardizzazione)| Classificazione lineare | scikit-learn |
| **k-Nearest Neighbors (k=14)** | Classificazione (non lineare) | scikit-learn |
|**Random Forest (200 estimators)** | Classificazione (non lineare, ensemble)| scikit-learn|
|**Decision Tree** | Classificazione (non lineare)| scikit-learn|


### Metriche di Valutazione
- **Accuracy**:  metrica di base, poco informativa su dataset sbilanciati
- **Precision, Recall, F1-score**: calcolati sulla classe minoritaria `Attrition = Yes`
- **ROC-AUC**: confronto tra modelli indipendente dalla soglia di decisione
- **Curva Precision-Recall**: analisi del comportamento al variare della soglia (Regressione Logistica)
---
## Struttura del repository (DA SISTEMARE)

├── data/
│   ├── raw/               # Dataset originale
│   └── processed/         # Dataset pre-processato
├── notebooks/
│   ├── 01_eda.ipynb        # Analisi esplorativa
│   ├── 02_preprocessing.ipynb
│   └── 03_modeling.ipynb   # Training e valutazione modelli
├── src/
│   ├── preprocessing.py
│   └── models.py
├── reports/
│   └── relazione.pdf       # Report LaTeX compilato
├── requirements.txt
└── README.md

---
## Istruzioni per l’esecuzione

### Installazione
#### 1. Clona il repository sul tuo computer:

```
git clone https://github.com/asiamilan/employee-attrition.git (DA CONTROLLARE)
cd employee-attrition
```

#### 2. Installa tutte le librerie necessarie:
```
install pandas numpy matplotlib seaborn scikit-learn 
```

#### 3. Apri Jupyter Notebook:
```
jupyter notebook
```

#### 4. Eseguire il progetto
- [ ] Apri il file .ipynb
- [ ] Esegui tutte le celle una dopo l’altra (da sopra a sotto)

---

## Dipendenze Principali

```
pandas
numpy
matplotlib
seaborn
scikit-learn
```
---
## Risultati principali
La variabile target `Attrition` è sbilanciata:
- circa 84% No (rimane)
- circa 16% Yes (lascia l'azienda)

La **regressione logistica** ha ottenuto le migliori prestazioni complessive, risultando il modello più efficace nell’individuare i dipendenti a rischio di attrition.

| Modello | Accuracy | AUC (ROC) | F1-score (classe Yes) |
|--------|----------|-----------|------------------------|
| **Regressione Logistica** | ~0.87 | migliore | migliore recall |
| **k-NN (k = 14)** | ~0.84 | intermedio | bilanciato |
| **Random Forest (200 estimators)** | ~0.83 | intermedio | precision alta |
| **Decision Tree** | ~0.74 | più basso | performance inferiori |

‼️I valori esatti dipendono dall’esecuzione del notebook (*random_state=42 garantisce la riproducibilità*).

---
## Interpretazione Critica

### Modello migliore
La **Regressione Logistica** risulta il modello più efficace, grazie alle migliori prestazioni complessive e a un buon equilibrio tra *precision* e *recall*. In particolare, è il modello più adatto quando l’obiettivo è identificare i dipendenti a rischio di attrition.
> Inoltre, abbassare la soglia di decisione (inferiore a 0.5) permette di aumentare il *recall*, riducendo i falsi negativi. Questa scelta è utile in contesti reali, dove non individuare un dipendente a rischio è più grave rispetto a generare un falso negativo.

### Confronto tra modelli
Dal confronto emerge che:
- la Regressione Logistica è il modello più equilibrato;
- k-NN e Random Forest mostrano buone prestazioni, ma minore capacità di riconoscere la classe `Yes`;
- il Decision Tree è il modello meno accurato, ma il più interpretabile.

‼️ Tutti i modelli tendono a classificare correttamente i dipendenti che rimangono, ma mostrano difficoltà nel riconoscere quelli che lasciano.

### Tipologia di errori
L’analisi delle confusion matrix mostra che molti dipendenti che lasciano l’azienda non vengono riconosciuti dal modello. Questi casi, i falsi negativi, indicano che il modello predice “rimane” quando in realtà il dipendente lascia. Questo tipo di errore è particolarmente critico perché impedisce all’azienda di individuare in tempo i dipendenti a rischio e quindi di intervenire per evitarne l’abbandono.

### Rischio di overfitting
La Random Forest è più a rischio di overfitting, cioè tende ad adattarsi molto bene ai dati di training ma può funzionare meno bene su nuovi dati. Mentre la Regressione Logistica, è un modello più semplice e lineare, per questo motivo è meno soggetto a overfitting e riesce a generalizzare meglio, mantenendo prestazioni più stabili anche su dati nuovi su cui il modello non è stato allenato.

### Variabili più rilevanti:
- `OverTime` 
- `MonthlyIncome`  
- `Age`  
- `JobLevel`  
- `TotalWorkingYears`  
- `YearsAtCompany` 

In particolare, emerge che:
- chi svolge frequentemente straordinari ha una maggiore probabilità di lasciare l’azienda;
- un reddito più basso è associato a un rischio più alto di abbandono;
- i dipendenti più giovani o con minore esperienza tendono a lasciare più spesso.

‼️ Questi risultati sono coerenti con l’analisi esplorativa e suggeriscono che l’`Attrition` è legata sia alle condizioni lavorative sia alla carriera.

---

### Conclusione
Nel complesso, i modelli permettono di individuare pattern significativi, ma mostrano una difficoltà nel riconoscere la classe `Yes`. Questo evidenzia che, oltre al miglioramento dei modelli, è necessario approfondire strategie per gestire lo sbilanciamento dei dati e migliorare la capacità di identificare i dipendenti a rischio.
