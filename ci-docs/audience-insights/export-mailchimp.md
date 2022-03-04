---
title: Exporter des données Customer Insights vers Mailchimp
description: Apprenez à configurer la connexion et à exporter vers Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226843"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exporter des segments vers Mailchimp (version préliminaire)

Exportez des segments de profils clients unifiés vers Mailchimp pour créer des bulletins d’informations et des campagnes par e-mail.

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte Mailchimp](https://mailchimp.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des audiences dans Mailchimp et les ID correspondants. Pour plus d’informations, consultez [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).
-   Vous avez [configuré des segments](segments.md)
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils clients par exportation vers Mailchimp.
- L’exportation vers Mailchimp est limitée aux segments.
- L’exportation de segments avec 1 million de profils clients peut prendre jusqu’à trois heures. 
- Le nombre de profils clients que vous pouvez exporter vers Mailchimp dépend de votre contrat et est limité à Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurer la connexion à Mailchimp

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Mailchimp** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Mailchimp.

1. Sélectionnez **S’authentifier avec Mailchimp** et fournissez vos informations d’identification Mailchimp.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-the-connector"></a>Configurer le connecteur

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données**> **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Mailchimp. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre **[ID d’audience Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. 

1. Vous pouvez éventuellement exporter le **Prénom** et le **Nom** pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Mailchimp.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Mailchimp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Mailchimp respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
