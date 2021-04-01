---
title: Mapper des entités pour l’unification des données
description: Mappez des données pour créer des profils clients unifiés.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595990"
---
# <a name="map-entities-and-attributes"></a>Mapper les entités et attributs

Le **Mappage** est la première étape du processus d’unification des données des informations sur l’audience. Le mappage comprend trois phases :

- *Sélection d’entité* : Identifier les entités pouvant être combinées et qui peuvent conduire à un jeu de données contenant des informations plus complètes sur vos clients.
- *Sélection d’attribut* : Pour chaque entité, identifiez les colonnes à combiner et les réconcilier lors des étapes d’unification suivantes, à savoir la *mise en correspondance* et la *fusion*. Ces colonnes sont appelées *Attributs*.
- *Sélection de la clé primaire et du type de sémantique* : Pour chaque entité, identifiez un attribut que vous souhaitez définir comme clé primaire pour cette entité, et pour chaque attribut, identifiez un type de sémantique qui décrit le mieux cet attribut.

Pour plus d’informations sur le flux général d’unification des données, consultez [Unifier ](data-unification.md).

## <a name="select-the-first-entities"></a>Sélectionner les premières entités

1. Dans les informations sur l’audience, accédez à **Données** > **Unifier** > **Mapper**.

2. Lancer la phase de mappage en sélectionnant **Sélectionner des entités**.

3. Sélectionnez les entités et attributs que vous souhaitez utiliser dans les phases *mettre en correspondance* et *fusionner*. Vous pouvez sélectionner les attributs requis individuellement à partir d’une entité ou inclure tous les attributs d’une entité en cochant la case **Inclure tous les champs** au niveau de l’entité. Nous vous recommandons de sélectionner au moins deux entités pour bénéficier du processus d’unification des données.

   > [!div class="mx-imgBorder"]
   > ![Ajouter des entités - Exemple](media/data-manager-configure-map-add-entities-example.png "Ajouter des entités - Exemple")

   Dans cet exemple, nous ajoutons les entités **eCommerceContacts** et **loyCustomers**. En choisissant ces entités, vous pouvez obtenir des informations sur les clients professionnels en ligne qui sont membres du programme de fidélité.
   
   Vous pouvez rechercher des mots-clés dans tous les attributs et entités pour sélectionner les attributs requis que vous souhaitez mapper.
   
     > [!div class="mx-imgBorder"]
   > ![Exemple de champs de recherche](media/data-manager-configure-map-search-fields-example.png "Exemple de champs de recherche")

4. Sélectionnez **Appliquer** pour confirmer vos sélections.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Sélectionnez la clé primaire et le type de sémantique pour les attributs

Après avoir sélectionné vos entités, la page **Mapper** répertorie les entités sélectionnées pour votre examen. Définissez la clé primaire d’une entité et identifiez le type de sémantique d’un attribut dans l’entité.

- **Clé primaire** : Sélectionnez un attribut comme clé primaire pour chacune de vos entités. Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle. Les attributs de type de données Chaîne, Entier et GUID sont pris en charge en tant que clés primaires et seront affichés dans un champ dans lequel vous pourrez effectuer votre sélection.

- **Type de sémantique d’attribut :** Catégories dans lesquelles tombent vos attributs, telles que l’adresse de messagerie ou le nom. Pour utiliser des modèles IA pour la prédiction intelligente de la sémantique, gagner du temps et améliorer la précision, définissez **Mappage intelligent** sur **Activé**. Le mappage intelligent met en évidence la recommandation sémantique basée sur l’IA dans le champ **Type**. Si vous définissez cette option sur **Désactivé**, vous verrez nos recommandations de mappage normales. Vous pouvez sélectionner n’importe quel type sémantique dans la liste des options disponibles et remplacer la sélection suggérée.

> [!div class="mx-imgBorder"]
> ![Type d’attribut et prédiction sémantique](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Type d’attribut et prédiction sémantique")

Il est aussi possible d’ajouter un type de sémantique personnalisé. Sélectionnez le champ de type pour un attribut, puis tapez le nom de votre type de sémantique. De cette manière, vous pouvez également modifier les types d’attributs qui ont été identifiés par le système.

Tous les attributs pour lesquels un type de sémantique est automatiquement identifié sont regroupés dans la section **Examiner les champs mappés**. Passez en revue ces attributs et leurs types de sémantiques, car ils seront utilisés pour combiner vos entités lors de l’étape de fusion de l’unification des données.

Les attributs qui ne sont pas automatiquement mappés à un type de sémantique sont regroupés dans la section **Définir les données dans les champs non mappés**. Sélectionnez le champ de type de sémantique pour les attributs non mappés ou entrez votre nom de type d’attribut personnalisé.

> [!div class="mx-imgBorder"]
> ![Clé primaire et type d’attribut](media/data-manager-configure-map-add-attributes.png "Clé primaire et type d’attribut")

> [!NOTE]
> Un champ doit correspondre au type de sémantique Person.FullName pour renseigner le nom du client dans la fiche client. Sinon, les cartes client apparaîtront sans nom. 

## <a name="add-and-remove-attributes-and-entities"></a>Ajouter et supprimer des attributs et des entités

1. Sur **Unifier** > **Mapper**, sélectionnez **Modifier les champs**.

2. Dans le volet **Modifier les champs**, ajoutez ou supprimez des attributs et des entités. Utilisez la recherche ou faites défiler la liste des attributs et des entités qui vous intéressent. Vous ne pouvez pas supprimer un attribut ou une entité s’ils ont déjà été mis en correspondance.

   > [!div class="mx-imgBorder"]
   > ![Ajouter ou supprimer des attributs](media/configure-data-map-edit.png "Ajouter ou supprimer des attributs")

3. Cliquez sur **Appliquer**.

## <a name="add-images-to-profiles"></a>Ajouter des images aux profils

Si une entité contient des URL vers des images de profil ou des logos accessibles au public, vous pouvez les ajouter au profil client unifié.

Sélectionnez l’entité et recherchez le champ contenant l’URL vers l’image du profil. Dans le champ de saisie **Type**, entrez manuellement la valeur suivante : 
- Pour une personne : Person.ProfileImage
- Pour une organisation : Organization.LogoImage

Poursuivez les étapes d’unification et assurez-vous que l’attribut qui contient l’URL de l’image est également ajouté à l’étape [Fusionner](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Définir des attributs pour des organisations

Pour les organisations (version préliminaire), le type d’attribut doit être mis en correspondance avec « Organization.Name »
> [!div class="mx-imgBorder"]
> ![Clé primaire et type d’attribut B2B](media/configure-data-map-edit-b2b.png "Clé primaire et type d’attribut B2B")

## <a name="next-step"></a>Étape suivante

Dans le cadre du processus d’unification des données, accédez à la page **Mettre en correspondance**. Consultez [**Mettre en correspondance**](match-entities.md) pour vous familiariser avec cette phase.

> [!TIP]
> Consultez la vidéo suivante : [Mise en route : Création d’un profil client unifié](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]