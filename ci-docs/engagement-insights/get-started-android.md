---
title: Mise en route du SDK Android
description: Apprenez à personnaliser et à exécuter le SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036915"
---
# <a name="get-started-with-the-android-sdk"></a>Mise en route du SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ce tutoriel vous guide dans le processus d’instrumentation de votre application Android avec le SDK des informations d’engagement de Dynamics 365 Customer Insights. Vous commencerez à voir les événements dans votre portail dans cinq minutes ou avant.

## <a name="configuration-options"></a>Options de configuration
Les options de configuration suivantes peuvent être transmises au SDK :

- **ingestionKey** : la clé d’ingestion est utilisée pour envoyer des événements vers votre espace de travail.

## <a name="prerequisites"></a>Conditions préalables

- Android Studio

- Niveau minimal de l’API Android : 16 (Jelly Bean)

- Une clé d’ingestion (voir ci-dessous les instructions pour savoir comment l’obtenir)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Étape 1. Intégrer le SDK dans votre application
Commencez le processus en sélectionnant un espace de travail, en sélectionnant la plateforme mobile Android et en téléchargeant le SDK Android.

- Utilisez le sélecteur d’espaces de travail dans le volet de navigation de gauche pour sélectionner votre espace de travail.

- Si vous n’avez pas d’espace de travail existant, sélectionnez **Nouvel espace de travail** et suivez les étapes pour créer un [nouvel espace de travail](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Étape 2. Configurer le SDK

1. Une fois que vous avez créé un espace de travail, accédez à **Administrateur** > **Espace de travail**, puis sélectionnez **Guide d’installation**. 

1. Téléchargez le [SDK Android des informations d’engagement](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) et placez le fichier `eiandroidsdk-debug.aar` dans le dossier `libs`.

1. Ouvrez le fichier `build.gradle` au niveau de votre projet et ajoutez les extraits de code suivants :
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Paramétrez la configuration du SDK des informations d’engagement via votre fichier `AndroidManifest.xml` situé dans le dossier `manifests`. 
1. Copiez l’extrait de code XML à partir du **Guide d’installation**. `Your-Ingestion-Key` devrait être automatiquement renseigné.

   > [!NOTE]
   > Il n’est pas nécessaire de remplacer la section `${applicationId}`. Elle est automatiquement renseignée.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Activez ou désactivez la capture automatique des événements `View` en définissant le champ `autoCapture` ci-dessus sur `true` ou `false`.

1. (Facultatif) D’autres configurations comprennent la définition de l’URL du collecteur du point de terminaison. Elles peuvent être ajoutées dans les métadonnées de la clé d’ingestion dans `AndroidManifest.xml` :
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Étape 3. Initialiser le SDK à partir de MainActivity 

Une fois que vous avez initialisé le SDK, vous pouvez utiliser les événements et leurs propriétés dans l’environnement MainActivity.

    
Java :
```java
Analytics analytics = new Analytics();
```

Kotlin :
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Définir la propriété pour tous les événements (facultatif)
    
Java :
```java
analytics.setProperty("year", 2021);
```

Kotlin :
```kotlin
analytics.setProperty("year", 2021)
```

Les types suivants sont pris en charge pour les propriétés de l’événement de contexte :
- String
- Date
- Double
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Suivre un événement

Java :
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin :
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Définir les détails de l’utilisateur pour votre événement (facultatif)

Le SDK vous permet de définir les informations utilisateur qui peuvent être envoyées avec chaque événement. Vous pouvez spécifier les informations de l’utilisateur en appelant l’API `setUser(user: User)` au niveau de `Analytics`.

Java :
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin :
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

La classe de données `User` contient les propriétés de chaîne suivantes :

- **localId** : L'ID local de l'utilisateur.
- **authId** : L'ID utilisateur authentifié.
- **authType** : type d’authentification utilisé pour obtenir l’ID utilisateur authentifié.
- **name** : Le nom de l’utilisateur.
- **email** : L'adresse e-mail de l’utilisateur.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
