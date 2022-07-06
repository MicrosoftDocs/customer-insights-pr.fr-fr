---
title: Se connecter à une source de données Power Query (contient une vidéo)
description: Ingérer des données via un connecteur Power Query (contient une vidéo).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080993"
---
# <a name="connect-to-a-power-query-data-source"></a>Se connecter à une source de données Power Query

Power Query offre un large éventail de connecteurs pour ingérer des données. La plupart de ces connecteurs sont pris en charge par Dynamics 365 Customer Insights.

L’ajout de sources de données basées sur les connecteurs Power Query suit généralement les étapes décrites dans cette section. Cependant, selon le connecteur que vous utilisez, des informations différentes sont requises. Pour en savoir plus, consultez la documentation sur les connecteurs individuels dans la [Référence des connecteurs Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Créer une source de données

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Sélectionnez **Microsoft Power Query**.

1. Fournissez un **Nom** et une **description** facultative pour la source de données, puis sélectionnez **Suivant**.

1. Choisissez l’un des [connecteurs disponibles](#available-power-query-data-sources). Dans cet exemple, nous sélectionnons le connecteur **Texte/CSV**.

1. Entrez les détails requis dans les **Paramètres de connexion** pour le connecteur sélectionné et sélectionnez **Suivant** pour voir un aperçu des données.

1. Sélectionnez **Transformer les données**. Dans la cette étape, vous allez ajouter des entités à votre source de données. Les entités sont des jeux de données. Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.

1. La boîte de dialogue **Power Query – Modifier les requêtes** vous permet de revoir et d'affiner les données. Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s’affiche dans le volet de gauche.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Boîte de dialogue Modifier les requêtes":::

1. Vous pouvez également transformer vos données. Sélectionnez une entité à modifier ou transformer. Utilisez les options de la fenêtre Power Query pour appliquer les transformations. Chaque transformation est répertoriée sous **Étapes appliquées**. Power Query fournit de nombreuses options de transformation prédéfinies. Pour plus d’informations, voir l’aide de [Transformations Power Query](/power-query/power-query-what-is-power-query#transformations).

   Nous vous recommandons d’utiliser les transformations suivantes :

   - Si vous ingérez des données à partir d’un fichier CSV, la première ligne contient souvent des en-têtes. Accédez à **Transformer**, puis sélectionnez **Utiliser la première ligne pour les en-têtes**.
   - Assurez-vous que le type de données est défini de manière appropriée. Par exemple, pour les champs de date, sélectionnez un type de date.

1. Pour ajouter des entités supplémentaires à votre source de données dans la boîte de dialogue **Modifier les requêtes**, accédez à **Accueil** et sélectionnez **Obtenir des données**. Répétez les étapes 6 à 10 jusqu'à ce que vous ayez ajouté toutes les entités pour ce source de données.

1. Cliquez sur **Enregistrer**. La page **Source de données** s'ouvre et affiche la nouvelle source de données avec le statut **Actualisation en cours**.

### <a name="available-power-query-data-sources"></a>Sources de données Power Query disponibles

Consultez la [Référence des connecteurs Power Query](/power-query/connectors/) pour obtenir une liste de connecteurs que vous pouvez utiliser pour importer des données dans Customer Insights.

Les connecteurs avec une coche dans la colonne **Customer Insights (dataflows)** sont disponibles pour créer des sources de données basées sur Power Query. Consultez la documentation d'un connecteur spécifique pour en savoir plus sur ses prérequis, [limites des requêtes](/power-query/power-query-online-limits) et d'autres détails.

## <a name="add-data-from-on-premises-data-sources"></a>Ajouter des données de sources de données locales

L’ingestion de données à partir de sources de données locales est prise en charge en fonction des flux de données Microsoft Power Platform (PPDF). Vous pouvez activer les flux de données dans Customer Insights en [fournissant l’URL de l’environnement Microsoft Dataverse](create-environment.md) lors de la configuration de l’environnement.

Les sources de données créées après avoir associé un environnement Dataverse à Customer Insights utilisent les [flux de données Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) par défaut. Les flux de données prennent en charge la connectivité locale à l’aide de la passerelle de données. Vous pouvez supprimer et recréer des sources de données qui existaient avant l’association d’un environnement Dataverse [en utilisant les passerelles de données locales](/data-integration/gateway/service-gateway-app).

Les passerelles de données d’un environnement Power BI ou Power Apps existant seront visibles et vous pourrez les réutiliser dans Customer Insights. La page des sources de données affiche des liens pour accéder à l’environnement Microsoft Power Platform dans lequel vous pouvez afficher et configurer les passerelles de données locales.

> [!IMPORTANT]
> Assurez-vous que vos passerelles sont mises à jour vers la version la plus récente. Vous pouvez installer une mise à jour et reconfigurer une passerelle à partir d’une invite affichée sur l’écran de la passerelle directement ou [télécharger la version la plus récente](https://powerapps.microsoft.com/downloads/). Si vous n’utilisez pas la version la plus récente de la passerelle, l’actualisation du flux de données échoue avec des messages d’erreur comme **Le mot clé n’est pas pris en charge : propriétés de configuration. Nom du paramètre : mot clé**.

## <a name="edit-power-query-data-sources"></a>Modifier les sources de données Power Query

> [!NOTE]
> Remarque : il se peut qu’apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l’application (*segmentation*, *mise en correspondance*, *fusion*, etc.) ne soit pas possible.
>
> Dans la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs. Lorsqu’un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.

1. Accédez à **Données** > **Sources de données**.

1. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez **Modifier**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Appliquez vos changements et transformations dans la boîte de dialogue **Power Query – Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).

1. Sélectionnez **Enregistrer** dans Power Query après avoir terminé vos modifications pour enregistrer vos modifications.
