---
title: Mappages sémantiques (version préliminaire)
description: Présentation et utilisation des mappages sémantiques.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183628"
---
# <a name="semantic-mappings-preview"></a>Mappages sémantiques (version préliminaire)

Les mappages sémantiques vous permettent de mapper vos données de non-activité à des schémas prédéfinis. Ces schémas aident Customer Insights à mieux comprendre vos attributs de données. Le mappage sémantique et les données fournies permettent de nouvelles informations et fonctionnalités dans Customer Insights. Pour mapper vos données d’activité aux schémas, consultez la documentation des [activités](activities.md).

**Les mappages sémantiques sont actuellement activés pour les environnements basés sur des comptes d’entreprise**. *ContactProfile* est le seul type de mappage sémantique actuellement disponible dans Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Définir un mappage d’entité sémantique ContactProfile

1. Accédez à **Données** > **Mappages sémantiques (version préliminaire)**.

1. Sélectionnez **Ajouter un mappage sémantique** pour commencer l’expérience guidée.

1. À l’étape **Données d’entité**, définissez les valeurs des champs suivants :

   - **Nom de mappage d’entité sémantique** : nom pour votre mappage d’entité sémantique.
   - **Entité source** : entité contenant des données de contact.
   - **Clé primaire** : champ qui identifie de manière unique un enregistrement de contact. Il ne doit contenir aucune valeur en double, vide ou manquante.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurez le mappage d’entité sémantique avec le nom, l’entité source et la clé primaire.":::

1. Cliquez sur **Suivant**.

1. À l’étape **Relation**, configurez les détails pour connecter vos données de contact aux données de compte correspondantes. Cette étape visualise la connexion entre les entités.  

   Il existe deux types de chemins relationnels qui peuvent être implémentés : **Relations directes** et **Relations indirectes**. Pour plus d’informations, accédez aux [chemins relationnels directs et indirects](relationships.md#relationship-paths).

   1. Sélectionnez **Ajouter une relation** pour configurer la relation.
   1. Choisissez l’attribut de votre entité source qui relie votre entité de contact à une autre entité.
   1. Choisissez l’entité à laquelle connecter votre entité de contact. Choisissez une entité dans la section **Entités de compte** ou **Entité intermédiaire**. Si vous sélectionnez une entité intermédiaire, définissez une seconde relation pour vous connecter à votre entité de compte cible.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Sélectionnez soit une entité de compte, soit une entité intermédiaire.":::

   1. Fournissez le **Nom de la relation**. Si une relation entre vos entités existe déjà, le nom de la relation est en lecture seule. Si aucune relation n’existe, une nouvelle relation est créée avec le nom que vous fournissez.
   1. Sélectionnez **Appliquer** pour terminer la configuration de la relation.

   > [!NOTE]
   > Vous pouvez configurer plus de relations entre l’entité de contact et d’autres entités de compte avec des entités intermédiaires.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisation de diverses relations qui connectent les entités de contact aux entités de compte.":::

1. Cliquez sur **Suivant**.

1. À l’étape **Définir le type sémantique**, choisissez un **Type sémantique**. Actuellement, il existe un **Type sémantique** appelé *ContactProfile*.

1. Mappez votre ID de contact au type sémantique *ContactProfile* **ID de contact**. Si nécessaire, mappez d’autres champs tels que prénom, nom, genre ou e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mappez les attributs de vos données de contact aux champs obligatoires et facultatifs fournis.":::

1. Cliquez sur **Suivant**.

1. À l’étape **Vérifier**, examinez la configuration du mappage sémantique. Sélectionnez **Modifier** pour la section correspondante afin d’apporter des modifications.

1. Cliquez sur **Enregistrer**.

1. Pour traiter le mappage sémantique, sélectionnez **Exécuter**. Ou sélectionnez **Fermer** pour enregistrer votre mappage sémantique sans le traiter. Pour l’exécuter ultérieurement, sélectionnez le mappage sémantique et sélectionnez **Actualiser**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gérer les mappages sémantiques existants

Accédez à **Données** > **Mappages sémantiques (version préliminaire)** pour afficher vos mappages sémantiques enregistrés, leur entité source, leur type sémantique, leur type de mappage et leur statut.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Options pour gérer les mappages sémantiques.":::

Sélectionnez le mappage sémantique pour afficher les actions disponibles.
- **Modifiez** la configuration actuelle. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.
- **Actualisez** le mappage sémantique pour inclure les dernières données. L’actualisation d’un mappage sémantique donné actualise tous les mappages sémantiques du même type.
- **Renommez** le mappage sémantique. Cliquez sur **Enregistrer**.
- **Supprimez** le mappage sémantique. Pour supprimer plusieurs mappages sémantiques à la fois, sélectionnez les mappages sémantiques et l’icône de suppression. Sélectionnez **Supprimer** pour confirmer la suppression.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utiliser un mappage d’entité sémantique ContactProfile pour créer des activités au niveau du contact

Après avoir créé un mappage d’entité sémantique *ContactProfile*, vous pouvez capturer les activités des contacts. Il vous permet de voir dans la chronologie des activités d’un compte quel contact était responsable de chaque activité. La plupart des étapes suivent la configuration du mappage d’activité classique.

   > [!NOTE]
   > Pour que les activités au niveau du contact puissent fonctionner, vous devez avoir les deux attributs **AccountID** et **ContactID** pour chaque enregistrement dans vos données d’activité.

1. [Définissez un mappage d’entités sémantiques *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) et exécutez le mappage sémantique.

1. Accédez à **Données** > **Activités**.

1. Sélectionnez **Ajouter une activité** pour créer une nouvelle activité.

1. Nommez l’activité, sélectionnez l’entité d’activité source et sélectionnez la clé primaire de l’entité d’activité.

1. Dans l’étape **Relations**, créez une relation indirecte entre vos données d’activité sources et vos comptes, en utilisant vos données de contact comme entité intermédiaire. Pour plus d’informations, consultez [Chemins de relations directes et indirectes](relationships.md#relationship-paths).
   - Exemple de relation pour une activité appelée *Achats* :
      - **Données d’activité sources des achats** > **Données du contact** sur l’attribut **ContactID**
      - **Données du contact** > **Données du compte** sur l’attribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuration d’un exemple de relation.":::

1. Après avoir configuré la ou les relations, sélectionnez **Suivant** et finalisez la configuration de votre mappage d’activité. Pour obtenir des étapes détaillées sur la création d’une activité, consultez [Définir une activité](activities.md).

1. Exécutez vos mappages d’activité.

1. Après l’exécution d’un mappage d’activités au niveau du contact, sélectionnez **Clients**. Les activités au niveau du contact s’affichent sur votre chronologie client.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Résultat final après configuration des activités du contact":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrage de la chronologie des activités au niveau du contact

Le chronologie de l’activité pour vos clients inclut leurs ID ou noms, selon votre configuration *ContactProfile*, pour les activités concernées. Filtrez les activités par contacts dans la chronologie pour voir les contacts spécifiques qui vous intéressent. Pour afficher toutes les activités qui ne sont pas affectées à un contact spécifique, sélectionnez **Activités non mappées à un contact**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Options de filtrage disponibles pour les activités au niveau du contact.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
