# Projet d’Analyse des Transactions Bancaires

## Description
Ce projet consiste à nettoyer, analyser et enrichir des données de transactions bancaires afin de :
- Améliorer la qualité des données
- Détecter les anomalies (fraude ou erreurs)
- Créer de nouvelles variables (feature engineering)
- Préparer les données pour l’analyse ou le Machine Learning

---

## Dataset
Fichier utilisé : `bankdata.csv`

Variables principales :
- transaction_id
- client_id
- montant
- date_transaction
- score_credit_client
- type_operation
- agence
- devise

---

## Nettoyage des données

### Suppression des doublons
- Basée sur `transaction_id`
- Conservation de la première occurrence

### Correction des formats
- `montant` → conversion en float
- `solde_avant` → suppression "EUR" puis conversion
- `date_transaction` → format datetime

### Normalisation
- `devise` → MAJUSCULE
- `segment_client` → Title Case
- `agence` → suppression des espaces

### Valeurs manquantes
- Numériques → médiane
- Catégorielles → mode

---

## Détection des anomalies

### Méthodes utilisées
- IQR → valeurs extrêmes
- Z-score → seuil |Z| > 3
- Règle métier → score entre 0 et 850

### Variable finale
`is_anomaly` : combinaison de toutes les anomalies

---

## Feature Engineering

### Variables temporelles
- annee
- mois
- trimestre
- jour_semaine

### Vérification des montants
- `montant_eur_verifie`
- `montant_eur_diff`

### Catégorie de risque
- High
- Medium
- Low

### Solde net par client
Crédit - Débit

### Agrégation client
- Nombre de transactions
- Montant moyen
- Produits distincts

### Taux de rejet par agence
- Pourcentage de transactions rejetées

---

## Visualisation
- Graphique des valeurs manquantes

---

## Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy

---

## Résultats
- Données propres et exploitables
- Anomalies détectées
- Variables enrichies
- Dataset prêt pour analyse ou ML

---

## Améliorations possibles
- Dashboard avec Streamlit
- Détection de fraude (Machine Learning)
- Segmentation client
- Analyse avancée

---

## Auteur
Lamiyaa El Arabi
