---
title: Activer les rapports de profil prêts à l'emploi
description: Comment créer des rapports de profil prêts à l'emploi regroupés par sexe, âge et pays d'origine.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486117"
---
# <a name="out-of-box-profile-reports"></a>Rapports de profil prêts à l'emploi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un rapport est un ensemble de visualisation de données pour vous aider à comprendre le comportement des utilisateurs. En vous connectant à la fonction Informations sur l’audience de Customer Insights., la fonction Informations sur l’engagement peut afficher un rapport contenant des informations sur les profils client unifiés. Ce rapport comprend le nombre de profils dont vous disposez, regroupés par sexe, âge et emplacement géographique.

## <a name="prerequisites"></a>Conditions préalables

L'environnement Informations sur l’audience doit stocker les données dans un compte Azure Data Lake Storage géré par le client.

Si vous utilisez une version d'essai de la fonction Informations sur l’audience ou un environnement dans un lac de données géré par Customer Insights, [contactez-nous](https://go.microsoft.com/fwlink/?linkid=2145734) pour obtenir de l'aide.  


## <a name="enable-the-customer-profile-report"></a>Activer le rapport de profil client

Un administrateur d’environnement doit [lier les informations sur l’engagement et les informations sur l’audience](integrate-audience-insights-engagement-insights.md).

Après avoir spécifié les détails de connexion, l'administrateur peut accorder l'accès à d'autres personnes de l'organisation pour voir le rapport. L'administrateur de l'environnement qui configure la connexion a automatiquement accès au rapport. 

Une fois la connexion établie, la fonction **Profils** sera disponible dans le volet de navigation de gauche. 

- Pour consulter le rapport, allez dans **Découvrir** > **Profils**.

Le rapport **Profils** contient des visualisations sur le sexe, l'âge et l'emplacement géographique des profils clients connectés.

:::image type="content" source="media/customer-profiles.png" alt-text="Rapport de profil client.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]