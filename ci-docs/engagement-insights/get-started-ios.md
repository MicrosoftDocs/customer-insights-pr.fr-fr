---
title: Mise en route du SDK iOS
description: Apprenez à personnaliser et à exécuter le SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494227"
---
# <a name="get-started-with-the-ios-sdk"></a>Mise en route du SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ce tutoriel vous guide dans le processus d’instrumentation de votre application iOS avec le SDK des informations d’engagement de Dynamics 365 Customer Insights. Vous commencerez à voir les événements dans votre portail dans cinq minutes ou avant.

## <a name="configuration-options"></a>Options de configuration

Les options de configuration suivantes peuvent être transmises au SDK via le fichier `EIConfig.plist` fourni :

- **ingestionKey** : clé d’ingestion utilisée pour envoyer des événements vers votre projet.
- **autocollectAction** : valeur booléenne pour activer ou désactiver l’auto-instrumentation de l’événement d’action.
- **autocollectView** : valeur booléenne pour activer ou désactiver l’auto-instrumentation de l’événement de vue.
- **endpointUrl** : URL du point de terminaison vers laquelle les événements seront dirigés.

## <a name="prerequisites"></a>Conditions préalables

- Xcode version 9 et versions ultérieures
- iOS version 8.2 et versions ultérieures
- Une clé d’ingestion (voir les instructions ci-dessous pour savoir comment l’obtenir)

## <a name="integrate-the-sdk-into-your-application"></a>Intégrer le SDK dans votre application

Commencez le processus en sélectionnant un espace de travail à utiliser, en sélectionnant la plateforme mobile iOS et en téléchargeant le SDK.

- Utilisez le sélecteur d’espaces de travail dans le volet de navigation de gauche pour sélectionner votre espace de travail.

- Si vous n’avez pas d’espace de travail existant, sélectionnez **Nouvel espace de travail** et suivez les étapes pour créer un [nouvel espace de travail](create-workspace.md).

- Une fois que vous avez créé un espace de travail, accédez à **Administrateur** > **Espace de travail**, puis sélectionnez **Guide d’installation**.

## <a name="configure-the-sdk"></a>Configurer le SDK

Une fois que vous avez téléchargé le SDK, vous pouvez l’utiliser dans Xcode pour activer et définir des événements. Deux méthodes sont disponibles :

### <a name="option-1-using-cocoapods-recommended"></a>Option 1 : utiliser CocoaPods (recommandé)
CocoaPods est un gestionnaire de dépendances pour les projets Swift et Objective-C Cocoa. Son utilisation facilite l’intégration du SDK des informations sur l’engagement pour iOS. CocoaPods vous permet également d’effectuer une mise à niveau vers la dernière version du SDK des informations sur l’engagement. Voici comment utiliser CocoaPods pour intégrer le SDK des informations sur l’engagement dans votre projet Xcode. 

1. Installez CocoaPods. 

1. Créez un nouveau fichier appelé Podfile dans le répertoire racine de votre projet et ajoutez-y les instructions suivantes. Remplacez YOUR_TARGET_PROJECT_NAME par le nom de votre projet Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
La configuration de pod ci-dessus contient à la fois les versions de débogage et de publication du SDK. Choisissez celle qui convient le mieux à votre projet.

1. Installez le pod en exécutant la commande suivante : `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Option 2 : utiliser le lien de téléchargement

1. Téléchargez le [SDK iOS des informations d’engagement](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) et placez le fichier `EIObjC.xcframework` dans le dossier `Frameworks`.

1. Si un dossier `Frameworks` n’existe pas, créez-en un dans le dossier du projet.

## <a name="enable-auto-instrumentation"></a>Activer l’auto-instrumentation
 
Vous pouvez facilement activer l’auto-instrumentation sans codage. Lorsque le projet s’exécute, il suivra automatiquement les événements `view` et `action` en utilisant la clé d’ingestion configurée. 

1. Mettez à jour et incluez le fichier `EIConfig.plist` fourni dans le dossier du répertoire de votre projet pour les champs suivants :
    - Clé d’ingestion = `"Your-Ingestion-Key"`
    - autocollectView = OUI
    - autocollectAction = OUI

2. Ajoutez ensuite le fichier `EIConfig.plist` à votre projet dans Xcode. 



Pour désactiver l’auto-instrumentation, mettez à jour les champs suivants dans le fichier `EIConfig.plist` fourni dans le dossier du répertoire de votre projet. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implémenter des événements personnalisés

1. Ouvrez votre projet dans Xcode et accédez aux paramètres **Généraux**. 
1. Ajoutez le fichier `EIObjC.xcframework` au projet dans la section « Infrastructures, bibliothèques et contenu incorporé ».

1. Importez le fichier d’en-tête du framework dans AppDelegate.m avec l’extrait de code suivant :

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initialisez le SDK des informations d’engagement à partir de l’application : didFinishLaunchingWithOptions.
1. Copiez l’extrait de code XML à partir du **Guide d’installation**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Suivez un événement :

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Définir les détails de l’utilisateur pour votre événement

Le SDK vous permet de définir les informations utilisateur qui peuvent être envoyées avec chaque événement. Vous pouvez spécifier les informations de l’utilisateur en appelant l’API `setUser:(nonnull EIUser *)user` dans le SDK.

Si vous spécifiez les détails de l’utilisateur au niveau de `Analytics`, cela signifie que toutes les télémétries contiendront ces informations. Cependant, si vous les spécifiez au niveau de l’événement en appelant l’API `setUser:(nonnull EIUser *)user` sur l’objet EIEvent, seul cet événement spécifique contiendra les informations.

La classe de données `EIUser` contient les propriétés NSString suivantes :

- **localId** : L'ID local de l'utilisateur.
- **authId** : L'ID utilisateur authentifié.
- **authType** : Le type d'authentification utilisé pour obtenir l'ID utilisateur authentifié.
- **name** : Le nom de l’utilisateur.
- **email** : L'adresse e-mail de l’utilisateur.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
