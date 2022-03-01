---
title: Connecteur Power BI
description: Découvrez comment utiliser le connecteur Dynamics 365 Customer Insights dans Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405641"
---
# <a name="connector-for-power-bi-preview"></a>Connecteur pour Power BI (préversion)

Créez des visualisations pour vos données avec Power BI Desktop. Générez des informations supplémentaires et créez des rapports avec vos données client unifiées.

## <a name="prerequisites"></a>Conditions préalables

- Vous disposez de profils clients unifiés.
- La dernière version de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) est installée sur votre ordinateur. [En savoir plus sur Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurer le connecteur pour Power BI

1. Dans Power BI Desktop, sélectionnez **Fichier** > **Obtenir les données**.

1. Sélectionnez **Afficher plus** et recherchez **Dynamics 365 Customer Insights**

1. Sélectionnez le résultat et sélectionnez **Se connecter**.

1. **Connectez-vous** à l’aide du compte d’organisation que vous utilisez pour Customer Insights et sélectionnez **Se connecter**.
   > [!NOTE]
   > Le compte que vous indiquez à cette étape est utilisé pour récupérer les données de Customer Insights et n'a pas besoin d'être le même que celui avec lequel vous êtes connecté à Power BI. Pour réinitialiser le compte utilisé pour la récupération de données, ouvrez Power BI et accédez à **Fichier** > **Options** > **Paramètres** > **Paramètres de la source de données**. Dans la liste des sources de données, sélectionnez **Connexion à Dynamics 365 Customer Insights** et sélectionnez **Effacer les autorisations**.  

1. La boîte de dialogue **Navigateur** affiche la liste de tous les environnements auxquels vous pouvez accéder. Développez un environnement et ouvrez l'un des dossiers (entités, mesures, segments, enrichissements). Par exemple, ouvrez le dossier **Entités**, pour voir toutes les entités que vous pouvez importer.

   ![Connecteur Power BI Navigateur](media/power-bi-navigator.png "Connecteur Power BI Navigateur")

1. Activez les cases à cocher en regard des entités à inclure et **Charger**. Vous pouvez sélectionner plusieurs entités depuis plusieurs environnements.

1. La boîte de dialogue de chargement s’affiche pendant le chargement de vos entités. Une fois que toutes les entités sélectionnées sont chargées, vous pouvez utiliser les fonctionnalités de Power BI pour visualiser les données.

## <a name="large-data-sets"></a>Jeux de données volumineux

Le connecteur Customer Insights pour Power BI est conçu pour fonctionner avec des jeux de données contenant jusqu’à 1 million de profils client. L’importation de jeux de données plus volumineux peut fonctionner, mais cela prend beaucoup de temps. De plus, le processus peut s’exécuter dans un délai d’attente en raison des limites de Power BI. Pour plus d’informations, voir [Power BI : Recommandations concernant les jeux de données volumineux](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Utiliser un sous-ensemble de données

Envisagez d'utiliser un sous-ensemble de vos données. Par exemple, vous pouvez créer des [segments](segments.md) au lieu d'exporter tous les enregistrements clients vers Power BI.
