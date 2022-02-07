---
title: Enrichissement de l’amélioration des adresses (contient une vidéo)
description: Enrichissez et normalisez les informations sur les adresses des profils client avec les modèles Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
---

# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enrichissement des profils client avec des adresses améliorées

Les adresses dans vos données peuvent être non structurées, incomplètes ou incorrectes. Utilisez les modèles de Microsoft pour normaliser et enrichir vos adresses dans le [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) pour une meilleure précision et une meilleure compréhension.

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

Les adresses améliorées ne fonctionnent qu’avec les valeurs qui existent déjà dans vos données d’adresse ingérées. Le modèle ne : 

1. vérifie pas si l’adresse est une adresse valide ;
2. vérifie pas si les valeurs, telles que le code postal ou le nom de rue, sont valides ;
3. modifie pas les valeurs qu’il ne reconnaît pas.

Le modèle utilise des techniques basées sur le Machine Learning pour améliorer les adresses. Bien que nous appliquions un seuil de confiance élevé lorsque le modèle modifie une valeur d’entrée, comme pour tout modèle basé sur Machine Learning, une précision de 100 % n’est pas garantie.

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

Les adresses doivent contenir une valeur de pays/région. Nous ne traitons pas les adresses de pays ou de régions qui ne sont pas pris en charge et les adresses pour lesquelles aucun pays ou région n’a été fourni.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Adresses améliorées**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Capture d’écran de la vignette Adresses améliorées.":::

1. Sélectionnez le **jeu de données client** et choisissez l’entité contenant les adresses que vous souhaitez enrichir. Vous pouvez sélectionner l’entité *Client* pour enrichir les adresses de tous vos profils client ou sélectionner une entité de segment pour enrichir les adresses uniquement dans les profils client contenus dans ce segment.

1. Sélectionnez la mise en forme des adresses dans votre jeu de données. Choisissez **Adresse à attribut unique** si les adresses de vos données utilisent un seul champ. Choisissez **Adresse à attributs multiples** si les adresses de vos données utilisent plusieurs champs de données.

   > [!NOTE]
   > Le pays ou la région est obligatoire à la fois dans les adresses à attribut unique et à attributs multiples. Les adresses qui ne contiennent pas de valeurs de pays ou de région valides ou prises en charge ne seront pas enrichies.

1.  Mappez les champs d’adresse de votre entité client unifiée.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Page de mappage de champs d’adresse améliorée.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un nom pour l’enrichissement et pour l’entité de sortie.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépend de la taille de vos données client.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez voir un exemple des données enrichies dans la vignette **Aperçu des clients enrichis**. Sélectionnez **Afficher plus** et sélectionnez l’onglet **Données** pour accéder à une vue détaillée de chaque profil enrichi.

### <a name="overview-card"></a>Carte de présentation

La carte de présentation affiche des détails sur la couverture de l’enrichissement. 

* **Adresses traitées et modifiées** : le nombre de profils clients avec des adresses qui ont été enrichis avec succès.

* **Adresses traitées et non modifiées** : le nombre de profils clients avec des adresses qui ont été reconnus mais non modifiés. Cela se produit généralement lorsque les données d’entrée sont valides et ne peuvent pas être améliorées par l’enrichissement.

* **Adresses non traitées et non modifiées** : le nombre de profils clients avec des adresses qui n’ont pas été reconnus. Généralement pour les données d’entrée non valides ou non prises en charge par l’enrichissement.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
