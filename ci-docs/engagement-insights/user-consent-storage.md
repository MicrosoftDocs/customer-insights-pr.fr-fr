---
title: Gérer les cookies et le consentement de l’utilisateur pour stocker les données utilisateur dans Dynamics 365 Customer Insights
description: Découvrez comment les cookies et le consentement de l'utilisateur sont utilisés pour identifier les visiteurs du site Web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558868"
---
# <a name="manage-cookies-and-user-consent"></a>Gérer les cookies et le consentement de l’utilisateur

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La fonctionnalité des informations sur l’engagement de Dynamics 365 Customer Insights utilise des cookies et des clés (`localStorage`) pour identifier les visiteurs du site Web.

Les cookies sont de petits fichiers qui stockent des informations sur les interactions d'un utilisateur avec le site Web. Ils sont stockés dans des navigateurs Web. Lorsque les utilisateurs visitent un site Web pour lequel ils ont stocké des cookies, le navigateur envoie ces informations au serveur, qui renvoie des informations uniques à l'utilisateur. Cette technologie permet, par exemple, à un panier d'achat en ligne de conserver des articles sélectionnés même si un utilisateur quitte le site Web.

## <a name="user-consent"></a>Consentement de l'utilisateur

Le [Règlement général sur la protection des données (RGPD)](/dynamics365/get-started/gdpr/) est un règlement de l'Union européenne (UE) qui impose aux organisations de gérer la confidentialité et la sécurité de leurs utilisateurs. Les cookies stockent ou collectent souvent des « données personnelles », comme un identifiant en ligne, qui est couvert par le RGPD. Vous êtes concerné par le RGPD si votre entreprise emploie et/ou vend à des personnes concernées de l'UE. [En savoir plus sur la manière dont Microsoft peut vous aider à vous conformer au RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Pour permettre au SDK de la fonction Informations sur l’engagement de stocker des cookies ou d'autres informations sensibles, vous devez spécifier que vos utilisateurs ont donné leur consentement. Cela se produit lors de l’initialisation du SDK en définissant un champ `userConsent` dans la configuration.

Si vous indiquez qu'il n'y a pas de consentement de l'utilisateur, le SDK ne stockera aucune donnée et n'enverra pas d'événements pouvant être utilisés pour suivre le comportement de l'utilisateur. Toutes les données précédemment stockées seront supprimées du navigateur.

Si aucune valeur de consentement de l'utilisateur n'est spécifiée, le SDK supposera que l'utilisateur a donné son consentement. Cela signifie que si vous (en tant que client) ne spécifiez pas de valeur pour le consentement de l'utilisateur dans le SDK, les données seront collectées. Cependant, si vous spécifiez que la valeur du consentement de l'utilisateur doit être définie sur « true », les données ne seront pas collectées si un utilisateur refuse ou ne donne pas son consentement explicite.

Vous trouverez ci-dessous un extrait de code pour initialiser le SDK Web avec le consentement utilisateur :
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Stockage des données des visiteurs dans la fonction Informations sur l’engagement

### <a name="cookies"></a>Cookies

- _msei
    - Stocke l'ID utilisateur anonyme. Ce cookie est défini dans le domaine client et expire dans 365 jours.

### <a name="local-storage"></a>Stockage local

La fonctionnalité des informations sur l’engagement utilise également des clés (`localStorage`) pour suivre les données non sensibles. Ces données sont entièrement stockées dans le navigateur lui-même, sans trafic envoyé vers ou depuis vos serveurs.

- *EISession.Id*
    - Stocke des informations sur la session utilisateur en cours, comme l'ID de session, quand elle a démarré et quand elle expire.
- *EISession.Previous*
    - Stocke l'URL de la page précédemment visitée dans la session en cours.

Les clés du stockage local n’expirent pas automatiquement et seront réinitialisées lors de la prochaine session du SDK.

## <a name="deleting-cookies"></a>Suppression des cookies

Vos clients peuvent supprimer manuellement les cookies et les clés de stockage local à tout moment via les paramètres de leur navigateur.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
