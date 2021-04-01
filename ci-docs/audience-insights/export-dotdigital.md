---
title: Exporter des données Customer Insights vers DotDigital
description: Découvrez comment configurer la connexion à DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598014"
---
# <a name="connector-for-dotdigital-preview"></a>Connecteur pour DotDigital (version préliminaire)

Exportez des segments de profils clients unifiés vers les carnets d’adresses DotDigital et utilisez-les pour les campagnes, le marketing par e-mail, ainsi que pour créer des segments de client avec DotDigital. 

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte DotDigital](https://dotdigital.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des carnets d’adresses dans DotDigital et les ID correspondants. L’ID se trouve dans l’URL lorsque vous sélectionnez et ouvrez un carnet d’adresses. Pour plus d’informations, consultez [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-dotdigital"></a>Se connecter à DotDigital

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **DotDigital**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Volet de configuration pour l’exportation vers DotDigital.":::

1. Entrez vos **Nom d’utilisateur et mot de passe DotDigital**.

1. Entrez votre **[ID de carnet d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à DotDigital.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Nom complet**, **Sexe** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers DotDigital.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab). Dans DotDigital, vous trouverez désormais vos segments dans le [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils par exportation vers DotDigital.
- L’exportation vers DotDigital est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 3 heures en raison des limitations du côté du fournisseur. 
- Le nombre de profils que vous pouvez exporter vers DotDigital dépend et est limité par votre contrat avec DotDigital.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers DotDigital, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que DotDigital respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]