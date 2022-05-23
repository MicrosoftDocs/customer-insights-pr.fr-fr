---
title: Spécifier les paramètres système pour la gestion du consentement
description: Définissez la langue et les paramètres locaux pour la fonctionnalité de gestion du consentement de Dynamics 365 Customer Insights.
ms.date: 11/12/2021
ms.subservice: consent-management
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fa30cc72d846764ecd6f2bbd2a088db412a060f5
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755665"
---
# <a name="system-settings-in-consent-center-preview"></a>Paramètres système dans le Centre de consentement (préversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La [fonctionnalité de gestion du consentement](overview.md) dans Dynamics 365 Customer Insights vous permet de configurer certains paramètres système pour vos environnements. 

:::image type="content" source="media/system-settings.png" alt-text="Extrait de la vue des paramètres système.":::

## <a name="change-the-language"></a>Changer la langue

Lors de la prévisualisation publique, l’application n’est disponible qu’en anglais et en français. D’autres langues sont ajoutées lorsque la capacité est généralement disponible. 

Pour changer de langue, [mettez à jour vos paramètres de langue dans Customer Insights](../system.md#update-the-settings).

## <a name="stop-using-the-consent-management-capability"></a>Arrêter d’utiliser la capacité de gestion du consentement

Une fois qu’un administrateur a mis en service la capacité de gestion du consentement, celle-ci est automatiquement disponible dans l’environnement Customer Insights lié. Actuellement, vous ne pouvez pas supprimer la gestion du consentement de votre environnement une fois qu’il est mis en service. 

Cependant, il existe des solutions de contournement qu’un administrateur peut utiliser pour ne plus appliquer les règles de consentement et, par conséquent, désactiver la fonctionnalité liée à la gestion du consentement. 

1. Dans Customer Insights, accédez à **Système** > **Consentement (version préliminaire)**. 

1. Cochez la case pour autoriser les remplacements. 

1. Autorisez les remplacements pour tous les segments existants. 

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule sur **Désactivé**.

-OU- 

1. Dans Customer Insights, accédez à **Système** > **Consentement (version préliminaire)**. 

1. Dans la section **Activer les contrôles de consentement**, réglez la bascule sur **Désactivé**. 

1. Supprimez toutes les règles de consentement par défaut.
