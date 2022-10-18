---
title: Exporter des segments vers Braze (version préliminaire)
description: Découvrez comment configurer la connexion et exporter vers Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655272"
---
# <a name="export-segments-to-braze-preview"></a>Exporter des segments vers Braze (version préliminaire)

Exportez des segments de profils clients unifiés vers Braze et utilisez-les pour les activités marketing.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Braze](https://www.braze.com/) et les informations d’identification de l’administrateur correspondantes.
- Une [clé API Braze](https://www.braze.com/docs/api/basics/)
- Votre [point de terminaison REST Braze](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segments configurés](segments.md) dans Customer Insights.
- Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail et un ID client Braze.

## <a name="known-limitations"></a>Limitations connues

- Un maximum d’un million de profils clients vers Braze, ce qui peut prendre jusqu’à 40 minutes. Le nombre de profils clients que vous pouvez exporter vers Braze dépend de votre contrat avec Braze.
- Segments uniquement.
- Azure Private Link n’est pas pris en charge pour l’exportation Braze.

## <a name="set-up-connection-to-braze"></a>Configurer la connexion à Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Braze**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez votre clé API Braze pour continuer la connexion.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Connecter** pour initialiser la connexion.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Braze. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez votre point de terminaison REST dans le champ **Nom d’hôte** au format suivant : `rest.iad-03.braze.com`.

1. Entrez un nom pour l’exportation.

1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Dans le champ **ID client**, sélectionnez le champ représentant l’ID Braze du client. Les segments dans Braze seront créés avec le même nom de segment que dans Dynamics 365 Customer Insights. Vous pouvez choisir des champs facultatifs supplémentaires pour la correspondance des données.

1. Sélectionnez les entités ou des segments à exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
