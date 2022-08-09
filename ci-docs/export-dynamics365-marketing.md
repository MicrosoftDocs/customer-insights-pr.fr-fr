---
title: Exporter des segments vers Dynamics 365 Marketing (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196621"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exporter des segments vers Dynamics 365 Marketing (version préliminaire)

Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Si vous utilisez les nouvelles fonctionnalités de Dynamics 365 Marketing pour orchestrer le parcours du client en temps réel dans une organisation Dataverse, il n’est pas nécessaire de créer une exportation standard vers Dynamics 365 Marketing. Les contacts et les segments de Customer Insights sont disponibles directement dans Dynamics 365 Marketing après avoir connecté Marketing et Customer Insights. Avant de supprimer les exportations existantes, consultez la documentation sur la [connexion de Customer Insights et l’orchestration du parcours client de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Conditions préalables

Les enregistrements de contact doivent être présents dans Dynamics 365 Marketing avant de pouvoir exporter un segment de Customer Insights vers Marketing. En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Marketing utilisant Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> L’exportation de segments de Customer Insights vers Marketing ne créera pas de nouveaux enregistrements de contact dans les instances Marketing. Les enregistrements de contact de Marketing doivent être ingérés dans Customer Insights et utilisés comme source de données. Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.

## <a name="set-up-connection-to-marketing"></a>Configurer la connexion à Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Dynamics 365 Marketing**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.

1. Mappez le champ ID de contact de l’entité Client sur l’ID de contact de Dynamics 365.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Dynamics 365 Marketing. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Sélectionnez le champ ID de contact de l’entité Client correspondant à l’ID de contact de Dynamics 365.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
