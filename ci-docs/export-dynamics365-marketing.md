---
title: Exporter des données Customer Insights vers Dynamics 365 Marketing
description: Apprenez à configurer la connexion et à exporter vers Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645969"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Utiliser des segments dans Dynamics 365 Marketing (version préliminaire)



Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec Dynamics 365 Marketing. Pour plus d’informations, voir [Utiliser des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Si vous utilisez les nouvelles fonctionnalités de Dynamics 365 Marketing pour orchestrer le parcours du client en temps réel dans une organisation Dataverse, il n’est pas nécessaire de créer une exportation standard vers Dynamics 365 Marketing. Les contacts et les segments de Customer Insights sont disponibles directement dans Dynamics 365 Marketing après avoir connecté Marketing et Customer Insights. Avant de supprimer les exportations existantes, consultez la documentation sur la [connexion de Customer Insights et l’orchestration du parcours client de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Conditions préalables à une connexion

- Les enregistrements de contact doivent être présents dans Dynamics 365 Marketing avant de pouvoir exporter un segment de Customer Insights vers Marketing. En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Marketing utilisant Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > L’exportation de segments de Customer Insights vers Marketing ne créera pas de nouveaux enregistrements de contact dans les instances Marketing. Les enregistrements de contact de Marketing doivent être ingérés dans Customer Insights et utilisés comme source de données. Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.

## <a name="set-up-connection-to-marketing"></a>Configurer la connexion à Marketing

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Dynamics 365 Marketing** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.

1. Mappez le champ ID de contact de l’entité Client sur l’ID de contact de Dynamics 365.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Dynamics 365 Marketing. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Choisissez un ou plusieurs segments.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
