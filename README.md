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
Anstelle von klassischen Faltungsnetzwerken (CNNs) habe ich einen **Vision Transformer (ViT)** implementiert. Die Bilder wurden in Patches unterteilt und durch die Transformer-Architektur geleitet, um globale Zusammenhänge in den Bildern besser zu verstehen. 

### 2. Klassisches Machine Learning (ML)
Zum Vergleich habe ich die Bilddaten (z. B. durch Flattening oder das Extrahieren von Features) aufbereitet und mit mehreren traditionellen Machine Learning Algorithmen trainiert. Untersucht wurden unter anderem:
* Support Vector Machines (SVM)
* Random Forest
* K-Nearest Neighbors (KNN)
*(Passe diese Liste an die Algorithmen an, die du tatsächlich verwendet hast)*

## 🛠️ Verwendete Technologien
* **Python 3**
* **Deep Learning:** PyTorch / Hugging Face Transformers *(oder TensorFlow/Keras – bitte anpassen)*
* **Machine Learning:** Scikit-Learn
* **Datenverarbeitung & Visualisierung:** NumPy, Pandas, Matplotlib, Seaborn

## 📈 Ergebnisse & Vergleich
Hier vergleiche ich die Leistung der klassischen ML-Modelle mit der Performance des Vision Transformers.

* **Bester klassischer ML-Ansatz:** [Name des Modells, z.B. SVM] mit einer Genauigkeit von **XX.X%**
* **Vision Transformer (ViT):** Genauigkeit von **XX.X%**

*(Tipp: Hier kannst du kurz in ein bis zwei Sätzen erwähnen, warum der ViT besser/schlechter war oder dass er z. B. rechenintensiver, aber genauer ist.)*

## 🚀 So führst du den Code aus
1. Klone dieses Repository auf deinen PC:
   ```bash
   git clone https://github.com/DeinBenutzername/Dein-Repo-Name.git
