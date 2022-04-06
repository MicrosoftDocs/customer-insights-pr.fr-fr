---
title: Exporter des données Customer Insights vers Google Ads
description: Apprenez à configurer la connexion et à exporter vers Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523791"
---
# <a name="export-segments-to-google-ads-preview"></a>Exporter des segments vers Google Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers une liste d’audience Google Ads et utilisez-les pour faire de la publicité dans Google Search, Gmail, YouTube et le Réseau Display de Google. 


## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte Google Ads](https://ads.google.com/) et des informations d’identification administrateur correspondantes.
-   Vous remplissez les conditions de la [Stratégie de correspondance de clients](https://support.google.com/adspolicy/answer/6299717).
-   Vous remplissez les conditions des [tailles de liste de remarketing](https://support.google.com/google-ads/answer/7558048).
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un numéro de téléphone, un ID d’annonceur mobile, un ID utilisateur tiers ou une adresse.

## <a name="known-limitations"></a>Limitations connues

- L’exportation vers Google Ads est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils clients peut prendre jusqu’à 30 minutes en raison des limitations du côté du fournisseur. 
- La mise en correspondance dans Google Ads peut prendre jusqu’à 48 heures.

## <a name="set-up-connection-to-google-ads"></a>Configurer la connexion à Google Ads

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Google Ads** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **[ID de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **S’authentifier avec Google Ads** et fournissez vos informations d’identification Google Ads.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Google Ads. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Si vous souhaitez créer une nouvelle audience, laissez le champ ID d’audience Google vide. Nous créerons automatiquement une nouvelle audience dans votre compte Google Ads et utiliserons le nom du segment exporté. Si vous souhaitez mettre à jour une audience Google Ads existante, entrez votre [ID d’audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Dans la section **Correspondance des données**, sélectionnez un ou plusieurs champs de données à exporter, puis sélectionnez le champ qui représente les champs de données correspondants dans Customer Insights.

1. Sélectionnez les segments que vous souhaitez exporter. 

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). 

Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Google Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Google Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
