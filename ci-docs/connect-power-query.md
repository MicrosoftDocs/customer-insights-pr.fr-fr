---
title: Se connecter à une source de données Power Query (contient une vidéo)
description: Ingérer des données via un connecteur Power Query (contient une vidéo).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609887"
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

1. Sélectionnez **Transformer les données**.

1. Examinez et affinez vos données dans la page **Power Query - Modifier les requêtes**. Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s’affiche dans le volet de gauche.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Boîte de dialogue Modifier les requêtes":::

1. Transformez vos données. Sélectionnez une entité à modifier ou transformer. Utilisez les options de la fenêtre Power Query pour appliquer les transformations. Chaque transformation est répertoriée sous **Étapes appliquées**. Power Query fournit de nombreuses options de [transformation prédéfinie](/power-query/power-query-what-is-power-query#transformations).

   > [!IMPORTANT]
   > Nous vous recommandons d’utiliser les transformations suivantes :
   >
   > - Si vous ingérez des données à partir d’un fichier CSV, la première ligne contient souvent des en-têtes. Accédez à **Transformer**, puis sélectionnez **Utiliser la première ligne pour les en-têtes**.
   > - Assurez-vous que le type de données est correctement défini et correspond aux données. Par exemple, pour les champs de date, sélectionnez un type de date.

1. Pour ajouter des entités supplémentaires à votre source de données dans la boîte de dialogue **Modifier les requêtes**, accédez à **Accueil** et sélectionnez **Obtenir des données**. Répétez les étapes 5 à 10 jusqu'à ce que vous ayez ajouté toutes les entités pour ce source de données. Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.

1. Cliquez sur **Enregistrer**. La page **Source de données** s'ouvre et affiche la nouvelle source de données avec le statut **Actualisation en cours**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page [**Entités**](entities.md).

> [!CAUTION]
>
> - Une source de données basée sur Power Query crée un [flux de données dans Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ne modifiez pas le nom d’un flux de données dans le Centre d’administration de Power Platform utilisé dans Customer Insights. Renommer un flux de données entraîne des problèmes avec les références entre la source de données Customer Insights et le flux de données Dataverse.
> - Les évaluations simultanées pour les sources de données Power Query dans Customer Insights ont les mêmes [limites d’actualisation que les flux de données dans PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Si une actualisation des données échoue parce qu’elle a atteint la limite d’évaluation, nous vous recommandons d’ajuster la planification d’actualisation pour chaque flux de données afin de vous assurer que les sources de données ne sont pas traitées en même temps.

### <a name="available-power-query-data-sources"></a>Sources de données Power Query disponibles

Consultez la [Référence des connecteurs Power Query](/power-query/connectors/) pour obtenir une liste de connecteurs que vous pouvez utiliser pour importer des données dans Customer Insights.

Les connecteurs avec une coche dans la colonne **Customer Insights (dataflows)** sont disponibles pour créer des sources de données basées sur Power Query. Consultez la documentation d'un connecteur spécifique pour en savoir plus sur ses prérequis, [limites des requêtes](/power-query/power-query-online-limits) et d'autres détails.

## <a name="add-data-from-on-premises-data-sources"></a>Ajouter des données de sources de données locales

L’ingestion de données à partir de sources de données locales est prise en charge en fonction des flux de données Microsoft Power Platform (PPDF). Vous pouvez activer les flux de données dans Customer Insights en [fournissant l’URL de l’environnement Microsoft Dataverse](create-environment.md) lors de la configuration de l’environnement.

Les sources de données créées après avoir associé un environnement Dataverse à Customer Insights utilisent les [flux de données Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) par défaut. Les flux de données prennent en charge la connectivité locale à l’aide de la passerelle de données. Vous pouvez supprimer et recréer des sources de données qui existaient avant l’association d’un environnement Dataverse [en utilisant les passerelles de données locales](/data-integration/gateway/service-gateway-app).

Les passerelles de données à partir d’un environnement Power BI ou Power Apps seront visibles et vous pourrez les réutiliser dans Customer Insights si la passerelle de données et l’environnement Customer Insights se trouvent dans la même région Azure. La page des sources de données affiche des liens pour accéder à l’environnement Microsoft Power Platform dans lequel vous pouvez afficher et configurer les passerelles de données locales.

> [!IMPORTANT]
> Assurez-vous que vos passerelles sont mises à jour vers la version la plus récente. Vous pouvez installer une mise à jour et reconfigurer une passerelle à partir d’une invite affichée sur l’écran de la passerelle directement ou [télécharger la version la plus récente](https://powerapps.microsoft.com/downloads/). Si vous n’utilisez pas la version la plus récente de la passerelle, l’actualisation du flux de données échoue avec des messages d’erreur comme **Le mot clé n’est pas pris en charge : propriétés de configuration. Nom du paramètre : mot clé**.
>
> Les erreurs avec les passerelles de données sur site dans Customer Insights sont souvent dues à des problèmes de configuration. Pour plus d’informations sur la résolution des problèmes liés aux passerelles de données, consultez [Résoudre les problèmes de passerelle de données locale](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Modifier les sources de données Power Query

> [!NOTE]
> Remarque : il se peut qu’apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l’application (segmentation ou unification des données par exemple) ne soit pas possible.
>
> Dans la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs. Lorsqu’un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.

1. Accédez à **Données** > **Sources de données**.

1. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez **Modifier**.

1. Appliquez vos changements et transformations dans la boîte de dialogue **Power Query – Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).

1. Sélectionnez **Enregistrer** pour appliquer vos modifications et revenir à la page **Sources de données**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Raisons courantes aux erreurs d’ingestion ou aux données endommagées

### <a name="data-type-does-not-match-data"></a>Le type de données ne correspond pas aux données

L’incompatibilité de type de données la plus courante se produit lorsqu’un champ de date n’est pas défini sur le format de date correct.

Les données peuvent être corrigées à la source et réingérées. Ou bien, corrigez la transformation dans Customer Insights. Pour corriger la transformation :

1. Accédez à **Données** > **Sources de données**.

1. En regard de la source de données avec les données endommagées, sélectionnez **Modifier**.

1. Cliquez sur **Suivant**.

1. Sélectionnez chacune des requêtes et recherchez les transformations appliquées dans « Étapes appliquées » qui sont incorrectes, ou les colonnes de date qui n’ont pas été transformées avec un format de date.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query - Modification montrant un format de date incorrect":::

1. Modifiez le type de données pour qu’il corresponde correctement aux données.

1. Cliquez sur **Enregistrer**. Cette source de données est actualisée.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Résoudre les problèmes d’actualisation de la source de données PPDF basée sur Power Query

Si les données sont obsolètes ou si vous recevez des erreurs après une actualisation de la source de données, procédez comme suit :

1. Accédez à [Power Platform](https://make.powerapps.com).

1. Sélectionnez l’**Environnement** de votre instance Customer Insights.

1. Accédez à **Flux de données**.

1. Pour le flux de données correspondant à la source de données dans Customer Insights, sélectionnez les points de suspension verticaux (&vellip;), puis sélectionnez **Afficher l’historique d’actualisation**.

1. Si le **Statut** du flux de données est **Succès**, la propriété de la source de données basée sur Power Query a peut-être été modifiée :

   1. Examinez la planification de l’actualisation dans l’historique d’actualisation.
   1. Définissez la planification du nouveau propriétaire et enregistrez les paramètres.

1. Si le **Statut** du flux de données est **Échec** :

   1. Téléchargez le fichier de l’historique d’actualisation.
   1. Examinez le fichier téléchargé pour connaître la raison de l’échec.
   1. Si l’erreur ne peut pas être résolue, sélectionnez **?** pour ouvrir un ticket de support. Incluez le fichier de l’historique d’actualisation téléchargé.


[!INCLUDE [footer-include](includes/footer-banner.md)]
