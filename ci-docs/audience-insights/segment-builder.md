---
title: Créer et gérer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377785"
---
# <a name="create-and-manage-segments"></a>Créer et gérer des segments

> [!IMPORTANT]
> Plusieurs modifications seront apportées à l’expérience de création de segments en septembre 2021 : 
> - Le générateur de segments sera légèrement différent, avec des éléments restylés et un flux d’utilisateurs amélioré.
> - De nouveaux opérateurs de date/heure et un sélecteur de dates amélioré sont disponibles dans le générateur de segments.
> - Vous pourrez ajouter ou supprimer des conditions et des règles à partir de segments. 
> - Les règles imbriquées qui commencent par une condition OR deviennent disponibles. Vous n’avez plus besoin d’une condition AND au niveau de la couche la plus externe.
> - Un volet latéral pour sélectionner les attributs sera constamment disponible.
> - Option permettant de sélectionner des chemins d’accès de relation d’entité.
> Pour essayer le nouveau générateur de segments, envoyez un e-mail avec le sujet « Demande d’activation du nouveau générateur de segments » à cihelp [at] microsoft.com. Incluez le nom de votre organisation et l’ID de votre environnement de bac à sable.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Éléments du générateur de segments." lightbox="media/segment-builder-overview.png":::
>
> 1 - Organisez votre segment avec des règles et des sous-règles. Chaque règle ou sous-règle contient des conditions. Associer les conditions aux opérateurs logiques
>
> 2 - Choisissez le [chemin d’accès à la relation](relationships.md) entre les entités qui s’applique à une règle. Le chemin d’accès à la relation définit les attributs pouvant être utilisés dans une condition.
>
> 3 - Gérez les règles et les sous-règles. Modifiez la position d’une règle ou supprimez-la.
>
> 4 - Ajoutez des conditions et créez le bon niveau d’imbrication à l’aide des sous-règles.
>
> 5 - Appliquez des opérations d’ensemble aux règles connectées.
>
> 6 - Utilisez le volet des attributs pour ajouter les attributs d’entité disponibles ou créer des conditions basées sur les attributs. Le volet affiche la liste des entités et des attributs, en fonction du chemin d’accès à la relation sélectionné, qui sont disponibles pour la règle sélectionnée.
>
> 7 - Ajoutez des conditions basées sur les attributs aux règles et sous-règles existantes ou ajoutez-les à une nouvelle règle.
>
> 8 - Annulez et rétablissez les modifications lors de la génération du segment.

Définissez des filtres complexes autour de l’entité de client unifié et ses entités liées. Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions. Les segments sont gérés sur la page **Segments**. 

L’exemple suivant illustre la fonctionnalité de segmentation. Nous avons défini un segment pour les clients qui ont commandé au moins 500 USD de marchandises au cours des 90 derniers jours *et* qui ont été appelés par le service clientèle.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Capture d’écran de l’interface utilisateur du générateur de segments avec deux groupes qui spécifient un segment de clientèle.":::

## <a name="create-a-new-segment"></a>Créer un segment

Il existe plusieurs façons de créer un segment. Cette section décrit comment créer un *segment vide* à partir de zéro. Vous pouvez également créer un *segment rapide* basé sur des entités existantes ou utiliser des modèles Machine Learning pour obtenir des *segments suggérés*. Pour en savoir plus, consultez [Présentation des segments](segments.md).

Lors de la création d’un segment, vous pouvez enregistrer un brouillon. Il sera enregistré en tant que segment inactif et ne peut pas être activé s’il est terminé avec une configuration valide.

1. Accédez à la page **Segments**.

1. Sélectionnez **Nouveau** > **Segment vide**.

1. Dans le volet **Nouveau segment**, choisissez un type de segment :

   - Les **Segments dynamiques** [sont actualisés](segments.md#refresh-segments) selon un calendrier récurrent.
   - Les **Segments statiques** sont exécutés une fois lorsque vous les créez.

1. Indiquez un **Nom de l’entité de sortie** pour le segment. Vous pouvez aussi fournir un nom complet et une description qui aide à identifier le segment.

1. Sélectionnez **Suivant** pour arriver sur la page **Générateur de segments** où vous devez définir un groupe. Un groupe est un ensemble de clients.

1. Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez segmenter.

1. Choisissez l’attribut de segmentation. Cet attribut peut avoir un des quatre types de valeur : numérique, chaîne, date ou booléen.

1. Choisissez un opérateur et une valeur pour l’attribut sélectionné.

   > [!div class="mx-imgBorder"]
   > ![Filtre de groupe personnalisé.](media/customer-group-numbers.png "Filtre du groupe de clients")

   |Nombre |Définition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Opérateur         |
   |4    |valeur         |

   1. Pour ajouter plus de conditions à un groupe, vous pouvez utiliser deux opérateurs logiques :

      - Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation. Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.

      - Opérateur **OU** : L’une ou l’autre des conditions doit être satisfaite dans le cadre de le processus de segmentation. Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.

      > [!div class="mx-imgBorder"]
      > ![Opérateur OU où l'une ou l'autre des conditions doit être remplie.](media/segmentation-either-condition.png "Opérateur OU où l’une ou l’autre des conditions doit être remplie")

      Il est actuellement possible d’imbriquer un opérateur **OU** sous un opérateur **ET**, mais pas l’inverse.

   1. Chaque groupe correspond à un ensemble de clients. Vous pouvez combiner des groupes pour inclure les clients requis pour votre scénario professionnel.    
   Sélectionnez **Ajouter un groupe**.

      > [!div class="mx-imgBorder"]
      > ![Groupe de clients - Ajouter un groupe.](media/customer-group-add-group.png "Groupe de clients - Ajouter un groupe")

   1. Sélectionnez l’un des opérateurs définis : **Union**, **Intersection** ou **Exception**.

   > [!div class="mx-imgBorder"]
   > ![Groupe de clients - Ajouter une union.](media/customer-group-union.png "Groupe de clients - Ajouter une union")

   - **Union** unit les deux groupes.

   - **Intersection** fait se chevaucher les deux groupes. Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.

   - **Exception** combine les deux groupes. Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.

1. Si l’entité est connectée à l’entité client unifiée par le biais de [relations](relationships.md), vous devez définir le chemin d’accès de la relation pour créer un segment valide. Ajoutez les entités à partir du chemin d’accès de la relation jusqu’à ce que vous puissiez sélectionner l’entité **Client : CustomerInsights** dans la liste déroulante. Choisissez ensuite **Tous les enregistrements** pour chaque étape.

   > [!div class="mx-imgBorder"]
   > ![Chemin d’accès de la relation lors de la création d’un segment.](media/segments-multiple-relationships.png "Chemin d’accès de la relation lors de la création d’un segment")

1. Par défaut, les segments génèrent une entité de sortie qui contient tous les attributs des profils client qui correspondent aux filtres définis. Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie. Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.  
  
   Exemple : un segment est basé sur une entité qui contient des données d’activité client liées à l’entité *Client*. Le segment recherche tous les clients qui ont appelé le service d’assistance au cours des 60 derniers jours. Vous pouvez choisir d’ajouter la durée de l’appel et le nombre d’appels à tous les enregistrements client correspondants dans l’entité de sortie. Ces informations peuvent être utiles pour envoyer un e-mail contenant des liens utiles vers des articles d’aide en ligne et des questions fréquentes (FAQ) aux clients qui ont appelé fréquemment.

   > [!NOTE]
   > - Les attributs projetés ne fonctionnent que pour les entités qui ont une relation un-à-plusieurs avec l’entité client. Par exemple, un client peut avoir plusieurs abonnements.
   > - Vous ne pouvez projeter que les attributs d’une entité utilisée dans chaque groupe de requête de segment que vous créez.
   > - Les attributs projetés sont pris en compte lors de l’utilisation d’opérateurs définis.

1. Sélectionnez **Enregistrer** pour enregistrer votre segment. Votre segment sera enregistré et traité si toutes les exigences sont validées. Sinon, il sera enregistré en tant que brouillon.

1. Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.



## <a name="quick-segments"></a>Segments rapides

Les segments rapides vous permettent de créer rapidement des segments simples avec un seul opérateur pour des informations plus rapides.

1. Sur la page **Segments**, sélectionnez **Nouveau** > **Créer à partir de**.

   - Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité *client unifié*.
   - Sélectionnez l’option **Mesures** pour créer un segment autour des mesures que vous avez précédemment créées.
   - Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.

2. Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.

3. Le système fournit des informations supplémentaires qui vous permettent de créer de meilleurs segments de vos clients.
   - Pour les champs de catégorie, nous affichons les 10 meilleurs clients. Choisissez une **Valeur** et sélectionnez **Réviser**.

   - Pour un attribut numérique, le système affiche la valeur d’attribut correspondant au centile de chaque utilisateur. Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.

4. Le système vous fournira une **taille estimée du segment**. Vous pouvez choisir de générer le segment que vous avez défini ou de le revoir pour obtenir une taille de segment différente.

    > [!div class="mx-imgBorder"]
    > ![Nom et estimation pour un segment rapide.](media/quick-segment-name.png "Nom et estimation pour un segment rapide")

5. Fournissez un **Nom** pour votre segment. Indiquez éventuellement un **Nom complet**.

6. Sélectionnez **Enregistrer** pour créer votre segment.

7. Une fois le segment terminé, vous pouvez l’afficher comme tout autre segment que vous avez créé.

## <a name="next-steps"></a>Étapes suivantes

[Exportez un segment](export-destinations.md) et explorez l’[intégration de la carte client](customer-card-add-in.md) pour utiliser les segments dans d’autres applications.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
