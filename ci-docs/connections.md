---
title: Présentation des connexions (version préliminaire)
description: Connexions à d’autres services de Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: a8b4b8a9bdcf7cf43c47a67d547405dd20dad60d
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080973"
---
# <a name="connections-preview-overview"></a>Présentation des connexions (version préliminaire)

Les connexions sont essentielles pour activer le partage de données vers et depuis Customer Insights. Chaque connexion établit le partage de données avec un service spécifique. Les connexions sont la base pour [configurer des enrichissements tiers](enrichment-hub.md) et [configurer des exportations](export-destinations.md). La même connexion peut être utilisée plusieurs fois. Par exemple, une connexion à Dynamics 365 Marketing fonctionne pour plusieurs exportations et une connexion Leadspace peut être utilisée pour plusieurs enrichissements.

Accédez à **Administrateur** > **Connexions** pour créer et afficher les connexions.

L’onglet **Connexions** affiche toutes les connexions actives. La liste affiche une ligne pour chaque connexion.

Obtenez une description générale rapide et découvrez ce que vous pouvez faire avec chaque option d’extensibilité dans l’onglet **Découvrir**.

## <a name="exports"></a>Exportations

Seuls les administrateurs peuvent configurer de nouvelles connexions, mais ils peuvent accorder l’accès aux contributeurs pour qu’ils utilisent les connexions existantes. Les administrateurs contrôlent l’emplacement des données, les contributeurs définissent la charge utile et la fréquence correspondant à leurs besoins. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Enrichissements

Seuls les administrateurs peuvent configurer de nouvelles connexions, mais les connexions créées sont toujours disponibles à la fois pour les administrateurs et les contributeurs. Les administrateurs gèrent les informations d’identification et donnent leur consentement pour les transferts de données. Les connexions peuvent ensuite être utilisées pour les enrichissements à la fois par les administrateurs et les contributeurs.

## <a name="add-a-new-connection"></a>Ajouter une nouvelle connexion

Pour ajouter des connexions, vous devez disposer d’[autorisations administrateur](permissions.md). Si vous vous connectez à d’autres services Microsoft, nous supposons que les deux services se trouvent dans la même organisation.

1. Accédez à **Administrateur** > **Connexions (version préliminaire)**.

1. Accédez à l’onglet **Connexions**.

1. Sélectionnez **Ajouter une connexion** pour créer une connexion. Choisissez dans le menu déroulant le type de connexion que vous souhaitez créer.

1. Dans le volet **Configurer la connexion**, fournissez les détails nécessaires.
   1. Le **Nom d’affichage** et le type de connexion décrivent une connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de cette connexion.
   1. Les champs exacts dépendent du service auquel vous vous connectez. Vous pouvez obtenir des informations sur les détails d’un type de connexion spécifique dans l’article sur le service cible.
   1. Si vous [utilisez votre propre Key Vault](use-azure-key-vault.md) pour stocker des secrets, activez **Key Vault** et choisissez le secret dans la liste.

1. Pour créer la connexion, sélectionnez **Enregistrer**.

Vous pouvez également sélectionner **Configurer** sur une vignette sur l’onglet **Découvrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Autoriser les contributeurs à utiliser une connexion pour les exportations

Lors de la configuration ou de la modification d’une connexion d’exportation, vous choisissez les utilisateurs autorisés à utiliser cette connexion spécifique pour définir des [exportations](export-destinations.md). Par défaut, une connexion est disponible pour les utilisateurs disposant d’un rôle d’administrateur. Vous pouvez modifier ce paramètre dans **Choisir qui peut utiliser cette connexion** et autoriser les utilisateurs disposant du rôle de contributeur à utiliser cette connexion.

- Les contributeurs ne pourront ni afficher ni modifier la connexion. Ils ne verront que le nom d’affichage et son type lors de la création d’une exportation.
- En partageant une connexion, vous autorisez les contributeurs à utiliser une connexion. Les contributeurs verront les connexions partagées lors de la configuration des exportations. Ils peuvent gérer chaque exportation qui utilise cette connexion spécifique.
- Vous pouvez modifier ce paramètre tout en conservant les exportations qui ont déjà été définies par les contributeurs.

## <a name="edit-a-connection"></a>Modifier une connexion

1. Accédez à **Administrateur** > **Connexions (version préliminaire)**.

1. Accédez à l’onglet **Connexions**.

1. Sélectionnez les points de suspension verticaux (&vellip;) de la connexion que vous souhaitez modifier.

1. Cliquez sur **Modifier**.

1. Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.

## <a name="remove-a-connection"></a>Supprimer une connexion

Si la connexion que vous supprimez est utilisée par des enrichissements ou des exportations, vous devez d’abord les détacher ou les supprimer. La boîte de dialogue de suppression vous guidera vers les enrichissements ou les exportations appropriés.

Les enrichissements et les exportations détachés deviennent inactifs. Vous les réactivez en leur ajoutant une autre connexion dans la page [Enrichissements](enrichment-hub.md) ou [Exportations](export-destinations.md).

1. Accédez à **Administrateur** > **Connexions (version préliminaire)**.

1. Accédez à l’onglet **Connexions**.

1. Sélectionnez les points de suspension verticaux (&vellip;) de la connexion que vous souhaitez supprimer.

1. Sélectionnez **Supprimer** dans la liste déroulante. Une boîte de dialogue de confirmation s’affiche.

   1. Si des enrichissements ou des exportations utilisent cette connexion, sélectionnez le bouton pour voir ce que la connexion utilise.
      - **Exportations :** vous pouvez choisir de supprimer ou de déconnecter les exportations pour pouvoir supprimer la connexion. Pour déconnecter une exportation, les administrateurs peuvent utiliser l’action **Déconnecter**. Cette action est disponible pour les exportations sélectionnées individuelles et multiples. En déconnectant une exportation, vous conservez la configuration d’exportation, mais celle-ci ne sera exécutée que quand une autre connexion lui sera ajoutée.
      - **Enrichissements :** vous pouvez choisir de supprimer ou de désactiver les enrichissements pour pouvoir supprimer la connexion.
   1. Une fois que la connexion n’a plus de dépendances, revenez à **Administrateur** > **Connexions** et essayez de supprimer à nouveau la connexion.

1. Pour confirmer la suppression, sélectionnez **Supprimer**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurez des connexions avec des secrets gérés par votre propre Key Vault

Certaines connexions ont besoin de secrets comme des clés API ou des mots de passe. Certaines connexions prennent en charge les secrets stockés dans votre propre Key Vault. En savoir plus sur les connexions prises en charge et sur la configuration dans [votre propre Key Vault pour Customer Insights](use-azure-key-vault.md).
