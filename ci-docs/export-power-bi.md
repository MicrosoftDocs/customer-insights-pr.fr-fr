---
title: Connecteur Power BI
description: Découvrez comment utiliser le connecteur Dynamics 365 Customer Insights dans Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646316"
---
# <a name="connector-for-power-bi-preview"></a>Connecteur pour Power BI (préversion)

Créez des visualisations pour vos données avec Power BI Desktop. Générez des informations supplémentaires et créez des rapports avec vos données client unifiées.

## <a name="prerequisites"></a>Conditions préalables

- Vous disposez de profils clients unifiés.
- La dernière version de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) est installée sur votre ordinateur. [En savoir plus sur Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurer le connecteur pour Power BI

1. Dans Power BI Desktop, sélectionnez **Fichier** > **Obtenir les données**.

1. Sélectionnez **Afficher plus** et recherchez **Dynamics 365 Customer Insights**

1. Cliquez sur **Se connecter**.

1. **Connectez-vous** à l’aide du compte d’organisation que vous utilisez pour Customer Insights et sélectionnez **Se connecter**.
   > [!NOTE]
   > Le compte que vous indiquez à cette étape est utilisé pour récupérer les données de Customer Insights et n’a pas besoin d’être le même que celui avec lequel vous êtes connecté à Power BI. Pour réinitialiser le compte utilisé pour la récupération de données, ouvrez Power BI et accédez à **Fichier** > **Options** > **Paramètres** > **Paramètres de la source de données**. Dans la liste des sources de données, sélectionnez **Connexion à Dynamics 365 Customer Insights** et sélectionnez **Effacer les autorisations**.  

1. La boîte de dialogue **Navigateur** affiche la liste de tous les environnements auxquels vous pouvez accéder. Développez un environnement et ouvrez l’un des dossiers (entités, mesures, segments, enrichissements). Par exemple, ouvrez le dossier **Entités**, pour voir toutes les entités que vous pouvez importer.

   ![Connecteur Power BI-Navigateur.](media/power-bi-navigator.png "Connecteur Power BI Navigateur")

1. Activez les cases à cocher en regard des entités à inclure et **Charger**. Vous pouvez sélectionner plusieurs entités depuis plusieurs environnements.

1. La boîte de dialogue de chargement s’affiche pendant le chargement de vos entités. Une fois que toutes les entités sélectionnées sont chargées, vous pouvez utiliser les fonctionnalités de Power BI pour visualiser les données.

## <a name="large-data-sets"></a>Jeux de données volumineux

Le connecteur Customer Insights pour Power BI est conçu pour fonctionner avec des jeux de données contenant jusqu’à 1 million de profils client. L’importation de jeux de données plus volumineux peut fonctionner, mais cela prend beaucoup de temps. De plus, le processus peut s’exécuter dans un délai d’attente en raison des limites de Power BI. Pour plus d’informations, voir [Power BI : Recommandations concernant les jeux de données volumineux](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Utiliser un sous-ensemble de données

Envisagez d’utiliser un sous-ensemble de vos données. Par exemple, vous pouvez créer des [segments](segments.md) au lieu d’exporter tous les enregistrements clients vers Power BI.

## <a name="troubleshooting"></a>Dépannage

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L’environnement Customer Insights ne s’affiche pas dans Power BI

Les environnements qui ont plusieurs [relations](relationships.md) définies entre deux entités identiques dans Customer Insights ne seront pas disponibles dans le connecteur Power BI.

Vous pouvez identifier et supprimer les relations en double.

1. Accédez à **Données** > **Relations** dans l’environnement manquant dans Power BI.
2. Identifiez les relations dupliqués :
   - Vérifiez si plusieurs relations sont définies entre les deux mêmes entités.
   - Vérifiez s’il existe une relation créée entre deux entités qui sont toutes deux incluses dans le processus d’unification. Il existe une relation implicite définie entre toutes les entités incluses dans le processus d’unification.
3. Supprimez toutes les relations en double identifiées.

Après avoir supprimé les relations dupliquées, essayez de reconfigurer le connecteur Power BI. L’environnement devrait être disponible dès maintenant.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erreurs sur les champs de date lors du chargement des entités dans Power BI Desktop

Lors du chargement d’entités contenant des champs avec un format de date tel que MM/JJ/AAAA, vous pouvez rencontrer des erreurs dues à des formats de paramètres régionaux incompatibles. Cette incompatibilité se produit lorsque votre fichier Power BI Desktop est défini sur d’autres paramètres régionaux que l’anglais (États-Unis), car les champs de date dans Customer Insights sont enregistrés au format US.

Le fichier Power BI Desktop a un seul paramètre régional, qui est appliqué lors de la récupération des données. Pour faire en sorte que ces champs de date soient correctement interprétés, définissez les paramètres régionaux du fichier .BPI sur l’anglais (États-Unis). [Découvrir comment changer les paramètres régionaux d’un fichier Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
