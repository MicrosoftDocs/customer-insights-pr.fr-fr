---
title: Créer et modifier des mesures
description: Définissez des mesures relatives aux clients pour analyser et refléter la performance de certains domaines d'activité.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405679"
---
# <a name="define-and-manage-measures"></a>Définir et gérer des mesures

Les **mesures** représentent des indicateurs de performance clés (KPI) qui reflètent la performance et la santé de secteurs d'activité spécifiques. Audience Insights offre une expérience intuitive pour créer différents types de mesures, en utilisant un générateur de requêtes qui ne vous demande pas d'écrire du code ou de valider manuellement vos mesures. Vous pouvez suivre vos mesures commerciales sur la page **Accueil**, voir les mesures pour des clients spécifiques sur la **Carte client** et utiliser des mesures pour définir les segments de clientèle de la page **Segments**.

## <a name="create-a-measure"></a>Créer une mesure

Cette section vous guide à travers la création d'une mesure à partir de zéro. Vous pouvez générer des mesures en exploitant des données de plusieurs sources qui sont désormais connectées via l'entité Client. Certaines [limites du service](service-limits.md) s'appliquent.

1. Dans Audience Insights, accédez à **Mesures**.

2. Sélectionnez **Nouvelle mesure**.

3. Choisissez la mesure **Type** :

   - **Attribut client** : Un champ unique par client qui reflète un score, une valeur, ou un état du client. Les attributs de client sont créés en tant qu'attributs dans une nouvelle entité générée par le système **Customer_Measure.**

   - **Mesure client** : Informations sur le comportement des clients avec répartition par dimensions sélectionnées. Une nouvelle entité est générée par mesure, avec plusieurs enregistrements potentiels par client.

   - **Mesure d'activité** : Effectue le suivi des performances et de la santé de votre entreprise. Les mesures d’activité peuvent avoir deux sorties différentes : une sortie numérique qui apparaît sur la page d'**accueil** ou une nouvelle entité que vous trouvez sur la page **Entités**.

4. Indiquez un **Nom** et un **nom complet** (en option), puis sélectionnez **Suivant**.

5. Pour la section **Entités**, sélectionnez la première entité dans la liste déroulante. À ce stade, vous devez décider si les entités supplémentaires sont nécessaires dans le cadre de la définition de votre mesure.

   > [!div class="mx-imgBorder"]
   > ![Définition de la mesure](media/measure-definition.png "Définition de la mesure")

   Pour ajouter plus d'entités, sélectionnez **Ajouter une entité** et sélectionnez les entités que vous souhaitez utiliser pour la mesure.

   > [!NOTE]
   > Vous ne pouvez sélectionner que les entités qui ont une relation avec votre entité de départ. Pour plus d'informations sur la définition des relations, voir [Relations](relationships.md).

6. Vous pouvez, si vous le souhaitez, configurer des variables. Dans la section **Variables**, sélectionnez **Nouvelle variable**.

   Les variables sont des calculs effectués sur chacun des enregistrements de vos champs sélectionnés. Par exemple, en additionnant le PDV et les ventes en ligne pour chacun de vos enregistrements client.

7. Donnez un **nom** à la variable.

8. Dans la zone **Expression**, choisissez un champ pour commencer votre calcul.

9. Saisissez une expression dans la zone **Expression** tout en choisissant plus de champs à inclure dans votre calcul.

   > [!NOTE]
   > Actuellement, seules les expressions arithmétiques sont prises en charge. En outre, le calcul des variables n'est pas pris en charge pour les entités provenant de différents [chemins d'entité](relationships.md).

10. Sélectionnez **Terminé**.

11. Dans la section **Définition de la mesure**, vous devez définir la manière dont les entités que vous avez choisies et les variables calculées sont agrégées dans une nouvelle entité de mesure ou un nouvel attribut Mesure.

12. Sélectionnez **Nouvelle dimension**. Vous pouvez considérer une dimension comme une fonction *Regrouper par*. Les données de votre nouvel attribut ou entité Mesure seront regroupées selon toutes vos dimensions définies.

    > [!div class="mx-imgBorder"]
    > ![Choisir un cycle de regroupement](media/measures-businessreport-measure-definition2.png "Choisir un cycle de regroupement")

    Sélectionnez ou entrez les informations suivantes dans le cadre de la définition de votre dimension :

    - **Entité** : Si vous définissez une entité Mesure, elle doit inclure au moins un attribut. Si vous définissez un attribut Mesure, il contiendra uniquement un attribut par défaut. Cette sélection a pour but de choisir l'entité contenant cet attribut.
    - **Champ** : sélectionnez l'attribut approprié à inclure dans votre entité ou votre attribut Mesure.
    - **Compartiment** : choisissez si vous voulez regrouper les données sur une base quotidienne, mensuelle ou annuelle. Il s'agit d'une sélection uniquement nécessaire si vous avez sélectionné un attribut de type Date.
    - **En tant que** : Définit le nom de votre nouveau champ.
    - **Nom complet** : Définit le nom complet de votre champ.

    > [!NOTE]
    > Votre mesure d'activité est enregistrée en tant qu'entité à un seul chiffre et s'affiche dans la page d'**accueil**, à moins que vous ajoutiez d'autres dimensions à votre mesure. Après avoir ajouté d'autres dimensions, la mesure *ne s'affichera pas* sur la page d'**accueil**.

13. Vous pouvez ajouter des fonctions d'agrégation si vous le souhaitez. Toute agrégation que vous créez a pour résultat une nouvelle valeur dans votre entité ou votre attribut Mesures. Les fonctions d'agrégation prises en charge sont : **Min**, **Max**, **Moyenne**, **Médian**, **Somme**, **Nombre Unique**, **Premier** (prend le premier enregistrement d'une valeur de dimension) et **Dernier** (prend le dernier enregistrement ajouté à une valeur de dimension).

14. Sélectionnez **Enregistrer** pour appliquer vos modifications à la mesure.

## <a name="manage-your-measures"></a>Gérer vos mesures

Après avoir créé au moins une mesure, vous verrez une liste de mesures sur la page **Mesures**.

Vous trouverez des informations sur le type de mesure, le créateur, la date et l'heure de création, la dernière date et heure de modification, le statut (si la mesure est active, inactive ou échouée) et la dernière date et heure d'actualisation. Lorsque vous sélectionnez une mesure dans la liste, vous pouvez afficher un aperçu de sa sortie.

Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.

> [!div class="mx-imgBorder"]
> ![Actions pour gérer des mesures uniques](media/measure-actions.png "Actions pour gérer des mesures uniques")

Vous pouvez également sélectionner une mesure dans la liste et effectuer l'une des actions suivantes :

- Sélectionner le nom de la mesure pour afficher ses détails.
- **Modifier** la configuration de la mesure.
- **Renommer** la mesure.
- **Supprimer** la mesure.
- Sélectionner les points de suspension (...) puis **Actualiser** pour démarrer le processus d'actualisation de la mesure.
- Sélectionner les points de suspension (...) puis **Télécharger** pour obtenir un fichier .CSV de la mesure.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d'autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d'un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l'une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="next-step"></a>Étape suivante

Vous pouvez utiliser les mesures existantes pour créer votre premier segment de clientèle sur la page **Segments**. Pour plus d'informations, voir [Segments](segments.md).
