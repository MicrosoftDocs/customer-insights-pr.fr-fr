---
title: Prédire la valeur de durée de vie du client
description: Prévoyez le potentiel de revenus des clients actifs à l’avenir.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610371"
---
# <a name="predict-customer-lifetime-value-clv"></a>Prédire la valeur de durée de vie du client

Prévoyez la valeur potentielle (revenus) que les clients actifs individuels apporteront à votre entreprise sur une période future définie. Cette prédiction vous aide à :

- Identifier les clients à forte valeur ajoutée et traiter ces informations.
- Créer des segments de clientèle stratégiques en fonction de leur valeur potentielle pour mener des campagnes personnalisées avec des efforts de vente, de marketing et de soutien ciblés.
- Guider le développement de produits en se concentrant sur les fonctionnalités qui augmentent la valeur client.
- Optimiser la stratégie de vente ou de marketing et allouer le budget plus précisément pour la sensibilisation des clients.
- Reconnaître et récompenser les clients de grande valeur grâce à des programmes de fidélité ou de récompenses.

Déterminer ce que la CLV signifie pour votre entreprise. Nous prenons en charge la prédiction de la valeur de durée de vie du client basée sur les transactions. La valeur prédite d’un client est basée sur l’historique des transactions commerciales. Envisagez de créer plusieurs modèles avec des préférences d’entrée variables et comparez les résultats du modèle pour voir quel scénario de modèle correspond le mieux aux besoins de votre entreprise.

> [!TIP]
> Essayez la prédiction CLV en utilisant des exemples de données : [Exemple de guide de prédiction de la valeur de durée de vie du client (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Conditions préalables

- Au moins des autorisations [contributeur](permissions.md)
- Au moins 100 clients uniques, de préférence plus de 10 000 clients
- ID client, un identificateur unique pour faire correspondre les transactions à un client individuel
- Au moins, un an d’historique des transactions, de préférence deux à trois ans. Dans l’idéal, au moins deux ou trois transactions par ID client, de préférence sur plusieurs dates. L’historique des transactions doit inclure :
  - **ID de transaction** : identifiant unique de chaque transaction
  - **Date de transaction** : date ou horodateur de chaque transaction
  - **Montant de la transaction** : valeur monétaire (par exemple, chiffre d’affaires ou marge bénéficiaire) de chaque transaction
  - **Libellé affecté aux retours** : valeur booléenne vrai/faux indiquant si la transaction est un retour
  - **ID produit** : ID produit du produit impliqué dans la transaction
- Données sur les activités des clients :
  - **Clé primaire :** identificateur unique d’une activité
  - **Horodateur** : date et heure de l’événement identifié par la clé primaire
  - **Événement (nom de l’activité)**  : nom de l’événement que vous souhaitez utiliser
  - **Détails (montant ou valeur)**  : détails sur l’activité du client
- Données supplémentaires telles que :
  - Activités web : historique des visites du site web ou historique des e-mails
  - Activités de fidélisation : historique d’accumulation et d’échange de points de fidélité
  - Journal du service clientèle : appel de service, réclamation ou historique des retours
  - Informations sur le profil client
- Moins de 20 % de valeurs manquantes dans les champs obligatoires

> [!NOTE]
> Une seule entité de l’historique des transactions peut être configurée. S’il existe plusieurs entités d’achats ou de transactions, combinez-les dans Power Query avant l’ingestion des données.

## <a name="create-a-customer-lifetime-value-prediction"></a>Créer une prédiction de la valeur de durée de vie du client

Sélectionnez **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Le brouillon de prédiction s’affiche dans l’onglet **Mes prédictions**.

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Valeur de la durée de vie du client**.

1. Cliquez sur **Démarrer**.

1. **Nommez ce modèle** et le **Nom de l’entité de sortie** pour les distinguer des autres modèles ou entités.

1. Cliquez sur **Suivant**.

### <a name="define-model-preferences"></a>Définir les préférences de modèle

1. Définissez une **Période de prédiction** pour définir à quelle distance dans le futur vous souhaitez prédire la Valeur de la durée de vie du client. Par défaut, l’unité est définie sur les mois.

   > [!TIP]
   > Pour prédire avec précision la Valeur de la durée de vie du client pour la période définie, une période comparable de données historiques est nécessaire. Par exemple, si vous souhaitez prévoir la CLV pour les 12 prochains mois, vous devez disposez d’au moins 18 à 24 mois de données historiques.

1. Définissez le délai d’exécution dans lequel un client doit avoir eu au moins une transaction pour être considéré comme actif. Le modèle ne prédit la Valeur de la durée de vie du client que pour les **Clients actifs**.
   - **Laisser le modèle calculer l’intervalle d’achat (recommandé)**  : le modèle analyse vos données et détermine une période en fonction de l’historique des achats.
   - **Définir l’intervalle manuellement** : période pour votre définition d’un client actif.

1. Définissez le centile de **Client à forte valeur ajoutée**.
    - **Calcul du modèle (recommandé)**  : le modèle utilise la règle 80/20. Le pourcentage de clients ayant contribué à 80 % des revenus cumulés de votre entreprise au cours de la période historique est considéré comme des clients à forte valeur ajoutée. En règle générale, moins de 30 % à 40 % des clients contribuent à 80 % des revenus cumulés. Cependant, ce nombre peut varier en fonction de votre entreprise et de votre secteur d’activité.
    - **Pourcentage des meilleurs clients actifs** : centile spécifique pour un client à forte valeur ajoutée. Par exemple, saisissez **25** pour définir les clients à forte valeur comme 25 % des futurs clients payants.

    Si votre entreprise définit les clients à forte valeur ajoutée d’une manière différente, [donnez-vous votre avis, car nous aimerions le savoir](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Cliquez sur **Suivant**.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** pour **Historique des transactions client**.

1. Sélectionnez le type d’activité sémantique, **SalesOrder** ou **SalesOrderLine**, qui contient l’historique des transactions. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Ajouter les données requises pour le modèle CLV":::

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Ajoutez d’autres activités ou sélectionnez **Suivant**.

### <a name="add-optional-activity-data"></a>Ajouter des données d’activité supplémentaires

Les données reflétant les interactions client clés (comme le web, le service clientèle et les journaux d’événements) ajoutent du contexte aux enregistrements de transaction. Plus de modèles trouvés dans vos données d’activité client peuvent améliorer la précision des prévisions.

1. Sélectionnez **Ajouter des données** sous **Améliorer les aperçus de modèle grâce à des données d’activité supplémentaires**.

1. Sélectionnez un type d’activité qui correspond au type d’activité client que vous ajoutez. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Cliquez sur **Suivant**.

1. [Ajoutez des données client facultatives](#add-optional-customer-data) ou sélectionnez **Suivant** et accédez à [Définir la planification des mises à jour](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Ajouter des données client facultatives

Sélectionnez parmi 18 attributs de profil client couramment utilisés à inclure comme entrée dans le modèle. Ces attributs peuvent conduire à des résultats de modèle plus personnalisés, pertinents et exploitables pour vos cas d’utilisation métier.

Par exemple : Contoso Coffee souhaite prédire la valeur vie client pour cibler les clients à forte valeur ajoutée avec une offre personnalisée liée au lancement de leur nouvelle machine à expresso. Contoso utilise le modèle CLV et ajoute les 18 attributs de profil client pour voir quels facteurs influencent leurs clients les plus intéressants. Ils trouvent que l’emplacement du client est le facteur le plus influent pour ces clients.
Avec ces informations, ils organisent un événement local pour le lancement de la machine à expresso et s’associent à des vendeurs locaux pour des offres personnalisées et une expérience spéciale lors de l’événement. Sans ces informations, Contoso n’aurait peut-être envoyé que des e-mails marketing génériques et aurait raté l’occasion de personnaliser pour ce segment local de ses clients de grande valeur.

1. Sélectionnez **Ajouter des données** sous **Améliorer encore plus les aperçus du modèle grâce à des données supplémentaires sur les clients**.

1. Pour **Entité**, choisissez **Client : CustomerInsights** pour sélectionner le profil client unifié correspondant aux données d’attribut client. Pour **ID client**, choisissez **System.Customer.CustomerId**.

1. Mappez plus de champs si les données sont disponibles dans vos profils client unifiés.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemple de champs mappés pour les données de profil client.":::

1. Cliquez sur **Enregistrer**.

1. Cliquez sur **Suivant**.

### <a name="set-update-schedule"></a>Définir le planning de mise à jour

1. Choisissez la fréquence de renouvellement de l’entraînement de votre modèle en fonction des dernières données. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

### <a name="review-and-run-the-model-configuration"></a>Examiner et exécuter la configuration du modèle

L’étape **Réviser et exécuter** affiche un résumé de la configuration et offre la possibilité d’apporter des modifications avant de créer la prédiction.

1. Sélectionnez **Modifier** dans l’une des étapes pour réviser et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Cliquez sur **Terminé**. L’onglet **Mes prédictions** s’affiche pendant la création de la prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Afficher les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Mes prédictions**, sélectionnez la prédiction que vous souhaitez afficher.

La page de résultats comporte trois sections principales de données.

- **Performances du modèle de formation** : les notes A, B et C indiquent les performances de la prédiction et peuvent vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Image de la zone d’informations du score du modèle avec la note A.":::

  Customer Insights évalue les performances du modèle IA pour prédire les clients à forte valeur par rapport à un modèle de référence.

  Les notes sont calculées selon les règles suivantes :
  - **A** lorsque le modèle a prédit avec précision au moins 5 % de clients à forte valeur ajoutée en plus par rapport au modèle de référence.
  - **B** lorsque le modèle a prédit avec précision entre 0 % et 5 % de clients à forte valeur ajoutée en plus par rapport au modèle de référence.
  - **C** lorsque le modèle a prédit avec précision moins de clients à forte valeur ajoutée en plus par rapport au modèle de référence.
  
  Sélectionnez [**En savoir plus sur ce score**](#learn-about-the-score) pour ouvrir le volet **Évaluation du modèle** qui affiche des détails supplémentaires sur les performances du modèle IA et le modèle de référence. Il vous aidera à mieux comprendre les mesures de performance du modèle sous-jacent et comment la note de performance finale du modèle a été obtenue. Le modèle de base utilise une approche non basée sur l’IA pour calculer la valeur de la durée de vie du client en se basant principalement sur les achats historiques effectués par les clients.

- **Valeur des clients par centile** : les clients à faible et à forte valeur ajoutée s’affichent dans un graphique. Survolez les barres de l’histogramme pour voir le nombre de clients dans chaque groupe et la valeur de la durée de vie du client moyenne de ce groupe. Éventuellement, [créez des segments de clients](prediction-based-segment.md) sur la base de leurs prédictions CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valeur des clients par centile pour le modèle CLV":::

- **Facteurs les plus influents** : Différents facteurs sont pris en compte lors de la création de votre prédiction de valeur de la durée de vie du client en fonction des données d’entrée fournies au modèle IA. Chacun de ces facteurs a son importance calculée pour les prévisions agrégées qu’un modèle crée. Utilisez ces facteurs pour valider les résultats de votre prédiction. Ces facteurs permettent également de mieux comprendre les facteurs les plus influents qui ont contribué à prédire la valeur de la durée de vie du client pour tous vos clients.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Facteurs les plus influents pour le modèle CLV":::

### <a name="learn-about-the-score"></a>En savoir plus sur le score

Formule standard utilisée pour calculer la valeur de la durée de vie du client par le modèle de référence :

 _**Valeur de la durée de vie du client pour chaque client** = Achat mensuel moyen effectué par le client dans la fenêtre client actif * Nombre de mois dans la période de prédiction de la valeur de la durée de vie du client * Taux de rétention global de tous les clients*_

Le modèle IA est comparé au modèle de base sur la base de deux mesures de performance du modèle.
  
- **Taux de réussite de la prédiction des clients à forte valeur ajoutée**

  Voyez la différence entre la prévision des clients à forte valeur ajoutée à l’aide du modèle IA et le modèle de référence. Par exemple, un taux de réussite de 84 % signifie que sur tous les clients à forte valeur ajoutée dans les données d’entraînement, le modèle IA a pu capturer avec une précision 84 %. Nous comparons ensuite ce taux de réussite avec le taux de réussite du modèle de référence pour rendre compte du changement relatif. Cette valeur est utilisée pour attribuer une note au modèle.

- **Mesures d’erreur**

  Examinez les performances globales du modèle en termes d’erreur de prédiction des valeurs futures. Nous utilisons la métrique globale de l’erreur quadratique moyenne (RMSE) pour évaluer cette erreur. La RMSE est un moyen standard de mesurer l’erreur d’un modèle dans la prédiction de données quantitatives. La RMSE du modèle IA est comparée à la RMSE du modèle de base et la différence relative est rapportée.

Le modèle IA donne la priorité au classement précis des clients en fonction de la valeur qu’ils apportent à votre entreprise. Ainsi, seul le taux de réussite de la prédiction des clients à forte valeur ajoutée est utilisé pour calculer la note finale du modèle. La métrique RMSE est sensible aux valeurs aberrantes. Dans les scénarios où vous avez un petit pourcentage de clients avec des valeurs d’achat extrêmement élevées, la métrique RMSE globale peut ne pas donner une image complète des performances du modèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
