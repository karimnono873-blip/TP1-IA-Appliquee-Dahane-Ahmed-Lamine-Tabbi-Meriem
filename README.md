# TP N°1 : Classification de Clients avec Random Forest 🛒🌌

**Auteur :** Dahane Ahmed Lamine  
**Enseignante :** Mme. Fergani  
**Module :** Machine Learning / Data Science  

---

## 🎯 Objectif du Projet

Ce projet met en pratique l'algorithme d'apprentissage supervisé **Random Forest** pour segmenter les clients d'un centre commercial. L'objectif principal est de prédire la catégorie de dépense d'un client (Petit, Moyen ou Gros dépenseur) en se basant sur des données démographiques telles que l'âge, le revenu annuel et le genre.

Le livrable final de ce projet est un compte-rendu sous la forme d'une **page web HTML monolithique et interactive** (thème astronomie/galaxie) qui contient toute la théorie, le code, les résultats d'exécution et des visualisations générées nativement en CSS.

---

## 📊 À propos du Dataset

Le jeu de données utilisé est **Mall_Customers.csv**. Il contient 200 enregistrements avec les variables suivantes :
* `CustomerID` : Identifiant unique du client.
* `Gender` : Genre du client (Male/Female).
* `Age` : Âge.
* `Annual Income (k$)` : Revenu annuel estimé en milliers de dollars.
* `Spending Score (1-100)` : Score de dépense attribué par le centre commercial.

---

## ⚙️ Méthodologie et Prétraitement (Data Preprocessing)

Pour transformer ce problème non labellisé en un problème de classification supervisée, les étapes suivantes ont été réalisées :

1. **Labellisation (`pd.cut`) :** Discrétisation de la variable continue `Spending Score` en 3 classes cibles :
   * **0 : Petit** (Score de 0 à 40)
   * **1 : Moyen** (Score de 40 à 70)
   * **2 : Gros** (Score de 70 à 100)
2. **Prévention du Data Leakage (`drop`) :** Suppression de la colonne `Spending Score` pour éviter que l'algorithme ne triche (puisque c'est cette colonne qui a créé les labels). Suppression également de `CustomerID`.
3. **Encodage (`get_dummies`) :** Transformation de la variable textuelle `Gender` en variable binaire (`Gender_Male` : 0 ou 1) exploitable par l'algorithme.

---

## 📈 Évaluation et Visualisations natives

Le modèle **RandomForestClassifier** (configuré avec 100 arbres) est évalué et analysé au sein du rapport HTML grâce à :
* **Un Rapport de Classification textuel :** Détaillant l'Accuracy globale (~65%), la précision, le rappel et le F1-score pour chaque classe.
* **L'Importance des Variables (Feature Importances) :** Un diagramme en barres stylisé en CSS montrant que le Revenu Annuel (51.5%) et l'Âge (44.2%) sont les prédicteurs les plus forts, rendant le Genre négligeable.
* **Une Matrice de Confusion (Heatmap) :** Un tableau thermique intégré en HTML/CSS croisant les vraies catégories avec les prédictions, mettant en évidence les forces (bonne détection de la classe moyenne) et les faiblesses du modèle.

---

## 🚀 Structure du Dépôt

* 📄 `TP1_Random_Forest_Corrige.html` : Le compte-rendu complet, stylisé et autonome. Les graphiques et les résultats y sont intégrés directement en HTML/CSS. **(Il suffit de l'ouvrir dans un navigateur)**
* 📁 `Mall_Customers.csv` : Le jeu de données source.
* 📝 `README.md` : Ce fichier de présentation.

---

## 💻 Comment utiliser ce projet ?

1. **Pour lire le rapport :** Téléchargez simplement le fichier `TP1_Random_Forest_Corrige.html` et ouvrez-le avec Chrome, Firefox ou Edge. Aucune installation Python n'est requise pour visualiser le rapport complet.
2. **Pour exécuter le code :** Le script Python exact est disponible dans le rapport web. Vous pouvez le copier-coller dans **Google Colab** (en utilisant `files.upload()`) ou dans un notebook local.

**Dépendances Python nécessaires pour l'exécution :**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
