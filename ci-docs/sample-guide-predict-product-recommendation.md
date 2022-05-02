---
title: Exemple de guide de prédiction de recommandation de produit
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de recommandation de produit prédéfini.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646293"
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

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

5. Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**

6. **Enregistrez** la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise

1. Dans le champ **Nom** du volet latéral, renommez votre source de données **Requête** en **eCommercePurchases**.

1. **Enregistrez** la source de données.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.

1. **Enregistrez** la source de données.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

Après avoir ingéré les données, nous commençons maintenant le processus d’unification des données pour créer un profil client unifié. Pour plus d’informations, consultez [Unification des données](data-unification.md).

### <a name="map"></a>Mappage

1. Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants. Accédez à **Données** > **Unifier** > **Mettre en correspondance**.

2. Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.

   ![Unifiez les sources de données d’eCommerce et du programme de fidélité.](media/unify-ecommerce-loyalty.png)

3. Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.

   ![Unifiez LoyaltyId comme clé primaire.](media/unify-loyaltyid.png)

### <a name="match"></a>Correspondance

1. Accédez à l’onglet **Mettre en correspondance** et sélectionnez **Définir l’ordre**.

2. Dans la liste déroulante **Principal**, choisissez **eCommerceContacts : eCommerce** comme source principale et incluez tous les enregistrements.

3. Dans la liste déroulante **Entité 2**, choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.

   ![Unifiez l’ordre de mise en correspondance des données d’eCommerce et du programme de fidélité.](media/unify-match-order.png)

4. Sélectionnez **Créer une nouvelle règle**

5. Ajoutez votre première condition en utilisant FullName.

   - Pour eCommerceContacts, sélectionnez **FullName** dans la liste déroulante.
   - Pour loyCustomers, sélectionnez **FullName** dans la liste déroulante.
   - Sélectionnez la liste déroulante **Normaliser** et choisissez **Type (téléphone, nom, adresse, ...)**.
   - Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.

6. Saisissez le nom **FullName, Email** pour la nouvelle règle.

   - Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **Ajouter une condition**
   - Pour l’entité eCommerceContacts, choisissez **E-mail** dans la liste déroulante.
   - Pour l’entité loyCustomers, choisissez **E-mail** dans la liste déroulante.
   - Laissez le champ Normaliser vide.
   - Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.

   ![Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.](media/unify-match-rule.png)

7. Sélectionnez **Enregistrer** et **Exécuter**.

### <a name="merge"></a>Fusionner

1. Accédez à l’onglet **Fusionner**.

1. Dans le champ **ContactId** de l’entité **loyCustomers**, modifiez le nom d’affichage en **ContactIdLOYALTY** pour le différencier des autres ID ingérés.

   ![Renommez contactid à partir de l’ID du programme de fidélité.](media/unify-merge-contactid.png)

1. Sélectionnez **Enregistrer** et **Exécuter** pour démarrer le processus de fusion.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tâche 3 – Configurer la recommandation de produit prédiction

Une fois les profils clients unifiés en place, nous pouvons maintenant exécuter la prédiction de l’attrition des abonnements.

1. Aller à **Intelligence** > **Prédiction**, choisir **Recommandation de produit**.

1. Cliquez sur **Démarrer**.

1. Nommez le modèle **Modèle de recommandation de produit prédéfinis prédiction** et l’entité de sortie **OOBProductRecommendationModelPrediction**.

1. Définissez trois conditions pour le modèle :

   - **Nombre de produits** : Définissez cette valeur sur **5**. Ce paramètre définit le nombre de produits que vous souhaitez recommander à vos clients.

   - **Achats répétés attendus** : Sélectionnez **Oui** pour indiquer que vous souhaitez inclure dans la recommandation des produits que vos clients ont déjà achetés.

   - **Fenêtre de consultation :** Sélectionnez au moins **365 jours**. Ce paramètre définit la consultation de l’activité du client à utiliser comme entrée dans les recommandations.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Préférences de modèle pour le modèle de recommandation de produit.":::

1. Sélectionnez **Données requises** et sélectionnez **Ajouter des données** pour l’historique des achats.

1. Ajoutez l’entité **eCommercePurchases : eCommerce** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.

1. Associez l’entité **eCommercePurchases : eCommerce** à **eCommerceContacts : eCommerce**.

   ![Associez les entités d’eCommerce.](media/model-purchase-join.png)

1. Sélectionnez **Suivant** pour définir la planification du modèle.

   Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées. Dans cet exemple, sélectionnez **Mensuel**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.


## <a name="task-4---review-model-results-and-explanations"></a>Tâche 4 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Vous pouvez maintenant passer en revue les explications du modèle recommandation de produit. Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tâche 5 – Créer un segment de produits très achetés

L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.

Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1. Accédez à **Segments**. Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.

   ![Création d’un segment avec la sortie du modèle.](media/segment-intelligence.png)

1. Sélectionnez le point de terminaison **OOBProductRecommendationModelPrediction** et définissez le segment :

   - Champ : ProductID
   - Opérateur : Valeur
   - Valeur : Sélectionnez les trois premiers ID de produit

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Créez un segment à partir des résultats du modèle.":::

Vous disposez désormais d’un segment mis à jour dynamiquement qui identifie les clients les plus disposés à acheter les trois produits les plus recommandés 

Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
