# Artificial Intelligence: From Engineering to the Arts

## Music Emotion Classification and Visual Art Generation

Progetto di **Machine Learning e Intelligenza Artificiale Generativa** finalizzato alla trasformazione delle emozioni musicali in rappresentazioni visive astratte e figurative.

Il sistema analizza le caratteristiche audio di un brano, ne predice l'emozione prevalente e genera un'immagine coerente con il contenuto emotivo attraverso **Stable Diffusion**.

Il progetto utilizza il **4Q Audio Emotion Dataset**, basato sui quattro quadranti del modello Valence-Arousal di Russell.

### Pipeline

**Audio → Estrazione delle feature → Classificazione dell'emozione → Generazione del prompt → Stable Diffusion → Immagine → Valutazione CLIP**

### Classificazione delle emozioni

Le emozioni sono suddivise in quattro classi:
- Happy
- Tense
- Sad
- Calm

Vengono confrontati quattro modelli di Machine Learning:

- Random Forest
- Extra Trees
- Support Vector Machine (SVM) con kernel RBF
- Logistic Regression

Il modello migliore viene selezionato attraverso il **Macro F1 medio in cross-validation sul training set**. Le prestazioni vengono successivamente valutate sul test set.

### Generazione delle immagini

Le caratteristiche musicali estratte e l'emozione predetta vengono utilizzate per costruire un prompt destinato a Stable Diffusion.

Sono disponibili due modalità di generazione:

- **Abstract Art:** immagini non figurative basate su colori, forme e composizioni visive.
- **Figurative Art:** immagini con soggetti e ambientazioni riconoscibili, associati all'emozione musicale.

### Valutazione con CLIP

Il modello **CLIP (Contrastive Language–Image Pre-training)** viene utilizzato per valutare la similarità semantica tra le immagini generate e descrizioni testuali delle quattro emozioni.

La valutazione permette di confrontare l'emozione predetta dal classificatore audio con quella maggiormente associata all'immagine secondo CLIP.

La similarità CLIP rappresenta una misura esplorativa di coerenza semantica, non una valutazione diretta della percezione emotiva umana.

### Tecnologie utilizzate

- **Python e Google Colab** — sviluppo ed esecuzione
- **Librosa** — elaborazione audio ed estrazione delle feature
- **Scikit-learn** — classificazione e valutazione dei modelli
- **Stable Diffusion** — generazione delle immagini
- **CLIP** — valutazione della similarità immagine-testo
- **Google Drive** — salvataggio dei risultati

### Esecuzione

Il progetto è sviluppato come notebook Jupyter, eseguibile in **Google Colab**.

Per eseguirlo:

1. Aprire il notebook `.ipynb` in Google Colab.
2. Attivare una GPU nelle impostazioni dell'ambiente di esecuzione.
3. Montare Google Drive e rendere disponibile il dataset 4Q nel percorso configurato nel notebook.
4. Eseguire le celle in ordine.

Gli output permanenti vengono salvati nella directory:

`/content/drive/MyDrive/music_emotion_art_4q_project`

### Obiettivo del progetto

Esplorare l'integrazione tra **analisi musicale, riconoscimento delle emozioni e arte generativa**, mostrando come tecniche di Intelligenza Artificiale possano collegare il dominio ingegneristico a quello artistico.
