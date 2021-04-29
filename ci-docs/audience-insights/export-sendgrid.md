---
title: Exporter des données Customer Insights vers SendGrid
description: Apprenez à configurer la connexion et à exporter vers SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759762"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exporter des segments vers SendGrid (version préliminaire)

Exportez des segments de profils clients unifiés vers les listes de contacts SendGrid et utilisez-les pour les campagnes marketing et par e-mail dans SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte SendGrid](https://sendgrid.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des listes de contacts dans SendGrid et les ID correspondants. Pour plus d’informations, voir [SendGrid – Gérer les contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 100 000 profils au total vers SendGrid.
- L’exportation vers SendGrid est limitée aux segments.
- L’exportation de jusqu’à 100 000 profils vers SendGrid peut prendre jusqu’à quelques heures. 
- Le nombre de profils que vous pouvez exporter vers SendGrid dépend et est limité par votre contrat avec SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurer la connexion à SendGrid

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **SendGrid** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre **Clé API SendGrid** [Clé API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à SendGrid.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SendGrid. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre **[ID de liste SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Pays/Région**, **État**, **Ville** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter. Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers SendGrid. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers SendGrid, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que SendGrid respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]