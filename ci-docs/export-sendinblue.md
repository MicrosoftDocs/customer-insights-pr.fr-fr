---
title: Exporter des segments vers Sendinblue (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081196"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exporter des segments vers Sendinblue (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir le marketing par e-mail et utiliser des groupes de clients spécifiques avec Sendinblue.

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte Sendinblue](https://www.sendinblue.com/) et des informations d’identification administrateur correspondantes.
-   Il y a des listes existantes dans Sendinblue et les ID correspondants.
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils clients par exportation vers Sendinblue.
- L’exportation vers Sendinblue est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils clients peut prendre jusqu’à 90 minutes. 
- Le nombre de profils clients que vous pouvez exporter vers Sendinblue dépend de votre contrat et est limité à Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Configurer la connexion à Sendinblue

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Sendinblue** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s'agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **[Clé API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Sélectionnez **J’accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Sendinblue.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Sendinblue. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre **ID de liste Sendinblue** 

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. 

1. Vous pouvez éventuellement exporter le **prénom**, le **nom** et le **téléphone** pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Sendinblue, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Sendinblue respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE [footer-include](includes/footer-banner.md)]
