---
title: Exporter des données Customer Insights vers Marketo
description: Apprenez à configurer la connexion et à exporter vers Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d56ed779c342bb0855ee84d949f8d3ca604b92c1
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487512"
---
# <a name="export-segments-to-marketo-preview"></a>Exporter des segments vers Marketo (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir des activités de marketing par e-mail et utiliser certains groupes de clients avec Marketo.

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

-   Vous disposez d’un [compte Marketo](https://login.marketo.com/) et des informations d’identification administrateur correspondantes.
-   Il existe des listes dans Marketo et les ID correspondants. Pour plus d’informations, consultez [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils clients par exportation vers Marketo.
- L’exportation vers Marketo est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils clients peut prendre jusqu’à 3 heures. 
- Le nombre de profils clients que vous pouvez exporter vers Marketo dépend de votre contrat et est limité à Marketo.

## <a name="set-up-connection-to-marketo"></a>Configurer la connexion à Marketo

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Marketo** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez vos **[ID de client Marketo, secret client et nom d’hôte du point de terminaison REST](https://developers.marketo.com/rest-api/authentication/)**. Le nom d’hôte du point de terminaison REST est le nom d’hôte uniquement, sans `https://`. Exemple :`xyz-abc-123.mktorest.com`. 

1. Sélectionnez **J’accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Marketo.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Marketo. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre **[ID de liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. L’ID de liste est une valeur purement numérique. Par exemple, si votre ID de liste Marketo est ST12345A7, supprimez le caractère avant et après les chiffres et saisissez `12345`. 

1. Dans la section **Correspondance des données**, sélectionnez au moins un champ qui représente l’adresse e-mail d’un client ou l’ID Marketo d’un client. 

1. Vous pouvez éventuellement exporter le **Prénom**, le **Nom**, la **Ville**, le **Département** et le/la **Pays/région** pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Marketo.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). Dans Marketo, vous trouverez désormais vos segments sous [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Marketo, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Marketo respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
