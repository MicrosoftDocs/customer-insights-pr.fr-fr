---
title: Créer des segments avec le générateur de segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494493"
---
# <a name="create-segments"></a>Créer des segments

Définissez des filtres complexes autour de l’entité de client unifié et ses entités liées. Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions. Les segments sont gérés sur la page **Segments**. Vous pouvez [créer de nouveaux segments](#create-a-new-segment) à l’aide du [générateur de segments](#segment-builder) ou [créer des segments rapides](#quick-segments) à partir d’autres zones de l’application.

## <a name="segment-builder"></a>Générateur de segments

L’image suivante illustre les divers aspects du générateur de segments. Elle montre un segment qui génère un groupe de clients. Les clients ont commandé des marchandises sur une période spécifique et collecté un certain nombre de points de récompense ou dépensé une certaine somme d’argent. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Éléments du générateur de segments." lightbox="media/segment-builder-overview.png":::

1 - Organisez votre segment avec des règles et des sous-règles. Chaque règle ou sous-règle contient des conditions. Associer les conditions aux opérateurs logiques

2 - Choisissez le [chemin d’accès à la relation](relationships.md) entre les entités qui s’applique à une règle. Le chemin d’accès à la relation définit les attributs pouvant être utilisés dans une condition.

3 - Gérez les règles et les sous-règles. Modifiez la position d’une règle ou supprimez-la.

4 - Ajoutez des conditions et créez le bon niveau d’imbrication à l’aide des sous-règles.

5 - Appliquez des opérations d’ensemble aux règles connectées.

6 - Utilisez le volet des attributs pour ajouter les attributs d’entité disponibles ou créer des conditions basées sur les attributs. Le volet affiche la liste des entités et des attributs, en fonction du chemin d’accès à la relation sélectionné, qui sont disponibles pour la règle sélectionnée.

7 - Ajoutez des conditions basées sur les attributs aux règles et sous-règles existantes ou ajoutez-les à une nouvelle règle.

8 - Annulez et rétablissez les modifications lors de la génération du segment.

L’exemple ci-dessus illustre la fonctionnalité de segmentation. Nous avons défini un segment pour les clients qui ont acheté au moins $500 de marchandises en ligne *et* qui s’intéressent au développement de logiciels.

## <a name="create-a-new-segment"></a>Créer un segment

Il existe plusieurs façons de créer un segment. Cette section décrit comment créer votre propre segment à partir de zéro. Vous pouvez également créer un *segment rapide* basé sur des entités existantes ou utiliser des modèles Machine Learning pour obtenir des *segments suggérés*. Pour en savoir plus, consultez [Présentation des segments](segments.md).

Lors de la création d’un segment, vous pouvez enregistrer un brouillon. Il sera enregistré en tant que segment inactif et ne peut pas être activé s’il est terminé avec une configuration valide.

1. Accédez à la page **Segments**.

1. Sélectionnez **Nouveau** > **Créer votre propre segment**.

1. Sur la page du générateur de segments, vous définissez la première règle. Une règle se compose d’une ou plusieurs conditions et définit un ensemble de clients.

1. Dans la section **Règle 1**, choisissez un attribut d’entité selon lequel vous souhaitez filtrer les clients. Il existe deux façons de choisir des attributs : 
   - Consultez la liste des entités et attributs disponibles dans le volet **Ajouter à la règle** et sélectionnez l’icône **+** en regard de l’attribut à ajouter. Choisissez si vous souhaitez ajouter l’attribut à une règle existante ou l’utiliser pour créer une nouvelle règle.
   - Tapez le nom de l’attribut dans la section Règle pour voir les suggestions correspondantes.

1. Choisissez les opérateurs pour spécifier les valeurs correspondantes de la condition. L’attribut peut avoir l’un des quatre types de données comme valeur : numérique, chaîne, date ou booléen. Selon le type de données de l’attribut, différents opérateurs sont disponibles pour spécifier la condition. 

1. Sélectionnez **Ajouter une condition** pour ajouter d’autres conditions à une règle. Pour créer une règle sous la règle actuelle, sélectionnez **Ajouter une sous-règle**.

1. Si une règle utilise d’autres entités que l’entité *Client*, vous devez définir le chemin d’accès à la relation. Le chemin d’accès à la relation est nécessaire pour informer le système des relations qui peuvent accéder à l’entité client unifiée. Sélectionnez **Définir le chemin d’accès à la relation** pour associer l’entité sélectionnée à l’entité client unifiée. S’il n’existe qu’un seul chemin d’accès à la relation possible, le système le sélectionnera automatiquement. Différents chemins d’accès à la relation peuvent donner des résultats différents. Chaque règle peut avoir son propre chemin d’accès à la relation.

   :::image type="content" source="media/relationship-path.png" alt-text="Chemin d’accès à la relation potentiel lors de la création d’une règle basée sur une entité associée à l’entité client unifiée.":::

   Par exemple, l’entité *eCommerce_eCommercePurchases* dans la capture d’écran a quatre options à associer à l’entité *Client* : 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Client
   - eCommerce_eCommercePurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client. En choisissant la dernière option, nous pouvons inclure des attributs de toutes les entités répertoriées dans les conditions de la règle. Nous obtiendrons probablement moins de résultats car les enregistrements clients correspondants doivent faire partie de toutes les entités. Dans cet exemple, ils ont acheté des marchandises via le commerce électronique (*eCommerce_eCommercePurchases*), dans un point de vente (*POS_posPurchases*) et participé à notre programme de fidélité (*loyaltyScheme_loyCustomers*). En choisissant la deuxième option, nous ne pouvons choisir que des attributs de l’entité *eCommerce_eCommercePurchases* et de l’entité *Client*. On obtiendra probablement un plus grand nombre de profils clients.

1. Si une règle contient plusieurs conditions, vous pouvez choisir l’opérateur logique qui les connecte.

   - Opérateur **ET** : toutes les conditions doivent être remplies pour inclure un enregistrement dans le segment. Cette option est très utile lorsque vous définissez des conditions sur différentes entités.

   - Opérateur **OU** : l’une des conditions doit être remplie pour inclure un enregistrement dans le segment. Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Règle avec deux conditions ET.":::

   Lors de l’utilisation de l’opérateur OU, toutes les conditions doivent être basées sur les entités incluses dans le chemin d’accès à la relation.

   1. Vous pouvez créer plusieurs règles pour créer différents ensembles d’enregistrements clients. Vous pouvez combiner des groupes pour inclure les clients requis pour votre scénario professionnel. Pour créer une nouvelle règle, sélectionnez **Ajouter une règle**. Plus spécifiquement, si vous ne pouvez pas inclure une entité dans une règle en raison du chemin d’accès à la relation spécifié, vous devez créer une nouvelle règle pour choisir les attributs qui la forment.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Ajoutez une nouvelle règle à un segment et choisissez l’opérateur défini.":::

   1. Sélectionnez l’un des opérateurs définis : **Union**, **Intersection** ou **Exception**.

   - **Union** unit les deux groupes.

   - **Intersection** fait se chevaucher les deux groupes. Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.

   - **Exception** combine les deux groupes. Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.

1. Par défaut, les segments génèrent l’entité de sortie contenant tous les attributs des profils clients qui correspondent aux filtres définis. Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie. Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'attributs projetés sélectionnés dans le volet latéral à ajouter à l’entité de sortie.":::
  
   Exemple : un segment est basé sur une entité contenant des données d’achat, qui sont liées à l’entité *Client*. Le segment recherche tous les clients d’Espagne qui ont acheté des marchandises au cours de l’année en cours. Vous pouvez choisir d’ajouter des attributs tels que le prix des marchandises ou la date d’achat à tous les enregistrements clients correspondants dans l’entité de sortie. Ces informations peuvent être utiles pour analyser les corrélations saisonnières avec les dépenses totales.

   > [!NOTE]
   > - Les attributs projetés ne fonctionnent que pour les entités qui ont une relation un-à-plusieurs avec l’entité client. Par exemple, un client peut avoir plusieurs abonnements.
   > - Vous pouvez uniquement projeter les attributs d’une entité utilisée dans chaque règle de requête de segment que vous créez.
   > - Les attributs projetés sont pris en compte lors de l’utilisation d’opérateurs définis.

1. Avant d’enregistrer et d’exécuter le segment, sélectionnez **Modifier les détails** en regard du nom du segment. Fournissez un nom pour votre segment et mettez à jour le **Nom de l’entité de sortie** suggéré pour le segment. Vous pouvez également ajouter une description au segment.

1. Sélectionnez **Exécuter** pour enregistrer et traiter votre segment si toutes les conditions sont validées. Sinon, il sera enregistré en tant que brouillon de segment inactif.

1. Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.

> [!TIP]
> - Le générateur de segments ne suggérera pas de valeurs valides à partir d’entités lors de la définition des opérateurs pour les conditions. Vous pouvez accéder à **Données** > **Entités** et télécharger les données de l’entité pour voir les valeurs disponibles.
> - Les conditions basées sur les dates vous permettent de basculer entre des dates fixes et une plage de dates flottante.
> - Si vous avez plusieurs règles pour votre segment, vous trouvez une barre bleue autour de la règle que vous modifiez.
> - Vous pouvez déplacer les règles et les conditions vers d’autres emplacements dans la définition du segment. Sélectionnez [...] en regard d’une règle ou d’une condition et choisissez comment et où la déplacer.
> - Les contrôles **Annuler** et **Rétablir** de la barre de commandes vous permettent de restaurer les modifications.

## <a name="quick-segments"></a>Segments rapides

Les segments rapides vous permettent de créer rapidement des segments simples avec un seul opérateur pour des informations plus rapides.

1. Sur la page **Segments**, sélectionnez **Nouveau** > **Créer à partir de**.

   - Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité *client unifié*.
   - Sélectionnez l’option **Mesures** pour créer un segment autour des mesures que vous avez précédemment créées.
   - Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.

2. Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.

3. Le système fournira plus d’informations pour vous aider à créer de meilleurs segments de vos clients.
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
