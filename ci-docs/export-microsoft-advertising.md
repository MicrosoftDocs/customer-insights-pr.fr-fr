---
title: Exporter des segments vers Microsoft Advertising (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196529"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exporter des segments vers Microsoft Advertising (version préliminaire)

Exportez les segments Customer Insights vers Microsoft Advertising pour créer des audiences Customer Match. Utilisez ces audiences pour vos campagnes publicitaires.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Microsoft Advertising](https://ads.microsoft.com/) et des informations d’identification administrateur correspondantes.
- ID client et ID de compte Microsoft Advertising. Recherchez l’ID client (`cid`) et l’ID de compte (`aid`) dans les paramètres de l’URL lorsque vous êtes connecté à Microsoft Advertising.
- Les conditions d’utilisation Customer Match sont acceptées.
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Un maximum de 500 000 profils clients par exportation vers Microsoft Advertising, ce qui peut prendre jusqu’à 10 minutes.
- Segments uniquement.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurer la connexion à Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Microsoft Advertising**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, ce sont les administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez l’**ID client Microsoft Advertising**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **S’authentifier avec Microsoft Advertising** et fournissez vos informations d’identification administrateur pour Microsoft Advertising.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Microsoft Advertising. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Sélectionner les segments à exporter. Les audiences Customer Match dans Microsoft Advertising sont automatiquement créées avec le nom des segments sélectionnés pour l'exportation. Chaque segment aboutira à une audience Customer Match distincte.

1. Entrez votre **ID client et ID de compte Microsoft Advertising**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ contenant l’adresse e-mail d’un client.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
