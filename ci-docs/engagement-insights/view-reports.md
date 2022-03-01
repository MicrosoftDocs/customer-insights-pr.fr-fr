---
title: Afficher les rapports de données
description: Utilisez les rapports disponibles pour voir l'activité en temps réel sur votre site.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036645"
---
# <a name="view-reports"></a>Afficher les rapports

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un rapport est un ensemble de visualisations de données, qui utilise les données collectées par le biais du SDK, pour vous aider à mesurer et comprendre le comportement des utilisateurs. Les informations d’engagement de Dynamics 365 Customer Insights comprennent des rapports prédéfinis pour les projets web et mobiles.  

## <a name="web-reports"></a>Rapports web

Vous pouvez accéder aux rapports web sous **Découvrir** dans le volet de navigation de gauche.

:::image type="content" source="media/report-menu.png" alt-text="Navigation affichant la liste des rapports disponibles.":::

### <a name="real-time-usage-report"></a>Rapport d'utilisation en temps réel

Le rapport d'**Utilisation en temps réel** fournit un aperçu de l'activité actuelle sur votre site qui s'actualise automatiquement toutes les minutes. Utilisez l'utilisation en temps réel pour surveiller l'impact des campagnes marketing, des événements de presse et d'autres scénarios sur le trafic de votre site.

### <a name="key-metrics-reports"></a>Rapports de mesures clés

- **Vues de page** répertorie les vues de page pour des pages individuelles ainsi que le nombre total de vues de page sur la période sélectionnée.

- **Visites** affiche des informations sur le nombre de visites et la durée de la visite.

- **Visiteurs** informe sur les visiteurs nouveaux et récurrents de votre site.

### <a name="content-reports"></a>Rapports sur le contenu

- **Liens** affiche des informations sur le nombre et le type de clics.

- **Quitter les pages** répertorie les liens sur lesquels les visiteurs ont cliqué pour quitter votre site.

### <a name="traffic-sources-reports"></a>Rapports sur les sources de trafic

- **Référents** répertorie les domaines et les URL qui ont renvoyé les visiteurs vers votre site.

- **Codes de suivi** fournit des détails sur les codes de suivi dans les liens qui ont dirigé les visiteurs vers votre site.

### <a name="visitor-profiles-reports"></a>Rapports sur les profils des visiteurs

- **Appareils** répertorie les appareils physiques qui ont été utilisés pour accéder à votre site.

- **Système d’exploitation et navigateurs** fournit des informations sur les systèmes d’exploitation et les navigateurs en cours d’exécution lors de l’accès à votre site.

- **Emplacements** affiche des informations sur les visiteurs par pays, région et ville.

- **Langues** répertorie les vues de page selon les langues préférées du visiteur.

## <a name="mobile-reports"></a>Rapports mobiles

Les rapports mobiles sont regroupés en catégories d’utilisation en temps réel, d’applications et d’utilisateurs. Vous pouvez accéder aux rapports mobiles sous **Découvrir** dans le volet de navigation de gauche.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interface utilisateur des informations d’engagement affichant le rapport d’utilisation en temps réel avec les données dans les graphiques et les listes.":::   

### <a name="real-time-usage"></a>Utilisation en temps réel

**Utilisation en temps réel** donne un aperçu de l’activité actuelle dans votre application mobile qui est actualisée automatiquement tous les minutes. Utilisez l’utilisation en temps réel pour surveiller le nombre d’utilisateurs et de sessions actuellement actifs dans votre application et les vues de l’écran supérieur.

### <a name="app-reports"></a>Rapports sur l’application

- **Vues d’écran** répertorie les vues d’écran pour des écrans individuels d’une application ainsi que le nombre total de vues d’écran sur la période sélectionnée. Vous pouvez afficher les vues d’écran par nom d’écran ou par titre d’écran.

- **Sessions** affiche des informations sur le nombre de sessions et la durée de la session.

- **Fréquence de retour** regroupe le nombre de sessions par nombre de jours depuis la dernière session.

- **Utilisateurs** affiche les utilisateurs nouveaux et récurrents dans votre application mobile.

- **Événements** répertorie tous les événements collectés à partir de votre application, plus le nombre total pour chaque événement.

### <a name="user-reports"></a>Rapports sur les utilisateurs

- **Versions de l’application** répertorie les versions de votre application mobile utilisées par votre base d’utilisateurs.

- **Appareils et versions du système d’exploitation** fournit des informations sur les appareils et les systèmes d’exploitation qui exécutent votre application mobile.

- **Emplacements** affiche des informations sur les utilisateurs de l’application par pays, région et ville.

## <a name="filter-by-time-or-value"></a>Filtrer par heure ou valeur

Vous pouvez sélectionner la période ou la valeur dans un rapport web ou mobile pour vous concentrer sur une valeur ou une période. 

- Pour sélectionner une période, sélectionnez **Plus [...]** dans la liste déroulante du rapport. La sélection de la plage horaire est désactivée pour un rapport d'utilisation en temps réel ; l'intervalle de temps pour un rapport d'utilisation en temps réel est « maintenant ».

- Dans la plupart des rapports, vous pouvez sélectionner une valeur dans un graphique ou une liste pour filtrer en fonction de la valeur sélectionnée.

[!INCLUDE[footer-include](../includes/footer-banner.md)]