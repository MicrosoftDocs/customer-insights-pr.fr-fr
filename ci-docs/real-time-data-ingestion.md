---
title: Ingestion de données en temps réel (préversion)
description: Informations générales sur les fonctionnalités en temps réel dans Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 39d68011df9e4341244af627bb71f4e3635256bb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081219"
---
# <a name="real-time-data-ingestion-preview"></a>Ingestion de données en temps réel (préversion)

La fonctionnalité en temps quasi réel vous permet de voir, en quelques secondes, les dernières interactions de vos clients avec vos produits ou services.

Les [actualisations programmées](system.md#schedule-tab) comprennent un grand nombre d’enregistrements et plusieurs opérations complexes. Tout d’abord, les données sont extraites de la source de données. Ensuite, les données sont unifiées, puis enrichies avec des informations supplémentaires. Chaque exécution de ce processus peut prendre quelques minutes à plusieurs heures.

La fonctionnalité en temps réel fournit des données immédiatement pour la consommation, jusqu’à ce que l’actualisation programmée suivante extrait ces données de la source de données.

Les mises à jour en temps réel ont un délai d’expiration au-delà duquel elles ne remplacent plus la valeur de la source de données :

- Les mises à jour du profil seront conservées pendant 4 heures
- Les activités seront conservées pendant 30 jours

Ces valeurs sont des paramètres d’appel API que vous pouvez modifier. Elles visent à garantir que vos données sources demeurent votre source de référence. Si vous souhaitez que les mises à jour en temps réel soient conservées plus longtemps, vous devez les ajouter à une source de données afin qu’elles soient extraites lors de la prochaine actualisation programmée.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Mise à jour en temps réel des champs de profil client unifié

Les profils mis à jour s’afficheront dans la vue de la carte client, ou dans toute autre visualisation, en quelques secondes.

Étant donné que les opérations en temps réel ont lieu après l’unification des données, elles ne s’appliquent qu’aux profils client unifiés. Par conséquent, les modifications de profil en temps réel ne mettront pas à jour les mesures, l’appartenance du segment ou les enrichissements.

### <a name="limitations"></a>Limitations

- Vous pouvez mettre à jour les profils client, mais vous ne pouvez pas les créer ni les supprimer.
- L’exportation des mises à jour en temps réel vers des systèmes externes, comme Power BI, n’est pas possible pour le moment.

## <a name="real-time-creation-of-activities"></a>Création d’activités en temps réel

L’API en temps réel vous permet de publier une nouvelle activité de votre système source (un enregistrement source individuel) vers un profil client unifié. La nouvelle activité est disponible en tant qu’activité unifiée dans la chronologie de ce profil client unifié en quelques secondes. Vous pouvez voir la chronologie dans la vue de la carte client ou dans toute autre intégration de chronologie que vous avez configurée.

> [!NOTE]
>
> - Les activités sont immuables. Elles ne changent pas une fois créées.
> - Pour le moment, les segments et les mesures ne sont pas mis à jour en fonction de la nouvelle activité.
> - Les activités ajoutées uniquement via l’API en temps réel ne font pas partie des exportations et ne s’affichent pas dans PowerBI.

Vous pouvez vous connecter à l’API en temps réel de deux façons :

- [indirectement](#connect-via-the-dynamics-365-customer-insights-connector), en utilisant le connecteur [Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [directement](#connect-directly-to-the-real-time-api), avec un code

Les deux façons partagent les conditions préalables suivantes :

- Un environnement Customer Insights
- Profils client unifiés
- Activités configurées et exécutées
- Autorisations Contributeur ou Administrateur pour authentifier votre compte

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Connexion via le connecteur Dynamics 365 Customer Insights

L’API en temps réel peut ingérer des données à partir d’un connecteur dédié Power Platform, le [connecteur Dynamics 365 Customer Insights](/connectors/customerinsights/), sans qu’il soit nécessaire d’écrire et de déployer du code.    
Le connecteur peut effectuer les mêmes actions en temps réel que l’API. Une licence valide est nécessaire pour les connecteurs premium. Pour plus d’informations, voir [FAQ sur les licences Power Apps et Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps et/ou Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Pour plus d’informations sur la création de flux, consultez la [documentation de Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Connexion directe à l’API en temps réel

Vous pouvez utiliser les fonctionnalités en temps réel en créant votre propre pipeline et en le connectant directement à l’API en temps réel.    
Vous pouvez publier une activité au format de votre système source ou au format UnifiedActivity. Procurez-vous le format en effectuant un appel d’API vers /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Les détails de cette API, notamment les paramètres et les réponses, sont disponibles dans la section **EntityData** du [Guide de référence des API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Pour plus d’informations, consultez [Utiliser les API de Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Comprendre votre utilisation en temps réel avec la télémétrie

Obtenez une vue d’ensemble du volume de demandes adressées à l’API en temps réel ainsi que des informations sur les problèmes que le système peut rencontrer. Vous pouvez [accéder à la télémétrie en temps réel](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
