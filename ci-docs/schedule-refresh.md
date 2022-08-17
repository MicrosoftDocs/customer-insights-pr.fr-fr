---
title: Planifier l'actualisation du système
description: Planifier l’heure à laquelle le système doit être actualisé
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246338"
---
# <a name="schedule-system-refresh"></a>Planifier l'actualisation du système

Planifiez des actualisations automatiques de toutes vos [sources de données ingérées](data-sources.md). Les actualisations automatiques permettent de garantir que les mises à jour de vos sources de données se reflètent dans vos profils client unifiés.

> [!NOTE]
> Les sources de données Power Query que vous gérez s’actualisent selon leurs propres planifications. Pour planifier l’actualisation de ces sources de données Power Query, configurez les paramètres d’actualisation sur ces source de données spécifiques à partir de la page **Sources de données**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Paramètres d’actualisation du dataflow.":::

## <a name="set-system-refresh-schedule"></a>Définir le calendrier d'actualisation du système

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **Planifier**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Onglet Planifier l’actualisation de la page Système.":::

1. L’état par défaut de l’actualisation planifiée est **Désactivé**. Pour autoriser les actualisations planifiées, basculez le bouton en haut de l’écran sur **Activé**.

1. Choisissez entre les actualisations **Hebdomadaires** (par défaut) et **Quotidiennes**. Si vous prévoyez de planifier des actualisations hebdomadaires, sélectionnez un ou plusieurs jours pendant lesquels vous souhaitez exécuter l’actualisation.

1. Définissez votre **Fuseau horaire**, puis utilisez la liste déroulante **Heure** pour définir votre calendrier d’actualisation. Si vous souhaitez planifier plusieurs actualisations en une seule journée, sélectionnez **Ajouter une autre heure**.

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

[!INCLUDE [footer-include](includes/footer-banner.md)]
