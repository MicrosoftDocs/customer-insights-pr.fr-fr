---
title: Configuration du système dans Customer Insights
description: En savoir plus sur les paramètres système dans Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653613"
---
# <a name="system-configuration"></a>Configuration du système

Pour accéder aux configurations du système, allez à **Administrateur** > **Système** pour voir une liste de tâches et processus système.

La page **Système** comprend les onglets suivants :
- [Statut ](#status-tab)
- [Planification](#schedule-tab)
- [Utilisation de l’API](#api-usage-tab)
- [À propos](#about-tab)
- [GÉNÉRAL](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Onglets de paramètres sur la page système.":::

## <a name="status-tab"></a>Onglet Statut

L’onglet **Statut** vous permet de suivre la progression de l’ingestion des données, des exportations de données ainsi que de plusieurs autres processus importants du produit. Passez en revue les informations de cet onglet pour vous assurer que vos tâches et processus actifs sont complets.

Cet onglet comprend des tableaux avec des informations sur le statut et le traitement de divers processus. Chaque table suit le **Nom** de la tâche et son entité correspondante, le **Statut** de sa dernière exécution, et la **Dernière mise à jour**. Vous pouvez afficher les détails des dernières exécutions en sélectionnant le nom de la tâche ou du processus. 

Sélectionnez le statut près de la tâche ou du processus dans la colonne **Statut** pour ouvrir le volet **Détails de la progression**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Volet des détails de la progression du système":::

### <a name="status-definitions"></a>Définitions de statut

Le système utilise les statuts suivants pour les tâches et les processus :

|Statut  |Définition  |
|---------|---------|
|Annulée |Le traitement a été annulé par l’utilisateur avant sa fin.   |
|Échoué   |L’ingestion de données s’est heurtée à des erreurs.         |
|Échec  |Échec du traitement.  |
|Non démarré(e)(s)   |La source de données n’a pas encore de données ingérées ou est toujours en mode brouillon.         |
|Traitement  |La tâche ou le processus est en cours.  |
|Actualisation    |L’ingestion de données est en cours. Vous pouvez annuler cette opération en sélectionnant **Arrêter l’actualisation** dans la colonne **Actions**. L’arrêt de l’actualisation d’une source de données la ramène à son dernier état d’actualisation.       |
|Ignorée  |La tâche ou le processus a été ignoré. Un ou plusieurs des processus en aval dont dépend cette tâche échouent ou sont ignorés.|
|Opération réussie  |Tâche ou processus terminé. Pour les sources de données, indique que les données ont été ingérées avec succès si une heure est mentionnée dans la colonne **Actualisé**.|
|Mis(e) en file d’attente | Le traitement est mis en file d’attente et démarrera une fois que toutes les tâches et tous les processus en amont seront terminés. Pour plus d’informations, voir [Actualisation des processus](#refresh-processes).|

### <a name="refresh-processes"></a>Actualisation des processus

L’actualisation des tâches et des processus est exécutée conformément à l’[horaire configuré](#schedule-tab). 

|Processus  |Description  |
|---------|---------|
|Activité  |S’exécute manuellement (actualisation unique). Dépend du processus de fusion. Les informations dépendent de son traitement.|
|Liaison d’analyse |S’exécute manuellement (actualisation unique). Dépend des segments.  |
|Préparation de l’analyse |S’exécute manuellement (actualisation unique). Dépend des segments.  |
|Préparation des données   |Nécessite une entité sur laquelle s’exécuter. Les entités de source de données dépendent de l’ingestion. Les entités enrichies dépendent des enrichissements. L’entité Client dépend de la fusion.  |
|Sources de données   |Ne dépend d’aucun autre processus. La mise en correspondance dépend de la bonne exécution de ce processus.  |
|Enrichissements   |S’exécute manuellement (actualisation unique). Dépend du processus de fusion. |
|Destinations des exportations |S’exécute manuellement (actualisation unique). Dépend des segments.  |
|Aperçus |S’exécute manuellement (actualisation unique). Dépend des segments.  |
|Intelligence   |Dépend de la fusion.   |
|Correspondance |Dépend du traitement des sources de données utilisées dans la définition de correspondance.      |
|Mesures  |S’exécute manuellement (actualisation unique). Dépend du processus de fusion.  |
|Fusionner   |Dépend de l’exécution du processus de mise en correspondance. Les segments, les mesures, l’enrichissement, la recherche, les activités, les prédictions et la préparation des données dépendent de la bonne exécution de ce processus.   |
|Profils   |S’exécute manuellement (actualisation unique). Dépend du processus de fusion. |
|Rechercher   |S’exécute manuellement (actualisation unique). Dépend du processus de fusion. |
|Segments  |S’exécute manuellement (actualisation unique). Dépend du processus de fusion. Les informations dépendent de son traitement.|
|Système   |Dépend de l’exécution du processus de mise en correspondance. Les segments, les mesures, l’enrichissement, la recherche, les activités, les prédictions et la préparation des données dépendent de la bonne exécution de ce processus.   |
|Utilisateur  |S’exécute manuellement (actualisation unique). Dépend des entités.  |

Sélectionnez l’état d’un processus pour voir les détails de la progression de l’ensemble de la tâche dans laquelle il se trouvait. Les processus d’actualisation ci-dessus peuvent aider à comprendre ce que vous pouvez faire pour résoudre un problème de tâche **Ignorée** ou **En file d’attente**.

## <a name="schedule-tab"></a>Onglet Planification

Utilisez l’onglet **Planification** pour planifier des actualisations automatiques de toutes vos [sources de données ingérées](data-sources.md). Les actualisations automatiques permettent de garantir que les mises à jour de vos sources de données se reflètent dans vos profils client unifiés.

> [!NOTE]
> Les sources de données que vous gérez s’actualisent selon leurs propres planifications. Pour planifier l’actualisation des sources de données que vous gérez, configurez les paramètres d’actualisation sur ces source de données spécifiques à partir de la page **Sources de données**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Paramètres d’actualisation du dataflow.":::

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **Planifier**.

2. L’état par défaut de l’actualisation planifiée est **Désactivé**. Pour autoriser les actualisations planifiées, basculez le bouton en haut de l’écran sur **Activé**.

3. Choisissez entre les actualisations **Hebdomadaires** (par défaut) et **Quotidiennes**. Si vous prévoyez de planifier des actualisations hebdomadaires, sélectionnez un ou plusieurs jours pendant lesquels vous souhaitez exécuter l’actualisation.

4. Définissez votre **Fuseau horaire**, puis utilisez la liste déroulante **Heure** pour définir votre calendrier d’actualisation. Lorsque vous avez terminé, sélectionnez **Configurer**. Si vous souhaitez planifier plusieurs actualisations en une seule journée, sélectionnez **Ajouter une autre heure**.

5. Sélectionnez **Enregistrer** pour appliquer vos modifications.

## <a name="about-tab"></a>Onglet À propos

L’onglet **À propos de** contient le **nom complet** de votre organisation, l’**ID d’environnement** actif, la **Région** et votre **ID de session**. Si vous avez plusieurs environnements de travail, vous devez donner un nom complet facilement identifiable à chacun d’eux.

## <a name="general-tab"></a>Onglet Général

Vous pouvez changer la langue et le format de pays/région sous l’onglet **Général**.

[Langues prises en charge pour](/dynamics365/get-started/availability) Customer Insights. L’application utilise votre préférence de langue pour afficher des éléments tels que le menu, le libellé de l’étiquette et les messages système dans votre langue préférée.

Les données et informations importées que vous avez saisies manuellement ne sont pas traduites.

### <a name="update-the-settings"></a>Mettre à jour les paramètres

Pour modifier votre langue par défaut, choisissez une **Langue** dans la liste déroulante.

Pour modifier votre mise en forme par défaut pour les dates, l’heure et les nombres, utilisez la liste déroulante **Format de pays/région**. Un aperçu de la mise en forme s’affiche sous ce champ. Le système suggérera automatiquement une sélection lorsque vous choisissez une nouvelle langue.

Choisissez **Enregistrer** pour confirmer vos sélections.

## <a name="api-usage-tab"></a>Onglet d’utilisation de l’API

Trouvez des détails sur l’utilisation de l’API en temps réel et voyez quels événements se sont produits sur une période donnée. Vous choisissez la période dans le menu déroulant **Sélectionner une période**. 

L’**Utilisation de l’API** contient trois sections : 
- **Appels API** – un graphique qui visualise le nombre total d’appels à l’API dans le délai d’exécution sélectionné.

- **Transfert de données** – un graphique qui montre la quantité de données transférées via l’API dans le délai d’exécution sélectionné.

-  **Opérations** – un tableau avec des lignes pour chaque opération API disponible et des détails sur l’utilisation des opérations. Vous pouvez sélectionner un nom d’opération pour accéder à [la référence API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Les opérations qui utilisent [l’ingestion de données en temps réel](real-time-data-ingestion.md) contiennent un bouton avec un symbole binoculaire pour visualiser l’utilisation de l’API en temps réel. Sélectionnez le bouton pour ouvrir un volet latéral contenant les détails de l’utilisation de l’API en temps réel dans l’environnement actuel.   
   Utilisez la zone **Par groupe** dans le volet **Utilisation de l’API en temps réel** pour choisir la meilleure façon de présenter vos interactions en temps réel. Vous pouvez regrouper les données par méthode API, nom qualifié d’entité (entité ingérée), créé par (source de l’événement), résultat (succès ou échec) ou codes d’erreur. Les données sont disponibles sous forme de graphique historique et sous forme de tableau.


[!INCLUDE [footer-include](includes/footer-banner.md)]
