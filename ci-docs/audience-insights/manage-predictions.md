---
title: Tâches partagées pour les scénarios prédiction
description: Apprenez à gérer, dépanner et affiner les prédictions.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095706"
---
# <a name="manage-predictions"></a>Gérer les prédictions

Cet article traite de certaines tâches partagées par la plupart des scénarios de prédiction.

## <a name="troubleshoot-a-failed-prediction"></a>Résoudre les problèmes liés à un échec de prédiction

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez les points de suspension verticaux en regard de la prédiction pour laquelle vous souhaitez afficher les journaux d’erreurs.

1. Sélectionnez **Journaux**.

1. Passez toutes les erreurs en revue. Plusieurs types d’erreurs peuvent survenir et décrivent la condition à l’origine de l’erreur. Par exemple, une erreur pour laquelle il n’y a pas suffisamment de données à prévoir avec précision est généralement résolue en chargeant des données supplémentaires dans Customer Insights.

## <a name="input-data-usability-report"></a>Rapport d’utilisation des données d’entrée

Le rapport d'utilisation des données d'entrée fournit une vue consolidée des erreurs et des avertissements que vos prédictions prêtes à l'emploi peuvent générer. Il donne également des recommandations sur la manière d'améliorer les performances du modèle.

Le rapport est disponible une fois qu'un modèle a terminé son processus d'entraînement. Il est créé pour chaque modèle séparément, qu'il soit terminé avec succès ou non.

> [!NOTE]
> Actuellement, cette fonctionnalité ne fonctionne que pour le modèle d’attrition des transactions.

### <a name="view-the-input-data-usability-report"></a>Afficher le rapport d’utilisation des données d’entrée

Une fois qu'un modèle prêt à l'emploi a terminé son étape d'entraînement, affichez le rapport :
- Sélectionnez les points de suspension à côté du nom du modèle et choisissez **Rapport d'utilisation des données d'entrée**.
- Sélectionnez le statut d'un modèle et sélectionnez **Voir le rapport d’utilisation des données d’entrée** dans le volet latéral.
- Sélectionnez l'un des modèles dans la liste et sélectionnez **Rapport d'utilisation des données d'entrée** dans la barre de commandes.
- Ouvrez la page de résultats du modèle et sélectionnez **Rapport d'utilisation des données d'entrée** dans la barre de commandes.

### <a name="information-in-the-input-data-usability-report"></a>Information dans le rapport d’utilisation des données d’entrée

Les colonnes suivantes du rapport contiennent des informations utiles pour améliorer les données du modèle.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple de rapport d'utilisation des données d'entrée montrant un tableau avec des erreurs, des avertissements et des recommandations.":::

- Nom : nom descriptif de l'erreur, de l'avertissement ou de la recommandation.
- Étape : phase, entraînement ou score du modèle auquel l'information fait référence.
- État : gravité de l'information (erreur, avertissement, recommandation).
- Nom de la colonne : colonne dans une entité qui doit être modifiée pour améliorer les performances du modèle.
- Nom de l'entité : nom de l'entité qui doit être modifiée pour améliorer les performances du modèle.
- Détails : détails sur l'erreur, l'avertissement ou la recommandation.

## <a name="refresh-a-prediction"></a>Actualiser une prédiction

Les prédictions seront automatiquement actualisées sur le même paramètre [planifier vos actualisations de données](system.md#schedule-tab) comme configuré dans les paramètres. Vous pouvez également les actualiser manuellement.

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez actualiser.

1. Cliquez sur **Actualiser**.

## <a name="delete-a-prediction"></a>Supprimer une prédiction

La suppression d’une prédiction entraîne également la suppression de son entité de sortie.

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez supprimer.

1. Sélectionnez **Supprimer**.
