---
title: Exporter des données Customer Insights vers Microsoft Advertising
description: Apprenez à configurer la connexion et à exporter vers Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f009ed0258ded424340061e5320dd7df68c199f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226888"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exporter des segments vers Microsoft Advertising (version préliminaire)

Exportez les segments Customer Insights vers Microsoft Advertising pour créer des audiences Customer Match. Utilisez ces audiences pour vos campagnes publicitaires.

## <a name="prerequisites"></a>Conditions préalables

-   Un [compte Microsoft Advertising](https://ads.microsoft.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez accepté les conditions d'utilisation Customer Match. 
-   [Segments configurés](segments.md) dans les informations sur l’audience.
-   Les profils client unifiés dans les segments exportés contiennent un champ avec une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 500 000 profils clients par exportation vers Microsoft Advertising.
- L’exportation vers Microsoft Advertising est limitée aux segments.
- L’exportation d’un maximum de 500 000 profils clients vers Microsoft Advertising peut prendre jusqu’à 10 minutes. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurer la connexion à Microsoft Advertising

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Microsoft Advertising** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, ce sont les administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Microsoft Advertising.

1. Sélectionnez **S’authentifier avec Microsoft Advertising** et fournissez vos informations d’identification administrateur pour Microsoft Advertising.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Microsoft Advertising. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Sélectionner les segments à exporter. Les audiences Customer Match dans Microsoft Advertising sont automatiquement créées avec le nom des segments sélectionnés pour l'exportation. Chaque segment aboutira à une audience Customer Match distincte. 

1. Entrez votre **ID client et ID de compte Microsoft Advertising**. Vous pouvez trouver l'ID client (`cid`) et l'ID de compte (`aid`) dans les paramètres de l'URL lorsque vous êtes connecté à Microsoft Advertising.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ contenant l’adresse e-mail d’un client. Il est obligatoire d’exporter des segments vers Microsoft Advertising.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Microsoft Advertising, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Microsoft Advertising respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour stopper l'utilisation de cette fonctionnalité.
