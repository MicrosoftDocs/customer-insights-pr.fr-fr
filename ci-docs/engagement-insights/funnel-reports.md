---
title: Rapports d'entonnoir
description: Comment utiliser des rapports d'entonnoir pour comprendre comment les clients prennent des décisions.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 81454a6c6e5aeec7d5bc5c4487123eafa1fe6a77
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555760"
---
# <a name="create-and-manage-funnel-reports"></a>Créer et gérer des rapports d'entonnoir

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un rapport d’entonnoir collecte des informations sur les étapes qui se produisent pendant un parcours client via votre site Web ou votre application mobile. Il vous aide à comprendre comment des clients progressent dans un processus et identifient les points de dépôt. Par exemple, vous pouvez utiliser un rapport de synthèse pour identifier les chemins empruntés par vos clients avant d'effectuer un achat. Un rapport d'entonnoir fournit des données pour éclairer les décisions et identifier les domaines à optimiser et améliorer les processus.

## <a name="create-a-funnel-report"></a>Créer un rapport d'entonnoir

Pour créer un rapport d'entonnoir, spécifiez les étapes que vous souhaitez inclure et l'activité pour chaque étape. Une activité est un [événement](glossary.md) qui représente le comportement des utilisateurs. Le rapport d'entonnoir affiche le nombre d'utilisateurs qui ont terminé chaque étape définie. 

1. Allez dans **Entonnoirs** et sélectionnez **+Nouvel entonnoir** pour démarrer un rapport d'entonnoir.

1. Dans l'**Éditeur d'entonnoir**, en dessous d'**Étapes**, sélectionnez **+Ajouter une étape.** 

1. Entrez un nom dans **Titre de l'étape**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nouveau rapport d'entonnoir.":::

1. Sélectionnez une **Activité**. Une activité enregistre lorsqu'un utilisateur consulte une page (activité d'**Affichage**) ou interagit avec le contenu (activité d'**Action**).

1. Utilisez des **Critères d'étape** pour spécifier la dimension de l'activité. Les [dimensions](dimensions.md) sont des attributs qui peuvent décrire, filtrer ou regrouper des données.

1. En option, vous pouvez configurer des étapes de synthèse à plusieurs conditions. Sélectionnez **Ajouter une condition** pour spécifier d'autres dimensions dans une étape. Les critères supplémentaires doivent utiliser le même type d'activité. Vous pouvez déterminer si plusieurs conditions sont connectées avec un opérateur ET ou OU.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Éditeur de synthèse affichant la configuration des étapes avec des étapes multiconditions.":::

1. Sélectionnez **Ajouter une étape** jusqu'à ce que vous ayez terminé toutes les étapes souhaitées dans le rapport.

1. Sélectionnez **Enregistrer**, nommez le rapport et cliquez à nouveau sur **Enregistrer**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemple : rapport d'entonnoir de l'entreprise Fourth Coffee

Le scénario suivant illustre une manière d'utiliser un rapport d'entonnoir. Un analyste de la société Fourth Coffee veut comprendre l'influence d'une récente promotion sur les tarifs d'abonnement. L'analyste crée un rapport de synthèse pour identifier l'activité des clients. Le rapport commence lorsque les clients arrivent sur la page d'accueil de l'entreprise jusqu'à ce qu'ils utilisent le code de promotion d'abonnement. L'analyste crée un rapport d'entonnoir avec les étapes suivantes :

Étape 1 : Clients qui arrivent sur la page d'accueil   
Étape 2 : Clients qui effectuent un achat   
Étape 3 : Clients qui utilisent le code promotionnel pour obtenir une réduction sur un abonnement   
Étape 4 : Inscription à l'abonnement   

:::image type="content" source="media/funnel-report-example.png" alt-text="exemple de rapport d'entonnoir.":::
  
Cet entonnoir vous permet de voir le nombre d'utilisateurs qui ont utilisé le code promotionnel après un achat unique pour s'inscrire au programme d'abonnement.

### <a name="configure-advanced-settings"></a>Configurer les paramètres avancés 

Les rapports de synthèse vous permettent de définir une limite de temps nécessaire pour exécuter une synthèse. Par exemple, vous pouvez définir le délai d'exécution de la synthèse sur quatre jours. Ce paramètre ne comptera que les inscriptions d'abonnement réussies qui se sont produites dans les quatre jours suivant la visite d'un utilisateur sur la page d'accueil.

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**.

1. Sélectionnez le nom du rapport à ouvrir. 

1. Dans le volet **Éditeur de synthèse**, sélectionnez **Paramètres avancés**. 

1. Définissez Limiter les délais d’exécution de la synthèse sur **Activer**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Éditeur de synthèse affichant des paramètres avancés et des options pour limiter le temps nécessaire pour exécuter une synthèse.":::

1. Choisissez l’heure à laquelle l’entonnoir doit être terminé dans la liste déroulante **Définir la limite sur**.

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.


## <a name="cross-channel-funnel-reports"></a>Rapports d’entonnoir entre canaux 

Les informations d’engagement peuvent également collecter les données comportementales des clients sur votre application mobile. Une fois que vous avez instrumenté votre application mobile avec le [SDK Android](get-started-android.md) ou le [SDK iOS](get-started-ios.md) des informations d’engagement, vous pouvez créer des rapports d’entonnoir entre canaux. 

### <a name="create-a-cross-channel-funnel-report"></a>Créer un rapport d’entonnoir entre canaux 

1. Suivez les étapes pour [créer un rapport d’entonnoir](#create-a-funnel-report).    

1. Pour suivre la façon dont vos clients interagissent avec votre marque à la fois dans votre site Web et votre application mobile, ou dans plusieurs sites Web, utilisez le sélecteur d’espaces de travail pour créer des étapes d’entonnoir avec les données des autres espaces de travail. Dans l’**Éditeur d’entonnoirs**, sous **Étapes**, sélectionnez l’espace de travail à partir duquel les données de votre étape d’entonnoir doivent provenir.

## <a name="manage-funnel-reports"></a>Gérer les rapports d'entonnoir

Vous pouvez consulter les rapports d'entonnoir pour analyser les données, suivre les performances et recueillir des informations.

> [!NOTE]
> - Les rapports d'entonnoir des informations sur l'engagement prennent actuellement en charge les scénarios dans lesquels tous les utilisateurs de l'entonnoir sont soit anonymes soit authentifiés. 
> - Les données historiques des rapports d'entonnoir sont disponibles pour les 30 derniers jours.

### <a name="view-funnel-reports"></a>Afficher les rapports d'entonnoir

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**.
1. Sélectionnez le nom du rapport à ouvrir.    

### <a name="see-the-data-collected-for-a-report"></a>Voir les données collectées pour un rapport   

Pour afficher des informations sur une phase

- Pointez sur une étape du rapport.

:::image type="content" source="media/funnel-step-data.png" alt-text="données d'entonnoir.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Modifier la plage de dates du rapport sur l'entonnoir de conversion

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**.

1. Sélectionnez le nom du rapport à ouvrir.

1. Ouvrez l'**intervalle de temps** et sélectionnez une nouvelle période dans la liste ou **Plage de dates fixe** pour spécifier une plage de dates.

## <a name="edit-or-delete-funnel-reports"></a>Modifier ou supprimer des rapports d'entonnoir

Vous pouvez changer le nom d'un rapport d'entonnoir, le supprimer ou modifier les étapes du rapport.

### <a name="rename-or-delete-a-funnel-report"></a>Renommer ou supprimer un rapport d'entonnoir

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**. 

1. Sélectionnez **Plus** à côté du rapport que vous souhaitez modifier et choisissez **Modifier le nom** ou alors **Supprimer**.

### <a name="edit-a-funnel-step"></a>Modifier une étape de l'entonnoir  

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**. 

1. Sélectionnez le nom du rapport à ouvrir.

1. Sélectionnez l'étape que vous souhaitez modifier.

1. Cliquez sur **Modifier**.

1. Dans l'**Éditeur d'entonnoir**, mettez à jour les informations que vous souhaitez modifier.  

1. Sélectionnez **Enregistrer**.

### <a name="reorder-a-funnel-step"></a>Réorganiser une étape de l'entonnoir

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**. 

1. Sélectionnez le nom du rapport à ouvrir.

1. Sélectionnez l'étape que vous souhaitez réorganiser.

1. Sélectionnez **Déplacer**, puis **Haut**, **Bas**, **Vers le haut**, ou alors **Vers le bas**, pour déplacer l'étape.

### <a name="delete-a-funnel-step"></a>Supprimer une étape de l'entonnoir

1. Allez dans **Entonnoirs** pour ouvrir la **Bibliothèque d'entonnoirs**. 

1. Sélectionnez le nom du rapport à ouvrir.

1. Sélectionnez l'étape que vous souhaitez supprimer, puis sélectionnez **Supprimer**.

