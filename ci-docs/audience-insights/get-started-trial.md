---
title: Créer et configurer une version d’essai de Customer Insights
description: Étapes pour obtenir un abonnement d’essai pour Dynamics 365 Customer Insights et le configurer.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035412"
---
# <a name="set-up-a-trial-environment"></a>Configurer un environnement de version d’essai 

Avec la version d’essai Dynamics 365 Customer Insights, examinez les fonctionnalités principales et découvrez-en davantage à leur sujet. Un abonnement d’essai est supprimé une fois arrivé à expiration. Les environnements d’essai sont créés par des utilisateurs individuels qui deviennent administrateur de leur environnement d’essai. Ils peuvent inviter plus d’utilisateurs à leur essai et configurer les différentes fonctionnalités.

## <a name="create-a-trial-environment"></a>Créer un environnement d’essai

Vous pouvez vous inscrire à un essai sur la [page d’inscription à un essai](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Choisissez l’option **S’inscrire à un essai gratuit** et sélectionnez **S’inscrire maintenant**.

1. Renseignez votre adresse e-mail professionnelle ou scolaire, dites-nous en plus sur vous et sélectionnez **Démarrer**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Boîte de dialogue pour s’inscrire à une instance d’essai":::

1. Examinez les conditions générales et sélectionnez **Continuer** pour confirmer.

1. Indiquez un **Nom** pour votre nouvel environnement. 

1. Définissez l’environnement **Type** sur **Essai**.

1. Dans le champ **Sélectionner une démo pour un secteur d’activité**, vous pouvez éventuellement choisir un jeu de données spécifique au secteur d’activité. Vous pouvez également [passer à une démo pour un secteur d’activité](#use-industry-specific-demo-data-sets-in-audience-insights) ultérieurement et commencer avec le jeu de données par défaut.

1. Choisissez la **Région** pour votre environnement.

1. Facultativement, si vous êtes l’administrateur d’une organisation Dynamics 365 : sélectionnez **Paramètres avancés** et fournissez l’URL de votre organisation pour utiliser les fonctionnalités de prédiction telles que la prédiction du taux de l’attrition clients. 

1. Cliquez sur **Créer**. 

La configuration de l’environnement peut prendre un moment. Une fois terminé, vous êtes redirigé vers l’environnement de démonstration ou la démonstration du secteur d’activité que vous choisissez à l'étape ci-dessus. Vous pouvez maintenant explorer l’application avec des données de démonstration en lecture seule. Pour ajouter vos propres données à l’environnement, consultez [Créer des données de démonstration spécifiques au scénario dans votre propre environnement](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Capture d’écran d’un environnement de version d’essai récemment créé.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Utiliser des ensembles de données de démonstration spécifiques au secteur dans les informations sur l’audience

La connexion de sources de données réelles est l’une des étapes critiques de l’utilisation de la puissance de Customer Insights. Pour essayer des fonctionnalités sans interférer avec vos propres données, vous pouvez éventuellement utiliser des données de démonstration spécifiques au secteur d’activité. Il existe quelques ensembles de données de démonstration disponibles pour les secteurs suivants : 

-   Automobile
-   Banques
-   Biens de consommation
-   Organismes d’état
-   Soins de santé
-   Institutions
-   Assurance
-   Fabrication
-   Services professionnels
-   Vente au détail

### <a name="see-industry-specific-demo-data-in-trials"></a>Voir les données de démonstration spécifiques au secteur d’activité dans les versions d’essai

Pour une version en lecture seule de Customer Insights, adaptée à un secteur d’activité ou à un scénario spécifique, démarrez dans l’environnement de démonstration. 
 
1.  Dans les informations sur l’audience, sélectionnez l’environnement **Démo** dans le sélecteur d’environnement.

2.  Sur **Accueil**, choisissez une option dans le menu déroulant Sélectionner une démo pour un secteur d’activité.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Choisissez un secteur d’activité pour l’environnement de la version d’essai.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Créer des données de démonstration spécifiques au scénario dans votre propre environnement

En tant qu’administrateur, sélectionnez le sélecteur d’environnement dans l’en-tête de l’application pour créer un environnement. Dans le nouvel environnement, vous pouvez configurer vos propres sources de données et configurer l’application en fonction de vos besoins. 

1.  Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2.  Pour importer vos propres sources de données, accédez au [guide sur l’ingestion des données](data-sources.md).     
   Si vous préférez travailler avec des exemples de données qui vous permettent d’essayer l’ingestion des données, vous pouvez ingérer les données de démonstration du secteur d’activité dans votre environnement. Sélectionnez l’option **Importer à partir d’un DataHub** et suivez les étapes ci-dessous.

3.  Sélectionnez la carte du secteur d’activité qui convient à votre scénario. 

4.  Vérifiez et mettez à jour éventuellement le nom suggéré de la source de données. 

5.  Sélectionnez **Suivant** pour ingérer les exemples de données. 

Vous pouvez désormais utiliser les données ingérées pour adapter Customer Insights à votre scénario. Pour voir un environnement spécifique aux données de démonstration ingérées, choisissez l’option **<Industry>Démo** dans le sélecteur d’environnement.

## <a name="limitations-in-trials"></a>Limitations dans les versions d’essai

- Par défaut, les versions d’essai sont actives pendant 30 jours. Cependant, vous pouvez les prolonger après le 23ème jour lorsque vous vous connectez à votre version d’essai.
- Vous ne pouvez pas utiliser votre propre compte Azure Data Lake Storage pour stocker des données de sortie pendant un essai. Cependant, vous pouvez ingérer des données à partir d’un compte de Data Lake Storage.
- Vous pouvez stocker jusqu'à 3 Go de données dans l’environnement Dataverse mis en service automatiquement lorsque vous démarrez un essai Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copier les données d’une version d’essai vers un abonnement payant

En règle générale, nous vous recommandons de recommencer avec vos propres données lors de la mise à niveau vers la version payante de Customer Insights. 

En option, vous pouvez copier vos données à partir d’un environnement d’essai si vous achetez Customer Insights. Vous devez être l’administrateur de la version d’essai de Customer Insights et l’administrateur global de votre client Microsoft 365, ou l’administrateur Dynamics 365 de votre organisation pour migrer les paramètres d’un environnement de version d’essai vers un environnement payant. 

Après vous être connecté à votre instance payante de Customer Insights pour la première fois, vous êtes invité à créer un environnement. Dans ce processus, vous pouvez choisir de copier la configuration à partir d’un environnement existant et de migrer la plupart des paramètres. Si vous disposez des autorisations mentionnées ci-dessus, l’environnement de la version d’essai apparaît dans cette liste. Pour plus d’informations, voir [Copier la configuration de l’environnement](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Étapes suivantes

Consultez les articles suivants pour vous aider à démarrer avec la configuration de Customer Insights. 

- [Ajoutez plus d’utilisateurs et attribuez des autorisations](permissions.md).
- [Ingérez vos sources de données](data-sources.md) et faites-les passer par le [processus d’unification des données](data-unification.md) pour obtenir des [profils clients unifiés](customer-profiles.md).
- [Enrichissez les profils clients unifiés](enrichment-hub.md) ou [exécutez des modèles prédictifs](predictions-overview.md).
- Créez des [segments](segments.md) pour grouper les clients et des [mesures](measures.md) pour passer en revue les KPI.
- Configurez les [connexions](connections.md) et les [exportations](export-destinations.md) pour traiter des sous-ensembles de vos données dans d’autres applications.