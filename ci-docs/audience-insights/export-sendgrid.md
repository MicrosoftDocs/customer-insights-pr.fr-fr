---
title: Exporter des données Customer Insights vers SendGrid
description: Découvrez comment configurer la connexion à SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268729"
---
# <a name="connector-for-sendgrid-preview"></a>Connecteur pour SendGrid (version préliminaire)

Exportez des segments de profils clients unifiés vers les listes de contacts SendGrid et utilisez-les pour les campagnes marketing et par e-mail dans SendGrid. 

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte SendGrid](https://sendgrid.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des listes de contacts dans SendGrid et les ID correspondants. Pour plus d’informations, voir [SendGrid – Gérer les contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-sendgrid"></a>Se connecter à SendGrid

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **SendGrid**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Volet de configuration d’exportation SendGrid.":::

1. Entrez votre **Clé API SendGrid** [Clé API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Entrez votre **[ID de liste SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à SendGrid.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Pays/Région**, **État**, **Ville** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter. Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers SendGrid. 

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 100 000 profils au total vers SendGrid.
- L’exportation vers SendGrid est limitée aux segments.
- L’exportation de jusqu’à 100 000 profils vers SendGrid peut prendre jusqu’à quelques heures. 
- Le nombre de profils que vous pouvez exporter vers SendGrid dépend et est limité par votre contrat avec SendGrid.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers SendGrid, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que SendGrid respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]