---
title: Données Customer Insights dans Microsoft Dataverse
description: Utiliser les entités Customer Insights en tant que tables dans Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032893"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utiliser des données Customer Insights dans Microsoft Dataverse

Customer Insights offre la possibilité de rendre les entités de sortie disponibles dans [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Cette intégration facilite le partage de données et permet un développement personnalisé grâce à une approche « low code »/sans code. Les entités de sortie seront disponibles sous forme de tables dans Dataverse. Ces tables permettent des scénarios comme des [flux de travail automatisés via Power Automate](/power-automate/getting-started), des [applications pilotées par modèle](/powerapps/maker/model-driven-apps/) et des [applications canevas](/powerapps/maker/canvas-apps/) via Power Apps. Vous pouvez utiliser les données pour toute autre application basée sur des tables Dataverse. L'implémentation actuelle prend principalement en charge les recherches où les données des entités d'informations sur l’audience disponibles peuvent être récupérées pour un ID client donné.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Joindre un environnement Dataverse à Customer Insights

**Organisations ayant déjà des environnements Dataverse**

Les organisations qui utilisent déjà Dataverse peuvent [utiliser l'un de leurs environnements Dataverse existants](get-started-paid.md) lorsqu'un Administrateur met en place des informations sur l’audience. En fournissant l'URL à l'environnement Dataverse, il s'attache au nouvel environnement d'informations sur l'audience. Pour garantir les meilleures performances possibles, les environnements Customer Insights et Dataverse doivent être hébergés dans la même région.

Pour joindre un environnement Dataverse, développez **Paramètres avancés** lors de la création de l'environnement d'informations sur l'audience. Fournissez l'URL de l'environnement **Microsoft Dataverse** et cochez la case pour **Activer le partage de données**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Nouvelle organisation**

Si vous créez une nouvelle organisation lors de la configuration de Customer Insights, vous obtiendrez automatiquement un nouvel environnement Dataverse.

> [!NOTE]
> Si votre organisation utilise déjà Dataverse dans son client, il est important de se rappeler que [la création d'un environnement Dataverse est contrôlée par un administrateur](/power-platform/admin/control-environment-creation.md). Par exemple, si vous configurez un nouvel environnement d'informations sur l'audience avec votre compte professionnel et que l'administrateur a désactivé la création d'environnements d'essai Dataverse pour tout le monde à l'exception des administrateurs, vous ne pouvez pas créer un nouvel environnement d'essai.
> 
> Les environnements d'essai Dataverse créés dans Customer Insights disposent de 3 Go de stockage qui ne seront pas pris en compte dans la capacité globale à laquelle le locataire a droit. Les abonnements payants obtiennent un droit Dataverse de 15 Go pour la base de données et de 20 Go pour le stockage de fichiers.

## <a name="output-entities"></a>Entités de sortie

Certaines entités de sortie des informations sur l'audience sont disponibles en tant que tables dans Dataverse. Les sections ci-dessous décrivent le schéma attendu de ces tables.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichissement](#enrichment)
- [Prédiction](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Cette table contient le profil client unifié de Customer Insights. Le schéma d'un profil client unifié dépend des entités et des attributs utilisés dans le processus de fusion. Le schéma d'un profil client contient généralement un sous-ensemble des attributs de la [définition Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La table AlternateKey contient les clés des entités qui ont participé au processus d'unification.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la source de données. Par exemple : `datasource5`        |
|EntityName        | String        | Nom de l'entité dans les informations sur l’audience. Par exemple : `contact1`        |
|AlternateValue    |String         |ID alternatif mappé à l'ID client. Exemple : `cntid_1078`         |
|KeyRing           | Texte multiligne        | Valeur JSON  </br> Exemple : [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Customerid         | String        | ID du profil client unifié.         |
|AlternateKeyId     | GUID         |  GUID déterministe AlternateKey basé sur msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple : `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Cette table contient les activités des utilisateurs qui sont disponibles dans Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | String      | ID profil client                                                                      |
| ActivityId        | String      | ID interne de l'activité client (clé primaire)                                       |
| SourceEntityName  | String      | Nom de l'entité source                                                                |
| SourceActivityId  | String      | Clé primaire de l'entité source                                                       |
| ActivityType      | String      | Type d'activité sémantique ou nom de l'activité personnalisée                                        |
| ActivityTimeStamp | DATETIME    | Horodatage de l'activité                                                                      |
| Titre             | String      | Titre ou non de l’activité                                                               |
| Description       | String      | Description de l’activité                                                                     |
| URL                | String      | Lien vers une URL externe spécifique à l'activité                                         |
| SemanticData      | Chaîne JSON | Comprend une liste de paires clé-valeur pour les champs de mappage sémantique spécifiques au type d'activité |
| RangeIndex        | String      | Horodatage Unix utilisé pour trier la chronologie des activités et les requêtes de plage effective |
| mydynci_unifiedactivityid   | GUID | ID interne de l'activité client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Cette table contient les données de sortie des mesures basées sur les attributs du client.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| Customerid         | String           | ID profil client        |
| Mesures           | Chaîne JSON      | Inclut une liste de paires clé-valeur pour le nom de la mesure et les valeurs pour le client donné | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profil client |


### <a name="enrichment"></a>Enrichissement

Cette table contient le résultat du processus d'enrichissement.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | String           | ID profil client                                 |
| EnrichmentProvider   | String           | Nom du fournisseur pour l’enrichissement                                  |
| EnrichmentType       | String           | Type d'enrichissement                                      |
| Valeurs               | Chaîne JSON      | Liste des attributs produits par le processus d'enrichissement |
| msdynci_enrichmentid | GUID             | GUID déterministe généré à partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prédiction

Cette table contient le résultat des prédictions de modèle.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | String      | ID profil client                                  |
| ModelProvider        | String      | Nom du fournisseur du modèle                                      |
| Modèle                | String      | Nom du modèle                                                |
| Valeurs               | Chaîne JSON | Liste des attributs produits par le modèle |
| msdynci_predictionid | GUID        | GUID déterministe généré à partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
