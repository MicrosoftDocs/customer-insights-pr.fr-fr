---
title: Exporter des segments vers Constant Contact (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724498"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exporter des segments vers Constant Contact (version préliminaire)

Exportez des segments de profils client unifiés vers Constant Contact et utilisez-les pour les activités marketing.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Constant Contact](https://www.constantcontact.com/account-home) et des informations d’identification administrateur correspondantes.
- Un [ID de liste Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Ouvrez une liste dans Constant Contact pour trouver l’ID de liste dans l’URL.
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- Un maximum d’un million de profils clients par exportation vers Constant Contact, ce qui peut prendre jusqu’à une heure. Le nombre de profils clients que vous pouvez exporter vers Constant Contact dépend de votre contrat avec Autopilot et est limité à Constant Contact.
- Segments uniquement.

## <a name="set-up-connection-to-constant-contact"></a>Configurer la connexion à Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Constant Contact**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Authentification avec Constant Contact** et fournissez vos informations d’identification d’administrateur pour Constant Contact.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Constant Contact. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez votre **ID de liste Constant Contact**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client.

1. Si nécessaire, exportez les champs **Prénom** et **Nom** comme champs supplémentaires pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
