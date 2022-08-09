---
title: Créer des mesures à partir de modèles
description: Définissez des mesures à l’aide de modèles pour les cas d’utilisation courants.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170770"
---
# <a name="create-measures-from-templates"></a>Créer des mesures à partir de modèles

Utilisez des modèles prédéfinis de [mesures](measures.md) couramment utilisées pour les créer. Les modèles reposent sur les données mappées de l’entité *Activité unifiée*. Assurez-vous donc d’avoir configuré les [activités client](activities.md) avant de créer une mesure à partir d’un modèle.

Les modèles de mesures ne sont pris en charge que dans les environnements pour les **clients particuliers**. Pour créer des mesures personnalisées ou créer des mesures pour le B2B, voir [Utiliser le générateur de mesures](measure-builder.md).

Modèles de mesure disponibles :
- Valeur moyenne de la transaction (ATV)
- Valeur totale des transactions
- Chiffre d’affaires quotidien moyen
- Revenu mensuel moyen
- Chiffre d’affaires annuel moyen
- Nombre de transactions
- Points de fidélité gagnés
- Points de fidélité utilisés
- Solde des points de fidélité
- Durée de vie active du client
- Durée d’adhésion au programme de fidélité
- Durée écoulée depuis le dernier achat

## <a name="build-a-new-measure-using-a-template"></a>Créer une nouvelle mesure à l’aide d’un modèle

1. Accédez à **Mesures**.

1. Sélectionnez **Nouveau** et sélectionnez **Choisir un modèle**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Capture d’écran du menu déroulant lors de la création d’une nouvelle mesure avec mise en surbrillance du modèle.":::

1. Recherchez le modèle correspondant à vos besoins et sélectionnez **Choisir le modèle**.

1. Vérifiez les données requises et sélectionnez **Démarrer** si toutes les données sont en place.

1. Sélectionnez **Modifier les détails** en regard de Nom de la mesure. Attribuez un nom à la mesure. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags) à la mesure.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Boîte de dialogue Modifier les détails.":::

1. Cliquez sur **Terminé**.

1. Dans la section **Définir la période de temps**, définissez la période de temps des données. Choisissez si vous souhaitez que la nouvelle mesure couvre l’ensemble du jeu de données en sélectionnant **Tout le temps**, ou si vous souhaitez que la mesure se concentre sur une **Période spécifique**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Capture d’écran montrant la section de la période de temps lors de la configuration d’une mesure à partir d’un modèle.":::

1. Dans la section suivante, sélectionnez **Ajouter des données** pour choisir les activités et mapper les données correspondantes de votre entité *Activité unifiée*.

    1. Étape 1 sur 2 : dans **Type d’activité**, choisissez le type d’entité que vous souhaitez utiliser. Pour **Activités**, sélectionnez les entités à mapper, puis sélectionnez **Suivant**.
    1. Étape 2 sur 2 : choisissez l’attribut de l’entité *Activité unifiée* pour le composant requis par la formule. Par exemple, pour la valeur de transaction moyenne, il s’agit de l’attribut représentant la valeur de la transaction. Pour **Horodateur de l’activité**, choisissez l’attribut de l’entité *Activité unifiée* qui représente la date et l’heure de l’activité.
    1. Cliquez sur **Enregistrer**.

    Une fois le mappage des données terminé, vous pouvez voir le statut défini sur **Terminer** et le nom des activités et des attributs mappés.

1. Sélectionnez **Exécuter** pour calculer les résultats de la mesure. Sélectionnez **Enregistrer la version préliminaire** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement. La page **Mesures** s’affiche.

## <a name="next-step"></a>Étape suivante

Utilisez des mesures existantes pour créer un [segment de clients](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
