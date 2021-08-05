---
title: Informations sur les segments existants
description: Obtenez des informations sur les segments existants pour voir les différences et les points communs.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0803be651662480ddf1fd22952f6a69ee1603001
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554982"
---
# <a name="segment-insights-preview"></a>Aperçu des segments (version préliminaire)

Découvrez des aperçus et des informations supplémentaires sur vos segments existants. Découvrez ce qui différencie deux segments ou ce qu’ils ont en commun.

## <a name="segment-overlap"></a>Chevauchement de segment

L’analyse de chevauchement des segments montre combien et quels clients sont communs à deux segments ou plus. Par exemple, comment un segment de clients fréquents chevauche un segment qui contient des clients satisfaits de votre service ou produit.
Vous pouvez également analyser la façon dont le chevauchement change pour des attributs spécifiques.

### <a name="run-an-overlap-analysis"></a>Exécuter une analyse de chevauchement

1. Accédez à **Segments** et sélectionnez l’onglet **Insights (aperçu)**.

1. Sélectionnez **Nouveau** et choisissez l’option **Chevauchement** dans le volet **Choisir le type d’informations**.

1. Choisissez les segments d’intérêt et sélectionnez **Prochain**.

1. Facultativement, choisissez un ou plusieurs champs d’intérêt pour analyser les chevauchements pour chaque valeur de champ possible et sélectionnez **Prochain**.

1. Fournissez un nom pour votre analyse de chevauchement, un nom complet facultatif et une description.

1. Sélectionnez **Enregistrer** pour démarrer l’analyse. L’analyse de chevauchement est prête lorsque le statut passe de Actualisation à Réussi.

### <a name="view-and-optimize-an-overlap-analysis"></a>Afficher et optimiser une analyse de chevauchement

Après avoir terminé l’analyse, trouvez des détails sur cet aperçu sur **Segments** > **Aperçu (version préliminaire)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Détails des informations sur le chevauchement des segments.":::

Sélectionnez un aperçu pour voir les résultats de l’analyse :

- Nombre de membres chevauchant les segments sélectionnés pour l’analyse.
- Le nombre de membres inclus dans l’un des segments, mais pas dans le reste des segments.
- Si vous avez sélectionné des champs lors de la configuration de l’analyse de chevauchement, vous les trouverez dans les onglets correspondants. Vous pouvez utiliser le menu déroulant de filtres pour sélectionner un niveau d’attribut d’intérêt et la table en bas affichera les données correspondantes.

## <a name="segment-differentiators"></a>Facteurs de différenciation des segments

Les différenciateurs de segments vous aident à découvrir ce qui différencie un segment du reste de vos clients ou d’un autre segment. Il vous suffit de sélectionner un segment et le système identifie les attributs de profil et les mesures qui distinguent le segment sélectionné.

### <a name="run-a-differentiator-analysis"></a>Exécuter une analyse de différenciation

1. Accédez à **Segments** et sélectionnez l’onglet **Insights (aperçu)**.

1. Sélectionnez **Nouveau** et choisissez l’option **Chevauchement** dans le volet **Choisir le type d’informations**.

1. Choisissez le segment que vous souhaitez analyser comme **Segment principal** et sélectionnez **Prochain**.

1. Choisissez **Tous les clients** ou un **Segment secondaire** pour comparer votre segment principal et sélectionnez **Prochain**.

1. Facultativement, choisissez un ou plusieurs champs d’intérêt pour concentrer l’analyse sur des attributs spécifiques et sélectionnez **Prochain**.

1. Fournissez un nom pour votre analyse de chevauchement, un nom complet facultatif et une description.

1. Sélectionnez **Enregistrer** pour démarrer l’analyse. L’analyse de chevauchement est prête lorsque le statut passe de Actualisation à Réussi.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Afficher et optimiser une analyse des différenciateurs

Après avoir terminé l’analyse, trouvez des détails sur cet aperçu sur **Segments** > **Aperçu (version préliminaire)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Détails des informations sur le différenciateur des segments.":::

Sélectionnez un aperçu pour voir les résultats de l’analyse. Une analyse de différenciation comprend deux onglets : L’onglet **Attributs** répertorie les attributs de profil considérés comme des différenciateurs. L’onglet **Mesures** répertorie les différenciateurs. Chaque onglet comprend les détails suivants :

- Liste classée des différenciateurs, triée par score de différence.
- Le **Score de différence** pour chaque différenciateur. Le score de différence représente le degré de différence d’un attribut entre deux segments. Plus le score de différence est élevé, plus les attributs diffèrent entre les deux segments. Sélectionnez une partition pour ouvrir le volet **Score de différence** avec les distributions de valeurs pour cet attribut.

## <a name="manage-segment-insights"></a>Gérer les informations du segment

Vous pouvez utiliser les options suivantes sur vos informations à partir de la barre de commandes :

- **Retour** pour revenir à la liste des informations
- **Actualiser** pour exécuter à nouveau l’analyse
- **Supprimer** pour supprimer cette idée


[!INCLUDE[footer-include](../includes/footer-banner.md)]