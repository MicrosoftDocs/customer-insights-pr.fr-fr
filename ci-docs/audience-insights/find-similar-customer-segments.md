---
title: Trouver des clients similaires avec l’IA
description: Recherchez des segments de client similaires grâce à l’intelligence artificielle.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 96fbd18a20e0df7abd4e79ff77e2c3a396e33ccc
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554202"
---
# <a name="similar-customers-preview"></a>Clients similaires (version préliminaire)

Cette fonctionnalité vous permet de trouver des clients similaires dans votre clientèle en utilisant l’intelligence artificielle. Vous devez avoir créé au moins un segment pour utiliser cette fonction. L’élargissement des critères d’un segment existant permet de trouver des clients similaires à ce segment.

> [!NOTE]
> *Rechercher des clients similaires* utilise des moyens automatisés pour évaluer les données et faire des prévisions sur la base de ces données, et a donc la capacité d’être utilisé comme méthode de profilage, tel que ce terme est défini par le Règlement général sur la protection des données (« RGPD »). L’utilisation par le client de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment les prédictions, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

## <a name="finding-similar-customers"></a>Rechercher les clients similaires

1. Dans les informations sur l’audience, accédez à **Segments** et sélectionnez le segment sur lequel vous souhaitez baser votre nouveau segment. C’est votre *segment source*.

1. Dans la barre d’actions, sélectionnez **Rechercher des clients similaires**.

1. Vérifiez le nom suggéré pour votre nouveau segment et modifiez-le si nécessaire.

1. Passez en revue les champs qui définissent votre nouveau segment. Ces champs définissent la base sur laquelle le système tentera de trouver des clients similaires à votre segment source. Le système sélectionnera les champs recommandés par défaut.
  Les champs susceptibles de réduire considérablement les performances du modèle sont automatiquement exclus :
  
   - Champs avec les types de données suivants : StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Champs avec une cardinalité (le nombre d’éléments dans un champ) inférieure à 2 ou supérieure à 30

1. Choisissez si vous souhaitez inclure **Tous les clients** ou seulement des clients dans un **Segment existant spécifique** dans votre nouveau segment.

1. Excluez les clients dans votre segment source en sélectionnant la case **Exclure tout le monde dans le segment source**.

1. Par défaut, le système suggère d’inclure seulement 20 % de la taille cible audience dans votre sortie. Modifiez ce seuil si nécessaire. L’augmentation du seuil réduira la précision.

1. Sélectionnez **Exécuter** en bas de la page pour démarrer une tâche de classification binaire (une méthode de Machine Learning) qui analyse le jeu de données.

## <a name="view-the-similar-segment"></a>Voir le segment similaire

Après avoir traité le segment similaire, vous rechercherez le nouveau segment répertorié sur la page **Segments**.

> [!div class="mx-imgBorder"]
> ![Segment des clients similaires.](media/expanded-segment.png "Segment des clients similaires")

Sélectionnez **Vue** dans la barre d’action pour ouvrir le détail du segment. Cette vue contient des informations sur la distribution des résultats sur les [scores de similarité](#about-similarity-scores). Vous trouverez également les valeurs des scores de similarité dans l’**Aperçu des membres du segment**.

## <a name="use-the-output-of-a-similar-segment"></a>Utiliser la sortie d’un segment similaire

Vous pouvez [utiliser le résultat d’un segment similaire](segments.md) comme vous le faites avec d’autres segments. Par exemple, exportez le segment ou créez une mesure.

## <a name="refresh-and-edit-a-similar-segment"></a>Actualiser et modifier un segment similaire

Pour actualiser un segment similaire, sélectionnez-le sur la page **Segments** et sélectionnez **Actualiser** dans la barre d’actions.

La modification d’un segment similaire retraitera vos données. Le segment précédemment créé est mis à jour avec des données actualisées.    
Pour modifier un segment similaire, sélectionnez-le sur la page **Segments** et sélectionnez **Modifier** dans la barre d’actions. Appliquez vos modifications et sélectionnez **Exécuter** pour démarrer le traitement.

## <a name="delete-a-similar-segment"></a>Supprimer un segment similaire

Sélectionnez le segment sur la page **Segments** et sélectionnez **Supprimer** dans la barre d’actions. Puis confirmez votre suppression.

## <a name="about-similarity-scores"></a>À propos des scores de similarité

Le modèle de classification binaire Machine Learning attribue un score aux clients du segment similaire. Le score est basé sur la similitude avec les clients du segment source.

- Les scores de similarité inférieurs à 0,55 sont des clients classés comme *différents* aux clients du segment source.
- Les scores de similarité entre 0,55 et 0,7 sont classés comme *peu similaires*.
- Les scores de similarité entre 0,7 et 0,85 sont classés comme *similaires*.
- Les scores de similarité entre 0,85 et 1 sont des clients classés comme *très similaires*.

Les clients avec des scores de similarité inférieurs à 0,4 ne sont pas inclus dans la sortie du modèle. Le système ne les considère pas suffisamment similaires au segment source.


[!INCLUDE[footer-include](../includes/footer-banner.md)]