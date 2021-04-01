---
title: Relations entre des entités et des chemins d’accès d’entités
description: Créez et gérez les relations entre des entités à partir de plusieurs sources de données.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595209"
---
# <a name="relationships-between-entities"></a>Relations entre les entités

Avec les relations, connectez les entités entre elles et générez des graphiques de vos données lorsque les entités partagent un identificateur commun (clé étrangère) qui peut être référencé d’une entité à une autre. Les entités connectées vous permettent de définir des segments et des mesures à partir de sources de données multiples.

Il existe deux types de relations : Relations du système non modifiable, qui sont créées automatiquement, et relations personnalisées, créées et configurées par les utilisateurs.

Pendant les processus de mise en correspondance et de fusion, les relations système sont créées en coulisse en fonction de la mise en correspondance intelligente. Ces relations permettent d’associer les enregistrements du profil client avec d’autres enregistrements d’entités correspondantes. Le schéma suivant illustre la création de trois relations système quand l’entité Client est mise en correspondance avec d’autres entités pour générer l’entité finale Profil du client.

> [!div class="mx-imgBorder"]
> ![Création d’une relation](media/relationships-entities-merge.png "Création d’une relation")

- La **relation *CustomerToContact*** a été créée entre l’entité Client et l’entité Contact. L’entité Client reçoit le champ clé **Contact_contactId** pour se lier au champ clé **contactId** de l’entité Contact.
- La **relation *CustomerToAccount*** a été créée entre l’entité Client et l’entité Compte. L’entité Client reçoit le champ clé **Account_accountId** pour se lier au champ clé **accountId** de l’entité Compte.
- La **relation *CustomerToWebAccount*** a été créée entre l’entité Client et l’entité Compte Web. L’entité Client reçoit le champ clé **WebAccount_webaccountId** pour se lier au champ clé **webaccountId** de l’entité Compte Web.

## <a name="create-a-relationship"></a>Créer une relation

Définissez des relations personnalisées sur la page **Relations**. Chaque relation se compose d’une entité source (l’entité qui détient la clé étrangère) et d’une entité cible (l’entité vers laquelle pointe la clé étrangère de l’entité source).

1. Dans les informations sur l’audience, accédez à **Données** > **Relations**.

2. Sélectionnez **Nouvelle relation**.

3. Dans le volet **Ajouter une relation**, fournissez les informations suivantes :

   > [!div class="mx-imgBorder"]
   > ![Entrer les détails de la relation](media/relationships-add.png "Entrer les détails de la relation")

   - **Nom de la relation** : Indiquez un nom qui reflète l’objectif de la relation (par exemple, **Journauxcompteweb**).
   - **Description** : Description de la relation.
   - **Entité source** : Sélectionnez l’entité qui sert de source dans la relation (par exemple, Journalweb).
   - **Cardinalité** : Sélectionnez la cardinalité des enregistrement de l’entité source. Par exemple, « Beaucoup » signifie que plusieurs enregistrements de journal web sont associés à un Compte web.
   - **Champ Clé source** : Représente le champ de clé étrangère dans l’entité source. Par exemple, Journalweb possède le champ de clé étrangère **accountId**.
   - **Entité cible** : Sélectionnez l’entité qui sert de cible dans la relation (par exemple, Compte web).
   - **Cardinalité cible** : Sélectionnez la cardinalité des enregistrement de l’entité cible. Par exemple, « Un » signifie que plusieurs enregistrements de journal web sont associées à un Compte web.
   - **Champ de clé cible** : ce champ représente le champ de clé de l’entité cible. Par exemple, Compte web possède le champ de clé **accountId**.

> [!NOTE]
> Seuls les types de relation plusieurs-à-un et un-à-un sont pris en charge. Les relations Plusieurs-à-plusieurs peuvent être créées à l’aide de deux relations plusieurs-à-un et une entité de liaison (une entité qui sert à connecter l’entité source et l’entité cible).

## <a name="delete-a-relationship"></a>Supprimer une relation

1. Dans les informations sur l’audience, accédez à **Données** > **Relations**.

2. Activez les cases à cocher correspondant aux relations que vous souhaitez supprimer.

3. Sélectionnez **Supprimer** en haut de la table **Relations**.

4. Confirmez votre suppression.

## <a name="next-step"></a>Étape suivante

Les relations système et personnalisées sont utilisées pour créer des segments à partir de plusieurs sources de données qui ne sont plus en silos. Pour plus d’informations, voir [Segments](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]