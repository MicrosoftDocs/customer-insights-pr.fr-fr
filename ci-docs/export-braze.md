---
title: Exporter des segments vers Braze (version préliminaire)
description: Découvrez comment configurer la connexion et exporter vers Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081107"
---
# <a name="export-segments-to-braze-preview"></a>Exporter des segments vers Braze (version préliminaire)

Exportez des segments de profils clients unifiés vers Braze et utilisez-les pour les activités marketing.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Braze](https://www.braze.com/) et les informations d’identification de l’administrateur correspondantes.
- [Segments existants dans Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail et un ID client Braze.

## <a name="known-limitations"></a>Limitations connues

- L’exportation vers Braze est limitée aux segments.
- L'exportation d’un maximum d’un million de profils clients vers Braze peut prendre jusqu’à 40 minutes.
- Le nombre de profils clients que vous pouvez exporter vers Braze dépend de votre contrat et est limité à Braze.

## <a name="set-up-connection-to-braze"></a>Configurer la connexion à Braze

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Braze** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez votre [clé API Braze](https://www.braze.com/docs/api/basics/) pour continuer la connexion.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connexion** pour initialiser la connexion à Braze.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Braze. Si cette section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.  

1. Ajoutez un **Nom complet** pour votre exportation.

1. Ajoutez l’identificateur de l’API du segment Braze vers lequel vous souhaitez exporter dans le champ **Identificateur de l’API du segment Braze**. Vous trouverez l’identificateur dans les détails du segment sur la plateforme Braze.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Dans le champ **ID client**, sélectionnez le champ représentant l’ID Braze du client. Il est nécessaire d’exporter des segments vers Braze. Vous pouvez éventuellement choisir d’autres champs.

1. Cliquez sur **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Braze, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que Braze respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
