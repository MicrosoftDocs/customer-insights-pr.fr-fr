---
title: Exporter des segments vers LinkedIn Ads (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6ad3901f7b8dc1ae8edc54c0b09a99b01be34cd
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050853"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exporter des segments vers LinkedIn Ads (version préliminaire)

Exportez des segments de profils clients unifiés vers LinkedIn Ads pour créer des audiences correspondantes. Utilisez les audiences correspondantes pour le ciblage des entreprises et le ciblage des contacts.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) et des informations d’identification administrateur correspondantes.
-   Vous avez des [segments configurés](segments.md) dans Customer Insights.
-   Les profils client dans les segments exportés contiennent un champ avec une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Votre segment dans Customer Insights doit contenir au moins 300 profils uniques. 
- Vous pouvez exporter jusqu’à 100 000 profils clients par exportation vers LinkedIn Ads.
- L’exportation vers LinkedIn Ads est limitée aux segments.
- L’exportation d’un maximum de 100 000 profils clients vers LinkedIn Ads peut prendre jusqu’à 10 minutes. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurer la connexion à LinkedIn Ads

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **LinkedIn Ads** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, ce sont par défaut les administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez votre [ID de compte LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Campaign Monitor.

1. Sélectionnez **S’authentifier avec LinkedIn** et fournissez vos informations d’identification administrateur pour LinkedIn Campaign Manager.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer une exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LinkedIn Ads. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Choisissez si vous souhaitez exporter les données pour effectuer un [ciblage des contacts](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou un [ciblage des entreprises](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) sur Linkedin. 

1. Dans la section **Mise en correspondance de données**, pour le ciblage des contacts, sélectionnez au moins un champ qui représente l’adresse e-mail d’un client, l’ID de publicité Apple, l’ID de publicité Google, l’ID d’utilisateur Google, ou le prénom et le nom. Si vous choisissez le ciblage par entreprise, sélectionnez au moins un champ qui représente un nom d’entreprise, un domaine de courrier, une URL de page LinkedIn, un symbole boursier ou un site web. Des champs supplémentaires peuvent être sélectionnés pour mieux définir votre exportation. 

1. Sélectionnez les segments que vous souhaitez exporter. Les audiences correspondantes dans LinkedIn Campaign Manager seront automatiquement créées avec le nom des segments que vous avez choisi d'exporter. Chaque segment aboutira à une audience correspondante distincte. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers LinkedIn Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que LinkedIn Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour stopper l'utilisation de cette fonctionnalité.
