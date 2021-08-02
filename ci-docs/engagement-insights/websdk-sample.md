---
title: Exécuter un exemple de SDK Web
description: Apprenez à personnaliser et à exécuter un exemple de SDK Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: d51d06812e071852451e0c6c83648e59a4dad803
ms.sourcegitcommit: 302910e39153f4b5c850ed9b1a62cb867e4df358
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6218530"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Exécutez l'exemple de SDK Web pour la fonction Informations sur l’engagement Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La bibliothèque de SDK Web de la fonction Informations sur l’engagement est une bibliothèque JavaScript avec un exemple de code que vous pouvez utiliser sur votre site Web.

## <a name="prerequisites"></a>Conditions préalables

- Installez [Visual Studio Code](https://code.visualstudio.com/).
- [Installez l'extension Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dans Visual Studio Code et familiarisez-vous avec l'exécution de Live Server.
- Vous devez disposer de la [clé d'ingestion](instrument-website.md).

## <a name="run-sample"></a>Exécuter un échantillon

1. [Télécharger l’exemple de SDK Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Décompressez le fichier compressé `ei_websdk_sample.zip`.

1. Ouvrez le dossier décompressé dans Visual Studio Code.

1. Dans le fichier `ei_websdk_sample.html`, remplacez la chaîne « INGESTION_KEY » par votre clé d'ingestion du portail de la fonction Informations sur l’engagement et la chaîne « NOM » par le nom global dans lequel vous souhaitez que le SDK soit instancié. Assurez-vous de remplacer toutes les occurrences.

1. Ouvrez le fichier `ei_websdk_sample.html` utilisant Live Server dans Visual Studio Code en sélectionnant **Mise en service** à partir de la barre d'état.

1. À l'ouverture de la page, un événement de visualisation doit être automatiquement envoyé. Le fait de cliquer sur l'un des boutons de la page enverra des événements d'action. Le bouton **Suivre les événements** enverra également des événements personnalisés. Le fait de cliquer sur le bouton **Aller sur Bing** enverra un événement d'action avant de naviguer sur le site Web de Bing.

1. Regardez les événements qui se déroulent lorsque vous accédez à votre espace de travail. Cet espace de travail est associé à la clé d'ingestion saisie à l'étape 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]