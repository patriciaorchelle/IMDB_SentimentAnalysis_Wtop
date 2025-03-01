**Projet** : Analyse des Sentiments sur les Reviews (Critiques de films) IMDB

**Objectif** : Développer un modèle de Machine Learning pour prédire la polarité des avis (positif/négatif) sur IMDb en utilisant différentes techniques de vectorisation et de classification.


Le dataset **IMDB Reviews** est une référence en **analyse des sentiments** et est souvent utilisé pour l'entraînement et l'évaluation des modèles de classification de texte.

### **Présentation du dataset IMDB Reviews**
- **Nom** : IMDB Large Movie Review Dataset
- **Taille** : **50 000 critiques de films** (reviews)  
- **Labels** : Sentiments positifs (`1`) ou négatifs (`0`)
- **Format des données** :  
  - Chaque critique est un **fichier texte**.
  - Organisé en **train/test**, avec **25 000 reviews** pour l'entraînement et **25 000 reviews** pour le test.
  - Chaque set contient **12 500 critiques positives** et **12 500 négatives**.
  - Les critiques sont équilibrées : **50% positives, 50% négatives**.

### **Organisation du dataset**
Après extraction, la structure du dataset ressemble à ceci :

```
aclImdb/
│── train/
│   ├── pos/  # 12 500 critiques positives
│   ├── neg/  # 12 500 critiques négatives
│── test/
│   ├── pos/  # 12 500 critiques positives
│   ├── neg/  # 12 500 critiques négatives
```

Chaque fichier texte contient **une critique de film**.


### **Objectif en NLP**
L'objectif principal est de **classifier les critiques en "positives" ou "négatives"** en utilisant des méthodes de **traitement du langage naturel (NLP)**.


### **Exemple d'une critique**
 **Fichier dans `train/pos/` :**

This movie was absolutely amazing! The story was engaging, and the actors delivered fantastic performances. Highly recommend!

 **Label** : `1` (positif)

 **Fichier dans `train/neg/` :**
```
I was really disappointed by this movie. The plot was boring and predictable, and the acting was terrible. Not worth watching.
```
 **Label** : `0` (négatif)


###  **Ce que nous allons faire avec ce dataset**
 
 **I. Exploration des données**
  - Exploration des données : Chargement et affichage des critiques.
  - Analyse de la distribution des sentiments : Répartition équilibrée entre positif/négatif.
  - Statistiques sur les longueurs des critiques : Boxplot et histogramme.
  - WordCloud : Visualisation des mots fréquents en positif et négatif.
  - Corrélation entre longueur et sentiment : Vérifier si les avis positifs sont plus longs.

 **II. Prétraitement des textes**
- **Nettoyage des données** : suppression des balises HTML, des ponctuations, conversion en minuscules.
- **Tokenization** : découpage du texte en mots.
- **Suppression des stopwords** (mots fréquents mais peu informatifs : "the", "is", "and"...).
- **Lemmatisation ou Stemming** : réduire les mots à leur forme de base.

 **III. Modélisation en Machine Learning**
1. **Vectorisation du texte** avec `CountVectorizer`,`TfidfVectorizer`, `Word2Vec`.
2. **Entraînement d'un modèle de classification** :
   - Modèles classiques : **Logistic Regression, Naïve Bayes, SVM, Random Forest**.
   - Modèles avancés (future amélioration) : **, GloVe, Transformers (BERT, DistilBERT, etc.)**.


 **IV. Évaluation des performances**
- **Métriques classiques** : Précision, Recall, F1-score, Matrice de confusion.
- **Visualisation des erreurs** : Examiner les avis mal classifiés.
