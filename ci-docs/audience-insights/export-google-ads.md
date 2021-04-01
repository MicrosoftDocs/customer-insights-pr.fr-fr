---
title: Exporter des données Customer Insights vers Google Ads
description: Découvrez comment configurer la connexion à Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598244"
---
# <a name="connector-for-google-ads-preview"></a>Connecteur pour Google Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers la liste d’audience Google Ads et utilisez-les pour faire de la publicité sur Google Search, Gmail, YouTube et le Réseau Display de Google. 

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte Google Ads](https://ads.google.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des audiences dans Google Ads et les ID correspondants. Pour plus d’informations, consultez [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Vous avez [configuré des segments](segments.md)
-   Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un prénom et un nom

## <a name="connect-to-google-ads"></a>Se connecter à Google Ads

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Google Ads**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Entrez votre **[ID de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Entrez votre **[Jeton de développeur approuvé par Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Entrez votre **[ID d’audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** et sélectionnez **Connecter** pour initialiser la connexion à Google Ads.

1. Sélectionnez **S’authentifier avec Google Ads** et fournissez vos informations d’identification Google Ads.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Capture d’écran d’exportation pour la connexion à Google Ads":::

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les champs **Prénom** et **Nom**.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Google Ads.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab). Dans Google Ads, vous trouverez désormais vos segments sous [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils par exportation vers Google Ads.
- L’exportation vers Google Ads est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 5 minutes en raison des limitations du côté du fournisseur. 
- La mise en correspondance dans Google Ads peut prendre jusqu’à 48 heures.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Google Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Google Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]