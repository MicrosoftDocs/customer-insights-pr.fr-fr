---
title: Exporter des segments vers Google Ads (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725075"
---
# <a name="export-segments-to-google-ads-preview"></a>Exporter des segments vers Google Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers une liste d’audience Google Ads et utilisez-les pour faire de la publicité dans Google Search, Gmail, YouTube et le Réseau Display de Google.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Google Ads](https://ads.google.com/) et des informations d’identification administrateur correspondantes.
- Un [ID de client Google Ads](https://support.google.com/google-ads/answer/1704344).
- Les conditions de la [Stratégie de correspondance de clients](https://support.google.com/adspolicy/answer/6299717) sont remplies.
- Les conditions des [tailles de liste de remarketing](https://support.google.com/google-ads/answer/7558048) sont remplies.
- [Segments configurés](segments.md).
- Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un numéro de téléphone, un ID d’annonceur mobile, un ID utilisateur tiers ou une adresse.

## <a name="known-limitations"></a>Limitations connues

- Le lien privé en combinaison avec Bring your own storage (BYOS) n’est pas pris en charge.
- Exportez jusqu’à 1 million de profils clients par exportation vers Google Ads, ce qui peut prendre jusqu’à 30 minutes en raison des limitations du côté du fournisseur.
- Segments uniquement.
- La mise en correspondance dans Google Ads peut prendre jusqu’à 48 heures.

## <a name="set-up-connection-to-google-ads"></a>Configurer la connexion à Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Google Ads**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre ID de client Google Ads.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **S’authentifier avec Google Ads** et fournissez vos informations d’identification Google Ads.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Google Ads. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez d’utiliser un environnement existant ou d’en créer un :
   - Si vous souhaitez mettre à jour une audience Google Ads existante, entrez votre [ID d’audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Si vous souhaitez créer une nouvelle audience, laissez le champ ID d’audience Google vide. Customer Insights créera automatiquement une nouvelle audience dans votre compte Google Ads et utiliserons le nom du segment exporté.

1. Dans la section **Correspondance des données**, sélectionnez un ou plusieurs champs de données à exporter, puis sélectionnez le champ qui représente les champs de données correspondants dans Customer Insights.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
