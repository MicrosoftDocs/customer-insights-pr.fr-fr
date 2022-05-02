---
title: Données Customer Insights dans Microsoft Dataverse
description: Utiliser les entités Customer Insights en tant que tables dans Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646029"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utiliser des données Customer Insights dans Microsoft Dataverse

Customer Insights offre la possibilité de rendre les entités de sortie disponibles dans [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Cette intégration facilite le partage de données et permet un développement personnalisé grâce à une approche low code/sans code. Les [entités de sortie](#output-entities) sont disponibles sous forme de tableaux dans un environnement Dataverse. Vous pouvez utiliser les données pour toute autre application basée sur les tables Dataverse. Ces tables permettent des scénarios tels que des flux de travail automatisés via Power Automate ou la création d’applications avec Power Apps. L’implémentation actuelle prend principalement en charge les recherches dans lesquelles les données des entités de Customer Insights disponibles peuvent être extraites pour un ID client donné.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Joindre un environnement Dataverse à Customer Insights

**Organisation existante**

Les administrateurs peuvent configurer Customer Insights pour [utiliser un existant environnement Dataverse](create-environment.md) lorsqu’ils créent un environnement Customer Insights. En fournissant l’URL à l’environnement Dataverse, celui-ci est associé à leur nouvel environnement Customer Insights. Les environnements Customer Insights et Dataverse doivent être hébergés dans la même région. 

Si vous ne souhaitez pas utiliser un environnement Dataverse existant, le système crée un nouvel environnement pour les données Customer Insights dans votre locataire. 

> [!NOTE]
> Si votre organisation utilise déjà Dataverse dans son client, il est important de se rappeler que la [création d’un environnement Dataverse est contrôlée par un administrateur](/power-platform/admin/control-environment-creation). Par exemple, si vous configurez un nouvel environnement Customer Insights avec votre compte d’organisation et que l’administrateur a désactivé la création d’environnements d’essai Dataverse pour tout le monde à l’exception des administrateurs, vous ne pouvez pas créer un nouvel environnement d’essai.
> 
> Les environnements d'essai Dataverse créés dans Customer Insights disposent de 3 Go de stockage qui ne seront pas pris en compte dans la capacité globale à laquelle le locataire a droit. Les abonnements payants obtiennent un droit Dataverse de 15 Go pour la base de données et de 20 Go pour le stockage de fichiers.

**Nouvelle organisation**

Si vous créez une nouvelle organisation lors de la configuration de Customer Insights, le système crée automatiquement un nouvel environnement Dataverse dans votre organisation.

## <a name="output-entities"></a>Entités de sortie

Certaines entités de sortie de Customer Insights sont disponibles en tant que tables dans Dataverse. Les sections ci-dessous décrivent le schéma attendu de ces tables.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichissement](#enrichment)
- [Prédiction](#prediction)
- [Appartenance aux segments](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Cette table contient le profil client unifié de Customer Insights. Le schéma d'un profil client unifié dépend des entités et des attributs utilisés dans le processus de fusion. Le schéma d'un profil client contient généralement un sous-ensemble des attributs de la [définition Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La table AlternateKey contient les clés des entités qui ont participé au processus d'unification.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la source de données. Par exemple : `datasource5`        |
|Nom de l’entité        | String        | Nom de l’entité dans Customer Insights. Par exemple : `contact1`        |
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
| URL               | String      | Lien vers une URL externe spécifique à l'activité                                         |
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

### <a name="segment-membership"></a>Appartenance aux segments

Ce tableau contient des informations sur l'appartenance aux segments des profils clients.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Customerid        | String       | ID profil client        |
| SegmentProvider      | String       | Application qui publie les segments.      |
| SegmentMembershipType | String       | Type de client que cette appartenance aux segments enregistre. Prend en charge plusieurs types tels que Client, Contact ou Compte. Par défaut : Client  |
| Segments       | Chaîne JSON  | Liste des segments uniques dont le profil client est membre      |
| msdynci_identifier  | String   | Identificateur unique de l’enregistrement sur l’appartenance aux segments. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID déterministe généré à partir de `msdynci_identifier`          |
