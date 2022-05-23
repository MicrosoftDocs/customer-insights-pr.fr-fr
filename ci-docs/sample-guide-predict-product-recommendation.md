---
title: Exemple de guide de prédiction de recommandation de produit
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de recommandation de produit prédéfini.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762683"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Exemple de guide de prédiction de recommandation de produit

Nous vous présenterons un exemple de bout en bout de prédiction de recommandation de produit en utilisant les exemples de données fournis ci-dessous.

## <a name="scenario"></a>Scénario

Contoso est une société qui produit du café et des machines à café de haute qualité qu’elle vend sur son site web Contoso Coffee. Leur objectif est de comprendre quels produits doivent-ils recommander à leurs clients récurrents. Savoir ce que sont les clients **susceptible d’acheter**, peut les aider à économiser leurs efforts de marketing en se concentrant sur des éléments spécifiques.

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tâche 1 : ingérer les données

Consultez les articles [à propos de l’ingestion de données](data-sources.md) et [importation de sources de données à l’aide connecteurs Power Query](connect-power-query.md) spécifiquement. Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingérer les données client d’une plateforme d’eCommerce

1. Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce : [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**

1. **Enregistrez** la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données d’**achats en ligne** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise

1. Dans le champ **Nom** du volet latéral, renommez votre source de données **Requête** en **eCommercePurchases**.

1. **Enregistrez** la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.

1. **Enregistrez** la source de données.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tâche 3 – Configurer la recommandation de produit prédiction

Maintenant que les profils de clients unifiés sont en place, nous pouvons exécuter la prédiction de recommandation de produit.

1. Aller à **Intelligence** > **Prédiction**, choisir **Recommandation de produit**.

1. Cliquez sur **Démarrer**.

1. Nommez le modèle **Modèle de recommandation de produit prédéfinis prédiction** et l’entité de sortie **OOBProductRecommendationModelPrediction**.

1. Définissez trois conditions pour le modèle :

   - **Nombre de produits** : Définissez cette valeur sur **5**. Ce paramètre définit le nombre de produits que vous souhaitez recommander à vos clients.

   - **Achats répétés attendus** : Sélectionnez **Oui** pour indiquer que vous souhaitez inclure dans la recommandation des produits que vos clients ont déjà achetés.

   - **Fenêtre de consultation :** Sélectionnez au moins **365 jours**. Ce paramètre définit la consultation de l’activité du client à utiliser comme entrée dans les recommandations.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Préférences de modèle pour le modèle de recommandation de produit.":::

1. À l’étape **Ajouter les données requises**, sélectionnez **Ajouter des données**.

1. Dans le volet **Ajouter des données**, choisissez **SalesOrderLine** en tant qu’entité d’historique des achats. À ce stade, cette entité n’est probablement pas encore configurée. Ouvrez le lien dans le volet pour créer l’activité en procédant comme suit :
   1. Entrez un **Nom d’activité** et choisissez *eCommercePurchases:eCommerce* comme **Entité d’activité**. La **Clé primaire** est *PurchaseId*.
   1. Définissez et nommez la relation sur l’entité *eCommerceContacts:eCommerce* et choisissez **ContactId** comme clé étrangère.
   1. Pour l’unification des activités, définissez **Activité d’événement** comme *TotalPrice* et Horodateur sur *PurchasedOn*. Vous pouvez spécifier d’autres champs comme indiqué dans [Activités du client](activities.md).
   1. Pour **Type d’activité**, choisissez *SalesOrderLine*. Mappez les champs d’activité suivants :
      - ID de ligne de commande : PurchaseId
      - ID commande : PurchaseId
      - Données de commande : PurchasedOn
      - ID produit : ProductId
      - Montant : TotalPrice
   1. Passez les données en revue et terminez l’activité avant de revenir à la configuration du modèle.

1. De retour dans l’étape **Sélectionner des activités**, choisissez l’activité nouvellement créée dans la section **Activités**. Sélectionnez **Suivant** et le mappage d’attribut est déjà renseigné. Sélectionnez **Enregistrer**.

1. Dans cet exemple de guide, nous sautons les étapes **Ajouter des informations sur les produits** et **Filtres de produits** car nous n’avons pas de données sur les informations des produits.

1. À l’étape **Mises à jour des données**, définissez la planification du modèle.

   Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées. Dans cet exemple, sélectionnez **Mensuel**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**. Il faudra quelques minutes pour exécuter le modèle la première fois.

## <a name="task-4---review-model-results-and-explanations"></a>Tâche 4 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Vous pouvez maintenant passer en revue les explications du modèle recommandation de produit. Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tâche 5 – Créer un segment de produits très achetés

L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.

Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1. Accédez à **Segments**. Sélectionnez **Nouveau** et choisissez **Créer à partir d’Intelligence**.

   ![Création d’un segment avec la sortie du modèle.](media/segment-intelligence.png)

1. Sélectionnez le point de terminaison **OOBProductRecommendationModelPrediction** et définissez le segment :

   - Champ : ProductID
   - Valeur : Sélectionnez les trois premiers ID de produit

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Créez un segment à partir des résultats du modèle.":::

Vous disposez maintenant d’un segment mis à jour dynamiquement qui identifie les clients susceptibles d’être intéressés par l’achat des trois produits les plus recommandés.

Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
