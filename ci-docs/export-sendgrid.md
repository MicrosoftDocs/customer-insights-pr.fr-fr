---
title: Exporter des segments vers SendGrid (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196989"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exporter des segments vers SendGrid (version préliminaire)

Exportez des segments de profils clients unifiés vers les listes de contacts SendGrid et utilisez-les pour les campagnes marketing et par e-mail dans SendGrid.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte SendGrid](https://sendgrid.com/) et des informations d’identification administrateur correspondantes.
- [Listes de contacts existants dans SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) et les ID correspondants.
- Une [clé API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Un maximum de 100 000 profils clients au total vers SendGrid, ce qui peut prendre jusqu’à quelques heures. Le nombre de profils clients que vous pouvez exporter vers SendGrid dépend de votre contrat avec SendGrid.
- Segments uniquement.

## <a name="set-up-connection-to-sendgrid"></a>Configurer la connexion à SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **SendGrid**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **clé API SendGrid**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SendGrid. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez votre **ID de liste SendGrid**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client.

1. Si nécessaire, sélectionnez des champs tels que **Prénom**, **Nom**, **Pays/Région**, **État**, **Ville** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter en respectant les limitations connues.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
