---
title: Activités du client
description: Définissez les activités clientes et visualisez-les dans une chronologie des profils clients.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188136"
---
# <a name="customer-activities"></a>Activités du client

Les activités client sont des actions ou des événements effectués par les clients. Par exemple, les transactions, la durée des appels au support, les avis sur le site web, les achats ou les retours. Ces activités sont contenues dans une ou plusieurs sources de données. Avec Customers Insights, consolidez vos activités clients à partir de ces [sources d’informations](data-sources.md) et associez-les à des profils clients. Ces activités s’affichent chronologiquement sur le profil client. Intégrez la chronologie dans les applications Dynamics 365 avec la solution [Complément de carte client](customer-card-add-in.md).

## <a name="define-an-activity"></a>Définir une activité

Pour être incluse dans une chronologie client, une entité doit avoir au moins un attribut du type **Date**. Le contrôle **Ajouter une activité** est désactivé si aucune entité de ce type n’est trouvée.

1. Accédez à **Données** > **Activités**.

1. Sélectionnez **Ajouter une activité** pour commencer l’expérience guidée.

1. Lors de l’étape **Données d’activité**, saisissez les informations suivantes :

   - **Nom de l’activité** : nom de votre activité.
   - **Entité de l’activité** : entité qui contient des données transactionnelles ou d’activité.
   - **Clé primaire** : champ identifiant de manière unique un enregistrement. Il ne doit contenir aucune valeur en double, vide ou manquante.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configurez les données de l’activité avec le nom, l’entité et la clé primaire.":::

1. Cliquez sur **Suivant**.

1. Lors de l’étape **Relation**, sélectionnez **Ajouter une relation** pour connecter vos données d’activité à l’enregistrement client correspondant. Cette étape visualise la connexion entre les entités.  

   - **Clé étrangère de l’entité** : champ de votre entité d’activité qui sera utilisé pour établir une relation avec une autre entité.
   - **Au nom de l’entité** : entité client source correspondante avec laquelle votre entité d’activité sera en relation. Vous ne pouvez établir de relation qu’avec les entités client sources utilisées dans le processus d’unification des données.
   - **Nom de la relation** : nom identifiant la relation entre les entités. S’il existe déjà une relation entre cette entité d’activité et l’entité client source sélectionnée, le nom de la relation est en mode lecture seule.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Définissez la relation entre les entités.":::

   > [!TIP]
   > Dans les environnements B2B, vous pouvez choisir entre des entités de compte et d’autres entités. Si vous sélectionnez une entité de compte, le chemin de la relation est automatiquement défini. Pour les autres entités, vous devez définir le chemin de la relation sur une ou plusieurs entités intermédiaires jusqu’à atteindre une entité de compte.

1. Sélectionnez **Appliquer** pour créer la relation.

1. Cliquez sur **Suivant**.

1. Dans l’étape **Unification de l’activité**, choisissez l’événement de l’activité et l’heure de début de votre activité.
   - **Champs obligatoires**
      - **Activité de l’événement** : champ correspondant à l’événement de cette activité.
      - **Horodateur** : champ qui représente l’heure de début de votre activité.

   - **Champs facultatifs**
      - **Détails supplémentaires** : champ avec des informations pertinentes pour cette activité.
      - **Icône** : icône qui représente le mieux ce type d’activité.
      - **Adresse web** : champ contenant une URL avec des informations sur cette activité. Par exemple, le système transactionnel d’où provient cette activité. Cette URL peut être n’importe quel champ de la source de données, ou elle peut être construite comme un nouveau champ à l’aide d’une transformation Power Query. Les données de l’URL seront stockées dans l’entité *Activité unifiée*, qui peut être consommée en aval en utilisant les [API](apis.md).

   - **Afficher dans la chronologie**
      - Choisissez si vous voulez afficher cette activité dans la vue chronologique de vos profils clients. Sélectionnez **Oui** pour afficher l’activité dans la chronologie ou **Non** pour la masquer.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Spécifiez les données de l’activité client dans une entité Activité unifiée.":::

1. Sélectionnez **Suivant** pour choisir le type d’activité ou sélectionnez **Terminer et réviser** pour enregistrer l’activité maintenant avec le type d’activité défini sur **Autre**.

1. Dans l’étape **Type d’activité**, choisissez le type d’activité et, éventuellement, sélectionnez si vous souhaitez mapper sémantiquement certains des types d’activités pour les utiliser dans d’autres zones de Customer Insights. Actuellement, les types d’activité *Commentaires*, *Fidélité*, *SalesOrder*, *SalesOrderLine* et *Abonnement* prennent en charge la sémantique après avoir accepté de mapper les champs. Si un type d’activité n’est pas pertinent pour la nouvelle activité, vous pouvez choisir *Autre* ou *Créer* pour un type d’activité personnalisé.

1. Cliquez sur **Suivant**.

1. Dans l’étape **Réviser**, vérifiez vos sélections. Revenez à l’une des étapes précédentes et mettez à jour les informations si nécessaire.

1. Sélectionnez **Enregistrer l’activité** pour appliquer vos modifications et sélectionnez **Terminé** pour revenir à **Données** > **Activités**. L’activité créée s’affiche.

1. Après avoir créé toutes vos activités, sélectionnez **Exécuter** pour les traiter.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Gérer les activités existantes

Accédez à **Données** > **Activités** pour afficher vos activités enregistrées, leur entité source, le type d’activité et si elles sont incluses dans la chronologie du client. Vous pouvez trier la liste des activités par colonne ou utiliser la zone de recherche pour trouver l’activité que vous souhaitez gérer.

Sélectionnez une activité pour afficher les actions disponibles.

- **Modifiez** l’activité pour changer sa configuration. Vous accédez à l’étape de révision de la configuration. Une fois la configuration modifiée, sélectionnez **Enregistrer l’activité**, puis sélectionnez **Exécuter** pour traiter les modifications.
- **Renommez** l’activité. Sélectionnez **Enregistrer** pour appliquer vos modifications.
- **Supprimez** l’activité. Pour supprimer plusieurs activités à la fois, sélectionnez-les, puis cliquez sur **Supprimer**. Confirmez la suppression.

## <a name="view-activity-timelines-on-customer-profiles"></a>Afficher les chronologies des activités sur les profils des clients

1. Si vous avez sélectionné **Afficher dans la chronologie des activités** dans la configuration des activités, accédez à **Clients**, puis sélectionnez un profil client afin d’afficher les activités du client dans la section **Chronologie des activités**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Affichez les activités configurées dans les profils client.":::

1. Pour filtrer les activités dans la chronologie des activités :

   - Sélectionnez une ou plusieurs icônes d’activité pour affiner vos résultats afin d’inclure uniquement les types sélectionnés.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrez les activités par type à l’aide des icônes.":::

   - Sélectionnez **Filtre** pour ouvrir un volet de filtre afin de configurer vos filtres de chronologie. Filtrez par *ActivityType* et/ou *Date*. Cliquez sur **Appliquer**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilisez le volet de filtre pour configurer les conditions de filtrage.":::

1. Pour supprimer les filtres, sélectionnez **Effacer les filtres** ou **Filtre** et décochez la case du filtre.

> [!NOTE]
> Les filtres d’activité sont supprimés lorsque vous quittez un profil client. Vous devez les appliquer chaque fois que vous ouvrez un profil client.

[!INCLUDE [footer-include](includes/footer-banner.md)]
