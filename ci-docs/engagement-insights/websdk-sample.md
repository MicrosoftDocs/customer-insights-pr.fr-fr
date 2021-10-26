---
title: Exécuter un exemple de SDK Web
description: Apprenez à personnaliser et à exécuter un exemple de SDK Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606297"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Exécutez l'exemple de SDK Web pour la fonction Informations sur l’engagement Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La bibliothèque de SDK Web de la fonction Informations sur l’engagement est une bibliothèque JavaScript avec un exemple de code que vous pouvez utiliser sur votre site Web.

## <a name="prerequisites"></a>Conditions préalables

- Installez [Visual Studio Code](https://code.visualstudio.com/).
- [Installez l'extension Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dans Visual Studio Code et familiarisez-vous avec l'exécution de Live Server.
- Vous devez avoir un [espace de travail des informations sur l’engagement](create-workspace.md).

## <a name="run-sample"></a>Exécuter un échantillon

1. [Télécharger l’exemple de SDK Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Décompressez le fichier compressé `ei_websdk_sample.zip`.

1. Ouvrez le dossier décompressé dans Visual Studio Code.

1. Accédez au portail d’informations sur l’engagement pour votre espace de travail. Sélectionnez **Administrateur** > **Espace de travail**, puis **Guide d’installation**. Suivez la première option et sélectionnez **Copier le code** pour copier l’extrait de code JavaScript.

1. Dans le fichier `ei_websdk_sample.html`, collez l’extrait de code que vous venez de copier sous cette ligne :

   - <-- COLLEZ L’EXTRAIT DE CODE JAVASCRIPT DU PORTAIL DES INFORMATIONS SUR L’ENGAGEMENT ICI SOUS CETTE LIGNE -->

1. Ouvrez le fichier `ei_websdk_sample.html` utilisant Live Server dans Visual Studio Code en sélectionnant **Mise en service** à partir de la barre d'état.

1. À l'ouverture de la page, un événement de visualisation doit être automatiquement envoyé. Le fait de cliquer sur l'un des boutons de la page enverra des événements d'action. Le bouton **Suivre les événements** enverra également des événements personnalisés. Le fait de cliquer sur le bouton **Aller sur Bing** enverra un événement d'action avant de naviguer sur le site Web de Bing.

1. Regardez les événements qui se déroulent lorsque vous accédez à votre espace de travail. Cet espace de travail est associé à la clé d'ingestion saisie à l'étape 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
