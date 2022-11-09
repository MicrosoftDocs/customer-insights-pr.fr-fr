---
title: Exporter des segments vers Campaign Monitor (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724545"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exporter des segments vers Campaign Monitor (version préliminaire)

Exportez des segments de profils client unifiés vers Campaign Monitor et utilisez-les pour les activités marketing.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Campaign Monitor](https://www.campaignmonitor.com/) et des informations d’identification administrateur correspondantes.
- Un [ID de liste Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Une [clé API générée](https://www.campaignmonitor.com/api/getting-started/) à partir des **Paramètres du compte** de Campaign Monitor pour obtenir l’ID de la liste d’API.
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- In maximum d’un million de profils clients par exportation vers Campaign Monitor, ce qui peut prendre jusqu’à 20 minutes. Le nombre de profils clients que vous pouvez exporter vers Campaign Monitor dépend de votre contrat avec Autopilot et est limité à Campaign Monitor.
- Segments uniquement.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurer la connexion à Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Campaign Monitor**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Campaign Monitor.

1. Sélectionnez **S’authentifier avec Campaign Monitor** et fournissez vos informations d’identification administrateur pour Campaign Monitor.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Campaign Monitor. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez votre **ID de liste Campaign Monitor**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Il est obligatoire d’exporter des segments vers Campaign Monitor.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
