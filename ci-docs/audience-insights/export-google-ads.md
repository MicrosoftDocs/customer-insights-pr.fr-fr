---
title: Exporter des données Customer Insights vers Google Ads
description: Apprenez à configurer la connexion et à exporter vers Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5977b3de9fbb0d97c0912e2ada6a313b0ab92498adf9cdbed48191c0e5143567
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031654"
---
# <a name="export-segments-to-google-ads-preview"></a>Exporter des segments vers Google Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers une liste d’audience Google Ads et utilisez-les pour faire de la publicité dans Google Search, Gmail, YouTube et le Réseau Display de Google. 

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte Google Ads](https://ads.google.com/) et des informations d’identification administrateur correspondantes.
-   Vous disposez d’un [jeton de développeur Google Ads approuvé](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Vous remplissez les conditions de la [Stratégie de correspondance de clients](https://support.google.com/adspolicy/answer/6299717).
-   Vous remplissez les conditions des [tailles de liste de remarketing](https://support.google.com/google-ads/answer/7558048).
-   Il existe des audiences dans Google Ads et les ID correspondants. Pour plus d’informations, consultez [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un prénom et un nom.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils par exportation vers Google Ads.
- L’exportation vers Google Ads est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 5 minutes en raison des limitations du côté du fournisseur. 
- La mise en correspondance dans Google Ads peut prendre jusqu’à 48 heures.

## <a name="set-up-connection-to-google-ads"></a>Configurer la connexion à Google Ads

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Google Ads** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **[ID de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Entrez votre **[Jeton de développeur approuvé par Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **S’authentifier avec Google Ads** et fournissez vos informations d’identification Google Ads.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Google Ads. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Entrez votre **[ID d’audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** et sélectionnez **Connecter** pour initialiser la connexion à Google Ads.

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Google Ads.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). 

Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Google Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Google Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
