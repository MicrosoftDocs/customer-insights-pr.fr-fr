---
title: Sélectionner les champs source pour l’unification des données
description: La première étape du processus d’unification consiste à sélectionner des entités, des attributs, des clés primaires et des types sémantiques pour mapper les données sur le profil client unifié.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740992"
---
# <a name="select-source-fields-for-data-unification"></a>Sélectionner les champs source pour l’unification des données

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

La première étape de l’unification consiste à sélectionner les entités et les champs au sein des ensembles de données que vous souhaitez unifier. Sélectionnez les entités qui contiennent des détails relatifs au client, tels que le nom, l’adresse, le numéro de téléphone et l’adresse e-mail. Vous pouvez sélectionner une ou plusieurs entités.

## <a name="select-entities-and-fields"></a>Sélectionner des entités et des champs

1. Accédez à **Données** > **Unifier**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Capture d’écran de la page de destination Unifier pour la première expérience d’exécution avec Démarrer en surbrillance.":::

1. Cliquez sur **Démarrer**.

1. Sur la page **Champs source**, sélectionnez **Sélectionner des entités et des champs**. Le volet **Sélectionner des entités et des champs** s’affiche.

1. Sélectionnez au moins une entité.

1. Pour chaque entité sélectionnée, identifiez les champs à utiliser pour faire correspondre les enregistrements client et les champs à inclure dans le profil unifié. Ces champs sont appelés *Attributs*. Vous pouvez sélectionner les attributs requis individuellement à partir d’une entité ou inclure tous les attributs d’une entité en cochant la case au niveau de l’entité. Vous pouvez rechercher des mots-clés dans tous les attributs et entités pour sélectionner les attributs requis que vous souhaitez mapper.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Capture d’écran des entités et des attributs sélectionnés.":::

   Dans cet exemple, nous ajoutons les entités **Contacts** et **CustomerLoyalty**. En choisissant ces entités, vous pouvez obtenir des informations sur les clients professionnels en ligne qui sont membres du programme de fidélité.

1. Sélectionnez **Appliquer** pour confirmer vos sélections. Les entités et les attributs sélectionnés s’affichent.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Sélectionnez la clé primaire et le type de sémantique pour les attributs

   :::image type="content" source="media/m3_select_primary.png" alt-text="Capture d’écran des entités sélectionnées avec la clé primaire non sélectionnée." lightbox="media/m3_select_primary.png":::

Pour chaque entité, effectuez les étapes suivantes.

1. Choisissez la **Clé primaire**. La clé primaire est un attribut unique à l’entité. Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle. Les attributs de type de données chaîne, entier et GUID sont pris en charge en tant que clés primaires.

1. Pour utiliser des modèles d’IA pour une prédiction intelligente de la sémantique, pour gagner du temps et améliorer la précision, assurez-vous que l’option **Mappage intelligent** est activée. Le mappage intelligent met en évidence la recommandation sémantique basée sur l’IA dans le champ **Type**. Vous pouvez remplacer la sélection suggérée en choisissant n’importe quel type sémantique dans la liste des options disponibles.

1. Pour chaque attribut, choisissez un **Type** de sémantique qui décrit le mieux cet attribut, comme le nom, la ville ou l’adresse e-mail.

   > [!NOTE]
   > Un champ doit correspondre au type de sémantique *Person.FullName* pour renseigner le nom du client dans la fiche client. Sinon, les cartes client apparaîtront sans nom.

   1. Pour modifier un type d’attribut identifié par le système, sélectionnez un autre type. Si le type n’existe pas, créez un type de sémantique personnalisé en sélectionnant le champ **Type** pour l’attribut, et en saisissant le nom du type de sémantique personnalisé.

   1. Pour ajouter un attribut contenant une URL à des images de profil ou des logos accessibles au public, sélectionnez l’entité et le champ contenant l’URL. Entrez ce qui suit dans le champ **Type** :
      - Pour une personne : Person.ProfileImage
      - Pour une organisation : Organization.LogoImage

   1. Pour un attribut de nom de compte, entrez Organization.Name dans le champ **Type**.

1. Passez en revue les attributs où un type de sémantique est automatiquement identifié. Ces attributs sont répertoriés sous **Vérifier les champs mappés**. Seuls les attributs de même type peuvent être combinés dans l’étape **Champs client unifiés**. Les types de sémantique sont utilisés pour suggérer automatiquement des informations. Assurez-vous que les types que vous avez choisis sont cohérents dans toutes les entités sélectionnées.

1. Pour les attributs qui ne sont pas automatiquement mappés à un type de sémantique, sélectionnez un champ de type de sémantique, entrez votre nom de type d’attribut personnalisé ou laissez-les non mappés. Ces attributs sont répertoriés sous **Définir les données dans les champs non mappés**.

1. Une fois les étapes de chaque entité effectuées, sélectionnez **Enregistrer les champs source**.

1. Cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape suivante : Supprimer les doublons](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
