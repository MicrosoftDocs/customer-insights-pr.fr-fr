---
title: Activer les règles de consentement pour les segments dans les insights d’audience
description: Étapes pour lier les données de consentement et activer les contrôles de consentement dans les insights d’audience.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753058"
---
# <a name="activate-consent-rules"></a>Activer les règles de consentement

[Centre de consentement (version préliminaire)](../consent-management/overview.md) vous aide à harmoniser les données de consentement provenant de diverses sources. Utiliser l’entité *Consentement* unifiée pour appliquer les contrôles de consentement par défaut. Après avoir importé les données de consentement dans le Centre de consentement et configuré les règles pour les données de consentement importées, l’entité *Consentement* est automatiquement synchronisée avec les insights d’audience.

## <a name="enable-consent-checks"></a>Activer les vérifications de consentement

Une fois les données de consentement importées dans le Centre de consentement (version préliminaire) et les règles configurées, vous pouvez activer les contrôles de consentement dans les insights d’audience. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Onglet Consentement dans les paramètres d’insights d’audience avec les données de consentement activées.":::

1. Dans Audience Insights, accédez à **Administration** > **Système**.

1. Sélectionnez l’onglet **Consentement (version préliminaire)**.

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule pour la zone que vous souhaitez activer sur **Actif**.

1. Sélectionnez la case à cocher **Autoriser le remplacement des règles de consentement par défaut** pour supprimer les contrôles de consentement par défaut appliqués à un segment particulier. 

1. Dans le menu déroulant, sélectionnez l’endroit où vous souhaitez autoriser les remplacements.     

1. Dans la section **Lier le consentement aux profils des clients**, choisissez l’attribut qui est utilisé comme identifiant pour lier les données de consentement aux données client. Il s’agit probablement d’un numéro de téléphone ou d’une adresse e-mail. 

1. Sélectionnez **Enregistrer** pour appliquer vos paramètres.

## <a name="disable-consent-checks"></a>Désactiver les vérifications de consentement

Pour arrêter d’utiliser les données de consentement dans les insights d’audience, un administrateur doit mettre à jour les paramètres système en conséquence.

1. Dans Audience Insights, accédez à **Administration** > **Système**.

1. Sélectionnez l’onglet **Consentement (version préliminaire)**.

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule sur **Désactivé**.
