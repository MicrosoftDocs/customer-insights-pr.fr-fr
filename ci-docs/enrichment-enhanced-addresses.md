---
title: Enrichissement de l’amélioration des adresses (contient une vidéo)
description: Enrichissez et normalisez les informations sur les adresses des profils client avec les modèles Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953808"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enrichissement des profils client avec des adresses améliorées

Les adresses dans vos données peuvent être non structurées, incomplètes ou incorrectes. Utilisez les modèles de Microsoft pour normaliser et enrichir vos adresses dans le [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) pour une meilleure précision et une meilleure compréhension.

Vous pouvez également [enrichir les adresses sur les sources de données](data-sources-enrichment.md) pour améliorer la précision des correspondances dans le processus d’unification des données. 

## <a name="how-we-enhance-addresses"></a>Valorisation des adresses

Notre modèle passe par un processus en deux étapes pour améliorer une adresse. Tout d’abord, il analyse l’adresse pour identifier ses composants, puis les met dans un format structuré. Ensuite, nous utilisons l’IA pour corriger, compléter et normaliser les valeurs de l’adresse.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemple

Les informations d’adresse peuvent avoir un format non standard et contenir des fautes d’orthographe. Le modèle peut résoudre ces problèmes et créer des adresses cohérentes dans des profils client unifiés.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitations

Les adresses améliorées n’utilisent que les valeurs qui existent déjà dans les données d’adresse ingérées. Le modèle ne :

1. vérifie pas si l’adresse est une adresse valide ;
2. vérifie pas si les valeurs, telles que le code postal ou le nom de rue, sont valides ;
3. modifie pas les valeurs qu’il ne reconnaît pas.

Le modèle utilise des techniques basées sur le Machine Learning pour améliorer les adresses. Comme pour tout modèle basé sur l'apprentissage automatique, une précision à 100 % n'est pas garantie.

## <a name="supported-countries-or-regions"></a>Pays ou régions pris en charge

Nous prenons actuellement en charge l’enrichissement des adresses dans les pays ou régions suivants :

- Australie
- Canada
- France
- Allemagne
- Italie
- Japon
- Royaume-Uni
- États-Unis

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Adresses améliorées**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Capture d’écran de la vignette Adresses améliorées.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Sélectionnez la mise en forme des adresses dans votre jeu de données. Choisissez **Adresse à attribut unique** si les adresses de vos données utilisent un seul champ. Choisissez **Adresse à attributs multiples** si les adresses de vos données utilisent plusieurs champs de données.

1. Sélectionnez **Suivant** et mappez les champs d'adresse de votre entité client unifiée.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Page de mappage de champs d’adresse améliorée.":::

   > [!NOTE]
   > Le pays ou la région est obligatoire à la fois dans les adresses à attribut unique et à attributs multiples. Les adresses qui ne contiennent pas de valeurs de pays ou de région valides ou prises en charge ne seront pas enrichies.

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un **Nom** pour l’enrichissement et pour l’**Entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Le paramètre **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

### <a name="overview-card"></a>Carte de présentation

La carte **Vue d’ensemble des modifications apportées par les clients** affiche des détails sur la couverture de l’enrichissement :

- **Adresses traitées et modifiées** : le nombre de profils clients avec des adresses qui ont été enrichis avec succès.
- **Adresses traitées et non modifiées** : le nombre de profils clients avec des adresses qui ont été reconnus mais non modifiés. Cela se produit généralement lorsque les données d’entrée sont valides et ne peuvent pas être améliorées par l’enrichissement.
- **Adresses non traitées et non modifiées** : le nombre de profils clients avec des adresses qui n’ont pas été reconnus. Généralement pour les données d’entrée non valides ou non prises en charge par l’enrichissement.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
