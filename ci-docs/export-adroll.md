---
title: Exporter des segments vers AdRoll (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081138"
---
# <a name="export-segments-to-adroll-preview"></a>Exporter des segments vers AdRoll (version préliminaire)

Exportez des segments de profils clients unifiés vers AdRoll et utilisez-les pour la publicité. 

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

- Vous disposez d’un [compte AdRoll](https://www.adroll.com/) et des informations d’identification administrateur correspondantes.
- Vous avez des [segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 250 000 profils clients à la fois vers AdRoll.
- Vous ne pouvez pas exporter des segments avec moins de 100 profils clients vers AdRoll. 
- L’exportation vers AdRoll est limitée aux segments.
- L’exportation d’un maximum de 250 000 profils clients vers AdRoll peut prendre jusqu’à 10 minutes. 
- Le nombre de profils clients que vous pouvez exporter vers AdRoll dépend de votre contrat avec AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurer la connexion à AdRoll

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **AdRoll** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à AdRoll.

1. Sélectionnez **S’authentifier avec AdRoll** et fournissez vos informations d’administrateur pour AdRoll. 

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section AdRoll. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Entrez votre **ID d’annonceur AdRoll**. Pour plus d’informations, voir [Profils d’annonceur AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Il est nécessaire d’exporter des segments vers AdRoll.

1. Sélectionnez les segments que vous souhaitez exporter. Sélectionnez un segment avec au moins 100 membres. Vous ne pouvez pas exporter des segments plus petits. De plus, la taille maximale d’un segment à exporter est de 250 000 membres par exportation. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). 

Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers AdRoll, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que AdRoll respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
