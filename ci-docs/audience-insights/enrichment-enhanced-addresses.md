---
title: Enrichissement de l’amélioration des adresses
description: Enrichissez et normalisez les informations sur les adresses des profils client avec les modèles Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965575"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enrichissement des profils client avec des adresses améliorées

Les adresses dans vos données peuvent être non structurées, incomplètes ou incorrectes. Utilisez les modèles de Microsoft pour normaliser et enrichir vos adresses dans le [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) pour une meilleure précision et une meilleure compréhension.

## <a name="how-we-enhance-addresses"></a>Valorisation des adresses

Notre modèle passe par un processus en deux étapes pour améliorer une adresse. Tout d’abord, il analyse l’adresse pour identifier ses composants et les met dans un format structuré. Ensuite, nous utilisons l’intelligence artificielle pour corriger, compléter et normaliser les valeurs de l’adresse.

### <a name="example"></a>Exemple

Les informations d’une adresse peuvent être dans un format non standard et contenir des fautes d’orthographe. Le modèle peut résoudre ces problèmes et créer des adresses cohérentes dans des profils client unifiés.

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

Les adresses améliorées ne fonctionnent qu’avec les valeurs qui existent déjà dans vos données d’adresse ingérées. Le modèle : 

1. ne vérifie pas si l’adresse est une adresse valide ;
2. ne vérifie pas si les valeurs, telles que les codes postaux ou les noms de rue, sont valides ;
3. ne change pas les valeurs qu’il ne reconnaît pas.

Le modèle utilise des techniques basées sur le Machine Learning pour améliorer les adresses. Bien que nous appliquions un seuil de confiance élevé lorsque le modèle modifie une valeur d’entrée, comme pour tout modèle basé sur Machine Learning, une précision de 100 % n’est pas garantie.

## <a name="supported-countries-or-regions"></a>Pays ou régions pris en charge

Nous soutenons actuellement l’enrichissement des adresses dans les pays ou régions suivants : 

- Australie
- Canada
- Royaume-Uni
- États-Unis

Les adresses doivent contenir une valeur de pays/région. Nous ne traitons pas les adresses de pays ou de régions qui ne sont pas pris en charge et les adresses pour lesquelles aucun pays ou région n’a été fourni.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Adresses améliorées**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Capture d’écran de la vignette Adresses améliorées.":::

1. Sélectionnez le **jeu de données client** et choisissez l’entité contenant les adresses que vous souhaitez enrichir. Vous pouvez sélectionner l’entité *Client* pour enrichir les adresses de tous vos profils client ou sélectionner une entité de segment pour enrichir les adresses uniquement dans les profils client contenus dans ce segment.

1. Sélectionnez la mise en forme des adresses dans votre jeu de données. Choisissez **Adresse à attribut unique** si les adresses de vos données utilisent un seul champ. Choisissez **Adresse à attributs multiples** si les adresses de vos données utilisent plusieurs champs de données.

   > [!NOTE]
   > Le pays/la région est obligatoire dans les adresses à attribut unique et à attributs multiples. Les adresses qui ne contiennent pas de valeurs pays/région valides ou prises en charge ne seront pas enrichies

1.  Mappez les champs d’adresse de votre entité client unifiée.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Page de mappage de champs d’adresse améliorée.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un nom pour l’enrichissement et pour l’entité de sortie.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépend de la taille de vos données client.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
