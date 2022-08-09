---
title: Unifier les champs client pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139654"
---
# <a name="unify-customer-fields-for-data-unification"></a>Unifier les champs client pour l’unification des données

Dans cette étape du processus d’unification, choisissez et excluez les attributs à fusionner au sein de votre entité de profil unifié. Par exemple, si trois entités avaient des données d’e-mail, vous pouvez conserver les trois champs d’e-mail séparés ou les fusionner en un seul champ d’e-mail pour le profil unifié. Certains attributs sont automatiquement combinés par le système. Vous pouvez créer des ID client stables et uniques et regrouper des profils associés dans un cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Page de fusion dans le processus d’unification des données affichant une table avec des champs fusionnés qui définissent le profil client unifié.":::

## <a name="review-and-update-the-customer-fields"></a>Vérifier et mettre à jour les champs client

1. Passez en revue la liste des champs qui seront unifiés sous l’onglet **Champs client** du tableau. Apportez des modifications, le cas échéant.

   1. Pour tous les champs combinés, vous pouvez :
      - [Modifier](#edit-a-merged-field)
      - [Renommer](#rename-fields)
      - [Séparé](#separate-merged-fields)
      - [Exclure](#exclude-fields)
      - [Monter ou descendre](#change-the-order-of-fields)

   1. Pour tous les champs uniques, vous pouvez :
      - [Combiner des champs](#combine-fields-manually)
      - [Combiner un groupe de champs](#combine-a-group-of-fields)
      - [Renommer](#rename-fields)
      - [Exclure](#exclude-fields)
      - [Monter ou descendre](#change-the-order-of-fields)

1. [Générer la configuration de l’ID client](#configure-customer-id-generation) (facultatif).

1. [Regrouper les profils en foyers ou en clusters](#group-profiles-into-households-or-clusters) (facultatif).

> [!div class="nextstepaction"]
> [Étape suivante : examiner l’unification](review-unification.md)

### <a name="edit-a-merged-field"></a>Modifier un champ fusionné

1. Sélectionnez un champ fusionné et choisissez **Modifier**. Le volet Combiner les champs s’affiche.

1. Spécifiez comment combiner ou fusionner les champs de l’une des trois options :
    - **Importance** : identifie la valeur gagnante en fonction du rang d’importance spécifié pour les champs participants. C’est l’option de fusion par défaut. Sélectionnez **Monter/Descendre** pour définir le classement par importance.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Option Importance dans la boîte de dialogue de champs de fusion.":::

    - **Le plus récent** : identifie la valeur gagnante en fonction de l’ancienneté la plus faible. Nécessite une date ou un champ numérique pour chaque entité participante dans la portée des champs de fusion pour définir la récence.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Option Récence dans la boîte de dialogue de champs de fusion.":::

    - **Le moins récent** : identifie la valeur gagnante en fonction de l’ancienneté la plus grande. Nécessite une date ou un champ numérique pour chaque entité participante dans la portée des champs de fusion pour définir la récence.

1. Vous pouvez ajouter d’autres champs pour participer au processus de fusion.

1. Vous pouvez renommer le champ fusionné.

1. Sélectionnez **Terminé** pour appliquer vos modifications.

### <a name="rename-fields"></a>Renommer les champs

Modifiez le nom d’affichage des champs fusionnés ou séparés. Vous ne pouvez pas modifier le nom de l’entité de sortie.

1. Sélectionnez le champ et choisissez **Renommer**.

1. Entrez le nouveau nom d’affichage.

1. Cliquez sur **Terminé**.

### <a name="separate-merged-fields"></a>Champs fusionnés séparés

Pour séparer des champs fusionnés, recherchez l’attribut dans la table. Les champs séparés s’affichent sous forme de points de données individuels sur le profil client unifié.

1. Sélectionnez le champ fusionné et choisissez **Champs séparés**.

1. Confirmez la séparation.

### <a name="exclude-fields"></a>Exclure des champs

Excluez un champ fusionné ou séparé du profil client unifié. Si le champ est utilisé dans d’autres processus, par exemple dans un segment, supprimez-le de ces processus avant de l’exclure du profil client.

1. Sélectionnez un champ et choisissez **Exclure**.

1. Confirmez l’exclusion.

Pour voir la liste de tous les champs exclus, sélectionnez **Champs exclus**. Si nécessaire, vous pouvez lire le champ exclu.

### <a name="change-the-order-of-fields"></a>Modifier l’ordre des champs

Certaines entités contiennent plus de détails que d’autres. Si une entité inclut les dernières données concernant un champ, vous pouvez lui donner priorité par rapport aux autres entités lors de la fusion des valeurs.

1. Sélectionnez le champ.
  
1. Choisissez **Monter/descendre** pour définir l’ordre des champs ou faites-les glisser et déposez-les dans la position souhaitée.

### <a name="combine-fields-manually"></a>Combiner les champs manuellement

Combinez des champs séparés pour créer un attribut fusionné.

1. Sélectionnez **Combiner** > **Champs**. Le volet Combiner les champs s’affiche.

1. Spécifiez la stratégie gagnante de fusion dans le menu déroulant **Combiner les champs par**.

1. Sélectionnez **Ajouter un champ** pour combiner plusieurs champs.

1. Fournissez un **Nom** et un **Nom du champ de sortie**.

1. Sélectionnez **Terminé** pour appliquer les modifications.

### <a name="combine-a-group-of-fields"></a>Combiner un groupe de champs

Traitez un groupe de champs comme une seule unité. Par exemple, si nos enregistrements contiennent les champs Adresse1, Adresse2, Ville, État et Code postal, il est préférable de ne pas fusionner l’Adresse2 d’un enregistrement différent en nous disant que cela nous permettra de disposer de données plus complètes.

1. Sélectionnez **Combiner** > **Groupe de champs**.

1. Spécifiez la stratégie de gagnant de la fusion dans le menu déroulant **Classer les groupes par**.

1. Sélectionnez **Ajouter** et indiquez si vous souhaitez ajouter des champs ou des groupes aux champs.

1. Entrez un **Nom** et un **Nom de sortie** pour chaque champ combiné.

1. Entrez un **Nom** pour le groupe de champs.

1. Sélectionnez **Terminé** pour appliquer les modifications.

## <a name="configure-customer-id-generation"></a>Configurer la génération de l’ID client

Définissez comment générer des valeurs d’ID client, les identifiants uniques du profil client. L’étape d’unification des champs du processus d’unification des données génère l’identifiant de profil client unique. L’identificateur est le *CustomerId* de l’entité *Client* qui résulte du processus d’unification des données.

Le *CustomerId*  est basé sur un hachage de la première valeur des clés primaires gagnantes non nulles. Ces clés proviennent des entités utilisées dans l’unification des données et sont influencées par l’ordre de correspondance.Ainsi, l’ID client généré peut changer lorsqu’une valeur de clé primaire change dans l’entité principale de l’ordre de correspondance. La valeur de la clé primaire peut ne pas toujours représenter le même client.

La configuration d’un ID client stable vous permet d’éviter ce comportement.

1. Sélectionnez l’onglet **Clés**.

1. Survolez la ligne **CustomerId** et sélectionnez **Configurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Contrôle pour personnaliser la génération de l’ID.":::

1. Sélectionnez jusqu’à cinq champs qui comprennent un ID client unique et sont plus stables. Les enregistrements qui ne correspondent pas à votre configuration utilisent un ID configuré par le système à la place.  

1. Cliquez sur **Terminé**.

## <a name="group-profiles-into-households-or-clusters"></a>Regrouper les profils en foyers ou en clusters

Vous pouvez définir des règles pour regrouper des profils associés dans un cluster. Il existe actuellement deux types de clusters disponibles : les clusters domestiques et personnalisés. Le système choisit automatiquement un foyer avec des règles prédéfinies si l’entité *Client* contient les champs sémantiques *Person.LastName* et *Location.Address*. Vous pouvez également créer un cluster avec vos propres règles et conditions, similaires à des [règles de correspondance](match-entities.md#define-rules-for-match-pairs).

1. Sélectionnez **Avancé** > **Créer un cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Commande pour créer un cluster.":::

1. Choisissez entre un **Foyer** ou un cluster **Personnalisé**. Si les champs sémantiques *Person.LastName* et *Location.Address* existent dans l’entité *Client*, le foyer est automatiquement sélectionné.

1. Spécifiez un nom pour le cluster et sélectionnez **Terminé**.

1. Sélectionnez l’onglet **Clusters** pour trouver le cluster que vous avez créé.

1. Spécifiez les règles et conditions pour définir votre cluster.

1. Cliquez sur **Terminé**. Le cluster est créé une fois le processus d’unification terminé. Les identificateurs de cluster sont ajoutés en tant que nouveaux champs à l’entité *Client*.

> [!div class="nextstepaction"]
> [Étape suivante : examiner l’unification](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
