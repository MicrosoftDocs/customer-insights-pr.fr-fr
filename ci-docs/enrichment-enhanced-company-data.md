---
title: Amélioration des données de l’entreprise
description: Enrichissez et normalisez les données de l’entreprise avec les modèles de Microsoft.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645982"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enrichissement des profils d’entreprise avec des données d’entreprise enrichies

Utilisez les modèles de Microsoft et les données d’entreprise compilées pour corriger, compléter et standardiser les profils de votre entreprise. Nous allons utiliser le [format Common Data Model](/common-data-model/schema/core/applicationcommon/account) pour une meilleure précision et de meilleures informations.

Vous pouvez également [améliorer les données de l’entreprise sur les sources de données](data-sources-enrichment.md) pour améliorer la précision des correspondances dans le processus d’unification des données. 

Pour les entreprises publiques aux États-Unis, les informations telles que le revenu, le symbole boursier, le secteur d’activité, etc. sont disponibles.  

## <a name="how-we-enhance-company-data"></a>Notre façon d’améliorer les données de l’entreprise

Notre modèle exécute un processus en deux étapes pour améliorer un profil d’entreprise. Premièrement, il normalise le nom de l’entreprise. Par exemple, *Microsoft Corp* est corrigé et normalisé en *Microsoft Corporation*. Il essaie de trouver une correspondance dans les données d’entreprise compilées de Microsoft. Si une correspondance est trouvée, nous enrichissons le profil de l’entreprise avec des informations provenant de nos données d’entreprise compilées, y compris le nom de l’entreprise.


### <a name="example"></a>Exemple

Les informations de votre entreprise peuvent ne pas suivre un format standardisé et contenir des fautes d’orthographe. Le modèle essaie de résoudre ces problèmes et de créer des informations cohérentes.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitations

Il y a quelques limitations avec les données améliorées. Les éléments de la liste ci-dessous ne sont pas pris en charge par le modèle.

1.  Confirmez l’identité de la société. Nous ne vérifions pas si l’entrée est une organisation existante ou si une entreprise utilise la sortie comme nom standard.
2.  Couvrir complètement les entreprises du monde entier. Les données d’entreprise compilées de Microsoft ont une couverture mondiale, mais offrent la plupart des couvertures en Australie, au Canada, au Royaume-Uni et aux États-Unis.
3.  Standardisez les adresses des entreprises à l’échelle mondiale. Nous prenons actuellement en charge la normalisation des adresses dans ces pays ou régions : Australie, Canada, France, Allemagne, Italie, Japon, Royaume-Uni et États-Unis.
4.  Garantissez l’exactitude ou l’actualisation des données. Étant donné que les informations commerciales changent souvent, nous ne pouvons garantir que les données améliorées de l’entreprise fournies sont toujours exactes ou à jour.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Données d’entreprise améliorées**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Vignette Enrichissement dans le hub d’enrichissement des données de l’entreprise.":::

1. Sélectionnez le **jeu de données client** et choisissez l’entité contenant les adresses que vous souhaitez enrichir. Vous pouvez sélectionner l’entité *Client* pour enrichir les adresses de tous vos profils client ou sélectionner une entité de segment pour enrichir les adresses uniquement dans les profils client contenus dans ce segment.

1. Sélectionnez le type de champs de vos profils d’entreprise à utiliser pour la correspondance avec les données d’entreprise compilées de Microsoft. Cette sélection affectera les champs de mappage auxquels vous avez accès dans l’étape suivante.

1.  Mappez les champs de l’entreprise à partir de votre entité client unifiée. Plus vous mappez d’identifiants et de champs clés, plus le taux de correspondance est élevé.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Étape de mappage de données lors de la configuration d’un enrichissement d’entreprise.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un nom pour l’enrichissement et pour l’entité de sortie.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépend de la taille de vos données client.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez voir un exemple des données enrichies dans la vignette **Aperçu des clients enrichis**. Sélectionnez **Afficher plus** et sélectionnez l’onglet **Données** pour accéder à une vue détaillée de chaque profil enrichi.

### <a name="overview-card"></a>Carte de présentation

La carte de présentation affiche des détails sur la couverture de l’enrichissement. 

* **Entreprises traitées et modifiées** : le nombre de profils d’entreprises clientes qui ont été enrichis avec succès.

* **Entreprises traitées et non modifiées** : le nombre de profils d’entreprises clientes qui ont été reconnues mais non modifiées. Cela se produit généralement lorsque les données d’entrée sont valides et ne peuvent pas être améliorées par l’enrichissement.

* **Entreprises non traitées et non modifiées** : le nombre de profils d’entreprises clientes qui n’ont pas été reconnues. Cela se produit généralement pour les données d’entrée non valides ou non prises en charge par l’enrichissement.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
