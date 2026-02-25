# Intel Image Classification: Vision Transformer vs. Classical ML 🌄🏙️

Dieses Repository enthält mein Projekt zur [Intel Image Classification Challenge auf Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification). Das Ziel dieses Projekts ist es, Bilder von Naturlandschaften und städtischen Umgebungen in sechs verschiedene Kategorien einzuteilen. 

Dabei vergleiche ich in zwei separaten Ansätzen einen modernen **Vision Transformer (ViT)** (Deep Learning) mit **verschiedenen klassischen Machine Learning Algorithmen**.

## 📊 Informationen zum Datensatz
Der Datensatz besteht aus etwa 25.000 Farbbildern (Größe 150x150 Pixel), die in folgende 6 Kategorien unterteilt sind:
* `0` -> Gebäude (Buildings) 🏢
* `1` -> Wald (Forest) 🌲
* `2` -> Gletscher (Glacier) 🧊
* `3` -> Berg (Mountain) ⛰️
* `4` -> Meer (Sea) 🌊
* `5` -> Straße (Street) 🛣️

*Hinweis: Der eigentliche Datensatz ist aufgrund seiner Größe nicht in diesem Repository enthalten. Du kannst ihn direkt über [Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) herunterladen.*

## 🧠 Methodik & Architektur

Das Projekt ist in zwei Hauptbereiche unterteilt:

### 1. Deep Learning (Vision Transformer)
Anstelle von klassischen Faltungsnetzwerken (CNNs) habe ich Transfer Learning mit einem vortrainierten **Vision Transformer (ViT-B/16)** (ImageNet-1k Gewichte) implementiert. Dabei wurde die Feature-Extraktion eingefroren und nur der finale Classification-Head auf die 6 neuen Kategorien trainiert. Das Modell wurde mit dem AdamW-Optimizer über 20 Epochen trainiert.

### 2. Klassisches Machine Learning (ML)
Für die traditionellen ML-Modelle habe ich eine eigene Feature-Extraktions-Pipeline gebaut. Die Features wurden kombiniert aus:
* **ResNet-50 (ohne Classification-Head):** Zur Extraktion von Farbinformationen.
* **HOG (Histogram of Oriented Gradients):** Zur Extraktion von Kanten- und Texturinformationen.

Diese kombinierten Feature-Vektoren wurden dann genutzt, um drei verschiedene klassische Machine Learning Modelle zu trainieren:
* Linear Support Vector Machine (Linear SVM)
* RBF Support Vector Machine (RBF-SVM)
* K-Nearest Neighbors (k-NN)
* Random Forest (mit 300 Bäumen)

## 🛠️ Verwendete Technologien
* **Python 3**
* **Deep Learning:** PyTorch / Torchvision
* **Machine Learning:** Scikit-Learn (SVC, KNeighborsClassifier, RandomForestClassifier)
* **Bildverarbeitung:** Scikit-Image (HOG-Features, Resizing)
* **Datenverarbeitung & Visualisierung:** NumPy, Pandas, Matplotlib, Tqdm

## 📈 Ergebnisse & Vergleich
Der moderne Vision Transformer erzielt auf dem Test-Datensatz eine sehr hohe und robuste Genauigkeit, jedoch zeigen auch die klassischen ML-Modelle – dank der starken Feature-Extraktion durch ResNet + HOG – beachtliche Ergebnisse.

**Klassisches Machine Learning:**
* **Random Forest:** 91.70 %
* **Linear SVM:** 90.80 %
* **k-NN:** 92.06 % *(Hinweis: Zeigt eine hohe Test Log-Loss von 0.74, was auf Unsicherheit bei Vorhersagen hindeutet)*
* **RBF-SVM:** **93.06 %** 🏆 *(Bestes klassisches Modell)*

**Deep Learning:**
* **Vision Transformer (ViT-B/16):** **93.43 %** 🚀

Der Vision Transformer übertrifft das beste klassische Modell leicht, lernt sehr schnell (stabiles Training über 20 Epochen) und zeigt in der Konfusionsmatrix eine hohe Präzision über alle Klassen hinweg.

## 🚀 So führst du den Code aus
1. Klone dieses Repository auf deinen PC:
   ```bash
   git clone https://github.com/DeinBenutzername/Dein-Repo-Name.git
