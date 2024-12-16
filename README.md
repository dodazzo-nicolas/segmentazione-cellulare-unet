# U-Net Segmentation Model

Questo progetto implementa un modello di segmentazione delle immagini basato sull'architettura U-Net, utilizzando TensorFlow/Keras. Il modello è progettato per segmentare nuclei cellulari in immagini.

## Struttura del codice

### 1. **Preprocessing**
- Ridimensionamento delle immagini e delle maschere alla dimensione predefinita (`128x128x3`).
- Caricamento e preparazione del dataset di addestramento e di test.

### 2. **Modello U-Net**
- Implementazione di un'architettura U-Net con:
  - **Contraction path** (feature extraction attraverso convoluzioni e pooling).
  - **Bottleneck** (layer più profondo e compatto).
  - **Expansive path** (ricostruzione della dimensione dell'immagine).
- Compilazione del modello con ottimizzatore *Adam* e funzione di perdita *binary crossentropy*.

### 3. **Addestramento**
- Addestramento del modello su immagini di nuclei e relative maschere.
- Callback configurati per:
  - Early stopping.
  - Salvare il miglior modello.
  - Visualizzare i risultati nel TensorBoard.

### 4. **Valutazione**
- Generazione di previsioni sul dataset di training, validazione e test.
- Applicazione di thresholding per convertire le probabilità in maschere binarie.

### 5. **Visualizzazione dei risultati**
- Grafici di accuratezza e perdita durante l'addestramento.
- Confronto tra immagini originali, maschere di riferimento e previsioni del modello.

## Requisiti

Per eseguire il progetto, assicurarsi di avere i seguenti requisiti installati:

- Python 3.7 o superiore
- TensorFlow/Keras
- NumPy
- Scikit-Image
- Matplotlib
- tqdm

Utilizza il seguente comando per installare i pacchetti necessari:
```bash
pip install tensorflow numpy scikit-image matplotlib tqdm
```

## Esecuzione del progetto

1. Posizionare le cartelle `stage1_train` e `stage1_test` contenenti le immagini nella directory corretta.
2. Modificare i percorsi `TRAIN_PATH` e `TEST_PATH` nel codice Python, se necessario.
3. Eseguire il file Python per:
   - Caricare i dati.
   - Addestrare il modello.
   - Visualizzare i risultati.

## File principali

- **U-Net Architecture**: definizione e costruzione del modello U-Net.
- **Preprocessing**: caricamento, ridimensionamento e gestione delle immagini.
- **Training & Evaluation**: addestramento del modello e analisi delle prestazioni.

## Note

- Questo modello è stato progettato per funzionare su immagini di nuclei cellulari ma può essere adattato a diversi compiti di segmentazione modificando i dataset e i parametri del modello.
- Link per scaricare il dataset da noi utilizzato: https://drive.google.com/file/d/1rp0KIgX7gx6H6YxJjD8DmMWPJ2xqzGV9/view?usp=sharing
