---
title: Gérer les règles de consentement par défaut sur les segments
description: Avec la capacité de gestion du consentement, vous pouvez désactiver ou modifier les règles de consentement par défaut si les remplacements sont activés.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646099"
---
# <a name="disable-or-change-default-consent-rules"></a>Désactiver ou modifier les règles de consentement par défaut

Si votre organisation utilise la [capacité de gestion du consentement](consent-management/overview.md) avec Dynamics 365 Customer Insights, les [administrateurs peuvent imposer des règles de consentement](activate-consent.md) pour les segments. 

Avec des règles de consentement appliquées dans la zone de segment, chaque segment informe de l’état de la vérification du consentement et des règles. Si les remplacements sont autorisés, les règles de consentement par défaut sont désactivées pour des segments spécifiques. Chaque créateur d’un segment peut ajouter à un segment d’autres règles de consentement en plus des règles par défaut. 

## <a name="for-administrators"></a>Pour les administrateurs

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Générateur de segments avec options de règle de consentement.":::

**Pour désactiver les règles de consentement par défaut :**

1. Dans la notification **Règles de consentement**, sélectionnez **Voir les détails**. 

1. Définit la bascule **Règles de consentement par défaut** sur **Désactivé**.

**Pour ajouter d’autres règles de consentement :**

1. Dans la notification **Règles de consentement**, sélectionnez **Voir les détails**. 

1. Sélectionnez **Ajouter des règles de consentement** et choisissez une règle de consentement dans le menu déroulant **Sélectionner le type de données de consentement**.

1. Sélectionnez **Enregistrer** pour appliquer la nouvelle règle au segment.

## <a name="for-contributors"></a>Pour les contributeurs

Pour créer un segment sans règles de consentement appliquées, vous devez contacter votre administrateur pour les désactiver sur votre segment. Cependant, vous pouvez ajouter vos propres règles de consentement aux segments que vous possédez et gérez.

Ce processus comporte trois étapes : 
1. [Créez le segment](segments.md) dans Customer Insights et enregistrez-le. 

1. Partagez le nom du segment avec votre administrateur et demandez-lui d’[activer les remplacements pour votre segment](activate-consent.md). 

1. Ouvrez à nouveau vos segments. Dans la notification **Règles de consentement**, sélectionnez **Voir les détails** et ajoutez les règles de consentement que vous souhaitez appliquer. Ensuite, **Enregistrez** et **Exécutez** votre segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
