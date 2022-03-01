---
title: Exporter des données Customer Insights vers Autopilot
description: Découvrez comment configurer la connexion à Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269235"
---
# <a name="connector-for-autopilot-preview"></a>Connecteur pour Autopilot (version préliminaire)

Exportez des segments de profils clients unifiés vers Autopilot et utilisez-les pour le marketing par e-mail dans Autopilot. 

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte Autopilot](https://www.autopilothq.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-autopilot"></a>Se connecter Autopilot

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Autopilot**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Volet de configuration pour la connexion à Autopilot.":::

1. Entrez votre **Clé API Autopilot** [Clé API Autopilot](https://autopilot.docs.apiary.io/#).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Autopilot.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom** et **Nom**.

1. Sélectionnez les segments que vous souhaitez exporter. Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers Autopilot. 

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 100 000 profils clients au total vers Autopilot.
- L’exportation vers Autopilot est limitée aux segments.
- L’exportation de jusqu’à 100 000 profils vers Autopilot peut prendre jusqu’à quelques heures. 
- Le nombre de profils que vous pouvez exporter vers Autopilot dépend et est limité par votre contrat avec Autopilot.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Autopilot, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Autopilot respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]