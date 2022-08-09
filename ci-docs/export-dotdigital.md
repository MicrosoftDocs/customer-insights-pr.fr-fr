---
title: Exporter des segments vers DotDigital (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196069"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exporter des segments vers DotDigital (version préliminaire)

Exportez des segments de profils clients unifiés vers les carnets d’adresses DotDigital et utilisez-les pour les campagnes, le marketing par e-mail, ainsi que pour créer des segments de client avec DotDigital.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte DotDigital](https://dotdigital.com/) et un [utilisateur API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Un identifiant DotDigital d’un carnet d’adresses [nouveau](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ou existant dans DotDigital. L’ID se trouve dans l’URL lorsque vous sélectionnez et ouvrez un carnet d’adresses.
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils clients par exportation vers DotDigital, ce qui peut prendre jusqu’à trois heures en raison des limitations du côté du fournisseur. Le nombre de profils clients que vous pouvez exporter vers DotDigital dépend de votre contrat avec DotDigital.
- Segments uniquement.

## <a name="set-up-connection-to-dotdigital"></a>Configurer la connexion à DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **DotDigital**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez vos **Nom d’utilisateur et mot de passe DotDigital**.

1. Entrez votre **ID de carnet d’adresses DotDigital**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section DotDigital. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client.

1. Si nécessaire, exportez les **Prénom**, **Nom**, **Nom et prénom**, **Genre** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dans DotDigital, trouvez vos segments dans le [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
