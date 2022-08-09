---
title: Rechercher des clients similaires avec l’IA (version préliminaire) (contient une vidéo)
description: Recherchez des segments de client similaires grâce à l’intelligence artificielle.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170724"
---
# <a name="find-similar-customers-with-ai-preview"></a>Rechercher des clients similaires avec l’IA (version préliminaire)

Trouvez des clients similaires dans votre clientèle grâce à l’intelligence artificielle. Vous devez avoir créé au moins un segment pour utiliser cette fonction. L’élargissement des critères d’un segment existant permet de trouver des clients similaires à ce segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Trouver des clients similaires* utilise des moyens automatisés pour évaluer les données et faire des prédictions basées sur ces données. Par conséquent, il a la capacité d’être utilisé comme méthode de profilage, tel que ce terme est défini par le Règlement général sur la protection des données (« RGPD »). L’utilisation par le client de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment les prédictions, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

## <a name="find-similar-customers"></a>Trouver des clients similaires

1. Accédez à **Segments** et sélectionnez le segment sur lequel vous souhaitez baser votre nouveau segment. C’est votre *segment source*.

1. Sélectionnez **Trouver des clients similaires**.

1. Vérifiez le nom suggéré pour votre nouveau segment et modifiez-le si nécessaire.

1. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags) au nouveau segment.

1. Passez en revue les champs qui définissent votre nouveau segment. Ces champs définissent la base sur laquelle le système tentera de trouver des clients similaires à votre segment source. Le système sélectionne les champs recommandés par défaut. Si nécessaire, ajoutez d’autres champs.
  Les champs susceptibles de réduire considérablement les performances du modèle sont automatiquement exclus :
  
   - Champs avec les types de données suivants : StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Champs avec une cardinalité (le nombre d’éléments dans un champ) inférieure à 2 ou supérieure à 30

1. Choisissez si vous souhaitez inclure **Tous les clients** à l’exception du segment source ou seulement des clients d’un **segment différent** dans votre nouveau segment.

1. Par défaut, le système suggère d’inclure seulement 20 % de la taille cible audience dans votre sortie. Modifiez ce seuil si nécessaire. L’augmentation du seuil réduira la précision.

1. Ajoutez des clients dans votre segment source en cochant la case **Inclure les membres de votre segment source en plus des clients avec des attributs similaires**.

1. Sélectionnez **Exécuter** en bas de la page pour démarrer une [tâche de classification binaire](#about-similarity-scores) (une méthode de machine learning) qui analyse le jeu de données.

## <a name="view-the-similar-segment"></a>Voir le segment similaire

Après avoir traité le segment similaire, vous rechercherez le nouveau segment répertorié sur la page **Segments** avec le type **Expansion**.

Sélectionnez **Afficher** pour voir la distribution des résultats à travers des [scores de similarité](#about-similarity-scores) et les valeurs de score de similarité sous **Aperçu des membres du segment**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment des clients similaires.":::

## <a name="manage-a-similar-segment"></a>Gérer un segment similaire

[Utilisez le résultat d’un segment similaire](segments.md#manage-existing-segments) comme vous le faites avec d’autres segments. Par exemple, exportez le segment ou créez une mesure.

Modifier, actualiser, renommer, télécharger et supprimer un segment similaire. La modification d’un segment similaire retraite vos données. Le segment précédemment créé est mis à jour avec des données actualisées.

## <a name="about-similarity-scores"></a>À propos des scores de similarité

Le modèle de classification binaire Machine Learning attribue un score aux clients du segment similaire. Le score est basé sur la similitude avec les clients du segment source.

- Les scores de similarité inférieurs à 0,55 sont des clients classés comme *différents* aux clients du segment source.
- Les scores de similarité entre 0,55 et 0,7 sont classés comme *peu similaires*.
- Les scores de similarité entre 0,7 et 0,85 sont classés comme *similaires*.
- Les scores de similarité entre 0,85 et 1 sont des clients classés comme *très similaires*.

Les clients avec des scores de similarité inférieurs à 0,4 ne sont pas inclus dans la sortie du modèle. Le système ne les considère pas suffisamment similaires au segment source.

[!INCLUDE [footer-include](includes/footer-banner.md)]
