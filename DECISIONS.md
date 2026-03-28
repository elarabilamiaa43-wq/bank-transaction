
# DECISIONS DE NETTOYAGE

- Doublons supprimés par transaction_id
- Dates uniformisées au format AAAA-MM-JJ HH:MM:SS
- Montants et solde_avant convertis en float, virgules remplacées par points
- Devises en majuscules, segment_client title-case
- Espaces parasites supprimés dans agence
- Valeurs manquantes imputées par médiane ou mode
- Valeurs aberrantes détectées par IQR et flaggées (is_anomaly)
- Nouvelles features créées : année, mois, trimestre, jour_semaine, montant_eur_verifie, categorie_risque, solde_net, nb_transactions, montant_moyen, nb_produits_distincts, taux_rejet
