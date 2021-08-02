---
title: Gérer les cookies et le consentement de l'utilisateur pour stocker les données
description: Découvrez comment les cookies et le consentement de l'utilisateur sont utilisés pour identifier les visiteurs du site Web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a39255a63d56cdca66335b81c43800cbb318284d
ms.sourcegitcommit: 302910e39153f4b5c850ed9b1a62cb867e4df358
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6218260"
---
# <a name="manage-cookies-and-user-consent"></a>Gérer les cookies et le consentement de l’utilisateur

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La fonction Informations sur l’engagement Dynamics 365 Customer Insights utilise des cookies et un stockage local (`localStorage`) pour identifier les visiteurs de site Web.

Les cookies sont de petits fichiers qui stockent des informations sur les interactions d'un utilisateur avec le site Web. Ils sont stockés dans des navigateurs Web. Lorsque les utilisateurs visitent un site Web pour lequel ils ont stocké des cookies, le navigateur envoie ces informations au serveur, qui renvoie des informations uniques à l'utilisateur. Cette technologie permet, par exemple, à un panier d'achat en ligne de conserver des articles sélectionnés même si un utilisateur quitte le site Web.

## <a name="user-consent"></a>Consentement de l'utilisateur

Le [Règlement général sur la protection des données (RGPD)](/dynamics365/get-started/gdpr/) est un règlement de l'Union européenne (UE) qui impose aux organisations de gérer la confidentialité et la sécurité de leurs utilisateurs. Les cookies stockent ou collectent souvent des « données personnelles », comme un identifiant en ligne, qui est couvert par le RGPD. Vous êtes concerné par le RGPD si votre entreprise emploie et/ou vend à des personnes concernées de l'UE. [En savoir plus sur la manière dont Microsoft peut vous aider à vous conformer au RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Pour permettre au SDK de la fonction Informations sur l’engagement de stocker des cookies ou d'autres informations sensibles, vous devez spécifier que vos utilisateurs ont donné leur consentement. Cela se produit lors de l'initialisation du SDK.

Si vous indiquez qu'il n'y a pas de consentement de l'utilisateur, le SDK ne stockera aucune donnée et n'enverra pas d'événements pouvant être utilisés pour suivre le comportement de l'utilisateur. Toutes les données précédemment stockées seront supprimées du navigateur.

Si aucune valeur de consentement de l'utilisateur n'est spécifiée, le SDK supposera que l'utilisateur a donné son consentement. Cela signifie que si vous (en tant que client) ne spécifiez pas de valeur pour le consentement de l'utilisateur dans le SDK, les données seront collectées. Cependant, si vous spécifiez que la valeur du consentement de l'utilisateur doit être définie sur « true », les données ne seront pas collectées si un utilisateur refuse ou ne donne pas son consentement explicite.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Stockage des données des visiteurs dans la fonction Informations sur l’engagement

### <a name="cookies"></a>Cookies

- _msei
    - Stocke l'ID utilisateur anonyme. Ce cookie est défini dans le domaine client et expire dans 365 jours.

### <a name="local-storage"></a>Stockage local

La fonction Informations sur l’engagement utilise également le stockage local (`localStorage`) pour suivre les données non sensibles. Ces données sont entièrement stockées dans le navigateur lui-même, sans trafic envoyé vers ou depuis vos serveurs.

- *EISession.Id* 
    - Stocke des informations sur la session utilisateur en cours, comme l'ID de session, quand elle a démarré et quand elle expire.
- *EISession.Previous*
    - Stocke l'URL de la page précédemment visitée dans la session en cours.
    
Les clés du stockage local n'expirent pas automatiquement. Elles seront réinitialisées lors de la prochaine session par le SDK.

## <a name="deleting-cookies"></a>Suppression des cookies

Vos clients peuvent supprimer manuellement les cookies et les clés de stockage local à tout moment via les paramètres de leur navigateur.


[!INCLUDE[footer-include](../includes/footer-banner.md)]