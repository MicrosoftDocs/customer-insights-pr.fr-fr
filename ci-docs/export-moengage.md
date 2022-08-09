---
title: Exporter des segments vers MoEngage
description: Découvrez comment configurer la connexion et exporter vers MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199120"
---
# <a name="export-segments-to-moengage-preview"></a>Exporter des segments vers MoEngage (version préliminaire)

Exportez des segments de profils clients unifiés vers MoEngage et utilisez-les pour le marketing par e-mail dans MoEngage.

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

- Un [compte MoEngage](https://www.moengage.com/) et des informations d’identification administrateur correspondantes.
- Clé API MoEngage depuis Paramètres > API dans MoEngage.
- [Segments configurés](segments.md) dans Customer Insights.

## <a name="known-limitations"></a>Limitations connues

- Un maximum de 100 000 profils clients par exportation vers MoEngage peut prendre jusqu’à 15 minutes. Le nombre de profils clients que vous pouvez exporter vers MoEngage dépend de votre contrat avec MoEngage.
- Segments uniquement.

## <a name="set-up-connection-to-moengage"></a>Configurer la connexion à MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **MoEngage** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez votre [ID d’API de données MoEngage et de clé API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion à MoEngage.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section MoEngage. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs optionnels.

1. Sélectionnez les segments que vous souhaitez exporter. Nous allons créer un ou plusieurs segments avec le même nom que les segments sélectionnés dans MoEngage sous **segments** > **Segments personnalisés**.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
