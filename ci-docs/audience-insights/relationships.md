---
title: Relations entre des entités et des chemins d’accès d’entités
description: Créez et gérez les relations entre des entités à partir de plusieurs sources de données.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171161"
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

## <a name="view-relationships"></a>Afficher les relations

La page Relations répertorie toutes les relations qui ont été créées. Chaque ligne représente une relation, qui inclut également des détails sur l'entité source, l'entité cible et la cardinalité. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste des relations et options dans la barre d'action de la page Relations.":::

Cette page propose un ensemble d'options pour les relations existants et nouvelles : 
- **Nouvelle relation** : [Créer une relation personnalisée](#create-a-custom-relationship).
- **Visualiseur** : [Explorez le visualiseur de relations](#explore-the-relationship-visualizer) pour voir un diagramme réseau des relations existantes et de leur cardinalité.
- **Filtrer par** : Choisissez le type de relations à afficher dans la liste.
- **Rechercher des relations** : Utilisez une recherche textuelle sur les propriétés des relations.

### <a name="explore-the-relationship-visualizer"></a>Explorez le visualiseur de relations

Le visualiseur de relations montre un diagramme réseau des relations existantes entre les entités connectées et de leur cardinalité.

Pour personnaliser l'affichage, vous pouvez modifier la position des cases en les faisant glisser sur le canevas.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Capture d'écran du diagramme réseau du visualiseur de relations avec les connexions entre les entités associées.":::

Options disponibles : 
- **Exporter en tant qu'image** : enregistre la vue actuelle en tant que fichier image.
- **Changer en disposition horizontale/verticale** : Modifiez l'alignement des entités et des relations.
- **Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.

## <a name="manage-existing-relationships"></a>Gérer les relations existantes 

Sur la page Relations, chaque relation est représentée par une ligne. 

Sélectionnez une relation et choisissez l'une des options suivantes : 
 
- **Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.
- **Supprimer** : Supprimez les relations personnalisées.
- **Afficher** : Affichez les relations créées par le système et les relations héritées. 

## <a name="next-step"></a>Étape suivante

Les relations système et personnalisées sont utilisées pour [créer des segments](segments.md) à partir de plusieurs sources de données qui ne sont plus en silos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
