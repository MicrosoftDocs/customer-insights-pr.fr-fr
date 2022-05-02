---
title: Exporter des données Customer Insights vers Braze
description: Découvrez comment configurer la connexion et exporter vers Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646069"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exporter des listes de segments vers Braze (version préliminaire)

Exportez des segments de profils clients unifiés vers Braze et utilisez-les pour les activités marketing.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte Braze](https://www.braze.com/) et des informations d’identification de l’administrateur correspondantes.
-   Vous avez des [segments configurés](segments.md) dans Customer Insights.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail et un ID client Braze. 

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

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Braze. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.  

3. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client ; dans le champ « ID client », sélectionnez le champ qui représente l’ID Braze du client. Il est nécessaire d’exporter des segments vers Braze. Les segments dans Braze seront créés avec le même nom de segment que dans Dynamics 365 Customer Insights. Vous pouvez choisir des champs facultatifs supplémentaires pour la correspondance des données. 

1. Cliquez sur **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Braze, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que Braze respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
