---
title: Relations entre des entités et des chemins d’accès d’entités
description: Créez et gérez les relations entre des entités à partir de plusieurs sources de données.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: bd80d0315f4f501b8f8108b99c144082c21e0d4c
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622999"
---
# <a name="relationships-between-entities"></a>Relations entre les entités

Les relations connectent les entités et définissent un graphique de vos données lorsque les entités partagent un identifiant commun, une clé étrangère. Cette clé étrangère peut être référencée d'une entité à une autre. Les entités connectées permettent de définir des segments et des mesures en fonction de plusieurs sources de données.

Il existe trois types de relations : 
- Relations système non modifiables, créées par le système dans le cadre du processus d'unification des données
- Relations hérités non modifiables, qui sont créés automatiquement à partir de sources de données d'ingestion 
- Relations personnalisées modifiables, créées et configurées par les utilisateurs

## <a name="non-editable-system-relationships"></a>Relations système non modifiables

Lors de l'unification des données, les relations système sont créées automatiquement sur la base d'une correspondance intelligente. Ces relations permettent d’associer les enregistrements du profil client avec les enregistrements correspondants. Le diagramme suivant illustre la création de trois relations basées sur le système. L'entité Client est mise en correspondance avec d'autres entités pour produire l'entité *Client*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramme avec les chemins de relation pour l'entité Client avec trois Relations 1-n.":::

- La **relation *CustomerToContact*** a été créée entre l’entité *Client* et l’entité *Contact*. L’entité *Client* reçoit le champ clé **Contact_contactId** pour se lier au champ clé **contactID** de l’entité *Contact*.
- La **relation *CustomerToAccount*** a été créée entre l’entité *Client* et l’entité *Compte*. L’entité *Client* reçoit le champ clé **Account_accountID** pour se lier au champ clé **accountID** de l’entité *Compte*.
- La **relation *CustomerToWebAccount*** a été créée entre l’entité *Client* et l’entité *WebAccount*. L’entité *Client* reçoit le champ clé **WebAccount_webaccountID** pour se lier au champ clé **webaccountID** l’entité *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Relations héritées non modifiables

Pendant le processus d'ingestion de données, le système vérifie les sources de données pour les relations existantes. Si aucune relation n'existe, le système les crée automatiquement. Ces relations sont également utilisées dans les processus en aval.

## <a name="create-a-custom-relationship"></a>Créer une relation personnalisée

La relation consiste en une *entité source* contenant la clé étrangère et une *entité cible* vers laquelle pointe la clé étrangère de l'entité source. 

1. Dans les informations sur l’audience, accédez à **Données** > **Relations**.

2. Sélectionnez **Nouvelle relation**.

3. Dans le volet **Nouvelle relation**, fournissez les informations suivantes :

   :::image type="content" source="media/relationship-add.png" alt-text="Volet latéral Nouvelle relation avec des champs de saisie vides.":::

   - **Nom de la relation** : Nom qui reflète l'objectif de la relation. Exemple : CustomerToSupportCase.
   - **Description** : Description de la relation.
   - **Entité source** : Entité utilisée comme source dans la relation. Exemple : SupportCase.
   - **Entité cible** : Entité utilisée comme cible dans la relation. Exemple : Client.
   - **Cardinalité de la source** : Spécifie la cardinalité de l'entité source. La cardinalité décrit le nombre d'éléments possibles dans un ensemble. Elle se rapporte toujours à la cardinalité cible. Vous pouvez choisir les valeurs **Une** et **Plusieurs**. Seuls les types de relation plusieurs-à-un et un-à-un sont pris en charge.  
     - Plusieurs-à-un : plusieurs enregistrements source peuvent être liés à un seul enregistrement cible. Exemple : plusieurs cas d'assistance d'un même client.
     - Un-à-un : un seul enregistrement source se rapporte à un seul enregistrement cible. Exemple : un ID de fidélité pour un même client.

     > [!NOTE]
     > Les relations Plusieurs-à-plusieurs peuvent être créées à l'aide de deux relations Plusieurs-à-un et une entité de liaison, qui se connecte à l'entité source et l'entité cible.

   - **Cardinalité cible** : Sélectionnez la cardinalité des enregistrement de l’entité cible. 
   - **Champ de clé source** : champ de clé étrangère dans l'entité source. Exemple : SupportCase peut utiliser CaseID comme champ de clé étrangère.
   - **Champ de clé cible** : champ de clé de l’entité cible. Par exemple, Client peut utiliser le champ de clé **CustomerID**.

4. Sélectionnez **Enregistrer** pour créer la relation personnalisée.

## <a name="set-up-account-hierarchies"></a>Configurer des hiérarchies de compte

Les environnements configurés pour utiliser des comptes professionnels comme audience cible principale peuvent configurer des hiérarchies de compte pour les comptes professionnels associés. Par exemple, une entreprise qui a des divisions distinctes. 

Les organisations créent des hiérarchies de compte pour mieux gérer les comptes et leurs relations les uns avec les autres. La fonctionnalité d’informations d’audience prend en charge les hiérarchies de compte parent-enfant qui existent déjà dans les données client ingérées. Par exemple, les comptes de Dynamics 365 Sales. Ces hiérarchies peuvent être configurées sur la page **Relations** dans les insights d’audience, sous l’onglet Hiérarchie de compte.

1. Accédez à **Données** > **Relations**.
1. Sélectionnez l’onglet **Hiérarchie de compte**.
1. Sélectionnez **Nouvelle hiérarchie de compte**. 
1. Dans le volet **Hiérarchie de compte**, fournissez un nom pour la hiérarchie. Le système crée un nom pour l’entité de sortie. Vous pouvez modifier le nom de l’entité de nom de sortie.
1. Sélectionnez l’entité qui contient votre hiérarchie de compte. C’est généralement dans la même entité qui contient les comptes.
1. Sélectionnez l’**ID de compte** et l’**ID du parent du compte** de l’entité sélectionnée 
1. Sélectionnez **Enregistrer** pour appliquer les paramètres et finaliser la hiérarchie de compte.

## <a name="view-relationships"></a>Afficher les relations

La page Relations répertorie toutes les relations qui ont été créées. Chaque ligne représente une relation, qui inclut également des détails sur l'entité source, l'entité cible et la cardinalité. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste des relations et options dans la barre d'action de la page Relations.":::

Cette page propose un ensemble d'options pour les relations existants et nouvelles : 
- **Nouvelle relation** : [Créer une relation personnalisée](#create-a-custom-relationship).
- **Visualiseur** : [Explorez le visualiseur de relations](#explore-the-relationship-visualizer) pour voir un diagramme réseau des relations existantes et de leur cardinalité.
- **Filtrer par** : Choisissez le type de relations à afficher dans la liste.
- **Rechercher des relations** : Utilisez une recherche textuelle sur les propriétés des relations.

### <a name="explore-the-relationship-visualizer"></a>Explorez le visualiseur de relations

Le visualiseur de relations montre un diagramme réseau des relations existantes entre les entités connectées et de leur cardinalité. Il visualise également le chemin d’accès à la relation.

Pour personnaliser l'affichage, vous pouvez modifier la position des cases en les faisant glisser sur le canevas.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Capture d'écran du diagramme réseau du visualiseur de relations avec les connexions entre les entités associées.":::

Options disponibles : 
- **Exporter en tant qu'image** : enregistre la vue actuelle en tant que fichier image.
- **Changer en disposition horizontale/verticale** : Modifiez l'alignement des entités et des relations.
- **Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.

## <a name="relationship-paths"></a>Chemins d’accès de relation

Un chemin d’accès de relation décrit les entités connectées avec des relations entre une entité source et une entité cible. Il est utilisé lors de la création d’un segment ou d’une mesure qui inclut d’autres entités que l’entité de profil unifié et il existe plusieurs options pour atteindre l’entité de profil unifié. 

Un chemin d’accès de relation informe le système par quelles relations accéder à l’entité de profil unifié. Différents chemins d’accès à la relation peuvent donner des résultats différents.

Par exemple, l’entité *eCommerce_eCommercePurchases* a les relations suivantes avec l’entité *Client* de profil unifié :

- eCommerce_eCommercePurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client 

Un chemin d’accès de relation détermine les entités que vous pouvez utiliser lors de la création de règles pour les mesures ou les segments. Choisir l’option avec le chemin d’accès à la relation le plus long renvoie probablement moins de résultats car les enregistrements correspondants doivent faire partie de toutes les entités. Dans cet exemple, un client doit avoir acheté des marchandises via l’e-commerce (eCommerce_eCommercePurchases), dans un point de vente (POS_posPurchases) et participer à notre programme de fidélité (loyaltyScheme_loyCustomers). En choisissant la première option, vous obtiendrez probablement plus de résultats car les clients ne doivent exister que dans une seule entité supplémentaire.

### <a name="direct-relationship"></a>Relation directe

Une relation est classée comme une **relation directe** lorsqu’une entité source est liée à une entité cible avec une seule relation.

Par exemple, si une entité d’activité appelée *eCommerce_eCommercePurchases* est liée à une entité cible *eCommerce_eCommerceContacts* via *ContactId* uniquement, il s’agit d’une relation directe.

:::image type="content" source="media/direct_Relationship.png" alt-text="L’entité source se connecte directement à l’entité cible.":::

#### <a name="multi-path-relationship"></a>Relation à plusieurs chemins d’accès

Une **relation à plusieurs chemins d’accès** est un type spécial de relation directe qui connecte une entité source à plusieurs entités cibles.

Par exemple, si une entité d’activité appelée *eCommerce_eCommercePurchases* est liée à deux entités cibles, à la fois *eCommerce_eCommerceContacts* et *loyaltyScheme_loyCustomers*, il s’agit d’une relation à plusieurs chemins d’accès.

:::image type="content" source="media/multi-path_relationship.png" alt-text="L’entité source se connecte directement à plusieurs entités cibles par le biais d’une relation à plusieurs sauts.":::

### <a name="indirect-relationship"></a>Relation indirecte

Une relation est classée comme une **relation indirecte** lorsqu’une entité source est liée à une ou plusieurs entités supplémentaires avant d’être liée à une entité cible.

#### <a name="multi-hop-relationship"></a>Relation à plusieurs sauts

Une *relation à plusieurs sauts* est une *relation indirecte* qui vous permet de connecter une entité source à une entité cible par le biais d’une ou de plusieurs autres entités intermédiaires.

Par exemple, si une entité d’activité appelée *eCommerce_eCommercePurchasesWest* se connecte à une entité intermédiaire appelée *eCommerce_eCommercePurchasesEast*, puis se connecte à une entité cible appelée *eCommerce_eCommerceContacts*, il s’agit d’une relation à plusieurs sauts.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="L’entité source se connecte directement à une entité cible avec une entité intermédiaire.":::

### <a name="multi-hop-multi-path-relationship"></a>Relation à plusieurs sauts et plusieurs chemins d’accès

Les relations à plusieurs sauts et plusieurs chemins d’accès peuvent être utilisées ensemble pour créer des **relations à plusieurs sauts et plusieurs chemins d’accès**. Ce type spécial combine les fonctions des relations à **plusieurs sauts** et **plusieurs chemins d’accès**. Il vous permet de vous connecter à plusieurs entités cibles tout en utilisant des entités intermédiaires.

Par exemple, si une entité d’activité appelée *eCommerce_eCommercePurchasesWest* se connecte à une entité intermédiaire appelée *eCommerce_eCommercePurchasesEast*, puis se connecte à deux entités cibles, à la fois *eCommerce_eCommerceContacts* et *loyaltyScheme_loyCustomers*, il s’agit d’une relation à plusieurs sauts et plusieurs chemins d’accès.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="L’entité source se connecte directement à une entité cible et se connecte à une autre entité cible par le biais d’une entité intermédiaire.":::

## <a name="manage-existing-relationships"></a>Gérer les relations existantes 

Sur la page Relations, chaque relation est représentée par une ligne. 

Sélectionnez une relation et choisissez l'une des options suivantes : 
 
- **Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.
- **Supprimer** : Supprimez les relations personnalisées.
- **Afficher** : Affichez les relations créées par le système et les relations héritées. 

## <a name="next-step"></a>Étape suivante

Les relations système et personnalisées servent à [créer des segments](segments.md) et des [mesures](measures.md) basés sur plusieurs sources de données qui ne sont plus en silos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
