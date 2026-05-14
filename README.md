# Klassificering av ansiktsuttryck med CNN

Detta repository innehåller min individuella inlämningsuppgift i Deep Learning.

Syftet är att bygga, träna, utvärdera och använda en CNN-modell som klassificerar ansiktsuttryck från bilder.

Datasetet som används är FER-2013, som består av gråskalebilder av ansikten med storleken 48x48 pixlar.

## Filer

```text
notebook.ipynb
fer2013_best_model.keras
README.md
.gitignore
```

| Fil | Beskrivning |
|---|---|
| `notebook.ipynb` | Notebook med kod, resultat, analys och reflektion |
| `fer2013_best_model.keras` | Sparad tränad modell |
| `README.md` | Beskrivning av projektet |
| `.gitignore` | Filer/mappar som inte laddas upp |

## Dataset

Datasetet `FER-2013.zip` är inte uppladdat till GitHub eftersom filen är stor.

För att köra notebooken ska `FER-2013.zip` ligga i samma mapp som `notebook.ipynb`.

Datasetet innehåller sju klasser:

- angry
- disgust
- fear
- happy
- neutral
- sad
- surprise

När notebooken körs packas datasetet upp automatiskt till mappen `data/`.

## Installation

Skapa virtual environment:

```bash
python -m venv .venv
```

Aktivera i Git Bash:

```bash
source .venv/Scripts/activate
```

Installera bibliotek:

```bash
pip install tensorflow scikit-learn seaborn matplotlib numpy pandas
```

## Körning

1. Lägg `FER-2013.zip` i samma mapp som `notebook.ipynb`.
2. Öppna `notebook.ipynb` i VS Code eller Jupyter Notebook.
3. Välj Python-kernel, till exempel `.venv`.
4. Kör alla celler uppifrån och ner.
5. Den bästa modellen sparas som `fer2013_best_model.keras`.

## Modell

I notebooken testas två CNN-modeller:

1. **Baseline CNN** - en enklare CNN-modell.
2. **Improved CNN** - en förbättrad modell med fler convolutional layers, dropout, batch normalization och data augmentation.

## Resultat

| Modell | Test accuracy |
|---|---:|
| Baseline CNN | 0.264 |
| Improved CNN | 0.499 |

Den bästa modellen var **Improved CNN**.

## Kort analys

Improved CNN presterade bättre än Baseline CNN på testdatan. Det tyder på att fler convolutional layers, dropout, batch normalization och data augmentation förbättrade modellens generalisering.

Baseline-modellen visade tecken på overfitting eftersom training accuracy var högre än validation accuracy.

Modellen är inte perfekt eftersom bilderna är små, i gråskala och vissa ansiktsuttryck liknar varandra.

## Sparad modell

Den tränade modellen sparas som:

```text
fer2013_best_model.keras
```

Den kan laddas med:

```python
import tensorflow as tf
model = tf.keras.models.load_model("fer2013_best_model.keras")
```

## Begränsningar

- Bilderna är endast 48x48 pixlar.
- Bilderna är i gråskala.
- Vissa ansiktsuttryck är svåra att skilja åt.
- Datasetet kan innehålla otydliga eller felmärkta bilder.
- Modellen kanske inte fungerar lika bra på helt nya bilder från verkligheten.

## Krav som uppfylls

Notebooken innehåller:

- CNN-modell
- träning och validation
- testutvärdering med accuracy
- prediktion på ny bild
- sparad modell
- analys av overfitting och begränsningar
- jämförelse mellan två modeller

## Filer som inte laddas upp

Följande filer/mappar ignoreras:

```text
FER-2013.zip
data/
.venv/
__pycache__/
.ipynb_checkpoints/
```