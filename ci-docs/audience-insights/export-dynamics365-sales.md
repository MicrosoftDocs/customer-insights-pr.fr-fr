---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Apprenez à configurer la connexion et à exporter vers Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759588"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Utiliser des segments dans Dynamics 365 Sales (version préliminaire)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Conditions préalables à une connexion

1. Les enregistrements de contact doivent être présents dans Dynamics 365 Sales avant de pouvoir exporter un segment de Customer Insights vers Sales. En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Sales utilisant Common Data Services](connect-power-query.md).

   > [!NOTE]
   > L’exportation de segments des informations sur l’audience vers Sales ne créera pas des enregistrements de contact dans les instances Sales. Les enregistrements de contact de Sales doivent être intégrés aux informations sur l’audience et utilisés comme source de données. Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.

## <a name="set-up-the-connection-to-sales"></a>Configurer la connexion à Sales

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Dynamics 365 Sales** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.

1. Mappez un champ d’ID de client à l’ID de contact Dynamics 365.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Dynamics 365 Sales. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Choisissez un ou plusieurs segments.

1. Cliquez sur **Enregistrer**

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
