---
title: Aperçu des segments (version préliminaire)
description: Obtenez des informations sur les segments existants pour voir les différences et les points communs.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171000"
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

1. Après avoir terminé l’analyse, trouvez des détails sur cet aperçu sur **Segments** > **Aperçu (version préliminaire)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Détails des informations sur le chevauchement des segments.":::

1. Sélectionnez un aperçu pour voir les résultats de l’analyse :

   - Nombre de membres chevauchant les segments sélectionnés pour l’analyse.
   - Le nombre de membres inclus dans l’un des segments, mais pas dans le reste des segments.
   - Si vous avez sélectionné des champs lors de la configuration de l’analyse de chevauchement, vous les trouverez dans les onglets correspondants. Vous pouvez utiliser le menu déroulant de filtres pour sélectionner un niveau d’attribut d’intérêt et la table en bas affichera les données correspondantes.

## <a name="segment-differentiators"></a>Facteurs de différenciation des segments

Les différenciateurs de segments vous aident à découvrir ce qui différencie un segment du reste de vos clients ou d’un autre segment. Sélectionnez un segment et le système identifie les attributs de profil et les mesures qui distinguent le segment sélectionné.

### <a name="run-a-differentiator-analysis"></a>Exécuter une analyse de différenciation

1. Accédez à **Segments** et sélectionnez l’onglet **Insights (aperçu)**.

1. Sélectionnez **Nouveau** et choisissez l’option **Différenciateurs** dans le volet **Choisir le type d’informations**.

1. Choisissez le segment que vous souhaitez analyser comme **Segment principal** et sélectionnez **Prochain**.

1. Choisissez **Tous les clients** ou un **Segment secondaire** pour comparer votre segment principal et sélectionnez **Prochain**.

1. Facultativement, choisissez un ou plusieurs champs d’intérêt pour concentrer l’analyse sur des attributs spécifiques et sélectionnez **Prochain**.

1. Fournissez un nom pour votre analyse de différenciateur, un nom complet facultatif et une description.

1. Sélectionnez **Enregistrer** pour démarrer l’analyse. L’analyse de différenciateur est prête lorsque le statut passe de Actualisation à Réussi.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Afficher et optimiser une analyse des différenciateurs

1. Après avoir terminé l’analyse, accédez à **Segments** > **Aperçu (version préliminaire)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Détails des informations sur le différenciateur des segments.":::

1. Sélectionnez un aperçu pour voir les résultats de l’analyse. Une analyse de différenciation comprend deux onglets : L’onglet **Attributs** répertorie les attributs de profil considérés comme des différenciateurs. L’onglet **Mesures** répertorie les différenciateurs. Chaque onglet comprend les détails suivants :

   - Liste classée des différenciateurs, triée par score de différence.
   - Le **Score de différence** pour chaque différenciateur. Le score de différence représente le degré de différence d’un attribut entre deux segments. Plus le score de différence est élevé, plus les attributs diffèrent entre les deux segments. Sélectionnez une partition pour ouvrir le volet **Score de différence** avec les distributions de valeurs pour cet attribut.

## <a name="manage-segment-insights"></a>Gérer les informations du segment

Accédez à **segments** > **Insights (version préliminaire)** pour afficher vos informations sur les segments et les gérer. Sélectionnez une information pour afficher les actions disponibles.

- **Afficher** l’analyse des informations
- **Modifier** l’information pour changer ses propriétés
- **Actualiser** l’information pour exécuter à nouveau l’analyse
- **Renommer** l’information
- **Supprimer** l’information

[!INCLUDE [footer-include](includes/footer-banner.md)]
