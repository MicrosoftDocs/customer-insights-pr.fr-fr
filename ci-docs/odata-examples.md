---
title: Exemples OData pour l’API Dynamics 365 Customer Insights
description: Exemples couramment utilisés pour le protocole Open Data Protocol (OData) pour interroger les API Customer Insights afin d’examiner les données.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808458"
---
# <a name="odata-query-examples"></a>Exemples de requête OData

L’Open Data Protocol (OData) est un protocole d’accès aux données basé sur des protocoles de base comme HTTP. Il utilise des méthodologies communément acceptées comme REST pour le Web. Il existe différents types de bibliothèques et d’outils qui peuvent être utilisés pour utiliser les services OData.

Cet article répertorie quelques exemples de requêtes fréquemment demandés pour vous aider à créer vos propres implémentations basées sur les [API Customer Insights](apis.md).

Vous devez modifier les exemples de requêtes pour les faire fonctionner sur les environnements cibles : 

- {serviceRoot} : `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` où {instanceId} est le GUID de l’environnement Customer Insights que vous souhaitez interroger. L’[opération ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vous permet de trouver l’{InstanceId} à laquelle vous avez accès.
- {CID} : GUID d’un enregistrement de client unifié. Exemple :`ce759201f786d590bf2134bff576c369`.
- {AlternateKey} : Identifiant de la clé primaire d’un enregistrement de client dans une source de données. Exemple : `CNTID_1002`
- {DSname} : Chaîne avec le nom d’entité d’une source de données qui est ingéré dans Customer Insights. Exemple :`Website_contacts`.
- {SegmentName} : Chaîne avec le nom de l’entité de sortie d’un segment dans Customer Insights. Exemple :`Male_under_40`.

## <a name="customer"></a>Customer

Le tableau suivant contient un ensemble d’exemples de requêtes pour l’entité *Client*.

|Type de requête |Exemple  | Note  |
|---------|---------|---------|
|ID client unique     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clé secondaire    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Les clés secondaires persistent dans l’entité client unifiée       |
|Sélectionner   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Intérieur    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clé secondaire + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Recherche  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Renvoie les 10 premiers résultats pour une chaîne de recherche      |
|Appartenance aux segments  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Renvoie un nombre prédéfini de lignes à partir de l’entité de segmentation.      |

## <a name="unified-activity"></a>Activité unifiée

Le tableau suivant contient un ensemble d’exemples de requêtes pour l’entité *UnifiedActivity*.

|Type de requête |Exemple  | Note  |
|---------|---------|---------|
|Activité de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Répertorie les activités d’un profil client spécifique |
|Délai d’exécution de l’activité    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Activités d’un profil client dans un délai d’exécution       |
|Type d’activité    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Activité par nom d’affichage     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Tri des activités    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Trier les activités dans l’ordre croissant ou décroissant       |
|Activité développée à partir de l’appartenance aux segments  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Autres exemples

Le tableau suivant contient un ensemble d’exemples de requêtes pour d’autres entités.

|Type de requête |Exemple  | Note  |
|---------|---------|---------|
|Mesures de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marques enrichies de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Centres d’intérêt enrichis de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Dans-Clause + Développer     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Requêtes OData non prises en charge

Les requêtes suivantes ne sont pas prises en charge par Customer Insights :

- `$filter` sur les entités sources ingérées. Vous ne pouvez exécuter les requêtes $filter que sur les entités système créées par Customer Insights.
- `$expand` d’une requête `$search`. Exemple : `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` de `$select` si seul un sous-ensemble d’attributs est sélectionné. Exemple : `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` a enrichi les affinités de marque ou d’intérêt pour un client donné. Exemple : `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Interrogez les entités de sortie du modèle de prédiction via la clé secondaire. Exemple : `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
