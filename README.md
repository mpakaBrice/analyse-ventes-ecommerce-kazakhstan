# 📊 Analyse des ventes e-commerce – Kazakhstan 2020

> **Quels produits, marques et périodes portent le chiffre d'affaires, et où concentrer les efforts en 2021 ?**

Projet d'analyse de données de bout en bout : **2,6 millions de lignes** de ventes d'une enseigne en ligne d'électronique et d'électroménager, nettoyées et analysées en **Python**, puis restituées dans un **tableau de bord Power BI** avec des recommandations business.


---

## 🎯 Contexte et problématique

Fin 2020, la direction d'une enseigne e-commerce d'électronique au Kazakhstan prépare son budget 2021. Elle veut savoir :

1. Comment le chiffre d'affaires a-t-il évolué en 2020, notamment pendant le confinement ?
2. Quelles catégories et quelles marques génèrent le CA ?
3. Le CA est-il concentré sur peu de produits ?
4. À quoi ressemble un panier, et quels produits sont achetés ensemble ?
5. Les clients reviennent-ils acheter ? Qui sont les meilleurs clients ?

---

## 🧰 Outils

| Étape | Outils |
|---|---|
| Nettoyage et analyse | Python (pandas, matplotlib), Jupyter Notebook |
| Préparation des données | Power Query |
| Modélisation et mesures | Power BI, DAX |
| Visualisation | Power BI Desktop |

---

## 📁 Données

- **Source :** [nom du dataset](LIEN_KAGGLE_ICI)
- **Période :** janvier – novembre 2020
- **Volume :** 2 633 521 lignes · 1,4 million de commandes · 25 000 produits
- **Colonnes :** date, commande, produit, catégorie, marque, prix, client


---

## 🧹 Nettoyage des données

Le fichier brut contenait plusieurs problèmes de qualité, chacun traité et documenté :

| Problème | Lignes concernées | Décision |
|---|---|---|
| **Colonnes décalées** : le prix était rangé dans la catégorie, le client dans la marque | 431 954 (16 %) | **Réparées** (valeurs remises dans la bonne colonne) |
| Dates invalides (1970) | 19 631 | Supprimées |
| Doublons exacts | 675 | Supprimés |
| Prix à 0 | 3 813 | Supprimés |
| Catégorie ou marque manquante | ~40 % | Étiquetées `unknown` |
| Prix très bas (< 1) et très élevés | — | Vérifiés et conservés : prix stables pour chaque produit |

**Résultat :** 2 609 402 lignes conservées, soit **99 % des données**.

La découverte des colonnes décalées a permis de **récupérer 16 % des données** au lieu de les supprimer.

---

## 🔍 Résultats clés

| | |
|---|---|
| 💰 **346,7 M** de chiffre d'affaires | 🛒 **243** de panier moyen |
| 📦 **1,42 M** de commandes | 🔁 **32 %** de taux de réachat |

- **Effet COVID :** le CA chute de **−80 % en avril** pendant l'état d'urgence, puis repart fortement. **Août** est le meilleur mois (53,5 M).
- **Concentration :** **6,4 % des produits font 80 % du CA**, et les smartphones pèsent à eux seuls 29 % du CA total.
- **Marques :** Samsung et Apple contrôlent **78 % du marché smartphone**.
- **Panier :** **61 % des commandes** ne contiennent qu'un seul article. Smartphone + TV est l'association la plus fréquente (12 541 commandes).
- **Clients :** **19 % des clients génèrent 44 % du CA** (segmentation RFM).
- **Moments clés :** les commandes se concentrent entre **10 h et 19 h** (heure locale) et le **vendredi-samedi**.

---

## 📈 Tableau de bord Power BI

| Page | Question |
|---|---|
| **Accueil** | Présentation du projet et chiffres clés |
| **1 · Vue d'ensemble** | Comment va l'activité ? |
| **2 · Quand vend-on ?** | Quels sont les moments forts et faibles ? |
| **3 · Quoi et quelles marques ?** | Qu'est-ce qui fait le CA, et de qui dépend-on ? |
| **4 · Panier et clients** | Comment augmenter le panier et fidéliser ? |

<details>
<summary>📸 Voir toutes les pages</summary>

![Accueil](images/page_0_accueil.png)
![Vue d'ensemble](images/page_1_vue_ensemble.png)
![Quand vend-on ?](images/page_2_quand_vend_on.png)
![Quoi et quelles marques ?](images/page_3_quoi_marques.png)
![Panier et clients](images/page_4_panier_clients.png)

</details>

---

## 💡 Recommandations

| # | Constat | Recommandation | Indicateur à suivre |
|---|---|---|---|
| 1 | 6,4 % des produits font 80 % du CA | Suivi de stock prioritaire et stock de sécurité sur ces produits | Taux de rupture du top produits |
| 2 | Pics en juin-septembre, le vendredi-samedi et vers 15-16 h | Lancer les campagnes **avant** les pics et programmer les envois aux heures fortes | CA de l'été, taux de conversion |
| 3 | 61 % des commandes n'ont qu'un seul article | Suggestions « souvent acheté avec » et packs (cuisine, smartphone + accessoires) | Panier moyen, part des commandes à 2 articles ou plus |
| 4 | 19 % des clients font 44 % du CA ; les clients « à risque » pèsent 27 % | Programme de fidélité et campagne de réactivation ciblée | Taux de réachat |
| 5 | Samsung et Apple = 78 % des smartphones | Négocier les conditions fournisseurs et développer des marques alternatives | Part du CA hors Samsung et Apple |
| ➕ | 40 % des lignes sans catégorie, 77 % sans client identifié | Fiabiliser l'export et rendre la catégorie obligatoire | Taux de lignes complètes |

---

## ⚠️ Limites de l'analyse

- **~40 % des lignes sans catégorie connue :** elles ne représentent que 13 % du CA, mais les analyses par catégorie portent sur les catégories connues.
- **~77 % des lignes sans client identifié :** la partie clients (RFM, réachat) porte sur un **échantillon de 23 %**.
- **Novembre incomplet** (données jusqu'au 21/11). La baisse d'octobre reste à expliquer.
- **Devise non précisée** dans les données.

---


## 👤 Auteur

**Mpaka Brice** – Data Analyst <br> <br>
https://bit.ly/Portfolio-Brice-Mpaka <br> <br>
https://www.linkedin.com/in/bricempaka/


