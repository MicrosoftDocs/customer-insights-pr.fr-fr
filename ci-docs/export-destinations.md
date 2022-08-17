---
title: Vue d’ensemble des exportations (version préliminaire)
description: Gérez les exportations pour partager des données.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245324"
---
# <a name="exports-preview-overview"></a>Vue d’ensemble des exportations (version préliminaire)

 Les exportations vous permettent de partager des données spécifiques avec diverses applications. Ils peuvent inclure des profils client, des entités, des schémas et des détails de mappage. Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md). La page **Exportations** affiche toutes les exportations configurées.

## <a name="export-types"></a>Types d’exportation

Il existe deux types principaux d’exportations :  

- Les **exportations de données de sortie** : exportez tout type d’entité disponible dans Customer Insights. Les entités que vous sélectionnez pour l’exportation sont exportées avec tous les champs de données, métadonnées, schémas et détails de mappage.
- Les **exportations de segments** : exportez des entités de segment à partir de Customer Insights. Les segments représentent une liste de profils clients. Lors de la configuration de l’exportation, vous sélectionnez les champs de données inclus, en fonction du système cible vers lequel vous exportez les données.

### <a name="export-segments"></a>Exporter les segments

**Exportation de segments dans des environnements pour les comptes professionnels (B2B) ou les clients particuliers (B2C)**  
La plupart des options d’exportation prennent en charge les deux types d’environnements. L’exportation de segments vers divers systèmes cibles a des exigences spécifiques. 

**Exportations de segments dans des environnements pour clients particuliers (B2C)**  
- Les segments dans le cadre des environnements pour les clients individuels sont construits sur l’entité *profil de client unifié*. Chaque segment qui répond aux exigences des systèmes cibles (par exemple, une adresse e-mail) peut être exporté.

**Segmenter les environnements d'exportation pour les comptes d'entreprise (B2B)**  
- Les segments dans le cadre des environnements pour les comptes professionnels sont construits sur l’entité *Compte*. Pour exporter des segments de compte tels quels, le système cible doit prendre en charge les segments de compte purs. C’est le cas pour [LinkedIn](export-linkedin-ads.md) lorsque vous choisissez l’option **entreprise** lors de la définition de l’export.
- Tous les autres systèmes cibles nécessitent des champs de l’entité de contact. Pour garantir que les segments de compte peuvent récupérer les données des contacts associés, votre définition de segment doit projeter les attributs de l’entité de contact. En savoir plus sur la façon de [configurer les segments et les attributs du projet](segment-builder.md).

**Limites sur les exportations de segments**  
- Les systèmes cibles tiers peuvent limiter le nombre de profils clients que vous pouvez exporter. 
- Pour les clients individuels, vous verrez le nombre réel de membres du segment lorsque vous sélectionnez un segment à exporter. Vous recevrez un avertissement si un segment est trop grand. 
- Pour les comptes professionnels, vous verrez le nombre de comptes dans un segment ; cependant, le nombre de contacts pouvant être projetés ne s’affiche pas. Dans certains cas, cela pourrait conduire à ce que le segment exporté contienne en réalité plus de profils clients que le système cible n’en accepte. Si les limites du système cible sont dépassées, l’exportation est ignorée.

## <a name="set-up-a-new-export"></a>Configurer une nouvelle exportation

Pour configurer ou modifier une exportation, vous devez avoir les bonnes connexions disponibles. Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :
- Les **administrateurs** ont accès à toutes les connexions. Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.
- Les **contributeurs** peuvent avoir accès à des connexions spécifiques. Ils dépendent des administrateurs pour configurer et partager des connexions. La liste des exportations indique aux contributeurs s'ils peuvent modifier ou uniquement afficher une exportation dans la colonne **Vos autorisations**. Pour plus d’informations, rendez-vous sur [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Les **spectateurs** ne peut afficher que les exportations existantes, pas les créer.

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation** pour créer une nouvelle exportation.

1. Dans le volet **Configurer l’exportation**, sélectionnez la [connexion](connections.md) à utiliser.

1. Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation. Pour les détails requis, consultez la documentation Customer Insights pour l’exportation spécifique.

## <a name="manage-existing-exports"></a>Gérer les exportations existantes

Accédez à **Données** > **Exportations** pour afficher les exportations, leur nom de connexion, leur type de connexion et leur état. Tous les rôles d’utilisateur peuvent afficher les exportations configurées. Vous pouvez trier la liste des exportations par colonne ou utiliser la zone de recherche pour trouver l’exportation que vous souhaitez gérer.

Sélectionnez une exportation pour afficher les actions disponibles.

:::image type="content" source="media/exports_showmore.png" alt-text="Page Exportations":::

- **Afficher** ou **Modifier** l’exportation. Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.
- **Exécuter** l’exportation pour exporter les dernières données.
- **Créer un doublon** d’une exportation.
- **[Planifier](#schedule-and-run-exports)** l’exportation.
- **Détacher la connexion** pour supprimer la connexion pour cette exportation. Le fait de détacher la connexion ne supprime pas cette dernière, mais désactive l’exportation. La colonne **Connexion utilisée** affiche Aucune connexion.
- **Supprimer** l’exportation.

## <a name="schedule-and-run-exports"></a>Planifier et exécuter les exportations

Chaque exportation que vous configurez comporte une planification d’actualisation. Lors d'une actualisation, le système recherche des données nouvelles ou mises à jour à inclure dans une exportation. Par défaut, les exportations sont exécutées dans le cadre de chaque [actualisation du système planifiée](schedule-refresh.md). Vous pouvez personnaliser la planification d’actualisation ou la désactiver pour exécuter les exportations manuellement.

Les planifications d'exportation dépendent de l'état de votre environnement. Si des mises à jour sont en cours sur les [dépendances](system.md#refresh-processes) lorsqu’une exportation planifiée doit commencer, le système finalisera d’abord les mises à jour, puis exécutera l’exportation. La colonne **Actualisé** indique la dernière actualisation d’une exportation.

### <a name="schedule-exports"></a>Panifier des exportations

Définissez des planifications d’actualisation personnalisées pour des exportations individuelles ou plusieurs exportations à la fois. La planification actuellement définie est répertoriée dans la colonne **Planifier** de la liste d'exportations. L’autorisation nécessaire pour modifier la planification est la même que pour [modifier et définir des exportations](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez l'exportation à planifier.

1. Sélectionnez **Planifier**.

1. Dans le volet **Planifier l'exportation**, définissez l'option **Planifier l'exécution** sur **Activé** pour exécuter l'exportation automatiquement. Définissez l'option sur **Désactivé** pour une actualisation manuelle.

1. Pour que les exportations soient actualisées automatiquement, choisissez une valeur **Périodicité** et spécifiez les détails de celle-ci. Le temps défini s'applique à toutes les instances d'une périodicité. C'est le moment où l'actualisation d'une exportation doit commencer.

1. Cliquez sur **Enregistrer**.

Lorsque vous modifiez la planification de plusieurs exportations, effectuez une sélection sous **Conserver ou remplacer les planifications** :

- **Conserver les planifications individuelles** : conserver la planification précédemment définie pour les exportations sélectionnées et uniquement les désactiver ou les activer.
- **Définir une nouvelle planification pour toutes les exportations sélectionnées** : remplacer les planifications existantes des exportations sélectionnées.

### <a name="run-exports-on-demand"></a>Exécuter des exportations à la demande

Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**.

- Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes. Cette action n’exécutera que les exportations ayant une planification active. Pour exécuter une exportation qui n’est pas active, exécutez une seule exportation.
- Pour exécuter une seule exportation, sélectionnez-la dans la liste et sélectionnez **Exécuter** dans la barre de commandes.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
