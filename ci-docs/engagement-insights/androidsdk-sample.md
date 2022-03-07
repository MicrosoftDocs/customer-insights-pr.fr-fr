---
title: Exemple de SDK Android
description: Exemple de projet pour en savoir plus sur le SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: d3890a3719efcacfee649a250498e1d30306f1ba
ms.sourcegitcommit: 52f587ab6cdd30bdddd02290f9adab9373c1bcea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6296909"
---
# <a name="run-the-android-sdk-sample"></a>Exécuter l’exemple de SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cet exemple de projet Android vous aide à comprendre comment le SDK fonctionne dans une application. Il n’est pas nécessaire d’écrire du code. Ajoutez simplement votre clé d’ingestion pour voir immédiatement les événements dans votre espace de travail.

## <a name="prerequisites"></a>Conditions préalables

- [Android Studio](https://developer.android.com/studio)
- [Clé d’ingestion](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Télécharger l’exemple de SDK Android

1. [Téléchargez l’exemple du SDK Android des informations d’engagement](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Décompressez le fichier compressé `ei-android-sample.zip`.
1. Ouvrez le dossier décompressé dans Android Studio.
1. Dans le fichier `AndroidManifest.xml`, remplacez la chaîne `"Your-Ingestion-Key"` par la clé d’ingestion de votre espace de travail des informations d’engagement sous **Administrateur** > **Espace de travail** > **Guide d’installation**. 

   > [!NOTE]
   > Il n’est pas nécessaire de remplacer la section `${applicationId}`. Elle est automatiquement renseignée.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Sélectionnez **Exécuter** pour démarrer l’exemple de projet.
1. Affichez les événements dans votre espace de travail.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
