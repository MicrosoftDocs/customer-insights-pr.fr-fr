---
title: Présentation des connexions (version préliminaire)
description: Connexions à d’autres services de Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245508"
---
# <a name="connections-preview-overview"></a>Présentation des connexions (version préliminaire)

Les connexions sont essentielles pour activer le partage de données vers et depuis Customer Insights. Chaque connexion établit le partage de données avec un service spécifique. Utilisez les connexions pour [configurer des enrichissements tiers](enrichment-hub.md) et [configurer des exportations](export-destinations.md). La même connexion peut être utilisée plusieurs fois. Par exemple, une connexion à Dynamics 365 Marketing fonctionne pour plusieurs exportations et une connexion Leadspace peut être utilisée pour plusieurs enrichissements.

## <a name="export-connections"></a>Connexions pour les exportations

Seuls les administrateurs peuvent configurer de nouvelles connexions, mais ils peuvent [accorder l’accès aux contributeurs](#allow-contributors-to-use-a-connection-for-exports) pour qu’ils utilisent les connexions existantes. Les administrateurs contrôlent l’emplacement des données, les contributeurs définissent la charge utile et la fréquence correspondant à leurs besoins.

## <a name="enrichment-connections"></a>Connexions pour les enrichissements

Seuls les administrateurs peuvent configurer de nouvelles connexions, mais les connexions créées sont toujours disponibles à la fois pour les administrateurs et les contributeurs. Les administrateurs gèrent les informations d’identification et donnent leur consentement pour les transferts de données. Les connexions peuvent ensuite être utilisées pour les enrichissements à la fois par les administrateurs et les contributeurs.

## <a name="add-a-new-connection"></a>Ajouter une nouvelle connexion

### <a name="prerequisites"></a>Conditions préalables

- [Autorisations d’administrateur](permissions.md)
- Les autres services Microsoft, le cas échéant, se trouvent dans la même organisation

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez le type de connexion que vous souhaitez créer. Vous pouvez également sélectionner **Configurer** sur une vignette sur l’onglet **Découvrir**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Entrez les détails requis. Les champs exacts dépendent du service auquel vous vous connectez. Pour obtenir des informations sur les détails d’un type de connexion spécifique, consultez l’article sur le service cible.

1. Si vous [utilisez votre propre Key Vault](use-azure-key-vault.md) pour stocker des secrets, activez **Key Vault** et choisissez le secret dans la liste.

1. Passez en revue la confidentialité et conformité des données et sélectionnez **J'accepte**.

1. Pour créer la connexion, sélectionnez **Enregistrer**.

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à des tiers ou à d’autres produits Microsoft, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que le tiers respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette connexion à tout moment pour ne plus utiliser cette fonctionnalité.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Autoriser les contributeurs à utiliser une connexion pour les exportations

Lors de la configuration ou de la modification d’une connexion d’exportation, choisissez les utilisateurs autorisés à utiliser cette connexion spécifique pour définir des [exportations](export-destinations.md). Par défaut, une connexion est disponible pour les utilisateurs disposant d’un rôle d’administrateur. Modifiez le paramètre **Choisir qui peut utiliser cette connexion** et autorisez les utilisateurs disposant du rôle de contributeur à utiliser cette connexion.

- Les contributeurs ne pourront ni afficher ni modifier la connexion. Ils ne verront que le nom d’affichage et son type lors de la création d’une exportation.
- En partageant une connexion, vous autorisez les contributeurs à utiliser une connexion. Les contributeurs verront les connexions partagées lors de la configuration des exportations. Ils peuvent gérer chaque exportation qui utilise cette connexion spécifique.
- Vous pouvez modifier ce paramètre tout en conservant les exportations qui ont déjà été définies par les contributeurs.

## <a name="manage-existing-connections"></a>Gérer les connexions existantes

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez l'onglet **Enrichissement** ou **Exportations** pour afficher une liste des connexions d’enrichissement ou d’exportation, le type de connexion, sa date de création et les personnes qui y ont accès. Vous pouvez trier la liste de connexions par n'importe quelle colonne.

1. Sélectionnez la connexion pour afficher les actions disponibles.

   - **Modifier** la connexion.
   - [**Supprimer**](#remove-a-connection) une connexion.

### <a name="remove-a-connection"></a>Supprimer une connexion

Si la connexion que vous supprimez est utilisée par des enrichissements ou des exportations, commencez par les détacher ou les supprimer. La boîte de dialogue de suppression vous guide vers les enrichissements ou les exportations appropriés.

> [!TIP]
> Les enrichissements désactivés et les exportations détachées deviennent inactifs. Vous les réactivez en leur ajoutant une autre connexion dans la page [Enrichissements](enrichment-hub.md) ou [Exportations](export-destinations.md).

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez l'onglet **Enrichissement** ou **Exportations**.

1. Sélectionnez la connexion à supprimer.

1. Sélectionnez **Supprimer** dans la liste déroulante. Une boîte de dialogue de confirmation s’affiche.

   1. Si des enrichissements ou des exportations utilisent cette connexion, sélectionnez le bouton pour voir ce que la connexion utilise.
      - **Exportations :** choisissez soit **Supprimer** l’exportation soit **Détacher la connexion**. En détachant la connexion, vous conservez la configuration d’exportation, mais celle-ci ne sera exécutée que quand une autre connexion lui sera ajoutée.
      - **Enrichissements :** choisissez soit **Supprimer** soit **Désactiver** les enrichissements.
   1. Une fois que la connexion n’a plus de dépendances, revenez à **Administrateur** > **Connexions** et essayez de supprimer à nouveau la connexion.

1. Pour confirmer la suppression, sélectionnez **Supprimer**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurez des connexions avec des secrets gérés par votre propre Key Vault

Certaines connexions ont besoin de secrets comme des clés API ou des mots de passe. Certaines connexions prennent en charge les secrets stockés dans votre propre Key Vault. En savoir plus sur les connexions prises en charge et sur la configuration dans [votre propre Key Vault pour Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
