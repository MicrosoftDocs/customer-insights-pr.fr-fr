---
title: Exporter des segments vers Snapchat (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195379"
---
# <a name="export-segments-to-snapchat-preview"></a>Exporter des segments vers Snapchat (version préliminaire)

Exportez des segments de profils client unifiés vers Snapchat et utilisez-les pour les activités de publicité.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte professionnel Snapchat](https://business.snapchat.com/), d’un[Compte Snapchat Ads](https://ads.snapchat.com/) et des informations d’identification administrateur correspondantes. Vous devez au moins être membre d’un compte d’organisation et gestionnaire de données d’un compte publicitaire spécifique.
- Au moins une audience dans le Gestionnaire d’audience Snapchat de type SAM (Snap audience Match).
- Le [segment/ID d’audience Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). L'ID de l'audience se trouve dans l'URL après avoir sélectionné l'audience dans le Gestionnaire d'audience Snapchat.
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Un maximum d’un million de profils clients, ce qui peut prendre jusqu’à 15 minutes.
- Segments uniquement.

## <a name="set-up-connection-to-snapchat"></a>Configurer la connexion à Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Snapchat**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **S’authentifier avec Snapchat** et fournissez vos informations d’identification administrateur pour Snapchat.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Snapchat. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez le **segment/ID d’audience Snapchat**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
