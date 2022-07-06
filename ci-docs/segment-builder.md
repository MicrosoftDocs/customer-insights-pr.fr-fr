---
title: Créer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs en utilisant le générateur de segments ou des segments rapides.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: b99d9575d3b6af91758d80eb04170773b08cc9ab
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053969"
---
# <a name="create-segments"></a>Créer des segments

Définissez des filtres complexes autour de l’entité de client unifié et ses entités liées. Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions. Les segments sont gérés sur la page **Segments**. Vous pouvez [créer de nouveaux segments](#create-a-new-segment) à l’aide du générateur de segments ou [créer des segments rapides](#quick-segments) à partir d’autres zones de l’application.

> [!TIP]
> - Les segments rapides ne sont pris en charge que dans les environnements pour les **clients particuliers**.
> - Les segments basés sur des **clients particuliers** incluent automatiquement les informations de contact disponibles pour les membres du segment. Dans des environnements pour les **comptes d’entreprise**, les segments sont basés sur des comptes (sociétés ou filiales). Pour inclure des informations de contact dans un segment, utilisez la fonctionnalité **Attributs du projet** du générateur de segments. Assurez-vous que les sources de données de contact sont [mappées sémantiquement à l'entité ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Générateur de segments

L’image suivante illustre les divers aspects du générateur de segments. Elle montre un segment qui génère un groupe de clients. Les clients ont commandé des marchandises dans un délai d’exécution spécifique et ont accumulé des points de récompense ou dépensé une certaine somme d’argent.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Éléments du générateur de segments." lightbox="media/segment-builder-overview.png":::

1. Organisez votre segment avec des règles et des sous-règles. Chaque règle ou sous-règle contient des conditions. Associer les conditions aux opérateurs logiques

1. Choisissez le [chemin d’accès à la relation](relationships.md) entre les entités qui s’applique à une règle. Le chemin d’accès à la relation définit les attributs pouvant être utilisés dans une condition.

1. Gérez les règles et les sous-règles. Modifiez la position d’une règle ou supprimez-la.

1. Ajoutez des conditions et créez le bon niveau d’imbrication à l’aide des sous-règles.

1. Appliquez des opérations d’ensemble aux règles connectées.

1. Utilisez le volet des attributs pour ajouter les attributs d’entité disponibles ou créer des conditions basées sur les attributs. Le volet affiche la liste des entités et des attributs, en fonction du chemin d’accès à la relation sélectionné, qui sont disponibles pour la règle sélectionnée.

1. Ajoutez des conditions basées sur les attributs aux règles et sous-règles existantes ou ajoutez-les à une nouvelle règle.

1. Annulez et rétablissez les modifications lors de la génération du segment.

L’exemple ci-dessus illustre la fonctionnalité de segmentation. Nous avons défini un segment pour les clients qui ont acheté au moins $500 de marchandises en ligne *et* qui s’intéressent au développement de logiciels.

## <a name="create-a-new-segment"></a>Créer un segment

Il existe plusieurs façons de créer un segment. Cette section décrit comment créer votre propre segment à partir de zéro. Vous pouvez également créer un *segment rapide* basé sur des entités existantes ou utiliser des modèles Machine Learning pour obtenir des *segments suggérés*. Pour plus d’informations, consultez la [Vue d’ensemble des segments](segments.md).

Lors de la création d’un segment, vous pouvez enregistrer un brouillon. Au stade du brouillon, un segment est enregistré en tant que segment inactif. Une fois la configuration du segment terminée, exécutez-la pour activer le segment. Vous pouvez également **Activer** un segment à partir de la page **Tous les segments**.

1. Accédez à la page **Segments**.

1. Sélectionnez **Nouveau** > **Créer votre propre segment**.

1. Sur la page du générateur de segments, définissez ou composez des règles. Une règle se compose d’une ou plusieurs conditions qui définissent un ensemble de clients.

1. Dans la section **Règle 1**, choisissez l’attribut d’une entité que vous souhaitez utiliser pour filtrer les clients. Il existe deux façons de choisir des attributs :
   - Consultez la liste des entités et attributs disponibles dans le volet **Ajouter à la règle** et sélectionnez l’icône **+** en regard de l’attribut à ajouter. Choisissez si vous souhaitez ajouter l’attribut à une règle existante ou l’utiliser pour créer une nouvelle règle.
   - Tapez le nom de l’attribut dans la section Règle pour voir les suggestions correspondantes.

1. Choisissez les opérateurs pour spécifier les valeurs correspondantes de la condition. L’attribut peut avoir l’un des quatre types de données comme valeur : numérique, chaîne, date ou booléen. Selon le type de données de l’attribut, différents opérateurs sont disponibles pour spécifier la condition. Pour les segments avec des comptes professionnels, deux opérateurs spéciaux sont disponibles pour inclure des hiérarchies potentielles entre les comptes ingérés. Utilisez les opérateurs *enfant de* et *parent de* pour inclure des comptes associés.

1. Sélectionnez **Ajouter une condition** pour ajouter d’autres conditions à une règle. Pour créer une règle sous la règle actuelle, sélectionnez **Ajouter une sous-règle**.

1. Si une règle utilise d’autres entités que l’entité *Client*, vous devez définir le chemin d’accès à la relation. Le chemin d’accès à la relation est nécessaire pour informer le système des relations qui peuvent accéder à l’entité client unifiée. Sélectionnez **Définir le chemin d’accès à la relation** pour associer l’entité sélectionnée à l’entité client unifiée. S’il n’existe qu’un seul chemin d’accès à la relation possible, le système le sélectionnera automatiquement. Différents chemins d’accès à la relation peuvent donner des résultats différents. Chaque règle peut avoir son propre chemin d’accès à la relation.

   :::image type="content" source="media/relationship-path.png" alt-text="Chemin d’accès à la relation potentiel lors de la création d’une règle basée sur une entité associée à l’entité client unifiée.":::

   Par exemple, l’entité *eCommerce_eCommercePurchases* dans la capture d’écran a quatre options à associer à l’entité *Client* :
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Client
   - eCommerce_eCommercePurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client. En choisissant la dernière option, nous pouvons inclure des attributs de toutes les entités répertoriées dans les conditions de la règle. Nous obtiendrons probablement moins de résultats, car les enregistrements de clients correspondants doivent faire partie de toutes les entités. Dans cet exemple, ils ont acheté des marchandises via le e-commerce (*eCommerce_eCommercePurchases*), dans un point de vente (*POS_posPurchases*) et participé à notre programme de fidélité (*loyaltyScheme_loyCustomers*). En choisissant la deuxième option, nous ne pouvons choisir que des attributs de l’entité *eCommerce_eCommercePurchases* et de l’entité *Client*. On obtiendra probablement un plus grand nombre de profils clients.

1. Si une règle contient plusieurs conditions, vous pouvez choisir l’opérateur logique qui les connecte.  
   - Opérateur **ET** : toutes les conditions doivent être remplies pour inclure un enregistrement dans le segment. Cette option est très utile lorsque vous définissez des conditions sur différentes entités.
   - Opérateur **OU** : l’une des conditions doit être remplie pour inclure un enregistrement dans le segment. Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Règle avec deux conditions ET.":::

   Lors de l’utilisation de l’opérateur OU, toutes les conditions doivent être basées sur les entités incluses dans le chemin d’accès à la relation.

   - Vous pouvez créer plusieurs règles pour créer différents ensembles d’enregistrements clients. Vous pouvez combiner des groupes pour inclure les clients requis pour votre scénario professionnel. Pour créer une nouvelle règle, sélectionnez **Ajouter une règle**. Plus particulièrement, si vous ne pouvez pas inclure une entité dans une règle en raison du chemin de relation spécifié, vous devez créer une nouvelle règle pour choisir les attributs de celle-ci.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Ajoutez une nouvelle règle à un segment et choisissez l’opérateur défini.":::

   - Sélectionnez l’un des opérateurs définis : **Union**, **Intersection** ou **Exception**.

      - **Union** unit les deux groupes.
      - **Intersection** fait se chevaucher les deux groupes. Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.
      - **Exception** combine les deux groupes. Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.

1. Par défaut, les segments génèrent l’entité de sortie contenant tous les attributs des profils clients qui correspondent aux filtres définis. Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie. Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.

   > [!IMPORTANT]
   > Pour les segments basés sur des comptes professionnels, les détails d'un ou plusieurs contacts de chaque compte à partir de l'entité *ContactProfile* doivent être inclus dans le segment pour permettre à ce segment d'être activé ou exporté vers des destinations nécessitant des informations de contact. Pour plus d'informations sur l'entité *ContactProfil*, voir [Mappages sémantiques](semantic-mappings.md).
   > Un exemple de sortie pour un segment basé sur des comptes d'entreprise avec des attributs projetés de contacts pourrait ressembler à ceci :
   >
   > |ID  |Nom du compte  |Revenus  |Nom du contact  | Rôle du contact|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, Gestion des approvisionnements]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'attributs projetés sélectionnés dans le volet latéral à ajouter à l’entité de sortie.":::
  
   Par exemple : Un segment est basé sur une entité qui contient des données d’achat, qui sont liées à l’entité *Client*. Le segment recherche tous les clients d’Espagne qui ont acheté des marchandises au cours de l’année en cours. Vous pouvez choisir d’ajouter des attributs tels que le prix des marchandises ou la date d’achat à tous les enregistrements clients correspondants dans l’entité de sortie. Ces informations peuvent être utiles pour analyser les corrélations saisonnières avec les dépenses totales.

   > [!NOTE]
   > - **Attributs du projet** ne fonctionne que pour les entités qui ont une relation un-à-plusieurs avec l’entité cliente. Par exemple, un client peut avoir plusieurs abonnements.
   > - Si l’attribut que vous souhaitez projeter est à plus d’un saut de l’entité *Client*, telle que définie par la relation, cet attribut doit être utilisé dans chaque règle de la requête de segment que vous créez.
   > - Si l’attribut que vous souhaitez projeter n’est qu’à un saut de l’entité *Client*, cet attribut ne doit pas être présent dans chaque règle de la requête de segment que vous créez.
   > - Les **attributs projetés** sont pris en compte lors de l’utilisation d’opérateurs définis.

1. Sélectionnez **Modifier les détails** en regard de Segment sans titre. Fournissez un nom pour votre segment et mettez à jour le **Nom de l’entité de sortie** suggéré pour le segment. Si nécessaire, ajoutez une description et des [étiquettes](work-with-tags-columns.md#manage-tags) au segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Boîte de dialogue Modifier les détails.":::

1. Sélectionnez **Exécuter** pour enregistrer le segment, activez-le et commencez à traiter votre segment en fonction de toutes les règles et conditions. Sinon, il sera enregistré en tant que segment inactif.

1. Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.

1. Par défaut, le segment est créé en tant que segment dynamique. Cela signifie que le segment est actualisé lors des actualisations du système. Pour [arrêter l'actualisation automatique](segments.md#manage-existing-segments), sélectionnez le segment et choisissez l'option **Rendre statique**. Seuls les segments statiques peuvent être [actualisés manuellement](segments.md#refresh-segments) à tout moment.

> [!TIP]
> - Le générateur de segments ne suggérera pas de valeurs valides à partir d’entités lors de la définition des opérateurs pour les conditions. Vous pouvez accéder à **Données** > **Entités** et télécharger les données de l’entité pour voir les valeurs disponibles.
> - Les conditions basées sur les dates vous permettent de basculer entre des dates fixes et une plage de dates flottante.
> - Si vous avez plusieurs règles pour votre segment, la règle que vous modifiez a une ligne bleue verticale à côté d’elle.
> - Vous pouvez déplacer les règles et les conditions vers d’autres emplacements dans la définition du segment. Sélectionnez les points de suspension verticaux (&vellip;) en regard d’une règle ou d’une condition et choisissez comment et où la déplacer.
> - Les commandes **Annuler** et **Rétablir** de la barre de commandes vous permettent de restaurer les modifications.
> - Après avoir créé un segment, certains segments vous permettent de [suivre l’utilisation du segment](segments.md#track-usage-of-a-segment).

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

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nom et estimation pour un segment rapide.":::

5. Fournissez un **Nom** et un **Nom de l’entité de sortie** pour votre segment. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags).

6. Sélectionnez **Enregistrer** pour créer votre segment.

7. Une fois le segment terminé, vous pouvez l’afficher comme tout autre segment que vous avez créé.

## <a name="next-steps"></a>Étapes suivantes

[Exportez un segment](export-destinations.md) et explorez l’[intégration de la carte client](customer-card-add-in.md) pour utiliser les segments dans d’autres applications.

[!INCLUDE [footer-include](includes/footer-banner.md)]
