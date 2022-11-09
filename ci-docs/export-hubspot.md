---
title: Exporter des données Customer Insights vers HubSpot
description: Apprenez à configurer la connexion et à exporter vers HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725351"
---
# <a name="export-segments-to-hubspot-preview"></a>Exporter des segments vers HubSpot (version préliminaire)

Exportez des segments de profils clients unifiés vers HubSpot et utilisez-les pour le marketing par e-mail.

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

- Un [compte HubSpot](https://www.hubspot.com/) et des informations d’identification administrateur correspondantes.
- Une [clé API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) de HubSpot.
- [Segments configurés](segments.md) dans Customer Insights.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- Jusqu’à 100 000 profils clients par exportation vers HubSpot, ce qui peut prendre jusqu’à 15 minutes. Le nombre de profils clients que vous pouvez exporter vers HubSpot dépend de votre contrat et est limité à HubSpot.
- Segments uniquement.

## <a name="set-up-connection-to-hubspot"></a>Configurer la connexion à HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **HubSpot** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Quand vous y êtes invité, entrez vos informations d’identification HubSpot.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion à HubSpot.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section HubSpot. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs optionnels.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
