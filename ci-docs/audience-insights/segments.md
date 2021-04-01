---
title: Créer et gérer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597048"
---
# <a name="create-and-manage-segments"></a>Créer et gérer des segments

Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux. Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.

Vous pouvez définir des filtres complexes autour de l’entité Profil client et des entités associées. Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions. Certaines [limites du service](service-limits.md) s’appliquent.

Sauf indication contraire, tous les segments sont des **segments dynamiques**, qui sont actualisés selon un calendrier périodique.

L’exemple suivant illustre la fonctionnalité de segmentation. Nous avons défini un segment pour les clients qui ont commandé au moins 500 USD de marchandises au cours des 90 derniers jours *et* qui ont été appelés par le service clientèle.

> [!div class="mx-imgBorder"]
> ![Groupes multiples](media/segmentation-group1-2.png "Groupes multiples")

## <a name="create-a-new-segment"></a>Créer un segment

Les segments sont gérés sur la page **Segments**.

1. Dans les informations sur l’audience, accédez à la page **Segments**.

1. Sélectionnez **Nouveau** > **Segment vide**.

1. Dans le volet **Nouveau segment**, choisissez un type de segment et indiquez un **Nom**.

   Vous pouvez aussi fournir un nom complet et une description qui aide à identifier le segment.

1. Sélectionnez **Suivant** pour arriver sur la page **Générateur de segments** où vous devez définir un groupe. Un groupe est un ensemble de clients.

1. Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez segmenter.

1. Choisissez l’attribut de segmentation. Cet attribut peut avoir un des quatre types de valeur : numérique, chaîne, date ou booléen.

1. Choisissez un opérateur et une valeur pour l’attribut sélectionné.

   > [!div class="mx-imgBorder"]
   > ![Filtre de groupe personnalisé](media/customer-group-numbers.png "Filtre du groupe de clients")

   |Numéro |Définition  |
   |---------|---------|
   |1     |Entité          |
   |2     |Attribut          |
   |3    |Opérateur         |
   |4    |Valeur         |

8. Si l’entité est connectée à l’entité client unifiée par le biais de [relations](relationships.md), vous devez définir le chemin d’accès de la relation pour créer un segment valide. Ajoutez les entités à partir du chemin d’accès de la relation jusqu’à ce que vous puissiez sélectionner l’entité **Client : CustomerInsights** dans la liste déroulante. Ensuite, choisissez **Tous les enregistrements** pour chaque condition.

   > [!div class="mx-imgBorder"]
   > ![Chemin d’accès de la relation lors de la création d’un segment](media/segments-multiple-relationships.png "Chemin d’accès de la relation lors de la création d’un segment")

1. Par défaut, les segments génèrent une entité de sortie qui contient tous les attributs des profils client qui correspondent aux filtres définis. Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie. Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.  

   
   Exemple : un segment est basé sur une entité qui contient des données d’activité client liées à l’entité *Client*. Le segment recherche tous les clients qui ont appelé le service d’assistance au cours des 60 derniers jours. Vous pouvez choisir d’ajouter la durée de l’appel et le nombre d’appels à tous les enregistrements client correspondants dans l’entité de sortie. Ces informations peuvent être utiles pour envoyer un e-mail contenant des liens utiles vers des articles d’aide en ligne et des questions fréquentes (FAQ) aux clients qui ont appelé fréquemment.

1. Sélectionnez **Enregistrer** pour enregistrer votre segment. Votre segment sera enregistré et traité si toutes les exigences sont validées. Sinon, il sera enregistré en tant que brouillon.

1. Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.

## <a name="manage-existing-segments"></a>Gérer les segments existants

Sur la page **Segments** vous pouvez afficher tous vos segments enregistrés et les gérer.

Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.

Vous pouvez trier les segments d’une colonne en sélectionnant l’en-tête de colonne.

Utilisez la case **Rechercher** dans le coin supérieur droit pour filtrer les segments.

> [!div class="mx-imgBorder"]
> ![Options de gestion d’un segment existant](media/segments-selected-segment.png "Options de gestion d’un segment existant")

L’action suivante est disponible lorsque vous sélectionnez un segment :

- **Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.
- **Modifier** le segment pour modifier ses propriétés.
- **Créez un doublon** d’un segment. Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.
- **Actualiser** le segment pour inclure les dernières données.
- **Activer** ou **Désactiver** le segment. Les segments ont deux états possibles : actif ou inactif. Ces états sont utiles lors de l’édition d’un segment. Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients. Lorsque vous activez un segment, son état passe de « inactif » à « actif » et il commence à rechercher des clients qui correspondent à la définition du segment. Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu’une actualisation n’a même pas été tentée. Lorsqu’un segment inactif est activé, il s’actualise et sera inclus dans les actualisations programmées.
  Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d’activation et de désactivation d’un segment particulier.
- **Renommer** le segment.
- **Télécharger** la liste des membres en tant que fichier .CSV.
- L’option **Ajouter à** envoie la liste des ID clients du segment aux fins de traitement dans une autre application.
- **Supprimer** le segment.

## <a name="refresh-segments"></a>Actualiser des segments

Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options. Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="download-and-export-segments"></a>Télécharger et exporter des segments

Vous pouvez télécharger vos segments dans un fichier CSV ou les exporter vers Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Télécharger des segments dans un fichier CSV

1. Dans les informations sur l’audience, accédez à la page **Segments**.

2. Sélectionnez les points de suspension dans une vignette de segment spécifique.

3. Sélectionnez **Télécharger au format CSV** dans la liste déroulante des actions.

### <a name="export-segments-to-dynamics-365-sales"></a>Exporter des segments vers Dynamics 365 Sales

Avant d’exporter des segments vers Dynamics 365 Sales, un administrateur doit [créer la destination d’exportation](export-destinations.md) pour Dynamics 365 Sales.

1. Dans les informations sur l’audience, accédez à la page **Segments**.

2. Sélectionnez les points de suspension dans une vignette de segment spécifique.

3. Sélectionnez **Ajouter à** dans la liste déroulante des actions et sélectionnez la destination d’exportation vers laquelle vous souhaitez envoyer les données.

## <a name="draft-mode-for-segments"></a>Mode brouillon pour les segments

Si toutes les exigences pour traiter un segment ne sont pas remplies, vous pouvez enregistrer le segment en tant que brouillon et y accéder à partir de la page **Segments**.

Il est enregistré en tant que segment inactif et ne peut pas être activé tant qu’il n’est pas valide.

## <a name="add-more-conditions-to-a-group"></a>Ajouter plus de conditions à un groupe

Pour ajouter plus de conditions à un groupe, vous pouvez utiliser deux opérateurs logiques :

- Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation. Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.

- Opérateur **OU** : L’une ou l’autre des conditions doit être satisfaite dans le cadre de le processus de segmentation. Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.

   > [!div class="mx-imgBorder"]
   > ![Opérateur OU où l’une ou l’autre des conditions doit être remplie](media/segmentation-either-condition.png "Opérateur OU où l’une ou l’autre des conditions doit être remplie")

Il est actuellement possible d’imbriquer un opérateur **OU** sous un opérateur **ET**, mais pas l’inverse.

## <a name="combine-multiple-groups"></a>Combiner plusieurs groupes

Chaque produit groupe un ensemble spécifique de clients. Vous pouvez combiner ces groupes pour inclure les clients requis pour votre étude de cas.

1. Dans les informations sur l’audience, accédez à la page **Segments** et sélectionnez un segment.

2. Sélectionnez **Ajouter un groupe**.

   > [!div class="mx-imgBorder"]
   > ![Groupe de clients - Ajouter un groupe](media/customer-group-add-group.png "Groupe de clients - Ajouter un groupe")

3. Sélectionnez l’un des opérateurs d’ensemble suivants : **Union**, **Intersection** ou **Exception**.

   > [!div class="mx-imgBorder"]
   > ![Groupe de clients - Ajouter une union](media/customer-group-union.png "Groupe de clients - Ajouter une union")

   Sélectionnez un opérateur configuré pour définir un nouveau groupe. Enregistrez différents groupes pour déterminer quelles données sont conservées :

   - **Union** unit les deux groupes.

   - **Intersection** fait se chevaucher les deux groupes. Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.

   - **Exception** combine les deux groupes. Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.

## <a name="view-processing-history-and-segment-members"></a>Afficher l’historique de traitement et les membres du segment

Vous pouvez voir les données consolidées d’un segment en examinant ses détails.

Dans la page **Segments**, sélectionnez le segment à vérifier.

La partie supérieure de la page comprend un graphique de tendance qui indique l’évolution du nombre des membres. Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique.

Vous pouvez mettre à jour le délai d’exécution de la visualisation.

> [!div class="mx-imgBorder"]
> ![Intervalle de temps du segment](media/segment-time-range.png "Intervalle de temps du segment")

La partie inférieure contient la liste des membres du segment.

> [!NOTE]
> Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.
>
>La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l’évaluer et revoir ses définitions si nécessaire. Pour voir tous les enregistrements correspondants, vous devez [exporter le segment](export-destinations.md).

## <a name="quick-segments"></a>Segments rapides

Outre le générateur de segments, il existe un autre moyen de créer des segments. Les segments rapides vous permettent de créer des segments simples (avec un seul opérateur) rapidement et avec des informations instantanées.

1. Sur la page **Segments**, sélectionnez **Nouveau** > **Création rapide depuis**.

   - Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité Client unifiée.
   - Sélectionnez l’option **Mesures** pour créer un segment pour chaque type Attribut de client des mesures que vous avez précédemment créées dans la page **Mesures**.
   - Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.

2. Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.

3. Le système fournit des informations supplémentaires qui vous permettent de créer de meilleurs segments de vos clients.
   - Pour les champs de catégorie, nous affichons les 10 meilleurs clients. Choisissez une **Valeur** et sélectionnez **Réviser**.

   - Pour un attribut numérique, le système affiche la valeur d’attribut correspondant au centile de chaque utilisateur. Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.

4. Le système vous fournira une **taille estimée du segment**. Vous pouvez choisir de générer le segment que vous avez défini ou de le revoir pour obtenir une taille de segment différente.

    > [!div class="mx-imgBorder"]
    > ![Nom et estimation pour un segment rapide](media/quick-segment-name.png "Nom et estimation pour un segment rapide")

5. Fournissez un **Nom** pour votre segment. Indiquez éventuellement un **Nom complet**.

6. Sélectionnez **Enregistrer** pour créer votre segment.

7. Une fois le segment terminé, vous pouvez l’afficher comme tout autre segment que vous avez créé.

Pour les scénarios suivants, nous vous conseillons d’utiliser le générateur de segments plutôt que la capacité de segments recommandée :

- Création de segments avec des filtres sur des champs de catégorie où l’opérateur est différent de l’opérateur **Est**
- Création de segments avec des filtres sur des champs numériques où l’opérateur est différent des opérateurs **Entre**, **Supérieur à** et **Inférieur à**
- Création de segments avec des filtres sur des champs de type Date

## <a name="next-steps"></a>Étapes suivantes

[Exportez un segment](export-destinations.md) et explorer la [carte client](customer-card-add-in.md) et les [connecteurs](export-power-bi.md) pour obtenir des informations sur le niveau du client.


[!INCLUDE[footer-include](../includes/footer-banner.md)]