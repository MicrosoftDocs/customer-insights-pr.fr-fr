---
title: Créer de nouvelles mesures avec le générateur de mesures
description: Créez des mesures à partir de zéro pour analyser les indicateurs clés de votre entreprise.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170846"
---
# <a name="create-measures-with-measure-builder"></a>Créer de nouvelles mesures avec le générateur de mesures

Le générateur de mesures vous permet de définir des calculs à l’aide d’opérateurs mathématiques, de fonctions d’agrégation et de filtres. Définissez des mesures avec des attributs issus d’entités liées à l’entité *Client* unifiée.

La création de mesures dans des environnements B2C et B2B fonctionne de la même manière. Cependant, si votre environnement B2B [utilise des comptes avec des hiérarchies](relationships.md#set-up-account-hierarchies), vous pouvez choisir d’agréger la mesure sur des sous-comptes associés.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

Créez des mesures au niveau de clients individuels (attribut client, mesure client) ou au niveau de l’entreprise/organisation (mesure d’entreprise). L’attribut client et la mesure client vous permettent de suivre les performances par client. Par exemple, les dépenses totales de chaque client. Les mesures d’entreprise vous permettent de suivre les performances par entreprise. Par exemple, le chiffre d’affaires total de l’entreprise.

- Attribut client : génère un résultat sous forme de nouvel attribut, qui est enregistré en tant que nouvelle colonne dans l’entité générée par le système nommée *Mesure_client*. Lors de l’actualisation d’un attribut client, tous les autres attributs client de l’entité *Mesure_client* s’actualisent simultanément. De plus, les attributs du client sont affichés dans la carte de profil du client. Une fois exécuté ou enregistré, l’attribut client ne peut plus être remplacé par une mesure client.

- Mesure client : génère un résultat sous forme de sa propre entité et vous ne pouvez pas la remplacer par un attribut client une fois l’exécution ou l’enregistrement réalisé. Les mesures client ne s’affichent pas dans la carte de profil du client.

- Mesure d’entreprise : génère un résultat sous la forme de sa propre entité et s’affiche sur la page d’accueil de votre environnement Customer Insights.

1. Accédez à **Mesures**.

1. Sélectionnez **Nouveau** > **Créer votre propre segment**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Écran de configuration vide pour une mesure B2C." lightbox="media/measure-b2c.png":::

1. Sélectionnez **Modifier les détails** en regard de Mesure sans titre. Attribuez un nom à la mesure. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags) à la mesure.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Boîte de dialogue Modifier les détails.":::

1. Cliquez sur **Terminé**.

1. Pour suivre les performances au niveau de l’entreprise, basculez **Type de mesure** sur **Niveau entreprise**. L’option **Niveau client** est sélectionnée par défaut. Le **Niveau client** ajoute automatiquement l’attribut *CustomerId* aux Dimensions, tandis que le **Niveau entreprise** le supprime automatiquement.

1. Dans la zone de configuration, choisissez la fonction d’agrégation dans le menu déroulant **Sélectionner une fonction**. Les fonctions d’agrégation comprennent :
   - **Sum**
   - **Moyenne**
   - **Nombre**
   - **Nombre Unique**
   - **Max**
   - **Min**
   - **First** : prend la première valeur de l’enregistrement de données
   - **Dernière** : prend la dernière valeur ajoutée à l’enregistrement de données
   - **ArgMax** : trouve l’enregistrement de données qui donne la valeur maximale à partir d’une fonction cible
   - **ArgMin** : trouve l’enregistrement de données qui donne la valeur minimale à partir d’une fonction cible

1. Sélectionnez **Ajouter un attribut** pour sélectionner les données afin de créer cette mesure.

   1. Sélectionnez l’onglet **Attributs**.
   1. Entité Data : Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez mesurer.
   1. Attribut de données : choisissez l’attribut que vous souhaitez utiliser dans la fonction d’agrégation pour calculer la mesure. Vous ne pouvez sélectionner qu’un attribut à la fois.
   1. Si nécessaire, choisissez un attribut de données à partir d’une mesure existante en sélectionnant l’onglet **Mesures**. Sinon, recherchez un nom d’entité ou de mesure.
   1. Cliquez sur **Ajouter**.

1. Pour créer des mesures plus complexes, ajoutez plus d’attributs ou utilisez des opérateurs mathématiques sur votre fonction de mesure.

1. Pour ajouter des filtres, sélectionnez le **Filtre** dans la zone de configuration. L’application de filtres n’utilisera que les enregistrements qui correspondent aux filtres pour calculer la mesure.
  
   1. Dans la section **Ajouter un attribut** du volet **Filtres**, sélectionnez l’attribut que vous souhaitez utiliser pour créer des filtres.
   1. Définissez les opérateurs de filtre pour définir le filtre pour chaque attribut sélectionné.
   1. Cliquez sur **Appliquer**.

1. Sélectionnez **Dimension** pour choisir davantage de champs à ajouter en tant que colonnes à l’entité de sortie de la mesure.

   1. Sélectionnez **Modifier les dimensions** pour ajouter des attributs de données par lesquels vous souhaitez regrouper les valeurs de mesure. Par exemple, ville ou sexe.
      > [!TIP]
      > Si vous avez sélectionné **Niveau client** comme **Type de mesure**, l’attribut *CustomerId* est déjà ajouté. Si vous supprimez l’attribut, **Type de mesure** bascule sur **Niveau entreprise**.
   1. Cliquez sur **Terminé**.

1. Si des valeurs doivent être remplacées dans vos données par un entier, sélectionnez **Règles**. Configurez la règle et assurez-vous de ne choisir que des nombres entiers comme valeurs de remplacement. Par exemple, remplacez *nul* avec *0*.

1. S’il existe plusieurs chemins d’accès entre l’entité de données que vous avez mappée et l’entité *Client*, choisissez l’un des [chemins d’accès de relation d’entité](relationships.md). Les résultats de la mesure peuvent varier en fonction du chemin sélectionné.

   1. Sélectionner **Chemin d’accès vers la relation** et choisissez le chemin d’entité qui doit être utilisé pour identifier votre mesure. S’il n’y a qu’un seul chemin vers l’entité *Client*, ce contrôle ne s’affichera pas.
   1. Cliquez sur **Terminé**.

1. Pour ajouter d’autres calculs pour la mesure, sélectionnez **Nouveau calcul**. Utilisez uniquement les entités sur le même chemin d’entité que pour les nouveaux calculs. Des calculs supplémentaires s’affichent sous forme de nouvelles colonnes dans l’entité de sortie de mesure. Si nécessaire, sélectionnez **Modifier le nom** afin de créer un nom pour le calcul.

1. Sélectionnez les points de suspension verticaux (&vellip;) sur le calcul pour **dupliquer** ou **supprimer** un calcul d’une mesure.

1. Dans la zone **Aperçu**, vous verrez le schéma de données de l’entité de sortie de mesure, y compris les filtres et les dimensions. L’aperçu réagit de manière dynamique aux modifications de la configuration.

1. Sélectionnez **Exécuter** pour calculer les résultats de la mesure configurée. Sélectionnez **Enregistrer et fermer** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement. La page **Mesures** s’affiche.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

Créez des mesures au niveau de comptes individuels (mesure client) ou au niveau de tous les comptes (mesure d’entreprise).

- Mesure client : génère un résultat sous forme de sa propre entité. Les mesures client ne s’affichent pas dans la carte de profil du client.

- Mesure d’entreprise : génère un résultat sous la forme de sa propre entité et s’affiche sur la page d’accueil de votre environnement Customer Insights.

1. Accédez à **Mesures**.

1. Cliquez sur **Nouveau**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Écran de configuration vide pour une mesure B2B.":::

1. Sélectionnez **Modifier les détails** en regard de Mesure sans titre. Attribuez un nom à la mesure. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags) à la mesure. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Boîte de dialogue Modifier les détails.":::

1. Cliquez sur **Terminé**.

1. Dans la zone de configuration, choisissez la fonction d’agrégation dans le menu déroulant **Sélectionner une fonction**. Les fonctions d’agrégation comprennent :
   - **Sum**
   - **Moyenne**
   - **Nombre**
   - **Nombre Unique**
   - **Max**
   - **Min**
   - **First** : prend la première valeur de l’enregistrement de données
   - **Dernière** : prend la dernière valeur ajoutée à l’enregistrement de données

1. Sélectionnez **Ajouter un attribut** pour sélectionner les données afin de créer cette mesure.

   1. Sélectionnez l’onglet **Attributs**.
   1. Entité Data : Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez mesurer.
   1. Attribut de données : choisissez l’attribut que vous souhaitez utiliser dans la fonction d’agrégation pour calculer la mesure. Vous ne pouvez sélectionner qu’un attribut à la fois.
   1. Si nécessaire, choisissez un attribut de données à partir d’une mesure existante en sélectionnant l’onglet **Mesures**. Sinon, recherchez un nom d’entité ou de mesure.
   1. Sélectionnez **Ajouter** pour ajouter l’attribut sélectionné à la mesure.

1. Pour créer des mesures plus complexes, ajoutez plus d’attributs ou utilisez des opérateurs mathématiques sur votre fonction de mesure.

1. Pour ajouter des filtres, sélectionnez le **Filtre** dans la zone de configuration. L’application de filtres n’utilisera que les enregistrements qui correspondent aux filtres pour calculer la mesure.
  
   1. Dans la section **Ajouter un attribut** du volet **Filtres**, sélectionnez l’attribut que vous souhaitez utiliser pour créer des filtres.
   1. Définissez les opérateurs de filtre pour définir le filtre pour chaque attribut sélectionné.
   1. Sélectionnez **Appliquer** pour ajouter les filtres à la mesure.

1. Sélectionnez **Dimension** pour choisir davantage de champs à ajouter en tant que colonnes à l’entité de sortie de la mesure.

   1. Sélectionnez **Modifier les dimensions** pour ajouter des attributs de données par lesquels vous souhaitez regrouper les valeurs de mesure. Par exemple, ville ou sexe.
      > [!TIP]
      > L’attribut *CustomerId* est déjà ajouté. Il s’agit d’un type de mesure au niveau du client. Si vous supprimez l’attribut, le type de mesure passe sur Niveau entreprise.
   1. Sélectionnez **Terminé** pour ajouter les dimensions à la mesure.

1. Si des valeurs doivent être remplacées dans vos données par un entier, sélectionnez **Règles**. Configurez la règle et assurez-vous de ne choisir que des nombres entiers comme valeurs de remplacement. Par exemple, remplacez *nul* avec *0*.

1. Si vous [utilisez des comptes avec hiérarchies](relationships.md#set-up-account-hierarchies), passez en revue **Reporter des sous-comptes**.
   - S’il est défini sur **Désactivé**, la mesure est calculée pour chaque compte. Chaque compte obtient son propre résultat.
   - S’il est défini sur **Activé**, sélectionnez **Modifier** pour choisir la hiérarchie de compte en fonction des hiérarchies ingérées. La mesure ne produira qu’un seul résultat car elle est agrégée avec des sous-comptes.

1. S’il existe plusieurs chemins d’accès entre l’entité de données que vous avez mappée et l’entité *Client*, choisissez l’un des [chemins d’accès de relation d’entité](relationships.md). Les résultats de la mesure peuvent varier en fonction du chemin sélectionné.

   1. Sélectionner **Chemin d’accès vers la relation** et choisissez le chemin d’entité qui doit être utilisé pour identifier votre mesure. S’il n’y a qu’un seul chemin vers l’entité *Client*, ce contrôle ne s’affichera pas.
   1. Sélectionnez **Terminé** pour appliquer votre sélection.

1. Sélectionnez les points de suspension verticaux (&vellip;) sur le calcul pour **dupliquer** ou **supprimer** un calcul d’une mesure.

1. Dans la zone **Aperçu**, vous verrez le schéma de données de l’entité de sortie de mesure, y compris les filtres et les dimensions. L’aperçu réagit de manière dynamique aux modifications de la configuration.

1. Sélectionnez **Exécuter** pour calculer les résultats de la mesure configurée. Sélectionnez **Enregistrer et fermer** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement. La page **Mesures** s’affiche.

---

## <a name="next-step"></a>Étape suivante

Utilisez des mesures existantes pour créer un [segment de clients](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
