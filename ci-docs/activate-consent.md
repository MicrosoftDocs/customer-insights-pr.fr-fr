---
title: Activer les règles de consentement pour les segments
description: Suivez cette procédure pour lier les données de consentement et activer les contrôles de consentement dans Dynamics 365 Customer Insights. Un administrateur peut également désactiver les contrôles de consentement.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646049"
---
# <a name="activate-consent-rules"></a>Activer les règles de consentement

Le [Centre de consentement (version préliminaire)](consent-management/overview.md) vous aide à harmoniser les données de consentement provenant de diverses sources. Utiliser l’entité *Consentement* unifiée pour appliquer les contrôles de consentement par défaut. Après avoir importé les données de consentement dans le Centre de consentement et configuré les règles pour les données, l’entité *Consentement* est automatiquement synchronisée avec Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Activer les vérifications de consentement

Une fois les données de consentement importées dans le Centre de consentement (version préliminaire) et les règles configurées, vous pouvez activer les contrôles de consentement. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Onglet Consentement dans les paramètres Customer Insights avec les données de consentement activées.":::

1. Dans Customer Insights, accédez à **Admin** > **Système**.

1. Sélectionnez l’onglet **Consentement (version préliminaire)**.

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule sur **Activé** pour toutes les zones que vous souhaitez activer.

1. Sélectionnez la case à cocher **Autoriser le remplacement des règles de consentement par défaut** pour supprimer les contrôles de consentement par défaut appliqués à un segment particulier. 

1. Dans le menu déroulant, sélectionnez l’endroit où vous souhaitez autoriser les remplacements.     

1. Dans la section **Lier le consentement aux profils des clients**, choisissez l’attribut qui est utilisé comme identifiant pour lier les données de consentement aux données client. Il s’agira probablement d’un numéro de téléphone ou d’une adresse e-mail. 

1. Sélectionnez **Enregistrer** pour appliquer vos paramètres.

## <a name="disable-consent-checks"></a>Désactiver les vérifications de consentement

Pour arrêter d’utiliser les données de consentement dans Customer Insights, un administrateur doit mettre à jour les paramètres système en conséquence.

1. Dans Customer Insights, accédez à **Admin** > **Système**.

1. Sélectionnez l’onglet **Consentement (version préliminaire)**.

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule sur **Désactivé**.

> [!TIP]
> Pour ne plus utiliser la capacité de gestion du consentement, consultez [Paramètres système dans le Centre de consentement (version préliminaire)](consent-management/system-settings.md).
