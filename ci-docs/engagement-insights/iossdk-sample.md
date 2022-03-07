---
title: Exécuter l’exemple de SDK iOS
description: Exemple de projet pour en savoir plus sur le SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 38f0c13b3a61f1edb0f2ac462d42c1db67b313cf
ms.sourcegitcommit: 52f587ab6cdd30bdddd02290f9adab9373c1bcea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6296907"
---
# <a name="run-the-ios-sdk-sample"></a>Exécuter l’exemple de SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cet exemple de projet iOS vous aide à comprendre comment le SDK fonctionne dans une application. Il n’est pas nécessaire d’écrire du code. Ajoutez simplement votre clé d’ingestion pour voir immédiatement les événements dans votre espace de travail.

## <a name="prerequisites"></a>Conditions préalables

- [Xcode version 9+](https://developer.apple.com/xcode/downloads/)
- [Clé d’ingestion](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Télécharger l’exemple de SDK iOS

1. [Téléchargez l’exemple de SDK iOS d’analyse de l’engagement](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Décompressez le fichier compressé `ei-ios-sample.zip`.
1. Ouvrez l’exemple de projet d’application dans Xcode.
1. Dans le fichier `EIConfig.plist`, remplacez la chaîne `“YOUR-INGESTION-KEY”` dans le champ `ingestionKey` par la clé d’ingestion de votre espace de travail provenant de l’analyse de l’engagement sous **Administrateur** > **Espace de travail** > **Guide d’installation**.
1. Sélectionnez **Exécuter** pour démarrer l’exemple de projet.
1. Affichez les événements dans votre espace de travail.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
