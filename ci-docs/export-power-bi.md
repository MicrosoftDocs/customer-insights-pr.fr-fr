---
title: Connecteur Power BI (préversion)
description: Découvrez comment utiliser le connecteur Dynamics 365 Customer Insights dans Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196667"
---
# <a name="power-bi-connector-preview"></a>Connecteur Power BI (préversion)

Créez des visualisations pour vos données avec Microsoft Power BI Desktop. Générez des informations supplémentaires et créez des rapports avec vos données client unifiées.

## <a name="prerequisites"></a>Conditions préalables

- Profils clients unifiés.
- La dernière version de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) est installée sur votre ordinateur. [En savoir plus sur Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurer le connecteur pour Power BI

1. Dans Power BI Desktop, sélectionnez **Fichier** > **Obtenir les données**.

1. Sélectionnez **Afficher plus** et recherchez **Dynamics 365 Customer Insights**

1. Cliquez sur **Se connecter**.

1. **Connectez-vous** à l’aide du compte d’organisation que vous utilisez pour Customer Insights et sélectionnez **Se connecter**.
   > [!NOTE]
   > Le compte que vous indiquez à cette étape est utilisé pour récupérer les données de Customer Insights et n’a pas besoin d’être le même que celui avec lequel vous êtes connecté à Power BI. Pour réinitialiser le compte utilisé pour la récupération de données, ouvrez Power BI et accédez à **Fichier** > **Options** > **Paramètres** > **Paramètres de la source de données**. Dans la liste des sources de données, sélectionnez **Connexion à Dynamics 365 Customer Insights** et sélectionnez **Effacer les autorisations**.  

1. Dans la boîte de dialogue **Navigateur**, affichez la liste de tous les environnements auxquels vous avez accès. Développez un environnement et ouvrez l’un des dossiers (entités, mesures, segments, enrichissements). Par exemple, ouvrez le dossier **Entités**, pour voir toutes les entités que vous pouvez importer.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Connecteur Power BI-Navigateur.":::

1. Activez les cases à cocher en regard des entités à inclure et **Charger**. Vous pouvez sélectionner plusieurs entités depuis plusieurs environnements.

   La boîte de dialogue de chargement s’affiche pendant le chargement de vos entités. Une fois que toutes les entités sélectionnées sont chargées, utilisez les fonctionnalités de Power BI pour visualiser les données.

## <a name="large-data-sets"></a>Jeux de données volumineux

Le connecteur Customer Insights pour Power BI est conçu pour fonctionner avec des jeux de données contenant jusqu’à 1 million de profils client. L’importation d’ensembles de données plus volumineux peut fonctionner, mais prend beaucoup de temps et peut expirer en raison de limites de Power BI. Pour plus d’informations, voir [Power BI : Recommandations concernant les jeux de données volumineux](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Utiliser un sous-ensemble de données

Envisagez d’utiliser un sous-ensemble de vos données. Par exemple, créez des [segments](segments.md) au lieu d’exporter tous les enregistrements clients vers Power BI.

## <a name="troubleshooting"></a>Dépannage

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L’environnement Customer Insights ne s’affiche pas dans Power BI

Les environnements qui ont plusieurs [relations](relationships.md) définies entre deux entités identiques dans Customer Insights ne seront pas disponibles dans le connecteur Power BI.

Identifier et supprimer les relations en double.

1. Accédez à **Données** > **Relations** dans l’environnement manquant dans Power BI.
1. Identifiez les relations dupliqués :
   - Vérifiez si plusieurs relations sont définies entre les deux mêmes entités.
   - Vérifiez s’il existe une relation créée entre deux entités qui sont toutes deux incluses dans le processus d’unification. Il existe une relation implicite définie entre toutes les entités incluses dans le processus d’unification.
1. Supprimez toutes les relations en double identifiées.

Après avoir supprimé les relations dupliquées, essayez de reconfigurer le connecteur Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erreurs sur les champs de date lors du chargement des entités dans Power BI Desktop

Lors du chargement d’entités contenant des champs avec un format de date tel que MM/JJ/AAAA, vous pouvez rencontrer des erreurs dues à des formats de paramètres régionaux incompatibles. Cette incompatibilité se produit lorsque votre fichier Power BI Desktop est défini sur d’autres paramètres régionaux que l’anglais (États-Unis), car les champs de date dans Customer Insights sont enregistrés au format US.

Le fichier Power BI Desktop a un seul paramètre régional, qui est appliqué lors de la récupération des données. Pour résoudre les erreurs de date, [définissez les paramètres régionaux du fichier .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) sur Anglais (États-Unis).

[!INCLUDE [footer-include](includes/footer-banner.md)]
