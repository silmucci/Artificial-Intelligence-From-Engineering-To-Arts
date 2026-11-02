# Artificial-Intelligence-From-Engineering-To-Arts
# Music Emotion to Visual Art — Abstract and Figurative Generation

Questo notebook realizza una pipeline di **Machine Learning e AI generativa** per trasformare le emozioni musicali in immagini astratte e figurative.

Il progetto utilizza il **4Q Audio Emotion Dataset**, organizzato nei quattro quadranti del modello Valence-Arousal di Russell.

### Pipeline

**Audio → Estrazione delle feature → Classificazione dell'emozione → Prompt → Stable Diffusion → Immagine → Valutazione CLIP**

### Classi emotive

- **Q1 → Happy:** valenza positiva, arousal alto
- **Q2 → Tense:** valenza negativa, arousal alto
- **Q3 → Sad:** valenza negativa, arousal basso
- **Q4 → Calm:** valenza positiva, arousal basso

### Modelli confrontati

- Random Forest
- Extra Trees
- SVM con kernel RBF
- Logistic Regression

Il modello migliore viene selezionato in base al **Macro F1 medio in cross-validation sul training set**. Il test set viene utilizzato esclusivamente per la valutazione finale.

Le immagini vengono generate in modalità **astratta o figurativa** e valutate tramite **CLIP**, per analizzare la coerenza semantica con l'emozione predetta.

### Output

Tutti i risultati vengono salvati in:

`/content/drive/MyDrive/music_emotion_art_4q_project`
