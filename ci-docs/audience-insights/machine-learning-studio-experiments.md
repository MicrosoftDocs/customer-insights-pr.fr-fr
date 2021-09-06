---
title: Expériences Machine Learning Studio (classique)
description: Utilisez des modèles Machine Learning Studio (classique) dans Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033720"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Utiliser des modèles basés sur Azure Machine Learning Studio (classique)

Les données unifiées dans Dynamics 365 Customer Insights sont une source pour créer des modèles Machine Learning qui peuvent générer des informations métier supplémentaires. Customer Insights s’intègre à Machine Learning Studio (classique) pour utiliser vos propres modèles personnalisés. Pour voir comment les modèles développés dans Azure Machine Learning sont intégrés à Customer Insights, consultez [Expériences Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Conditions préalables

- Accéder à Customer Insights
- Activer l’abonnement Azure Enterprise
- [Profils client unifiés](data-unification.md)
- Configuration de l’[Exportation d’entité vers le stockage Blob Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurer Machine Learning Studio (classique)

Tout d’abord, nous devons créer un espace de travail et ouvrir Machine Learning Studio (classique).

1. Accédez à [https://www.portal.azure.com](https://www.portal.azure.com/) et connectez-vous.

1. Sélectionnez **Créer une ressource**.

1. Cherchez **Espace de travail Machine Learning Studio** et sélectionnez **Créer**.

1. Entrez les détails requis pour [créer l’espace de travail](/azure/machine-learning/studio/create-workspace). Choisissez le **Niveau tarifaire du plan de service web** en fonction de la quantité de données que vous prévoyez d’importer. Pour de meilleures performances, sélectionnez l’**Emplacement** qui est géographiquement le plus proche de vous.

1. Après avoir créé la ressource, le tableau de bord de l’espace de travail Machine Learning Studio apparaît. Sélectionnez **Lancer Machine Learning Studio**.

   ![Interface utilisateur Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Utiliser Azure Machine Learning Studio

Vous pouvez maintenant créer une nouvelle expérience ou importer un modèle de test existant à partir de la galerie d’échantillons. Il existe des exemples d’expériences pour trois scénarios standard :

- [Prédiction de perte de clientèle](#churn-analysis)

- [Valeur de la durée de vie du client](#customer-lifetime-value-prediction)

- [Recommandation de produit ou meilleure action suivante](#productrecommendation-or-next-best-action)

1. Si vous créez une nouvelle expérience ou utilisez un modèle d’expérience de la galerie, vous devez configurer les propriétés **Importer des données**. Utilisez l’expérience guidée ou fournissez directement des détails pour accéder au stockage Blob Azure contenant vos données.  

   ![Expérience Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Vous pouvez désormais créer un pipeline de traitement personnalisé pour nettoyer et prétraiter les données, extraire des fonctionnalités et former un modèle approprié.

1. Testez et optimisez les performances du modèle.

1. Lorsque vous êtes satisfait de la qualité d’un modèle, sélectionnez **Configurer le service Web** > **Service Web prédictif**. Cette option importe le modèle formé et le pipeline de fonctionnalités de l’expérience de formation vers un service prédictif. Le service prédictif peut utiliser un autre ensemble de données d’entrée avec le schéma utilisé dans l’expérience de formation pour effectuer des prédictions.

   ![Mettez en place un service Web prédictif.](media/predictive-webservice-control.png)

1. Une fois l’expérience de service Web prédictif réussie, vous pouvez la déployer pour la planification automatique. Pour que le service Web fonctionne avec Customer Insights, sélectionnez **Déployer le service Web** > **Déployer le service Web [Nouveau] - Version préliminaire**. [En savoir plus sur le déploiement d’un service Web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Déployez un service Web prédictif.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Exemples de modèles de la galerie

Nous utilisons un scénario fictif de Contoso Hôtel pour les modèles de cet article. Contoso Hotel recueille les données suivantes :

- Données CRM issues de l’activité hôtelière. Le jeu de données comprend des informations sur les dates de séjour de chaque client enregistré. Il contient également des informations sur les réservations, les types de chambres, les détails des dépenses, etc. Les données couvrent quatre ans, de janvier 2014 à janvier 2018.
- Profils des clients de l’hôtel. Ces profils contiennent des informations sur chaque client, notamment son nom, sa date de naissance, son adresse postale, son sexe et son numéro de téléphone.
- Utilisation des services proposés par l’hôtel, tels que le spa, la blanchisserie, le WiFi ou le coursier. Ces informations sont enregistrées pour chaque client enregistré. En règle générale, l’utilisation des services est liée au séjour. Dans certains cas, les services peuvent être utilisés par les clients sans qu’ils séjournent à l’hôtel.

## <a name="churn-analysis"></a>Analyse de perte de clientèle

L’analyse de perte de clientèle s’applique à différents domaines d’activité. Dans cet exemple, nous allons examiner la perte de clientèle des services, en particulier dans le contexte des services hôteliers comme décrit ci-dessus. Il fournit un exemple fonctionnel de pipeline de modèle de bout en bout qui peut être utilisé comme point de départ pour tout autre type de modèle de perte de clientèle.

### <a name="definition-of-churn"></a>Définition de perte de clientèle

La définition de perte de clientèle peut différer en fonction du scénario. Dans cet exemple, un client qui n’a pas séjourné à l’hôtel au cours de l’année écoulée doit être étiqueté comme perdu.  

Le modèle d’expérience peut être importé de la galerie. Tout d’abord, assurez-vous d’importer les données pour **Activité de séjour à l’hôtel**, **Données client**, et **Données d’utilisation du service** à partir du stockage Blob Azure.

   ![Importez des données pour le modèle de perte de clientèle.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Caractérisation

Sur la base de la définition de perte de clientèle, nous identifions d’abord les caractéristiques brutes qui influenceront l’étiquette. Ensuite, nous convertissons ces caractéristiques brutes en caractéristiques numériques qui peuvent être utilisées avec les modèles Machine Learning. L’intégration des données se produit dans Customer Insights afin que nous puissions joindre ces tables à l’aide de l’*ID de client*.

   ![Joignez les données importées.](media/join-imported-data.png)

La caractérisation de la construction du modèle pour l’analyse de perte de clientèle peut être un peu délicate. Les données sont fonction du temps, les nouvelles activités hôtelières étant enregistrées quotidiennement. Pendant la caractérisation, nous voulons générer des entités statiques à partir des données dynamiques. Dans ce cas, nous générons plusieurs fonctionnalités à partir de l’activité hôtelière avec une fenêtre glissante d’un an. Nous développons également les fonctionnalités catégorielles telles que le type de chambre ou le type de réservation dans des fonctionnalités distinctes à l’aide de l’encodage à chaud.  

Liste finale des fonctionnalités :

| **Numéro**  | **Original_Column**          | **Fonctionnalités dérivées**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Type de chambre                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Type de réservation                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Catégorie de voyage              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dollars dépensés                | TotalDollarSpent                                                                                                                          |
| 5           | Dates d’arrivée et de départ  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Utilisation du service                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Sélection du modèle

Nous devons maintenant choisir l’algorithme optimal à utiliser. Dans ce cas, la plupart des fonctionnalités sont basées sur des fonctionnalités catégorielles. En règle générale, les modèles basés sur un arbre de décision fonctionnent bien. S’il n’y a que des fonctionnalités numériques, les réseaux de neurones pourraient être un meilleur choix. La machine à vecteurs de support (SVM) est également un bon candidat dans de telles situations ; cependant, elle nécessite un peu de réglages pour extraire les meilleures performances. Nous choisissons **Arbre de décision amélioré à deux classes** comme premier modèle de choix suivi de **SVM à deux classes** comme deuxième modèle. Azure Machine Learning Studio vous permet de faire des tests A/B, il est donc avantageux de commencer avec deux modèles plutôt qu’un.

L’image suivante montre le pipeline de formation et d’évaluation du modèle d’Azure Machine Learning Studio :

![Modèle de perte de clientèle dans Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Nous appliquons également une technique appelée **Importance de la fonction de permutation**, un aspect important de l’optimisation des modèles. Les modèles intégrés ont peu ou pas d’informations sur l’impact d’une fonctionnalité spécifique sur la prédiction finale. Le calculateur d’importance des caractéristiques utilise un algorithme personnalisé pour calculer l’influence de caractéristiques individuelles sur le résultat d’un modèle spécifique. L’importance de la fonctionnalité est normalisée entre +1 et -1. Une influence négative signifie que la fonction correspondante a une influence contre-intuitive sur le résultat et doit être supprimée du modèle. Une influence positive indique que la fonctionnalité contribue fortement à la prédiction. Ces valeurs ne sont pas des coefficients de corrélation car ce sont des métriques différentes. Pour plus d’informations, consultez [Importance de la fonction de permutation](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

L’ensemble de [l’expérience de perte de clientèle est disponible dans Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Prédiction de la valeur de la durée de vie du client

Le calcul de la valeur de la durée de vie du client (CLTV) est l’une des mesures clés qu’une entreprise peut utiliser pour évaluer et segmenter ses clients. Pour l’hôtellerie, il est essentiel de connaître ses clients. Par exemple, comprendre les facteurs qui caractérisent les bons clients est crucial. Cela aide la direction de l’hôtel à évaluer les fonctionnalités sur lesquelles elle doit se concentrer et à améliorer ses décisions pour satisfaire ses clients à haut revenu. Ces décisions peuvent avoir un impact direct sur les ventes et les bénéfices.  

### <a name="definition-of-cltv"></a>Définition de la CLTV

Pour cet exemple, nous définissons la CLTV d’un client comme le montant total que le client est censé dépenser au cours des 365 prochains jours. Nous allons utiliser les données des trois dernières années pour tous les clients afin de prédire cette valeur.

### <a name="featurization"></a>Caractérisation

Dans ce cas, la caractérisation sera assez similaire au scénario de désabonnement. Cependant, les étiquettes et les valeurs prévues sont différentes de celles définies ci-dessus.

### <a name="model-selection"></a>Sélection du modèle

Prédire la CLTV est un problème de régression car la valeur prédite est une variable continue à valeur positive. En fonction des propriétés des fonctionnalités, nous sélectionnons **Régression améliorée de l’arbre de décision** comme un seul algorithme et **Régression du réseau neuronal** comme un autre algorithme pour entraîner le modèle.

## <a name="product-recommendation-or-next-best-action"></a>Recommandation de produit ou meilleure action suivante

La recommandation de produit dans un scénario hôtelier est interprétée comme une recommandation de services offerts par l’hôtel aux clients. L’objectif est de choisir les services appropriés pour les clients afin que leur utilisation soit maximisée. C’est similaire aux recommandations de films pour les utilisateurs de services de streaming vidéo.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Définition d’une recommandation de produit ou meilleure action suivante

Nous définissons l’objectif comme la maximisation du montant de l’utilisation des services en offrant les meilleurs services correspondants aux clients de l’hôtel en fonction de leur intérêt.

### <a name="featurization"></a>Caractérisation

Comme le modèle de perte de clientèle, nous joignons le ServiceCustomerID de l’hôtel avec le CustomerID afin de créer des recommandations cohérentes par CustomerID.

![Mise en avant du modèle de recommandation.](media/azure-machine-learning-model-featurization.png)

Les données proviennent de trois entités différentes et les caractéristiques en sont dérivées. La caractérisation du problème de recommandation est différente par rapport aux scénarios de perte de clientèle ou CLTV. Le modèle de recommandation a besoin de données d’entrée sous la forme de trois ensembles de fonctionnalités.

### <a name="model-selection"></a>Sélection du modèle

Nous prédisons les produits ou services en utilisant l’algorithme appelé **Entraîner la recommandation Matchbox** pour entraîner le modèle de recommandation.

![Algorithme de recommandation de produit.](media/azure-machine-learning-model-recommendation-algorithm.png)

Les trois ports d’entrée pour le modèle **Entraîner la recommandation Matchbox** prend en compte les données d’utilisation du service de formation, la description du client (facultatif) et la description du service. Il existe trois façons différentes de noter le modèle. La première concerne l’évaluation du modèle où un score de gain cumulé actualisé normalisé (NDCG) est calculé pour classer les éléments notés. Dans cette expérience, nous avons le score NDCG de 0,97. Les deux autres options évaluent le modèle sur l’ensemble du catalogue de services recommandables, ou évaluent uniquement les éléments que les utilisateurs n’ont pas utilisés auparavant.

En regardant plus loin les distributions des recommandations sur l’ensemble du catalogue de services, nous remarquons que le téléphone, le WiFi et le coursier sont les meilleurs services à recommander. Ceci est cohérent avec ce que nous avons trouvé à partir des distributions des données de consommation de services :

![Sortie de modèle de recommandation.](media/azure-machine-learning-model-output.png)

L’ensemble de l’[expérience de recommandation de produit est accessible dans Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Intégrer des modèles personnalisés

Pour utiliser ces prédictions dans Customer Insights, vous devez **exporter** les prédictions ainsi que les identifiants clients. [Exportez-les vers le même emplacement de stockage Blob Azure](/azure/storage/common/storage-import-export-data-from-blobs) que celui vers lequel vous exportez les données sources. Le service Web prédictif peut être planifié pour s’exécuter régulièrement et mettre à jour les scores.

Les données générées par le modèle personnalisé peuvent être utilisées pour enrichir davantage vos données client. Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]