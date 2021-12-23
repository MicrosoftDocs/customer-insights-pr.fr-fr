---
title: Auditer Dynamics 365 Customer Insights avec Azure Monitor
description: Apprenez à envoyer des journaux vers Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920831"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Transfert de journaux dans Dynamics 365 Customer Insights avec Azure Monitor (version préliminaire)

Dynamics 365 Customer Insights fournit une intégration directe avec Azure Monitor. Les journaux de ressources Azure Monitor vous permettent de surveiller et d’envoyer des journaux vers le [Stockage Azure](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ou de les diffuser sur [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights envoie les journaux d’événements suivants :

- **Événements d’audit**
  - **APIEvent** : active le suivi des modifications effectué via l’interface utilisateur de Dynamics 365 Customer Insights.
- **Événements opérationnels**
  - **WorkflowEvent** : le workflow permet de configurer des [Sources de données](data-sources.md), d’[unifier](data-unification.md), d’[enrichir](enrichment-hub.md) et enfin d’[exporter](export-destinations.md) des données dans d’autres systèmes. Toutes ces étapes peuvent être effectuées individuellement (par exemple, déclencher une exportation unique) ou orchestrées (par exemple, l’actualisation des données à partir de sources de données qui déclenchent le processus d’unification qui extraira des enrichissements supplémentaires et, une fois terminé, exportera les données dans un autre système). Pour plus d’informations, consultez [Schéma de WorkflowEvent](#workflow-event-schema).
  - **APIEvent** : tous les appels d’API à l’instance clients de Dynamics 365 Customer Insights. Pour plus d’informations, consultez [Schéma d’APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configurer les paramètres de diagnostic

### <a name="prerequisites"></a>Conditions préalables

Pour configurer les diagnostics dans Customer Insights, les conditions préalables suivantes doivent être remplies :

- Vous disposez d’un [Abonnement Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) actif.
- Vous disposez d’autorisations [administrateur](permissions.md#administrator) dans Customer Insights.
- Vous disposez du rôle **Contributeur** et **Administrateur de l’accès utilisateur** sur la ressource de destination dans Azure. La ressource peut être un compte de stockage Azure, un Azure Event Hub ou un espace de travail Azure Log Analytics. Pour plus d’informations, consultez [Ajouter ou supprimer des attributions de rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal).
- Les [Exigences de destination](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) pour le stockage Azure, Azure Event Hub ou Azure Log Analytics sont remplies.
- Vous disposez au moins du rôle **Lecteur** sur le groupe de ressources auquel appartient la ressource.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurer les diagnostics avec Azure Monitor

1. Dans Customer Insights, sélectionnez **Système** > **Diagnostics** pour voir les destinations de diagnostics configurées pour cette instance.

1. Sélectionnez **Ajouter une destination**.

   > [!div class="mx-imgBorder"]
   > ![Connexion aux diagnostics](media/diagnostics-pane.png "Connexion aux diagnostics")

1. Fournissez un nom dans le champ **Nom de la destination des diagnostics**.

1. Choisissez le **Client** de l’abonnement Azure avec la ressource de destination et sélectionnez **Se connecter**.

1. Sélectionnez le **Type de ressource** (compte de stockage, Event Hub ou Log Analytics).

1. Sélectionnez l’**Abonnement** pour la ressource de destination.

1. Sélectionnez le **Groupe de ressources** pour la ressource de destination.

1. Sélectionnez la **Ressource**.

1. Confirmez la déclaration **Confidentialité et conformité des données**.

1. Sélectionnez **Se connecter au système** pour se connecter à la ressource de destination. Les journaux commencent à apparaître dans la destination après 15 minutes, si l'API est en cours d’utilisation et génère des événements.

### <a name="remove-a-destination"></a>Supprimer une destination

1. Accédez à **Système** > **Diagnostics**.

1. Sélectionnez la destination des diagnostics dans la liste.

1. Dans la colonne **Actions**, sélectionnez l’icône **Supprimer**.

1. Confirmez la suppression pour arrêter le transfert de journaux. La ressource sur l’abonnement Azure ne sera pas supprimée. Vous pouvez sélectionner le lien dans la colonne **Actions** pour ouvrir le portail Azure pour la ressource sélectionnée et la supprimer à cet endroit.

## <a name="log-categories-and-event-schemas"></a>Catégories de journaux et schémas d’événements

Actuellement, les [événements d’API](apis.md) et les événements de workflow sont pris en charge et les catégories et schémas suivants s’appliquent.
Le schéma du journal suit le [Schéma commun Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Catégories

Customer Insights propose deux catégories :

- **Événements d’audit** : [événements d’API](#api-event-schema) pour suivre les changements de configuration du service. Les opérations `POST|PUT|DELETE|PATCH` entrent dans cette catégorie.
- **Événements opérationnels** : [événements d’API](#api-event-schema) ou [événements de workflow](#workflow-event-schema) générés lors de l’utilisation du service.  Par exemple, les requêtes `GET` ou les événements d’exécution d’un workflow.

## <a name="configuration-on-the-destination-resource"></a>Configuration de la ressource de destination

En fonction du type de ressource choisi, les étapes suivantes s’appliqueront automatiquement :

### <a name="storage-account"></a>Storage account

Le principal de service Customer Insights obtient l’autorisation **Contributeur du compte de stockage** sur la ressource sélectionnée et crée deux conteneurs dans l’espace de noms sélectionné :

- `insight-logs-audit` contenant les **événements d’audit**
- `insight-logs-operational` contenant les **événements opérationnels**

### <a name="event-hub"></a>Hub d’événements

Le principal de service Customer Insights obtient l’autorisation **Propriétaire des données Azure Event Hubs** sur la ressource et créera deux Event Hubs dans l’espace de noms sélectionné :

- `insight-logs-audit` contenant les **événements d’audit**
- `insight-logs-operational` contenant les **événements opérationnels**

### <a name="log-analytics"></a>Log Analytics

Le principal de service Customer Insights obtient l’autorisation **Contributeur Log Analytics** sur la ressource. Les journaux seront disponibles sous **Journaux** > **Tables** > **Gestion des journaux** dans l’espace de travail Log Analytics sélectionné. Développez la solution **Gestion des journaux** et localisez les tables `CIEventsAudit` et `CIEventsOperational`.

- `CIEventsAudit` contenant les **événements d’audit**
- `CIEventsOperational` contenant les **événements opérationnels**

Dans la fenêtre **Requêtes**, développez la solution **Audit** et localisez les exemples de requêtes fournis en recherchant `CIEvents`.

## <a name="event-schemas"></a>Schémas d’événements

Les événements d’API et les événements de workflow ont une structure commune et des détails sur leurs différences, consultez [Schéma de l’événement d’API](#api-event-schema) ou [Schéma de l’événement de workflow](#workflow-event-schema).

### <a name="api-event-schema"></a>Schéma de l’événement d’API

| Champ             | Type de données  | Obligatoires/facultatif | Description       | Exemple        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Horodateur | Requise          | Horodatage de l’événement (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Requise          | ResourceId de l’instance qui a émis l’événement         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Requise          | Nom de l’opération représentée par cet événement.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Requise          | Catégorie de journal de l’événement. Soit `Operational` soit `Audit`. Toutes les requêtes HTTP POST/PUT/PATCH/DELETE sont marquées avec `Audit`, tout le reste avec `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Requise          | Statut de l’événement. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Facultatif          | Statut du résultat de l’événement. Si l’opération correspond à un appel d’API REST, il s’agit du code de statut HTTP.        | `200`             |
| `durationMs`      | Long      | Facultatif          | Durée de l’opération en millisecondes.     | `133`     |
| `callerIpAddress` | String    | Facultatif          | Adresse IP de l’appelant, si l’opération correspond à un appel d’API qui provient d’une adresse IP accessible au public.                                                 | `144.318.99.233`         |
| `identity`        | String    | Facultatif          | Objet JSON décrivant l’identité de l’utilisateur ou de l’application qui a effectué l’opération.       | Consultez la section [Identité](#identity-schema).     |  |
| `properties`      | String    | Facultatif          | Objet JSON avec plus de propriétés pour la catégorie particulière d’événements.      | Consultez la section [Propriétés](#api-properties-schema).    |
| `level`           | String    | Requise          | Niveau de gravité de l’événement.    | `Informational`, `Warning`, `Error` ou `Critical`.           |
| `uri`             | String    | Facultatif          | URI absolu de la requête.    |               |

#### <a name="identity-schema"></a>Schéma d’identité

L’objet JSON `identity` a la structure suivante

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Champ                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Rôle attribué à l’utilisateur ou à l’application. Pour plus d’informations, consultez les [autorisations de l’utilisateur](permissions.md).                                     |
| `Authorization.RequiredRoles` | Rôles requis pour effectuer l’opération. Le rôle `Admin` est autorisé à effectuer toutes les opérations.                                                    |
| `Claims`                      | Revendications du JSON web token (JWT) de l’utilisateur ou de l’application. Les propriétés de revendication varient selon l’organisation et la configuration d’Azure Active Directory. |

#### <a name="api-properties-schema"></a>Schéma des propriétés de l’API

Les [événements d’API](apis.md) ont les propriétés suivantes.

| Champ                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Toujours `ApiEvent`, qui marque l’événement de journal comme événement d’API.                                                                 |
| `properties.userAgent`       | Agent du navigateur qui envoie la requête ou `unknown`.                                                                        |
| `properties.method`          | Méthode HTTP : `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Chemin d’accès relatif de la requête.                                                                                          |
| `properties.origin`          | URI indiquant l’origine d’une extraction ou `unknown`.                                                                  |
| `properties.operationStatus` | `Success` pour le code de statut HTTP < 400 <br> `ClientError` pour le code de statut HTTP < 500 <br> `Error` pour le statut HTTP >= 500 |
| `properties.tenantId`        | ID d’organisation                                                                                                        |
| `properties.tenantName`      | Nom de l'organisation.                                                                                              |
| `properties.callerObjectId`  | ObjectId Azure Active Directory de l’appelant.                                                                         |
| `properties.instanceId`      | `instanceId` de Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Schéma de l’événement de workflow

Le workflow contient plusieurs étapes. [Ingérez des sources de données](data-sources.md), [unifiez](data-unification.md), [enrichissez](enrichment-hub.md) et [exportez](export-destinations.md) des données. Toutes ces étapes peuvent être exécutées individuellement ou orchestrées avec les processus suivants. 

#### <a name="operation-types"></a>Types d’opération

| OperationType     | Grouper                                     |
| ----------------- | ----------------------------------------- |
| Ingestion         | [Sources de données](data-sources.md)           |
| DataPreparation   | [Sources de données](data-sources.md)           |
| Mappage               | [Unification des données](data-unification.md)   |
| Correspondance             | [Unification des données](data-unification.md)   |
| Fusionner             | [Unification des données](data-unification.md)   |
| ProfileStore      | [Profils de client](customer-profiles.md) |
| Recherche            | [Profils de client](customer-profiles.md) |
| Activité          | [Activités](activities.md)                  |
| AttributeMeasures | [Segments et mesures](segments.md)      |
| EntityMeasures    | [Segments et mesures](segments.md)      |
| Mesures          | [Segments et mesures](segments.md)      |
| Segmentation      | [Segments et mesures](segments.md)      |
| Enrichissement        | [Enrichissement](enrichment-hub.md)                                          |
| Intelligence      | [Prédictions](predictions-overview.md)                                          |
| AiBuilder         | [Prédictions](predictions-overview.md)                                          |
| Aperçus          | [Prédictions](predictions-overview.md)                                          |
| Export            | [Exportations](export-destinations.md)                                          |
| ModelManagement   | [Prédictions](custom-models.md)                                           |
| Relationship      | [Unification des données](relationships.md)                                           |

#### <a name="field-description"></a>Description du champ

| Champ           | Type de données  | Obligatoires/facultatif | Description                                                                                                                                                   | Exemple                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Horodateur | Requise          | Horodatage de l’événement (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Requise          | ResourceId de l’instance qui a émis l’événement.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Requise          | Nom de l’opération représentée par cet événement. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Consultez [Types d’opération](#operation-types) pour référence. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Requise          | Catégorie de journal de l’événement. Toujours `Operational` pour les événements de workflow                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Requise          | Statut de l’événement. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Facultatif          | Durée de l’opération en millisecondes.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Facultatif          | Objet JSON avec plus de propriétés pour la catégorie particulière d’événements.                                                                                        | Consultez la sous-section [Propriétés du workflow](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Requise          | Niveau de gravité de l’événement.                                                                                                                                  | `Informational`, `Warning` ou `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Schéma des propriétés du workflow

Les événements de workflow ont les propriétés suivantes.

| Champ              | Flux de travail | Task | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Oui      | Oui  | Toujours `WorkflowEvent`, qui marque l’événement comme événement de workflow.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Oui      | Oui  | Identificateur de l’exécution du workflow. Tous les événements de workflow et de tâche dans l’exécution du workflow ont le même `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Oui      | Oui  | Identificateur de l’opération, consultez [Types d’opération].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Oui      | No   | Workflow uniquement. Nombre de tâches déclenchées par le workflow.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Oui      | No   | Facultatif. Événements de workflow uniquement. [ObjectId de l’utilisateur Azure Active Directory](/azure/marketplace/find-tenant-object-id#find-user-object-id) qui a déclenché le workflow. Voir aussi `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Oui      | No   | Actualisation `full` ou `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Oui      | No   | `OnDemand` ou `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Oui      | No   | `Running` ou `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Oui      | Oui  | Horodateur UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Oui      | Oui  | Horodateur UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Oui      | Oui  | Horodateur UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Oui      | Oui  | `instanceId` de Customer Insights                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Oui  | - Pour OperationType = `Export`, l’identificateur est le GUID de la configuration d’exportation. <br> - Pour OperationType = `Enrichment`, il s’agit du GUID de l’enrichissement <br> - Pour OperationType `Measures` et `Segmentation`, l’identificateur est le nom de l’entité. |
| `properties.friendlyName`                    | No       | Oui  | Nom convivial de l’exportation ou de l’entité traitée.                                                                                                                                                                                           |
| `properties.error`                           | No       | Oui  | Facultatif. Message d’erreur avec plus de détails.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Oui  | Facultatif. Pour OperationType `Export` uniquement. Identifie le type de l’exportation. Pour plus d’informations, consultez [Présentation des destinations d’exportation](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Oui  | Facultatif. Pour OperationType `Export` uniquement. Contient une liste des entités configurées dans l’exportation.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Oui  | Facultatif. Pour OperationType `Export` uniquement. Message détaillé pour l’exportation.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Oui  | Facultatif. Pour OperationType `Segmentation` uniquement. Indique le nombre total de membres du segment.                                                                                                                                                    |
