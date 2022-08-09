---
title: Bot Teams pour Dynamics 365 Customer Insights (version préliminaire)
description: Recherchez des profils clients unifiés dans Microsoft Teams avec l’aide d’un bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195839"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams pour Dynamics 365 Customer Insights (version préliminaire)

Connectez-vous à Microsoft Teams pour permettre à un bot de rechercher des profils clients unifiés dans les canaux Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams montrant un dossier client":::

## <a name="prerequisites"></a>Conditions préalables

- Au moins une [source de données ajoutée](data-sources.md).
- Le [processus d’unification](data-unification.md) est complet.
- Des champs sont ajoutés à l’[index de recherche et de filtrage](search-filter-index.md).
- Customer Insights et Teams sont dans la même organisation.
- Votre environnement a l’audience cible principale définie sur des clients individuels. Les comptes professionnels ne sont pas pris en charge.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurer le bot

1. Accédez à **Administrateur** > **Connexions**.
1. Sur la vignette Microsoft Teams, sélectionnez **Configurer**.
1. Vous êtes redirigé vers la zone **Applications** dans Teams. Vous pouvez également ouvrir Teams et sélectionner **Applications** dans l’angle inférieur gauche ou [l’obtenir depuis AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directement.
1. Recherchez **Customer Insights** et sélectionnez l’application.
1. Cliquez sur **Ajouter**.
1. Connectez-vous à Customer Insights dans Teams. Un message d’accueil s’affiche.

## <a name="things-you-can-do-with-the-bot"></a>Choses que vous pouvez faire avec le bot

Le bot offre des capacités de recherche pour les profils client unifiés.

- Saisissez **rechercher** suivi d’un nom, d’une adresse e-mail ou de tout autre champ du profil client unifié ajouté à l’index de recherche et de filtrage.

  Vous obtenez une carte avec jusqu’à 15 champs de profil client résultant. Plusieurs correspondances renvoient une liste de résultats où vous pouvez sélectionner un profil. Pour rechercher une correspondance exacte, ajoutez le critère de recherche entre guillemets doubles.

- Si votre organisation gère plusieurs environnements Customer Insights dans la même organisation, entrez **switchinstance** pour choisir l’environnement auquel vous souhaitez connecter le bot.

- Saisissez **aide** pour voir une liste des commandes disponibles pour le bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]