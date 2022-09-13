---
title: Afficher la configuration du système
description: En savoir plus sur les paramètres système dans Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395998"
---
# <a name="view-system-configuration"></a>Afficher la configuration du système

Afficher les informations système, l’état du système et l’utilisation de l’API.

## <a name="view-api-usage"></a>Afficher l’utilisation de l'API

Affichez des détails sur l’utilisation de l’API en temps réel et voyez quels événements se sont produits sur une période donnée.

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **Utilisation de l'API**.

1. **Sélectionner un délai d’exécution** pour afficher les données.

   La page **Utilisation de l’API** contient trois sections :

   - **Appels API** – un graphique qui visualise le nombre total d’appels à l’API dans le délai d’exécution sélectionné.
   - **Transfert de données** – un graphique qui montre la quantité de données transférées via l’API dans le délai d’exécution sélectionné.
   - **Opérations** – un tableau avec des lignes pour chaque opération API disponible et des détails sur l’utilisation des opérations. Sélectionnez un nom d’opération pour accéder à [la référence API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Afficher les informations système

Affichez le nom complet, l'ID, la région, le type et l'ID de session de l’environnement.

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **À propos**.

1. Pour afficher la langue et le pays/région, sélectionnez l'onglet **Général** .

### <a name="update-preferred-language-or-countryregion"></a>Mettre à jour la langue ou le pays/la région de votre choix

[Langues prises en charge pour](/dynamics365/get-started/availability) Customer Insights. L’application utilise votre préférence de langue pour afficher des éléments tels que le menu, le libellé de l’étiquette et les messages système dans votre langue préférée.

Les données et informations importées que vous avez saisies manuellement ne sont pas traduites.

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **Général**.

1. Pour modifier votre langue par défaut, choisissez une **Langue** dans la liste déroulante.

1. Pour modifier votre mise en forme par défaut pour les dates, l’heure et les nombres, utilisez la liste déroulante **Format de pays/région**. Un aperçu de formatage s'affiche. Le système suggère automatiquement une sélection lorsque vous choisissez une nouvelle langue.

1. Cliquez sur **Enregistrer**.

## <a name="view-system-status"></a>Afficher le statut du système

Suivez la progression de l’ingestion des données, des exportations de données ainsi que de plusieurs autres processus importants du produit. Passez en revue les informations pour vous assurer que vos tâches et processus actifs sont complets.

1. Accédez à **Administrateur** > **Système** et sélectionnez l’onglet **Statut**.

   Les informations sur le statut et le traitement de divers processus s'affichent. Affichez le **Nom** de la tâche, le **Statut** de sa dernière exécution, et la **Dernière mise à jour**.

1. Pour afficher les détails des dernières exécutions, sélectionnez le nom de la tâche ou du processus.

1. Pour afficher les détails de l'avancement d'une tâche, sélectionnez le statut. Le volet **Détails de la progression** s’affiche.

   :::image type="content" source="media/system-progress-details.png" alt-text="Volet des détails de la progression du système":::

1. Pour afficher les détails de la progression de toutes les tâches, sélectionnez **Workflow entier**.

### <a name="status-definitions"></a>Définitions de statut

Le système utilise les statuts suivants pour les tâches et les processus :

|Status  |Définition  |
|---------|---------|
|Annulée |La tâche ou le processus a été annulé par l’utilisateur avant sa fin.   |
|Échoué   |La tâche ou le processus a rencontré des erreurs.         |
|Échec  |La tâche ou le processus a échoué.  |
|Non démarré(e)(s)   |La source de données n’a pas encore de données ingérées ou la tâche est toujours en mode brouillon.         |
|Traitement  |La tâche ou le processus est en cours.  |
|Actualisation    |La tâche ou le processus est en cours. Pour annuler cette opération, sélectionnez **Actualisation** et **Annuler la tâche**. L’arrêt de l’actualisation d’une tâche ou d'un processus le/la ramène à son dernier état d’actualisation.       |
|Ignorée  |La tâche ou le processus a été ignoré. Un ou plusieurs des processus en aval dont dépend cette tâche échouent ou sont ignorés.|
|Opération réussie  |Tâche ou processus terminé. Pour les sources de données, indique que les données ont été ingérées avec succès si une heure est mentionnée dans la colonne **Actualisé**.|
|Mis(e) en file d’attente | Le traitement est mis en file d’attente et démarrera une fois que toutes les tâches et tous les processus en amont seront terminés. Pour plus d’informations, voir [Actualisation des processus](#refresh-processes).|

### <a name="refresh-processes"></a>Actualisation des processus

L’actualisation des tâches et des processus est exécutée conformément à l’[horaire configuré](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
