---
title: Ingérer des données via un connecteur Power Query
description: Connecteurs pour sources de données basées sur Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305888"
---
# <a name="connect-to-a-power-query-data-source"></a>Connexion à une source de données Power Query

Power Query propose un large éventail de connecteurs pour ingérer des données. La plupart de ces connecteurs sont pris en charge par Dynamics 365 Customer Insights. L’ajout de sources de données basées sur des connecteurs Power Query suit généralement la procédure décrite dans la section suivante. Cependant, selon le connecteur que vous utilisez, des informations différentes sont requises. Pour plus d’informations, consultez la documentation sur les connecteurs individuels dans la [Référence des connecteurs Power Query](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Créer une source de données

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Choisissez la méthode **Importer des données** et sélectionnez **Suivant**.

1. Indiquez un **Nom** pour la source de données, et sélectionnez **Suivant** pour créer la source de données. Instructions relatives au nom : 
   - Commencez par une lettre.
   - Utilisez uniquement des lettres et des chiffres. Les espaces et caractères spéciaux ne sont pas autorisés.
   - Utilisez entre 3 et 64 caractères.

1. Choisissez l’un des [connecteurs disponibles](#available-power-query-data-sources). Pour cet exemple, nous sélectionnons le connecteur **Texte/CSV**.

1. Entrez les détails requis dans les **Paramètres de connexion** pour le connecteur sélectionné et sélectionnez **Suivant** pour voir un aperçu des données.

1. Sélectionnez **Transformer les données**. Dans la cette étape, vous allez ajouter des entités à votre source de données. Les entités sont des jeux de données. Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.

1. La boîte de dialogue **Power Query - Modifier les requêtes** vous permet d’examiner et d’affiner les données. Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s’affiche dans le volet de gauche.

   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue Modifier les requêtes](media/data-manager-configure-edit-queries.png "Boîte de dialogue Modifier les requêtes")

1. Vous pouvez également transformer vos données. Sélectionnez une entité à modifier ou transformer. Utilisez les options de la fenêtre Power Query pour appliquer les transformations. Chaque transformation est répertoriée sous **Étapes appliquées**. Power Query fournit de nombreuses options de transformation prédéfinies. Pour plus d’informations, consultez [Transformations Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Vous pouvez ajouter des entités supplémentaires à votre source de données en sélectionnant **Obtenir des données** dans la boîte de dialogue **Modifier les requêtes**.

   Ces transformations sont vivement recommandées :

   - Si vous ingérez des données à partir d’un fichier CSV, la première ligne contient souvent des en-têtes. Accédez à **Transformer la table**, puis sélectionnez **Utiliser les en-têtes comme première ligne**.
   - Assurez-vous que le type de données est défini de manière appropriée.

1. Sélectionnez **Enregistrer** au bas de la fenêtre Power Query pour enregistrer les transformations. Après l’enregistrement, vous trouverez votre source de données sur **Données** > **Sources de données**.

1. Dans la page **Sources de données**, vous remarquerez que la nouvelle source de données a le statut **Actualisation en cours**.

## <a name="available-power-query-data-sources"></a>Sources de données Power Query disponibles

Consultez la [Référence des connecteurs Power Query](/power-query/connectors/) pour voir la liste à jour des connecteurs que vous pouvez sélectionner pour importer des données dans Customer Insights. 

Les connecteurs portant une coche dans la colonne **Customer Insights (Dataflows)** sont disponibles pour créer de nouvelles sources de données basées sur Power Query. Consultez la documentation d’un connecteur spécifique pour en savoir plus sur ses prérequis, ses limitations et autres détails.

## <a name="edit-power-query-data-sources"></a>Modifier les sources de données Power Query

> [!NOTE]
> Remarque : il se peut qu’apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l’application (*segmentation*, *mise en correspondance*, *fusion*, etc.) ne soit pas possible. 
>
> Avec la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs. Lorsqu’un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez modifier et sélectionnez **Modifier** dans le menu déroulant.

   > [!div class="mx-imgBorder"]
   > ![Option Modifier](media/edit-option-data-sources.png "Option Modifier")

3. Appliquez vos modifications et transformations dans la boîte de dialogue **Power Query - Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).

4. Sélectionnez **Enregistrer** dans Power Query après avoir terminé vos modifications pour enregistrer vos modifications.


[!INCLUDE[footer-include](../includes/footer-banner.md)]