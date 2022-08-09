---
title: Exporter des segments vers LinkedIn Ads (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196805"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exporter des segments vers LinkedIn Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers LinkedIn Ads pour créer des audiences correspondantes. Utilisez les audiences correspondantes pour le ciblage des entreprises et le ciblage des contacts.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) et les informations d’identification de l’administrateur correspondantes.
- Un [ID de compte LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 100 000 million de profils clients par exportation vers LinkedIn Ads, ce qui peut prendre jusqu’à 10 minutes.
- Segments uniquement. Un segment doit contenir au moins 300 profils uniques.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurer la connexion à LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **LinkedIn Ads**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez votre ID de compte LinkedIn Campaign Manager.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **S’authentifier avec LinkedIn** et fournissez vos informations d’identification administrateur pour LinkedIn Campaign Manager.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LinkedIn Ads. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez si vous souhaitez exporter les données pour effectuer un [ciblage des contacts](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou un [ciblage des entreprises](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) sur Linkedin.

1. Dans la section **Mise en correspondance de données**, pour le ciblage des contacts, sélectionnez au moins un champ qui représente l’adresse e-mail d’un client, l’ID de publicité Apple, l’ID de publicité Google, l’ID d’utilisateur Google, ou le prénom et le nom. Si vous choisissez le ciblage par entreprise, sélectionnez au moins un champ qui représente un nom d’entreprise, un domaine de courrier, une URL de page LinkedIn, un symbole boursier ou un site web.

1. Si nécessaire, ajoutez des champs pour mieux définir votre exportation. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. Les audiences correspondantes dans LinkedIn Campaign Manager seront automatiquement créées avec le nom des segments que vous avez choisi d'exporter. Chaque segment aboutira à une audience correspondante distincte.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
