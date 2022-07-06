---
title: Exporter des segments vers Criteo (version préliminaire)
description: Découvrez comment configurer la connexion et exporter vers Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081130"
---
# <a name="export-segments-to-criteo-preview"></a>Exporter des segments vers Criteo (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir un marketing par e-mail et utiliser des groupes de clients spécifiques avec Criteo.

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte de reciblage dynamique Criteo](https://www.criteo.com/login/) et des informations d’identification de l’administrateur correspondantes.
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu'à 1 million de profils clients par exportation vers Criteo.
- L’exportation vers Criteo est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils clients peut prendre jusqu’à 30 minutes. 
- Le nombre de profils clients que vous pouvez exporter vers Criteo dépend de votre contrat et est limité à Criteo.

## <a name="set-up-connection-to-criteo"></a>Configurer la connexion à Criteo

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Criteo** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez **J’accepte** pour confirmer la **Confidentialité des données et conformité** et sélectionnez **Connecter** pour initialiser la connexion à Criteo.

1. Sélectionnez **S’authentifier auprès de Criteo** et fournissez votre nom d’utilisateur et vos informations d’identification administrateur pour Criteo. 

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Criteo. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible. 

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. 

1. En option, vous pouvez exporter l’**ID d’annonceur** et le **Nom**

1. Sélectionnez les segments que vous souhaitez exporter. 

1. Cliquez sur **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Criteo, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que Criteo respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](includes/footer-banner.md)]
