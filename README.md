#  Analyse de la Dette Brute du Québec 2024-2025

## 1. Background & Overview
**Organisation :** Ministère des Finances du Québec (Données Ouvertes).  
Cette analyse vise à auditer la structure de la dette brute du Québec pour identifier les risques de refinancement et la répartition des types de produits financiers.

**Valeur Ajoutée & Objectifs :**
* **Évaluation du Risque :** Segmentation de la dette par maturité (Court, Moyen, Long terme).
* **Analyse de Performance :** Calcul des écarts (Spreads) entre les taux de coupon et le rendement du marché.
* **Optimisation de Liquidité :** Identification des besoins de financement par type de produit financier.

**Liens du Projet :**
* [🌐 Source des données (Données Québec)](https://www.donneesquebec.ca/)
* [📂 Voir les scripts SQL (Views)](SQL/vues_dette.sql)
* [🛠️ Voir le script de nettoyage (Power Query)](Scripts/nettoyage_power_query.txt)
*  [📈 Visualisation Power BI https://github.com/Philippetatieze/Philippe-tatieze/blob/main/jeuxemprunt.pbix

---

## 2. Data Structure Overview (ETL Process)
Le projet suit une architecture hybride **ETL (Extract, Transform, Load)** pour garantir la propreté et la performance des données.

### Étape 1 : Extraction & Nettoyage (Power Query)
Le fichier CSV original présentait des problèmes de formatage (séparateurs de milliers, dates non reconnues).
* **Action :** Nettoyage des caractères parasites, typage des données et création d'une **Clé Primaire (Index)** pour l'intégrité dans PostgreSQL.

### Étape 2 : Chargement & Transformation SQL (PostgreSQL)
Injection des données dans PostgreSQL pour centraliser la logique métier via des **Vues SQL**.
* **Action :** Création de 4 vues calculées pour alléger le rapport Power BI (Pushdown technique).

> ![Image du Modèle de Données](LIEN_VERS_IMAGE_MODELE_DONNEES)

---

## 3. Executive Deep Dive
L'analyse montre une dette solide, principalement sécurisée sur le long terme, ce qui protège la province contre la volatilité immédiate des taux d'intérêt.

![Capture du Dashboard Power BI](LIEN_VERS_IMAGE_DASHBOARD)

**Problématique Business résolue :** L'identification d'un calendrier de remboursement irrégulier permet d'anticiper les pressions sur l'encaisse du gouvernement, notamment en identifiant les années "creuses" pour de nouvelles émissions.

---

## 4. Insights Deep Dive
* **Le "Trou" de 2025 :** Les requêtes SQL ont révélé qu'aucun titre majeur n'arrive à échéance en 2025, offrant une fenêtre stratégique pour le refinancement.
* **Stabilité Long Terme :** Plus de 60% de la dette est contractée à plus de 5 ans, verrouillant des taux historiquement bas.
* **Analyse des Spreads :** Certains produits affichent un rendement investisseur supérieur au coupon, indiquant une valorisation positive du crédit du Québec sur les marchés.

---
## 5. Recommandations Business
1. **Stratégie de Refinancement :** Utiliser la fenêtre de 2025 pour émettre de nouveaux billets à court terme afin de lisser la charge de remboursement globale.
2. **Couverture de Taux :** Maintenir la priorité sur les obligations à taux fixe pour se protéger contre les hausses prévues des taux directeurs.
3. **Optimisation du Service de la Dette :** Prioriser le rachat ou le refinancement des titres ayant les spreads les plus élevés pour réduire les frais d'intérêt annuels.

---
**Compétences démontrées :** Power Query (M), SQL (PostgreSQL), Modélisation de données, Visualisation Power BI, Analyse financière.
