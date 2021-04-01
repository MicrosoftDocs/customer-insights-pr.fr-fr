---
title: Exporter des données Customer Insights vers Mailchimp
description: Découvrez comment configurer la connexion à Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598198"
---
# <a name="connector-for-mailchimp-preview"></a>Connecteur pour Mailchimp (version préliminaire)

Exportez des segments de profils clients unifiés vers Mailchimp pour créer des bulletins d’informations et des campagnes par e-mail.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte Mailchimp](https://mailchimp.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des audiences dans Mailchimp et les ID correspondants. Pour plus d’informations, consultez [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).
-   Vous avez [configuré des segments](segments.md)
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-mailchimp"></a>Se connecter à Mailchimp

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Mailchimp**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Entrez votre **[ID d’audience Mailchimp](https://mailchimp.com/help/find-audience-id/)** et sélectionnez **Connecter** pour initialiser la connexion à Mailchimp.

1. Sélectionnez **S’authentifier avec Mailchimp** et fournissez vos informations d’identification Mailchimp.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Capture d’écran d’exportation pour la connexion à Mailchimp":::

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. 

1. Vous pouvez éventuellement exporter les champs **Prénom** et **Nom** comme champs supplémentaires pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Sélectionner les champs et les segments à exporter vers Mailchimp":::

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab). Dans Mailchimp, vous trouverez désormais vos segments sous [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils par exportation vers Mailchimp.
- L’exportation vers Mailchimp est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à trois heures en raison des limitations du côté du fournisseur. 
- Le nombre de profils que vous pouvez exporter vers Mailchimp dépend et est limité par votre contrat avec Mailchimp.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Mailchimp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Mailchimp respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]