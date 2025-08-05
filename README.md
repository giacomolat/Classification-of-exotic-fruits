![image](https://github.com/user-attachments/assets/1b701899-f179-4f08-a4cf-d50720bc827b)

# Versione <img width="40" height="50" alt="image" src="https://github.com/user-attachments/assets/eee9d20d-b30f-4ba8-9429-116d3d8ad6e2" /> (ITA)


# Master Professionale in AI Engineering - ProfessionAI
# Classificazione di Frutti Esotici con K-Nearest Neighbors (KNN) 

## Descrizione del progetto
Il progetto è stato sviluppato nell’ambito del modulo *Machine Learning: Modelli e Algoritmi* del **Master Professionale in AI Engineering**, con l’obiettivo di costruire un sistema di classificazione automatica per frutti esotici, basato su caratteristiche numeriche, mediante l'Algoritmo K-Nearest Neighbors (K-NN).

Il progetto simula un caso aziendale reale: **TropicTaste Inc.**. Questa azienda, leader nella distribuzione di frutta tropicale, vuole migliorare l’efficienza e l’accuratezza della classificazione dei prodotti riducendo errori umani e costi operativi. L’obiettivo è quindi costruire un *Modello di Machine Learning Supervisato* in grado di prevedere correttamente il tipo di frutto sulla base delle sue caratteristiche fisiche.

---

## Obiettivi Principali
- Costruire un **modello K-Nearest Neighbors (K-NN)** per la classificazione multiclasse.
- Effettuare una **corretta preparazione del dataset**, includendo analisi delle distribuzioni e gestione di anomalie nei dati.
- Valutare le performance del modello e **ottimizzare i parametri** per ottenere risultati affidabili.
- Visualizzare metriche di valutazione, ROC curve e matrici di confusione.

---

## Dataset
- **Fonte:** [fruits.csv](https://proai-datasets.s3.eu-west-3.amazonaws.com/fruits.csv)  
- **Campioni totali:** 500  
- **Target:** `Frutto` (variabile categorica con 5 classi)  
- **Variabili numeriche:**
  - `Peso (g)`
  - `Diametro medio (mm)`
  - `Lunghezza media (mm)`
  - `Durezza buccia (1–10)`
  - `Dolcezza (1–10)`

---

## Fasi del progetto

### 1. Analisi Esplorativa dei Dati
- **Visualizzazione distribuzioni**: è stato creato un istogramma per ciascuna feature continua.
- **Controllo del range**: per le variabili con range dichiarato (Durezza buccia e Dolcezza), sono stati corretti i valori anomali:
   - Per `Durezza buccia`, alcuni valori > 10 sono stati sostituiti con la **mediana**.
   - Nessuna anomalia in `Dolcezza`.

### 2. Preprocessing
- **Codifica etichette** tramite tecnica di Feature Encoding, Label Encoding, mediante la classe `LabelEncoder`.
- **Controllo e gestione outlier** per variabili con range noto.
- **Normalizzazione dei dati** mediante `MinMaxScaler`, per garantire che tutte le feature siano su scala comparabile.
- **Suddivisione training/test**: 80% train e 20% test con Cross Validation "Hold-Out", mediante la funzione `train_test_split`.

### 3. Modellazione con KNN
- **Implementazione del modello K-NN** tramite la classe `KNeighborsClassifier`
- **Ottimizzazione dell’iperparametro** `k` tramite `GridSearchCV` + `StratifiedKFold`
- **Addestramento e test**, con scelta finale del miglior `k` sulla base dei risultati

### 4. Valutazione delle Performance
- **Accuratezza** su training e test set
- **Matrice di Confusione** per il test set con etichette leggibili (es. “Mela”, “Banana”, “Arancia”, “Uva” e “Kiwi”)
- **Curva ROC** multiclasse con approccio One-vs-Rest (`RocCurveDisplay.from_prediction`)
- **Classification Report** completo con Accuracy, Precision, Recall e F1-score, per ogni classe

---

## Risultati principali
- **Accuratezza finale**: ~88%
- Il miglior valore di `k` ottenuto è **10**
- Ottima separabilità tra classi con distribuzioni ben distinte
- Il modello ha mostrato prestazioni solide su tutte le classi

---

## Tecnologie utilizzate
- Python 3.x
- Scikit-learn
- Pandas
- NumPy
- Matplotlib.pyplot & Seaborn

---

## 📂 Struttura del file
- `Progetto_Classificazione_di_frutti_esotici_Giacomo_Latini.ipynb`: notebook .ipynb completo
- `Progetto_Classificazione_di_frutti_esotici_Giacomo_Latini.py`: file.py completo

---

## 👨‍🎓 Studente
**Nome:** Giacomo Latini  
**Corso:** Master Professionale in AI Engineering  
**Modulo:** Machine Learning: Modelli e Algoritmi  
**Anno:** 2025

---

## 📜 Licenza
Questo progetto è rilasciato con licenza GNU GPL v3.
Vedi il file LICENSE per i dettagli.
