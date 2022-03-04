---
title: Créer des mesures à partir de modèles
description: Définissez des mesures à l’aide de modèles pour les cas d’utilisation courants.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359916"
---
# <a name="use-a-template-to-build-a-measure"></a>Utiliser un modèle pour créer une mesure

Vous pouvez utiliser des modèles prédéfinis de [mesures](measures.md) couramment utilisées pour les créer. Les descriptions détaillées des modèles et une expérience guidée vous aident à créer des mesures de manière efficace. Les modèles reposent sur les données mappées de l’entité *Activité unifiée*. Assurez-vous donc d’avoir configuré les [activités client](activities.md) avant de créer une mesure à partir d’un modèle.

Pour créer des mesures personnalisées, voir [Utiliser le générateur de mesures pour créer des mesures à partir de zéro](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

Modèles de mesure disponibles : 
- Valeur moyenne de la transaction (ATV)
- Valeur totale des transactions
- Chiffre d’affaires quotidien moyen
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

1. Dans le volet **Modifier le nom**, définissez le nom de votre mesure et l’entité de sortie. 

1. Cliquez sur **Terminé**.

1. Dans la section **Définir la période de temps**, définissez la période de temps des données à utiliser. Choisissez si vous souhaitez que la nouvelle mesure couvre l’ensemble du jeu de données en sélectionnant **Tout le temps**, ou si vous souhaitez que la mesure se concentre sur une **Période spécifique**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Capture d’écran montrant la section de la période de temps lors de la configuration d’une mesure à partir d’un modèle.":::

1. Dans la section suivante, sélectionnez **Ajouter des données** pour choisir les activités et mapper les données correspondantes de votre entité *Activité unifiée*.

    1. Étape 1 sur 2 : dans **Type d’activité**, choisissez le type d’entité que vous souhaitez utiliser. Pour **Activités**, sélectionnez les entités que vous souhaitez mapper.
    1. Étape 2 sur 2 : choisissez l’attribut de l’entité *Activité unifiée* pour le composant requis par la formule. Par exemple, pour la valeur de transaction moyenne, il s’agit de l’attribut représentant la valeur de la transaction. Pour **Horodateur de l’activité**, choisissez l’attribut de l’entité Activité unifiée qui représente la date et l’heure de l’activité.
   
1. Une fois le mappage des données terminé, vous pouvez voir le statut défini sur **Terminer** et le nom des activités et des attributs mappés.

1. Vous pouvez maintenant sélectionner **Exécuter** pour calculer les résultats de la mesure. Pour l’affiner ultérieurement, sélectionnez **Enregistrer le brouillon**.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

Cette fonctionnalité n’est disponible que pour les mesures créées dans des environnements avec des clients individuels comme audience cible principale.

---
