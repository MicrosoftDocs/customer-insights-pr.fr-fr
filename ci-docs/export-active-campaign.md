---
title: Exporter les données Customer Insights vers ActiveCampaign
description: Apprenez à configurer la connexion et à exporter vers ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646212"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exporter des segments vers ActiveCampaign (version préliminaire)

Exportez des segments de profils client unifiés vers ActiveCampaign et utilisez-les pour des activités de marketing.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte ActiveCampaign](https://www.activecampaign.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez des [segments configurés](segments.md) dans Customer Insights.
-   Les profils client unifiés dans les segments exportés contiennent un champ avec une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 1 million de profils clients par exportation vers ActiveCampaign et cela peut prendre jusqu’à 90 minutes.
- L’exportation vers ActiveCampaign est limitée aux segments.
- Le nombre de profils clients que vous pouvez exporter vers ActiveCampaign dépend de votre contrat avec ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurer la connexion à ActiveCampaign

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **ActiveCampaign** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez la [clé API ActiveCampaign et le nom d’hôte du point de terminaison REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Le nom d’hôte du point de terminaison REST est le nom d’hôte uniquement, sans https://. 

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à ActiveCampaign.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer une exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section ActiveCampaign. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre [**ID de liste ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Il est nécessaire d’exporter les segments vers ActiveCampaign. Vous pouvez éventuellement exporter le prénom, le nom et le téléphone pour créer des e-mails plus personnalisés. Sélectionnez Ajouter un attribut pour mapper ces champs.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à ActiveCampaign, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’ActiveCampaign respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.