---
title: Paramètres de sécurité dans Dynamics 365 Customer Insights
description: Découvrez les paramètres de sécurité dans Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653711"
---
# <a name="security-overview-page"></a>Page de présentation de la sécurité

La page **Sécurité** répertorie les options pour configurer les autorisations utilisateur et les fonctionnalités qui aident à rendre Dynamics 365 Customer Insights plus sécurisé. Seuls les administrateurs peuvent accéder à cette page. 

Accédez à **Administrateur** > **Sécurité** pour configurer les paramètres.

La page **Sécurité** comprend les onglets suivants :
- [Utilisateurs](#users-tab)
- [API](#apis-tab)
- [Coffre de clés ](#key-vault-tab)

## <a name="users-tab"></a>Onglet Utilisateurs

L’accès à Customer Insights est limité aux utilisateurs de votre organisation qui ont été ajoutés à l’application par un administrateur. L’onglet **Utilisateurs** vous permet de gérer l’accès des utilisateurs et leurs autorisations. Pour plus d’informations, consultez les [Autorisations utilisateur](permissions.md).

## <a name="apis-tab"></a>Onglet API

Affichez et gérez les clés pour utiliser les [API Customer Insights](apis.md) avec les données de votre environnement.

Vous pouvez créer de nouvelles clés primaires et secondaires en sélectionnant **Régénérer primaire** ou **Régénérer secondaire**. 

Pour bloquer l’accès de l’API à l’environnement, sélectionnez **Désactiver**. Si les API sont désactivées, vous pouvez sélectionner **Activer** pour accorder à nouveau l’accès.

## <a name="key-vault-tab"></a>Onglet Coffre de clés

L’onglet **Coffre de clés** vous permet de gérer votre propre [Azure Key Vault](/azure/key-vault/general/basic-concepts) et de le lier à l’environnement.
Le coffre de clés dédié peut être utilisé pour organiser et utiliser des secrets dans la limite de conformité d’une organisation. Customer Insights peut utiliser les secrets dans Azure Key Vault pour [établir des connexions](connections.md) avec des systèmes tiers.

Pour plus d’informations, voir [Apportez votre propre coffre de clés Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
