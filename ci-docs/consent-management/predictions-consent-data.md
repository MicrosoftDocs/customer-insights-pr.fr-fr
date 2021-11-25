---
title: Données de consentement dans des prédictions prêtes à l'emploi
description: Découvrez comment créer des modèles de prédiction qui utilisent les données de consentement.
ms.date: 10/30/2021
ms.service: customer-insights
ms.topic: how-to
author: dimutako
ms.author: dimutako
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e08f2616be66d0676cdfa7891190d613d6948972
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753041"
---
# <a name="use-consent-data-in-prediction-models"></a>Utilisez des données de consentement dans des modèles de prédiction

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Créez des modèles de prédiction prêts à l'emploi dans des informations d'audience pour prédire l'attrition des clients ou la valeur de la durée de vie des clients. Utilisez les données de consentement de la fonction de [gestion des consentements](overview.md) pour augmenter la précision des prédictions. Comprenez l'influence du consentement du client sur l'attrition des clients ou la valeur de la durée de vie des clients. 

Cet article explique comment utiliser les données de consentement dans des modèles prêts à l'emploi. Les étapes ci-dessous se concentrent sur le modèle sur le modèle d'attrition des clients pour les transactions. Cependant, vous pouvez appliquer les mêmes étapes aux modèles d'attrition des clients ou de valeur de la durée de vie des clients. 

## <a name="required-entities-and-fields"></a>Champs et entités requis

La liste suivante comprend les entités requises et les champs que ces entités doivent contenir. Pour plus d'informations, consultez les [Conditions préalables requises pour un modèle de transaction](../audience-insights/predict-transactional-churn.md).

1. Entité de *Consentement d'abonnement*
    - **Clé primaire ou ID :** une clé primaire pour chaque valeur de consentement unique. Il nécessite des valeurs uniques dans chaque ligne. Par exemple, un e-mail ou un ID client. 
    - **ID client :** un identifiant client qui relie l'entité de consentement à l'entité client et à leurs données de transaction. Cet identifiant doit être le même dans toutes les entités requises. 
    - **Date de début du consentement :** la date à laquelle le consentement a été mis à jour. Ce champ peut également inclure l'heure.
    - **Statut du consentement :** Une valeur de consentement qui indique quels clients ont consenti.
    
2.  Entité *Transactions client*
    - **ID de transaction :** une clé primaire pour chaque transaction.
    - **ID client :** un identifiant client qui relie l'entité de consentement à l'entité client et à leurs données de transaction. Cet identifiant doit être le même dans toutes les entités requises. 
    - **Date de la transaction :** date de chaque opération.
    - **Valeur de l'opération :** Montant de chaque transaction.
    - **Étiquette attribuée aux retours** (facultatif) : valeur booléenne qui indique si la transaction est un retour.
    - **Identifiant de produit unique** (facultatif) : ID qui représente le produit ou le service de la transaction. 

3.  Entité *Client* avec une clé primaire représentant chaque client unique. Cet identifiant doit être le même dans toutes les entités requises. 

## <a name="set-up-instructions"></a>Instructions d’installation

Cette section explique comment utiliser les données de consentement en tant qu'entrée de données d'activité dans le modèle d'attrition des transactions. Il s'agit de mettre en place une activité basée sur des données de consentement. Ensuite, vous configurez le modèle comme d'habitude et ajoutez l'activité de consentement en tant qu'activité client dans la configuration du modèle.

### <a name="step-1-create-a-consent-activity"></a>Étape 1 : Créer une activité de consentement

[Créez une activité](../audience-insights/activities.md) en fonction de votre entité de consentement. 

1. Démarrez l'expérience guidée pour créer une activité.
1. À l'étape **Relations**, sélectionnez l'*ID client* de l'entité *Consentement* comme clé étrangère.
1. Choisissez l'entité *Client* à mapper.
1. Sélectionnez l'*ID client* dans l'entité *Client* comme clé primaire.
1. À l'étape **Unification des activités**, sélectionnez le **Statut du consentement** de l'entité *Consentement* sous le champ **Activité événementielle**. 
1. Sélectionnez le champ qui décrit quand le consentement a été fourni dans le champ **Horodatage**.

   :::image type="content" source="media/consent-activity-unification.png" alt-text="Étape pour créer une activité unifiée dans le processus de configuration de l'activité.":::

1. À l'étape **Type d'activité**, sélectionnez **Créer** dans la liste déroulante pour **Type d'activité**.
1. Entrez un nom pour votre activité de consentement.

   :::image type="content" source="media/new-consent-activity-type.png" alt-text="Créez un nouveau type d'activité pour les données de consentement.":::

1. Examinez et exécutez l'activité de consentement. Passez à l'étape suivante après une exécution réussie. Pour plus d'informations sur les activités, consultez [Activités client](../audience-insights/activities.md).

### <a name="step-2-configure-and-run-the-model"></a>Étape 2 : configurer et exécuter le modèle 

Suivez les instructions pour [créer un modèle de transaction](../audience-insights/predict-transactional-churn.md) jusqu'à ce que vous configuriez les données supplémentaires.

1. À l'étape **Données supplémentaires (facultatif)** de la création du modèle, sélectionnez **Ajouter des données**. 

   :::image type="content" source="media/additional-data-choose-activity.png" alt-text="Choisissez l'activité de consentement à l'étape d'ajout de données.":::

1. Choisissez l'activité de consentement créée auparavant et choisissez l'activité *Consentement* correspondante.
1. Sélectionnez **ActualActivityId** comme clé primaire.
1. Sélectionnez **ActivityTime** comme horodatage.
1. Sélectionnez **ActivityName** comme événement d'activité.

   :::image type="content" source="media/additional-data-map-attributes.png" alt-text="Mappez les attributs lors de l'ajout de l'activité de consentement.":::

1. Sélectionnez **Enregistrer**, puis **Suivant**. 
1. Choisissez la fréquence à laquelle les données seront mises à jour et le modèle sera exécuté. Ensuite, cliquez sur **Suivant**.
1. Vérifiez et confirmez vos paramètres et sélectionnez **Courir**.  

## <a name="view-and-interpret-model-results"></a>Afficher et interpréter les résultats du modèle

Affichez les résultats du modèle pour trouver des informations.

- **Performances du modèle d'entraînement :** indique les performances de prédiction en fonction du nombre de clients qu'il a prédit avec précision. L'ajout de données de consentement et d'autres données facultatives permet d'augmenter la probabilité de prédictions précises. 
- **Probabilité d’attrition** (nombre de clients) : Groupes de clients en fonction du risque d’attrition prévu. 
- **Facteurs les plus influents :** Répertorie les facteurs qui affectent les résultats du modèle. Découvrez quelle influence les données de consentement ont eues en consultant les facteurs **Activité**. Une autre façon d'évaluer l'influence des données de consentement est de mettre en place un modèle sans données de consentement et de comparer les résultats à ce modèle.

:::image type="content" source="media/influential-factors-activity.png" alt-text="Facteurs d'influence dans la sortie du modèle.":::

Pour plus d'informations sur les résultats du modèle, voir [Taux d'attrition de prédiction des transactions](../audience-insights/predict-transactional-churn.md).

 

