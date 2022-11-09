---
title: Exporter des segments vers Marketo (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724937"
---
# <a name="export-segments-to-marketo-preview"></a>Exporter des segments vers Marketo (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir des activités de marketing par e-mail et utiliser certains groupes de clients avec Marketo.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Marketo](https://login.marketo.com/) et des informations d’identification administrateur correspondantes.
- Un [ID de client Marketo, secret client et nom d’hôte du point de terminaison REST](https://developers.marketo.com/rest-api/authentication/).
- [Listes existantes dans Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) et les ID correspondants.
- [Segments configurés](segments.md).
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- Jusqu’à 1 million de profils clients par exportation vers Marketo, ce qui peut prendre jusqu’à 3 heures. Le nombre de profils clients que vous pouvez exporter vers Marketo dépend de votre contrat avec Marketo.
- Segments uniquement.

## <a name="set-up-connection-to-marketo"></a>Configurer la connexion à Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Marketo**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez vos **ID de client Marketo, secret client et nom d’hôte du point de terminaison REST**. Le nom d’hôte du point de terminaison REST est le nom d’hôte uniquement, sans https://. Exemple : xyz-abc-123.mktorest.com.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Marketo. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez votre **ID de liste Marketo**. L’ID de liste est une valeur purement numérique. Par exemple, si votre ID de liste Marketo est ST12345A7, supprimez le caractère avant et après les chiffres et entrez *12345*.

1. Dans la section **Correspondance des données**, sélectionnez au moins un champ qui représente l’adresse e-mail d’un client ou l’ID Marketo d’un client.

1. Si nécessaire, exportez le **Prénom**, le **Nom**, la **Ville**, le **Département** et le/la **Pays/région** pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dans Marketo, retrouvez vos segments sous [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
