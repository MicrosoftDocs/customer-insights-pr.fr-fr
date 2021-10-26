---
title: Bot pour Microsoft Teams
description: Recherchez des profils clients unifiés dans Microsoft Teams avec l’aide d’un bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cff696834e3dad00ce5b0f1b5bcb13d86354a4e7
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617598"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams pour Dynamics 365 Customer Insights (version préliminaire)

Connectez-vous à Microsoft Teams pour permettre à un bot de rechercher des profils clients unifiés dans les canaux Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams montrant un dossier client.](media/teams-bot.png "Bot Teams montrant un dossier client")

## <a name="prerequisites"></a>Conditions préalables

Pour installer et configurer le bot, les conditions préalables suivantes doivent être remplies :

- Il y a au moins une [source de données ajoutée](data-sources.md).
- Le [processus d’unification](data-unification.md) est complet.
- Des champs sont ajoutés à l’[index de recherche et de filtrage](search-filter-index.md).
- Customer Insights et Teams sont dans la même organisation.
- Votre environnement a l’audience cible principale définie sur des clients individuels. Les comptes professionnels ne sont pas pris en charge.

## <a name="configure-the-bot"></a>Configurer le bot

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.
1. Sur la vignette Microsoft Teams, sélectionnez **Configurer**.
1. Vous êtes redirigé vers la zone **Applications** dans Teams. Vous pouvez également ouvrir Teams et sélectionner **Applications** dans l’angle inférieur gauche ou [l’obtenir depuis AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directement.
1. Recherchez **Customer Insights** et sélectionnez l’application.
1. Cliquez sur **Ajouter**.
1. Une fois connecté à Customer Insights dans Teams, vous voyez un message de bienvenue et vous pouvez commencer.

## <a name="things-you-can-do-with-the-bot"></a>Choses que vous pouvez faire avec le bot

Le bot offre des capacités de recherche pour les profils client unifiés.

- Saisissez **rechercher** suivi d’un nom, d’une adresse e-mail ou de tout autre champ du profil client unifié ajouté à l’index de recherche et de filtrage.

  Vous obtenez une carte avec jusqu’à 15 champs de profil client résultant. Plusieurs correspondances renvoient une liste de résultats où vous pouvez sélectionner un profil. Vous pouvez ajouter le critère de recherche entre guillemets doubles pour rechercher une correspondance exacte.

- Si votre organisation gère plusieurs environnements Customer Insights dans la même organisation, vous pouvez entrer **switchinstance** pour choisir l’environnement auquel vous souhaitez connecter le bot.

- Saisissez **aide** pour voir une liste des commandes disponibles pour le bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]