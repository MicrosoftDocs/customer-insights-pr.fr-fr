---
title: Utiliser des sources de données pour ingérer des données
description: Découvrez comment importer des données depuis des sources diverses.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085527"
---
# <a name="data-sources-overview"></a>Vue d’ensemble des sources de données

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights se connecte aux données d’un large éventail de sources. La connexion à une source de données est souvent appelée processus d’*ingestion de données*. Après avoir ingéré les données, vous pouvez les [unifier](data-unification.md) et agir dessus.

## <a name="add-a-data-source"></a>Ajouter une source de données

Reportez-vous aux articles détaillés sur la façon d’ajouter une source de données, selon l’option que vous choisissez.

Vous pouvez ajouter une source de données de trois manières principales :

- [Grâce à des dizaines de connecteurs Power Query](connect-power-query.md)
- [À partir d’un dossier Common Data Model](connect-common-data-model.md)
- [À partir de votre propre lac Common Data Service](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Ajouter des données de sources de données locales

L’ingestion de données de sources de données locales dans Audience Insights est prise en charge en fonction des flux de données Power Platform. Les flux de données peuvent être activés dans Customer Insights en [fournissant l’URL de l’environnement Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) lors de la configuration de l’environnement.

Les sources de données créées après l’association d’un environnement Dataverse à Customer Insights utiliseront les [flux de données Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) par défaut. Les flux de données prennent en charge la connectivité locale à l’aide de la passerelle de données. Supprimez et recréez les sources de données qui existaient avant l’association d’un environnement Dataverse pour [utiliser les passerelles de données locales](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).

Les passerelles de données d’un environnement Power BI ou Power Apps existant seront visibles et vous pourrez les réutiliser dans Customer Insights. La page des sources de données affiche des liens pour accéder à l’environnement Power Platform dans lequel vous pouvez afficher et configurer les passerelles de données locales.

## <a name="review-ingested-data"></a>Évaluer les données ingérées

Vous avez accès au nom de chaque source de données ingérée, à son statut et à la dernière date d’actualisation des données pour cette source de données. Vous pouvez trier la liste des sources de données par colonne.

> [!div class="mx-imgBorder"]
> ![Source de données ajoutée](media/configure-data-datasource-added.png "Source de données ajoutée")

|Statut  |Description  |
|---------|---------|
|Opération réussie   |La source de données a été ingérée avec succès si une heure est mentionnée dans la colonne **Actualisé**.
|Non démarré(e)   |La source de données n’a pas encore de données ingérées ou est toujours en mode brouillon.         |
|Actualisation    |L’ingestion de données est en cours. Vous pouvez annuler cette opération en sélectionnant **Arrêter l’actualisation** dans la colonne **Actions**. L’arrêt de l’actualisation d’une source de données la ramène à son dernier état d’actualisation.       |
|Échoué     |L’ingestion de données s’est heurtée à des erreurs.         |

Sélectionnez la valeur dans la colonne **Statut** de n’importe quelle source de données pour examiner plus de détails. Dans le volet **Détails de la progression**, développez **Sources de données**. Sélectionnez **Afficher les détails** pour obtenir plus d’informations sur le statut d’actualisation, notamment les détails de l’erreur et les mises à jour du processus en aval.

Le chargement des données peut prendre un certain temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**. Pour plus d’informations, voir [Entités](entities.md).

## <a name="refresh-a-data-source"></a>Actualiser une source de données

Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande. 

Accédez à **Administration** > **Système** > [**Planification**](system.md#schedule-tab) pour configurer des actualisations programmées de toutes vos sources de données ingérées.

Pour actualiser une source de données à la demande, procédez comme suit :

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**

2. Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez actualiser, puis sélectionnez **Actualiser** dans la liste déroulante.

3. La source de données est maintenant déclenchée pour une actualisation manuelle. Si vous actualisez une source de données, à la fois le schéma de l’entité et les données seront mis à jour pour toutes les entités spécifiées dans la source de données.

4. Sélectionnez **Arrêtez l’actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d’actualisation de la source de données.

## <a name="delete-a-data-source"></a>Supprimer une source de données

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension en regard de la source de données que vous souhaitez supprimer et sélectionnez **Supprimer** dans le menu déroulant.

3. Confirmez votre suppression.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
