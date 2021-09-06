---
title: Scénarios SDK Web avancés
description: Scénarios avancés à prendre en compte lors de l'instrumentation de votre site Web avec un kit de développement logiciel (SDK).
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036325"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentation Web avancée avec un SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cet article vous guide à travers des scénarios avancés à prendre en compte lors de l'[instrumentation de votre site Web](instrument-website.md) avec un kit de développement logiciel (SDK) de la fonction Informations sur l’engagement Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Définition des détails de l'utilisateur pour votre événement

Le SDK vous permet de définir les informations utilisateur qui peuvent être envoyées avec chaque événement. Vous pouvez spécifier les détails de l'utilisateur dans une propriété appelée `user` (les données attendues pour cette propriété sont l'objet `IUser`), similaire à `src`, `name`, et `cfg` dans la configuration d'extrait de code.

L'objet `IUser` contient les propriétés de chaîne suivantes :

- **localId** : L'ID local de l'utilisateur.
- **authId** : L'ID utilisateur authentifié.
- **authType** : Le type d'authentification utilisé pour obtenir l'ID utilisateur authentifié.
- **name** : Le nom de l’utilisateur.
- **email** : L'adresse e-mail de l’utilisateur.
    
L’exemple suivant montre un extrait de code qui envoie des informations sur l’utilisateur. Là où vous voyez Fonctions désignées par *, remplacez-les par votre implémentation de l'appel de ces valeurs :  

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
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Vous pouvez également spécifier les informations utilisateur en appelant l'API `setUser(user: IUser)` sur le SDK. La télémétrie envoyée après avoir appelé `setUser API` contiendra les informations utilisateur.

## <a name="adding-custom-properties-for-each-event"></a>Ajout de propriétés personnalisées pour chaque événement

Le SDK vous permet de spécifier des propriétés personnalisées qui peuvent être envoyées avec chaque événement. Vous pouvez spécifier les propriétés personnalisées comme un objet contenant un ensemble de paires clé/valeur (la valeur peut être de type `string | number | boolean`). L'objet peut être ajouté dans une propriété appelée `props`, semblable à `src`, `name` et `cfg` dans la configuration d'extrait de code. 

L’exemple suivant montre un extrait de code qui renvoie des propriétés personnalisées.

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Vous pouvez également spécifier des propriétés personnalisées individuellement en appelant l'API `setProperty(name: string, value: string | number | boolean)` sur le SDK.

## <a name="sending-custom-events"></a>Envoi d'événements personnalisés

Vous pouvez utiliser le SDK pour envoyer des événements personnalisés. Vous devez spécifier un nom pour l'événement et les propriétés à envoyer avec l'événement.

L’exemple suivant montre un extrait de code qui effectue le suivi d'un événement personnalisé. La valeur « NAME » est la valeur de la clé `name` dans la configuration de l'extrait. C'est aussi le nom de la variable dans l'objet window où le SDK est chargé.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]