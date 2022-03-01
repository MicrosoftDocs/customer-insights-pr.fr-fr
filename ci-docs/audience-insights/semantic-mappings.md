---
title: Mappages sémantiques (version préliminaire)
description: Présentation et utilisation des mappages sémantiques.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622932"
---
# <a name="semantic-mappings"></a>Mappages sémantiques

Les mappages sémantiques vous permettent de mapper vos données de non-activité à des schémas prédéfinis. Ces schémas aident les informations d’audience à mieux comprendre vos attributs de données. Le mappage sémantique et les données fournies permettent de nouvelles informations et fonctionnalités dans les informations d’audience. Pour mapper vos données d’activité aux schémas, consultez la documentation des [activités](activities.md).

**Les mappages sémantiques sont actuellement activés pour les environnements basés sur des comptes d’entreprise**. *ContactProfile* est le seul type de mappage sémantique actuellement disponible dans les insights d’audience.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Définir un mappage d’entité sémantique ContactProfile

1. Dans les insights d’audience, accédez à **Données** > **Mappages sémantiques (version préliminaire)**.

1. Sélectionnez **Ajouter un mappage sémantique** pour commencer l’expérience guidée.

1. À l’étape **Données d’entité**, définissez les valeurs des champs suivants :

   - **Nom de mappage d’entité sémantique** : Fournissez un nom pour votre mappage d’entité sémantique.
   - **Entité source** : sélectionnez une entité contenant des données de contact.
   - **Clé primaire** : Sélectionnez le champ qui identifie de manière unique un enregistrement de contact. Il ne doit contenir aucune valeur en double, vide ou manquante.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurez le mappage d’entité sémantique avec le nom, l’entité source et la clé primaire.":::

1. Cliquez sur **Suivant** pour continuer.

1. À l’étape **Relation**, configurez les détails pour connecter vos données de contact aux données de compte correspondantes. Cette étape visualise la connexion entre les entités.  

   Il existe deux types de chemins relationnels qui peuvent être implémentés : **Relations directes** et **Relations indirectes**. Pour plus d’informations, accédez aux [chemins relationnels directs et indirects](relationships.md#relationship-paths).

   1. Sélectionnez **Ajouter une relation** pour configurer la relation.
   1. Choisissez l’attribut de votre entité source qui relie votre entité de contact à une autre entité.
   1. Choisissez l’entité à laquelle connecter votre entité de contact. Vous pouvez choisir une entité dans la section **Entités de compte** ou **Entité intermédiaire**. Si vous sélectionnez une entité intermédiaire, vous devez définir une seconde relation pour vous connecter à votre entité de compte cible.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Sélectionnez soit une entité de compte, soit une entité intermédiaire.":::

   1. Fournissez le **Nom de la relation**. Si une relation entre vos entités existe déjà, le nom de la relation est en lecture seule. Si aucune relation n’existe, une nouvelle relation est créée avec le nom que vous fournissez.
   1. Sélectionnez **Appliquer** pour terminer la configuration de la relation.

   > [!NOTE]
   > Vous pouvez configurer plus de relations entre l’entité de contact et d’autres entités de compte avec des entités intermédiaires.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisation de diverses relations qui connectent les entités de contact aux entités de compte.":::

1. Sélectionnez **Suivant** lorsque vous avez terminé la configuration de la relation.

1. À l’étape **Définir le type sémantique**, choisissez un **Type sémantique**. Actuellement, il existe un **Type sémantique** appelé *ContactProfile*.

1. Mappez vos données au **type de sémantique** *ContactProfile* pour les champs affichés.
   - Champ obligatoire : ID de contact
   - Champs facultatifs : Prénom, Nom, Date de naissance, Sexe, E-mail principal et Téléphone principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappez les attributs de vos données de contact aux champs obligatoires et facultatifs fournis.":::

1. Cliquez sur **Suivant** pour continuer.

1. À l’étape **Vérifier**, jetez un œil à la configuration du mappage sémantique. Sélectionnez **Modifier** pour la section correspondante pour apporter des modifications.

1. Sélectionnez **Enregistrer** pour enregistrer votre nouveau **Mappage sémantique**.

1. Après l’enregistrement, vous pouvez sélectionner **Exécuter** pour traiter le mappage sémantique ou vous pouvez sélectionner **Fermer** pour enregistrer votre mappage sémantique sans le traiter.

1. Pour exécuter un mappage sémantique ultérieurement, sélectionnez le mappage sémantique et sélectionnez **Actualiser**.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="manage-existing-semantic-mappings"></a>Gérer les mappages sémantiques existants

Dans **Données** > **Mappages sémantiques (version préliminaire)**, vous pouvez afficher tous vos mappages sémantiques enregistrés et les gérer. Chaque mappage sémantique est représenté par une ligne distincte. Vous trouverez des détails sur l’entité source, le type sémantique, le type de mappage et son statut.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Options pour gérer les mappages sémantiques.":::

- **Modifier** : ouvre la configuration du mappage sémantique à l’étape de vérification. Vous pouvez modifier la configuration actuelle. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.

- **Actualiser** : Actualise le mappage sémantique sélectionné avec les données les plus récentes des entités qui font partie de sa configuration. L’actualisation d’un mappage sémantique donné actualise tous les mappages sémantiques du même type.

- **Renommer** : ouvre une boîte de dialogue dans laquelle vous pouvez entrer un nom différent pour le mappage sémantique sélectionné. Sélectionnez **Enregistrer** pour appliquer vos modifications.

- **Supprimer** : Ouvre une boîte de dialogue pour confirmer la suppression du mappage sémantique sélectionné. Vous pouvez également supprimer plusieurs mappages sémantiques à la fois en sélectionnant les mappages sémantiques et l’icône de suppression. Sélectionnez **Supprimer** pour confirmer la suppression.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
