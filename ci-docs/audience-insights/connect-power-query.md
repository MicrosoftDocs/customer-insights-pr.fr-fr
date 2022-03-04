---
title: Ingérer des données via un connecteur Power Query (contient une vidéo)
description: Connecteurs pour les sources de données basées sur Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355518"
---
# <a name="connect-to-a-power-query-data-source"></a>Se connecter à une source de données Power Query

Power Query offre un large éventail de connecteurs pour ingérer des données. La plupart de ces connecteurs sont pris en charge par Dynamics 365 Customer Insights. 

L’ajout de sources de données basées sur les connecteurs Power Query suit généralement les étapes décrites dans cette section. Cependant, selon le connecteur que vous utilisez, des informations différentes sont requises. Pour en savoir plus, consultez la documentation sur les connecteurs individuels dans la [Référence des connecteurs Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Créer une source de données

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Sélectionnez **Microsoft Power Query**.

1. Indiquez un **Nom** pour la source de données, et sélectionnez **Suivant** pour créer la source de données.

1. Choisissez l’un des [connecteurs disponibles](#available-power-query-data-sources). Dans cet exemple, nous sélectionnons le connecteur **Texte/CSV**.

1. Entrez les détails requis dans les **Paramètres de connexion** pour le connecteur sélectionné et sélectionnez **Suivant** pour voir un aperçu des données.

1. Sélectionnez **Transformer les données**. Dans la cette étape, vous allez ajouter des entités à votre source de données. Les entités sont des jeux de données. Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.

1. La boîte de dialogue **Power Query – Modifier les requêtes** vous permet de revoir et d'affiner les données. Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s’affiche dans le volet de gauche.

   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue Modifier les requêtes.](media/data-manager-configure-edit-queries.png "Boîte de dialogue Modifier les requêtes")

1. Vous pouvez également transformer vos données. Sélectionnez une entité à modifier ou transformer. Utilisez les options de la fenêtre Power Query pour appliquer les transformations. Chaque transformation est répertoriée sous **Étapes appliquées**. Power Query fournit de nombreuses options de transformation prédéfinies. Pour plus d’informations, voir l’aide de [Transformations Power Query](/power-query/power-query-what-is-power-query#transformations).

   Nous vous recommandons d’utiliser les transformations suivantes :

   - Si vous ingérez des données à partir d’un fichier CSV, la première ligne contient souvent des en-têtes. Accédez à **Transformer**, puis sélectionnez **Utiliser la première ligne pour les en-têtes**.
   - Assurez-vous que le type de données est défini de manière appropriée. Par exemple, pour les champs de date, sélectionnez un type de date.

1. Pour ajouter des entités supplémentaires à votre source de données dans la boîte de dialogue **Modifier les requêtes**, accédez à **Accueil** et sélectionnez **Obtenir des données**.

1. Sélectionnez **Enregistrer** dans la partie inférieure de la fenêtre Power Query pour enregistrer vos transformations. Après l’enregistrement, vous trouverez votre source de données sur **Données** > **Sources de données**.

1. Dans la page **Sources de données**, vous remarquerez que la nouvelle source de données a le statut **Actualisation en cours**.

## <a name="available-power-query-data-sources"></a>Sources de données Power Query disponibles

Consultez la [Référence des connecteurs Power Query](/power-query/connectors/) pour obtenir une liste de connecteurs que vous pouvez utiliser pour importer des données dans Customer Insights. 

Les connecteurs avec une coche dans la colonne **Customer Insights (dataflows)** sont disponibles pour créer des sources de données basées sur Power Query. Consultez la documentation d’un connecteur spécifique pour en savoir plus sur ses prérequis, ses limitations et autres détails.

## <a name="edit-power-query-data-sources"></a>Modifier les sources de données Power Query

> [!NOTE]
> Remarque : il se peut qu’apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l’application (*segmentation*, *mise en correspondance*, *fusion*, etc.) ne soit pas possible. 
>
> Dans la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs. Lorsqu’un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez modifier et sélectionnez **Modifier** dans le menu déroulant.

   > [!div class="mx-imgBorder"]
   > ![Option Modifier.](media/edit-option-data-sources.png "Option Modifier")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Appliquez vos changements et transformations dans la boîte de dialogue **Power Query – Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).

4. Sélectionnez **Enregistrer** dans Power Query après avoir terminé vos modifications pour enregistrer vos modifications.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
