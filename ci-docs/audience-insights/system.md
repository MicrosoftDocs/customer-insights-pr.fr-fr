---
title: Configuration du système dans les informations sur l’audience
description: En savoir plus sur les paramètres système de la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651837"
---
# <a name="system-configuration"></a>Configuration du système

La page **Système** comprend les onglets suivants :
- [Statut ](#status-tab)
- [Planification](#schedule-tab)
- [Utilisation de l’API](#api-usage-tab)
- [À propos](#about-tab)
- [GÉNÉRAL](#general-tab)
- [Sécurité](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Onglets de paramètres sur la page système.":::

## <a name="status-tab"></a>Onglet Statut

L’onglet **Statut** vous permet de suivre la progression de l’ingestion des données, des exportations de données et d’autres processus importants du produit. Passez en revue les informations de cet onglet pour vous assurer que les processus actifs sont complets.

Cet onglet comprend des tableaux avec des informations sur le statut et le traitement de divers processus. Chaque table suit le **Nom** de la tâche et son entité correspondante, le **Statut** de sa dernière exécution, et la **Dernière mise à jour**.

Vous pouvez afficher les détails des dernières exécutions de la tâche en sélectionnant son nom.

### <a name="status-types"></a>Types de statuts

Il existe six types de statuts pour les tâches. Les types de statuts suivants s’affichent également dans les pages *Mettre en correspondance*, *Fusionner*, *Sources de données*, *Segments*, *Mesures*, *Enrichissement*, *Activités* et *Prédictions* :

- **Traitement en cours :** La tâche est en cours. Le statut peut être modifié en Opération réussie ou Échec.
- **Opération réussie :** La tâche s’est terminée avec succès.
- **Ignoré :** La tâche a été ignorée. Un ou plusieurs des processus en aval dont dépend cette tâche échouent ou sont ignorés.
- **Échec :** Le traitement de la tâche a échoué.
- **Annulé :** Le traitement a été annulé par l’utilisateur avant la fin.
- **Mis en file d’attente :** Le traitement est mis en file d’attente et démarrera une fois toutes les tâches en amont terminées. Pour plus d’informations, voir [Stratégies d’actualisation](#refresh-policies).

### <a name="refresh-policies"></a>Stratégies d’actualisation

Cette liste affiche les stratégies d’actualisation pour chacun des processus principaux :

- **Sources de données :** S’exécute selon le [programme configuré](#schedule-tab). Ne dépend d’aucun autre processus. La mise en correspondance dépend de la bonne exécution de ce processus.
- **Mettre en correspondance :** S’exécute selon le [programme configuré](#schedule-tab). Dépend du traitement des sources de données utilisées dans la définition de correspondance. La fusion dépend de la bonne exécution de ce processus.
- **Fusionner :** S’exécute selon le [programme configuré](#schedule-tab). Dépend de l’exécution du processus de mise en correspondance. Les segments, les mesures, l’enrichissement, la recherche, les activités, les prédictions et la préparation des données dépendent de la bonne exécution de ce processus.
- **Segments** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion. Les informations dépendent de son traitement.
- **Mesures** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Activités** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Enrichissement** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Recherche** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Préparation des données :** S’exécute selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Informations** : S’exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend des segments.

Sélectionnez le statut d’une tâche pour afficher les détails de la progression de toute la tâche correspondante. Les stratégies d’actualisation ci-dessus peuvent vous aider à comprendre ce que vous pouvez faire pour gérer une tâche **Ignorée** ou **En file d’attente**.

## <a name="schedule-tab"></a>Onglet Planification

Utilisez l’onglet **Planification** pour planifier des actualisations automatiques de toutes vos [sources de données ingérées](data-sources.md). Les actualisations automatiques permettent de garantir que les mises à jour de vos sources de données se reflètent dans vos profils client unifiés.

1. Dans les informations sur l’audience, accédez à **Administration** > **Système** et sélectionnez l’onglet **Planification**.

2. L’état par défaut de l’actualisation planifiée est **Désactivé**. Pour autoriser les actualisations planifiées, basculez le bouton en haut de l’écran sur **Activé**.

3. Choisissez entre les actualisations **Hebdomadaires** (par défaut) et **Quotidiennes**. Si vous prévoyez de planifier des actualisations hebdomadaires, sélectionnez un ou plusieurs jours pendant lesquels vous souhaitez exécuter l’actualisation.

4. Définissez votre **Fuseau horaire**, puis utilisez la liste déroulante **Heure** pour définir votre calendrier d’actualisation. Lorsque vous avez terminé, sélectionnez **Configurer**. Si vous souhaitez planifier plusieurs actualisations en une seule journée, sélectionnez **Ajouter une autre heure**.

5. Sélectionnez **Enregistrer** pour appliquer vos modifications.

## <a name="about-tab"></a>Onglet À propos

L’onglet **À propos de** contient le **nom complet** de votre organisation, l’**ID d’environnement** actif, la **Région** et votre **ID de session**. Si vous avez plusieurs environnements de travail, vous devez donner un nom complet facilement identifiable à chacun d’eux.

## <a name="general-tab"></a>Onglet Général

Vous pouvez changer la langue et le format de pays/région sous l'onglet **Général**.

Customer Insights [prend en charge plusieurs langues](/dynamics365/get-started/availability). L’application utilise votre préférence de langue pour afficher des éléments tels que le menu, le libellé de l’étiquette et les messages système dans votre langue préférée.

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

   Les opérations qui utilisent [l’ingestion de données en temps réel](real-time-data-ingestion.md) contiennent un bouton avec un symbole binoculaire pour afficher l’utilisation de l’API en temps réel. Sélectionnez le bouton pour ouvrir un volet latéral contenant les détails de l’utilisation de l’API en temps réel dans l’environnement actuel.   
   Utilisez la zone **Par groupe** dans le volet **Utilisation de l’API en temps réel** pour choisir la meilleure façon de présenter vos interactions en temps réel. Vous pouvez regrouper les données par méthode API, nom qualifié d’entité (entité ingérée), créé par (source de l’événement), résultat (succès ou échec) ou codes d’erreur. Les données sont disponibles sous forme de graphique historique et sous forme de tableau.

## <a name="security-tab"></a>Onglet Sécurité

L'onglet **Sécurité** vous permet de lier et de gérer votre propre [coffre de clés Azure](/azure/key-vault/general/basic-concepts) à l'environnement.
Le coffre de clés dédié peut être utilisé pour organiser et utiliser des secrets dans la limite de conformité d’une organisation. Les informations d’audience peuvent utiliser les secrets dans Azure Key Vault pour [établir des connexions](connections.md) avec les systèmes tiers.

Pour plus d’informations, voir [Apportez votre propre coffre de clés Azure](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]