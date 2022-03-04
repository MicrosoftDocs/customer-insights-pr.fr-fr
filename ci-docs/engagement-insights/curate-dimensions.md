---
title: Utiliser les dimensions démographiques pour diviser les données comportementales (dimensions organisées)
description: Utilisez les dimensions organisées du profil unifié pour activer les propriétés pour les profils client des informations sur l’audience.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233044"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Utiliser les dimensions démographiques pour diviser les données comportementales

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En utilisant les dimensions démographiques du profil unifié, les utilisateurs des informations sur l’engagement peuvent accéder aux propriétés pour les profils des informations sur l’audience. Ces propriétés peuvent ensuite servir dans des analyses interactives de données comportementales, ce qui inclut les données capturées par les informations sur l’engagement sur votre site web ou votre application mobile.

>[!NOTE]
> Les informations sur l'engagement incluent des dimensions prêtes à l'emploi pour les propriétés de l'événement. Pur plus d’informations : [Afficher et créer des dimensions](dimensions.md)

## <a name="prerequisite"></a>Conditions préalables

- Un environnement d’informations sur l’engagement dans lequel vous disposez des données sur le profil client liées à l’environnement d’informations sur l’audience dans lequel les profils client sont créés. Plus d’informations : [Créer un lien entre les informations sur l’audience et les informations sur l’engagement](integrate-audience-insights-engagement-insights.md).

> [!NOTE]
> Après avoir créé un lien entre les environnements d’informations sur l’audience et d’informations sur l’engagement, vous ne recherchez peut-être que certaines données sur les propriétés pour les profils client car elles peuvent être utiles en tant que dimensions dans les informations sur l’engagement. Pour plus d’informations, accédez à [Activer les attributs et les segments des profils unifiés des informations sur l’audience](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Créer un rapport personnalisé

1. Dans le volet de gauche, sélectionnez **Personnalisé** > **Nouveau rapport**, puis sélectionnez la mesure de votre choix. (Pour cet exemple, nous avons choisi **Pages vues par heure**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Sélectionnez une mesure.":::

2. Dans l’éditeur de la visualisation, sélectionnez **Dimensions**, puis sélectionnez **Démographique** dans le menu déroulant **Type de dimension**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Sélectionnez une donnée démographique.":::

3. Sélectionnez une dimension **Signal.Customer.*xxx***. (Cet exemple montre Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Sélectionnez une dimension.":::
  
## <a name="limitations"></a>Limitations

Actuellement, seules les dimensions démographiques peuvent être utilisées pour diviser les données comportementales.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
