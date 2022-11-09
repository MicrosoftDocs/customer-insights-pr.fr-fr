---
title: Exporter des segments vers Sendinblue (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724891"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exporter des segments vers Sendinblue (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir le marketing par e-mail et utiliser des groupes de clients spécifiques avec Sendinblue.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Sendinblue](https://www.sendinblue.com/) et des informations d’identification administrateur correspondantes.
- Une [clé API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Listes existantes dans Sendinblue et les ID correspondants.
- [Segments configurés](segments.md).
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- Jusqu’à 1 million de profils clients par exportation vers Sendinblue, ce qui peut prendre jusqu’à 90 minutes. Le nombre de profils clients que vous pouvez exporter vers Sendinblue dépend de votre contrat avec Sendinblue.
- Segments uniquement.

## <a name="set-up-connection-to-sendinblue"></a>Configurer la connexion à Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Sendinblue**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s'agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **clé API SendinBlue**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Sendinblue. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez votre **ID de liste Sendinblue**.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client.

1. Si nécessaire, exportez le **prénom**, le **nom** et le **téléphone** pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
