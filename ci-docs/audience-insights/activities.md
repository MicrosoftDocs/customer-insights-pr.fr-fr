---
title: Activités du client
description: Définissez les activités client et affichez-les dans la chronologie client.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 6ebe899d3e3da43c4108678cd2e4f9a986e18ab35e839044becab4619adb0f14
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033628"
---
# <a name="customer-activities"></a>Activités du client

Combinez les activités client de [différentes sources de données](data-sources.md) dans Dynamics 365 Customer Insights pour créer une chronologie qui répertorie les activités dans l’ordre chronologique. Incluez la chronologie dans les applications Dynamics 365 avec la solution [Complément de carte client](customer-card-add-in.md), ou dans un tableau de bord Power BI.

## <a name="define-an-activity"></a>Définir une activité

Vos sources de données peuvent inclure des entités avec des données transactionnelles et d’activité provenant de plusieurs sources de données. Identifiez ces entités et sélectionnez les activités que vous souhaitez afficher sur la chronologie du client. Sélectionnez l’entité qui comprend votre activité ou vos activités cibles.

> [!NOTE]
> Une entité doit avoir au moins un attribut de type **Date** à inclure dans une chronologie client et vous ne pouvez pas ajouter d’entités sans champs **Date**. Le contrôle **Ajouter une activité** est désactivé si aucune entité de ce type n’est trouvée.

1. Dans les informations sur l’audience, accédez à **Données** > **Activités**.

1. Sélectionnez **Ajouter une activité** pour démarrer l’expérience guidée du processus de configuration de l’activité.

1. Dans l’étape **Données de l’activité**, définissez les valeurs des champs suivants :

   - **Nom de l’activité** : Sélectionnez un nom pour votre activité.
   - **Entité** : Sélectionnez une entité qui contient des données transactionnelles ou d’activité.
   - **Clé primaire** : Sélectionnez le champ qui identifie de manière unique un enregistrement. Il ne doit contenir aucune valeur en double, vide ou manquante.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurez les données de l’activité avec le nom, l’entité et la clé primaire.":::

1. Sélectionnez **Suivant** pour passer à l’étape suivante.

1. Dans l’étape **Relation**, configurez les détails pour connecter vos données d’activité au client correspondant. Cette étape visualise la connexion entre les entités.  

   - **Premier** : champ externe de votre entité d’activité qui sera utilisé pour établir une relation avec une autre entité.
   - **Second** : entité client source correspondante avec laquelle votre entité d’activité sera en relation. Vous ne pouvez établir de relation qu’avec les entités client sources utilisées dans le processus d’unification des données.
   - **Troisième** : s’il existe déjà une relation entre cette entité d’activité et l’entité client source sélectionnée, le nom de la relation sera en mode lecture seule. S'il n’existe aucune relation de ce type, une nouvelle relation sera créée avec le nom que vous indiquez dans cette zone.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Définissez la relation entre les entités.":::

1. Sélectionnez **Suivant** pour passer à l’étape suivante. 

1. Dans l’étape **Unification de l’activité**, choisissez l’événement de l’activité et l’heure de début de votre activité. 
   - **Champs obligatoires**
      - **Activité de l’événement** : champ correspondant à l’événement de cette activité.
      - **Horodateur** : champ qui représente l’heure de début de votre activité.

   - **Champs facultatifs**
      - **Détails supplémentaires** : champ avec des informations pertinentes pour cette activité.
      - **Icône** : icône qui représente le mieux ce type d’activité.
      - **Adresse web** : champ contenant une URL avec des informations sur cette activité. Par exemple, le système transactionnel d’où provient cette activité. Cette URL peut être n’importe quel champ de la source de données, ou elle peut être construite comme un nouveau champ à l’aide d’une transformation Power Query. Les données de l’URL seront stockées dans l’entité *Activité unifiée*, qui peut être consommée en aval en utilisant les [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Spécifiez les données de l’activité client dans une entité Activité unifiée.":::

1. Sélectionnez **Suivant** pour passer à l’étape suivante. Vous pouvez sélectionner **Terminer et réviser** pour enregistrer l’activité maintenant avec le type d’activité défini sur **Autre**. 

1. Dans l’étape **Type d’activité**, choisissez le type d’activité et, éventuellement, sélectionnez si vous souhaitez mapper sémantiquement certains des types d’activités pour les utiliser dans d’autres zones de Customer Insights. Actuellement, les types d’activité *Abonnement* et *SalesOrderLine* peuvent être mappés sémantiquement après avoir accepté de mapper les champs. Si un type d’activité n’est pas pertinent pour la nouvelle activité, vous pouvez choisir *Autre* ou *Créer* pour un type d’activité personnalisé.

1. Sélectionnez **Suivant** pour passer à l’étape suivante. 

1. Dans l’étape **Réviser**, vérifiez vos sélections. Revenez à l’une des étapes précédentes et mettez à jour les informations si nécessaire.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Révisez les champs spécifiés d’une activité.":::
   
1. Sélectionnez **Enregistrer l’activité** pour appliquer vos modifications et sélectionnez **Terminé** pour revenir à **Données** > **Activités**. Ici vous voyez les activités qui sont définies pour s’afficher dans la chronologie. 

1. Dans la page **Activités**, sélectionnez **Exécuter** pour traiter l’activité. 

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.


## <a name="manage-existing-activities"></a>Gérer les activités existantes

Dans **Données** > **Activités**, vous pouvez afficher toutes vos activités enregistrées et les gérer. Chaque activité est représentée par une ligne qui comprend également des détails sur la source, l’entité et le type d’activité.

Les actions suivantes sont disponibles lorsque vous sélectionnez une activité. 

- **Modifier** : ouvre la configuration de l’activité dans l’étape de révision. Vous pouvez modifier tout ou partie de la configuration actuelle à partir de cette étape. Une fois la configuration modifiée, sélectionnez **Enregistrer l’activité**, puis sélectionnez **Exécuter** pour traiter les modifications.

- **Renommer** : ouvre une boîte de dialogue dans laquelle vous pouvez entre un autre nom pour l’activité sélectionnée. Sélectionnez **Enregistrer** pour appliquer vos modifications.

- **Supprimer** : ouvre une boîte de dialogue pour confirmer la suppression de l’activité sélectionnée. Vous pouvez également supprimer plusieurs activités à la fois en sélectionnant les activités, puis en sélectionnant l’icône de suppression. Sélectionnez **Supprimer** pour confirmer la suppression.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
