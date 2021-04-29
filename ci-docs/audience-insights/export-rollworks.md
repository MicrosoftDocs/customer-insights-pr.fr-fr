---
title: Exporter des données Customer Insights vers RollWorks
description: Apprenez à configurer la connexion et à exporter vers RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760523"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Exporter des listes de segments vers RollWorks (version préliminaire)

Exportez des segments de profils client unifiés vers RollWorks et utilisez-les pour les activités de publicité. 

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [Compte RollWorks](https://www.rollworks.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 250 000 profils par exportation vers RollWorks.
- Vous ne pouvez pas exporter des segments avec moins de 100 profils vers RollWorks. 
- L’exportation vers RollWorks est limitée aux segments.
- L’exportation de jusqu’à 250 000 profils vers RollWorks peut prendre jusqu’à 10 minutes. 
- Le nombre de profils que vous pouvez exporter vers RollWorks dépend et est limité par votre contrat avec RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurer la connexion à RollWorks

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **RollWorks** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à RollWorks.

1. Sélectionnez **S’authentifier avec RollWorks** et fournissez vos informations d’identification administrateur pour RollWorks.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section RollWorks. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre **ID d’annonceur RollWorks** [Peut être annoncé dans RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Il est obligatoire d’exporter des segments vers RollWorks.

1. Sélectionnez les segments que vous souhaitez exporter. Sélectionnez un segment avec au moins 100 membres. Vous ne pouvez pas exporter des segments plus petits. De plus, la taille maximale d’un segment à exporter est de 250 000 membres par exportation. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers RollWorks, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que RollWorks respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
