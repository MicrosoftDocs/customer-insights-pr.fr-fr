---
title: Configuration du système dans Audience Insights
description: En savoir plus sur les paramètres système de la fonctionnalité Audience Insights de Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405680"
---
# <a name="system-configuration"></a>Configuration du système

La page **Système** comprend quatre onglets : **Statut**, **Planification**, **À propos de** et **Général**.

> [!div class="mx-imgBorder"]
> ![Page Système](media/system-tabs.png "Page Système")

## <a name="status-tab"></a>Onglet Statut

L'onglet **Statut** vous permet de suivre la progression de l'ingestion des données, les exportations de données, ainsi que de plusieurs processus importants du produit. Passez en revue les informations de cet onglet pour vous assurer que les processus actifs sont complets.

Cet onglet comprend des tableaux d'état pour **Sources de données**, **Processus système**, et **Préparation des données**. Chaque table suit le **Nom** de la tâche et son entité correspondante, le **Statut** de sa dernière exécution, et la **Dernière mise à jour**.

Vous pouvez afficher les détails des dernières exécutions de la tâche en sélectionnant son nom.

### <a name="status-types"></a>Types de statuts

Il existe six types de statuts pour les tâches. Les types de statuts suivants s'affichent également dans les pages *Mettre en correspondance*, *Fusionner*, *Sources de données*, *Segments*, *Mesures*, *Enrichissement*, *Activités* et *Prédictions* :

- **Traitement en cours :** La tâche est en cours. Le statut peut être modifié en Opération réussie ou Échec.
- **Opération réussie :** La tâche s'est terminée avec succès.
- **Ignoré :** La tâche a été ignorée. Un ou plusieurs des processus en aval dont dépend cette tâche échouent ou sont ignorés.
- **Échec :** Le traitement de la tâche a échoué.
- **Annulé :** Le traitement a été annulé par l'utilisateur avant la fin.
- **En file d'attente :** Le traitement est mis en file d'attente et démarrera une fois toutes les tâches en aval terminées. Pour plus d'informations, voir [Stratégies d'actualisation](#refresh-policies).

### <a name="refresh-policies"></a>Stratégies d'actualisation

Cette liste affiche les stratégies d'actualisation pour chacun des processus principaux :

- **Sources de données :** S'exécute selon le [programme configuré](#schedule-tab). Ne dépend d'aucun autre processus. La mise en correspondance dépend de la bonne exécution de ce processus.
- **Mettre en correspondance :** S'exécute selon le [programme configuré](#schedule-tab). Dépend du traitement des sources de données utilisées dans la définition de correspondance. La fusion dépend de la bonne exécution de ce processus.
- **Fusionner :** S'exécute selon le [programme configuré](#schedule-tab). Dépend de l'exécution du processus de mise en correspondance. Les segments, les mesures, l'enrichissement, la recherche, les activités, les prédictions et la préparation des données dépendent de la bonne exécution de ce processus.
- **Segments** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion. Les informations dépendent de son traitement.
- **Mesures** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Activités** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Enrichissement** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Recherche** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Préparation des données :** S'exécute selon le [programme configuré](#schedule-tab). Dépend de la fusion.
- **Informations** : S'exécute manuellement (actualisation unique) et selon le [programme configuré](#schedule-tab). Dépend des segments.

Sélectionnez le statut d'une tâche pour afficher les détails de la progression de toute la tâche correspondante. Les stratégies d'actualisation ci-dessus peuvent vous aider à comprendre ce que vous pouvez faire pour gérer une tâche **Ignorée** ou **En file d'attente**.

## <a name="schedule-tab"></a>Onglet Planification

Utilisez l'onglet **Planification** pour planifier des actualisations automatiques de toutes vos [sources de données ingérées](data-sources.md). Les actualisations automatiques permettent de garantir que les mises à jour de vos sources de données se reflètent dans vos profils client unifiés.

1. Dans Audience Insights, accédez à **Administration** > **Système** et sélectionnez l'onglet **Planification**.

2. L'état par défaut de l'actualisation planifiée est **Désactivé**. Pour autoriser les actualisations planifiées, basculez le bouton en haut de l'écran sur **Activé**.

3. Choisissez entre les actualisations **Hebdomadaires** (par défaut) et **Quotidiennes**. Si vous prévoyez de planifier des actualisations hebdomadaires, sélectionnez un ou plusieurs jours pendant lesquels vous souhaitez exécuter l'actualisation.

4. Définissez votre **Fuseau horaire**, puis utilisez la liste déroulante **Heure** pour définir votre calendrier d'actualisation. Lorsque vous avez terminé, sélectionnez **Configurer**. Si vous souhaitez planifier plusieurs actualisations en une seule journée, sélectionnez **Ajouter une autre heure**.

5. Sélectionnez **Enregistrer** pour appliquer vos modifications.

## <a name="about-tab"></a>Onglet À propos

L'onglet **À propos de** contient le **nom complet** de votre organisation, l'**ID d'environnement** actif, la **Région** et votre **ID de session**. Si vous avez plusieurs environnements de travail, vous devez donner un nom complet facilement identifiable à chacun d'eux.

## <a name="general-tab"></a>Onglet Général

L'onglet **Général** comporte deux options : **Langue** et **Format de pays/région**.

L'application [prend en charge un certain nombre de langues](supported-languages.md). Pour modifier votre langue par défaut, choisissez une **Langue** dans la liste déroulante.

Pour modifier votre mise en forme par défaut pour les dates, l'heure et les nombres, utilisez la liste déroulante **Format de pays/région**. Un aperçu de la mise en forme s'affiche sous ce champ. Le système suggérera automatiquement une sélection lorsque vous choisissez une nouvelle langue.

Choisissez **Enregistrer** pour confirmer vos sélections.

## <a name="api-usage-tab"></a>Onglet d'utilisation de l'API

Trouvez des détails sur l'utilisation de l'API en temps réel et voyez quels événements se sont produits dans une plage de temps donnée. Pour plus d’informations, voir [Ingestion de données en temps réel](real-time-data-ingestion.md).
