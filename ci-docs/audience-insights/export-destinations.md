---
title: Exporter des données de Customer Insights
description: Gérez les exportations pour partager des données.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539340"
---
# <a name="exports-preview-overview"></a>Vue d’ensemble des exportations (version préliminaire)

La page **Exportations** affiche toutes les exportations configurées. Les exportations partagent des données spécifiques avec diverses applications. Elles peuvent inclure des profils ou entités client, des schémas et des détails de mappage. Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md).

Accédez à **Données** > **Exportations** pour afficher la page des exportations. Tous les rôles d’utilisateur peuvent afficher les exportations configurées. Utilisez le champ de recherche dans la barre de commandes pour rechercher des exportations par leur nom, nom de connexion ou type de connexion.

## <a name="set-up-a-new-export"></a>Configurer une nouvelle exportation

Pour configurer ou modifier une exportation, vous devez avoir des connexions disponibles. Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :
- Les administrateurs ont accès à toutes les connexions. Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.
- Les contributeurs peuvent avoir accès à des connexions spécifiques. Ils dépendent des administrateurs pour configurer et partager des connexions. La liste des exportations indique aux contributeurs s'ils peuvent modifier ou uniquement afficher une exportation dans la colonne **Vos autorisations**. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Les utilisateurs peuvent uniquement afficher les exportations existantes, mais pas les créer.

### <a name="define-a-new-export"></a>Définir une nouvelle exportation

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation** pour créer une nouvelle exportation.

1. Dans le volet **Configurer l’exportation**, sélectionnez la connexion à utiliser. Les [Connexions](connections.md) sont gérées par les administrateurs. 

1. Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Définir une nouvelle exportation basée sur une exportation existante

1. Accédez à **Données** > **Exportations**.

1. Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez dupliquer.

1. Sélectionnez **Créer un doublon** dans la barre de commandes pour ouvrir le volet **Configurer l'exportation** avec les détails de l'exportation sélectionnée.

1. Vérifiez et adaptez l'exportation et sélectionnez **Enregistrer** pour créer une exportation.

### <a name="edit-an-export"></a>Modifier une exportation

1. Accédez à **Données** > **Exportations**.

1. Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez modifier.

1. Sélectionnez **Modifier** dans la barre de commandes.

1. Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.

## <a name="view-exports-and-export-details"></a>Afficher les exportations et les détails de l’exportation

Une fois les destinations d’exportation créées, elles sont répertoriées dans **Données** > **Exportations**. Tous les utilisateurs peuvent voir les données partagées et leur statut le plus récent.

1. Accédez à **Données** > **Exportations**.

1. Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.

1. Le volet latéral montre la configuration d'une exportation. Sans autorisations de modification, vous ne pouvez pas modifier les valeurs. Sélectionnez **Fermer** pour revenir à la page des exportations.

## <a name="schedule-and-run-exports"></a>Planifier et exécuter les exportations

Chaque exportation que vous configurez comporte une planification d’actualisation. Lors d'une actualisation, le système recherche des données nouvelles ou mises à jour à inclure dans une exportation. Par défaut, les exportations sont exécutées dans le cadre de chaque [actualisation du système planifiée](system.md#schedule-tab). Vous pouvez personnaliser la planification d’actualisation ou la désactiver pour exécuter les exportations manuellement.

Les planifications d'exportation dépendent de l'état de votre environnement. Si des mises à jour sont en cours sur les [dépendances](system.md#refresh-policies) lorsqu’une exportation planifiée doit commencer, le système finalisera d’abord les mises à jour, puis exécutera l’exportation. Vous pouvez consulter les informations relatives à la dernière actualisation d'une exportation dans la colonne **Actualisé**.

### <a name="schedule-exports"></a>Panifier des exportations

Vous pouvez définir des planifications d’actualisation personnalisées pour des exportations individuelles ou plusieurs exportations à la fois. La planification actuellement définie est répertoriée dans la colonne **Planifier** de la liste d'exportations. L'autorisation nécessaire pour modifier la planification est la même que pour [modifier et définir des exportations](export-destinations.md#set-up-a-new-export). 

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez l'exportation à planifier.

1. Sélectionnez **Planifier** dans la barre de commandes.

1. Dans le volet **Planifier l'exportation**, définissez l'option **Planifier l'exécution** sur **Activé** pour exécuter l'exportation automatiquement. Définissez l'option sur **Désactivé** pour une actualisation manuelle.

1. Pour que les exportations soient actualisées automatiquement, choisissez une valeur **Périodicité** et spécifiez les détails de celle-ci. Le temps défini s'applique à toutes les instances d'une périodicité. C'est le moment où l'actualisation d'une exportation doit commencer.

1. Appliquez et activez vos modifications en sélectionnant **Enregistrer**.

Lorsque vous modifiez la planification de plusieurs exportations, vous devez effectuer une sélection sous **Conserver ou remplacer les planifications** :
- **Conserver les planifications individuelles** : conserver la planification précédemment définie pour les exportations sélectionnées et uniquement les désactiver ou les activer.
- **Définir une nouvelle planification pour toutes les exportations sélectionnées** : remplacer les planifications existantes des exportations sélectionnées.

### <a name="run-exports-on-demand"></a>Exécuter des exportations à la demande

Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**.

- Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes. Cette action n'exécutera que les exportations ayant une planification active.
- Pour exécuter une seule exportation, sélectionnez-la dans la liste et sélectionnez **Exécuter** dans la barre de commandes. C'est de cette manière que vous exécutez les exportations sans planification active. 

## <a name="remove-an-export"></a>Supprimer une exportation

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez l'exportation à supprimer.

1. Sélectionnez **Supprimer** dans la barre de commandes.

1. Confirmez la suppression en sélectionnant **Supprimer** sur l’écran de confirmation.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
