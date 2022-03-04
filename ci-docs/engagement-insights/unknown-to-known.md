---
title: Reconnaître les événements web des visiteurs déjà authentifiés avec la fonctionnalité Inconnu à connu
description: La fonctionnalité Inconnu à connu vous permet d'associer des événements d'un site web à des visiteurs qui se sont déjà authentifiés.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230677"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Reconnaître les événements web des visiteurs déjà authentifiés

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La fonctionnalité **Inconnu à connu** des informations d'engagement permet d'associer des événements d'un site web à des visiteurs qui se sont déjà authentifiés. Si la fonctionnalité est désactivée, les visiteurs qui se sont authentifiés lors d'une visite précédente puis ont quitté le site ne sont pas identifiés s'ils ne s'authentifient pas à nouveau à leur prochaine visite. 

Par exemple, une personne a visité un site web la semaine dernière, s'est connectée à son compte d'utilisateur sur le site et a parcouru le catalogue de produits. Elle revient la semaine suivante pour parcourir d'autres produits sans se connecter à son compte. Le propriétaire du site qui utilise la fonctionnalité **Inconnu à connu** sait que la même personne est revenue et ce qu'elle a fait sur le site. Cela permet une analyse et des rapports plus précis des activités du site web.

## <a name="enable-unknown-to-known"></a>Activer la fonctionnalité Inconnu à connu

Vous devez être un [administrateur d'espace de travail](user-roles.md) pour activer cette fonctionnalité. 

1. Dans les informations d'engagement, accédez à **Administrateur** > **Espace de travail**. 
2. Sélectionnez l'onglet **Paramètres**.
3. Dans la section **Inconnu à connu**, définissez le bouton bascule sur **Activé**.

![Activer la fonctionnalité Inconnu à connu](media/U2Ktoggle.png "Activer la fonctionnalité Inconnu à connu")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Ajout de code JavaScript à l'extrait de suivi de votre site

Un site web peut capturer **user authId** avec l'exemple JavaScript suivant en utilisant le [SDK web des informations d'engagement](advanced-SDK-implementation.md). Pour que la fonctionnalité **Inconnu à connu** puisse fonctionner, vous devez capturer authId *et* activer userMapping:True dans votre extrait JavaScript, comme dans l'exemple ci-dessous.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
