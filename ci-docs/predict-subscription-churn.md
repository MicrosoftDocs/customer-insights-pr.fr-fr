---
title: Prédire le taux de désabonnement (contient une vidéo)
description: Déterminez si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610233"
---
# <a name="predict-subscription-churn"></a>Prédire le taux de désabonnement

Déterminez si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société. Les données d’abonnement comprennent les abonnements actifs et inactifs pour chaque client ; il y a donc plusieurs entrées par ID de client.

Vous devez avoir des connaissances des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de désabonnement basées sur le temps, ce qui signifie qu’un client est considéré comme perdu un certain temps après la fin de son abonnement.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Essayez la prédiction du taux de désabonnement en utilisant des exemples de données : [Exemple de guide de prédiction du taux de désabonnement](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md).
- Au moins 10 profils client, de préférence plus de 1 000 clients uniques.
- ID client, identificateur unique pour faire correspondre les abonnements à vos clients.
- Données d’abonnement pour au moins le double de la période de temps sélectionnée. De préférence, deux à trois ans de données d’abonnement. L’historique des abonnements doit inclure :
  - **ID d’abonnement :** identificateur unique d’un abonnement.
  - **Date de fin de l’abonnement :** date d’expiration de l’abonnement pour le client.
  - **Date de début de l’abonnement :** date de début de l’abonnement pour le client.
  - **Date de la transaction :** date à laquelle un changement d’abonnement s’est produit. Par exemple, un client achetant ou annulant un abonnement.
  - **S’agit-il d’un abonnement récurrent :** champ booléen vrai/faux qui détermine si l’abonnement sera renouvelé avec le même ID d’abonnement sans intervention du client.
  - **Fréquence de périodicité (en mois) :** pour les abonnements récurrents, mois pendant lequel l’abonnement sera renouvelé. Par exemple, un abonnement annuel qui se renouvelle automatiquement pour un client chaque année pour une autre année a la valeur 12.
  - **Montant de l’abonnement :** montant de devise qu’un client paie pour le renouvellement de son abonnement. Il peut aider à identifier les modèles pour différents niveaux d’abonnement.
- Au moins deux enregistrements d’activité pour 50 % des clients pour lesquels vous souhaitez calculer le taux de désabonnement. Les activités client doivent inclure :
  - **Clé primaire :** identificateur unique d’une activité. Par exemple, une visite d’un site Web ou un enregistrement d’utilisation montrant que le client a regardé un épisode d’une émission de télévision.
  - **Horodateur :** date et heure de l’événement identifié par la clé primaire.
  - **Événement :** nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans un service de vidéo en streaming peut avoir la valeur « Affiché ».
  - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « ShowTitle » dans un service de vidéo en streaming peut avoir la valeur d’une vidéo regardée par un client.
- Moins de 20 % des valeurs manquantes dans le champ de données de l’entité fournie.

## <a name="create-a-subscription-churn-prediction"></a>Créer une prédiction du taux de désabonnement

Sélectionnez **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Le brouillon de prédiction s’affiche dans l’onglet **Mes prédictions**.

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Modèle d’attrition clients**.

1. Sélectionnez **Abonnement** pour le type d’attrition, puis **Démarrer**.

1. **Nommez ce modèle** et le **Nom de l’entité de sortie** pour les distinguer des autres modèles ou entités.

1. Cliquez sur **Suivant**.

### <a name="define-customer-churn"></a>Définir l’attrition client

1. Entrez le nombre de **Jours depuis la fin de l’abonnement** qu’un client est parti selon votre entreprise. Cette période est généralement liée aux activités commerciales, telles que les offres ou autres efforts de marketing visant à éviter de perdre le client.

1. Saisissez le nombre de **Jours à examiner à l’avenir pour prévoir l’attrition**. Par exemple, prédisez le risque d’attrition de vos clients au cours des 90 prochains jours pour vous aligner sur vos efforts de fidélisation avec le marketing. Prédire le risque d’attrition sur des périodes plus ou moins longues peut rendre plus difficile de prendre en compte les facteurs de votre profil de risque d’attrition, en fonction des exigences spécifiques de votre entreprise.

1. Cliquez sur **Suivant**.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** pour **Historique des abonnements**.

1. Sélectionnez le type d’activité sémantique **Abonnement** qui contient les informations requises sur l’historique des abonnements. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Ajouter les données requises pour le modèle de taux de désabonnement":::

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Ajouter des données** pour **Activités client**.

1. Sélectionnez le type d’activité sémantique qui fournit les informations sur les activités du client. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Ajoutez d’autres activités ou sélectionnez **Suivant**.

### <a name="set-update-schedule"></a>Définir le planning de mise à jour

1. Choisissez la fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

### <a name="review-and-run-the-model-configuration"></a>Examiner et exécuter la configuration du modèle

L’étape **Réviser et exécuter** affiche un résumé de la configuration et offre la possibilité d’apporter des modifications avant de créer la prédiction.

1. Sélectionnez **Modifier** dans l’une des étapes pour réviser et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Cliquez sur **Terminé**. L’onglet **Mes prédictions** s’affiche pendant la création de la prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Afficher les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Mes prédictions**, sélectionnez la prédiction que vous souhaitez afficher.

La page de résultats comporte trois sections principales de données :

- **Performances du modèle de formation** : les notes A, B et C indiquent les performances de la prédiction et peuvent vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Image de la zone d’informations du score du modèle avec la note A.":::

  Les notes sont calculées selon les règles suivantes :
  - **A** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients qui se sont désabonnés est supérieur d’au moins 10 % au taux de désabonnement moyen historique.
  - **B** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients qui se sont désabonnés est jusqu’à 10 % supérieur au taux de désabonnement moyen historique.
  - **C** lorsque le modèle a prédit avec précision moins de 50 % du total des prévisions, ou lorsque le pourcentage de prévisions précises pour les clients qui se sont désabonnés est inférieur au taux de désabonnement moyen historique.
  
- **Probabilité d’attrition (nombre de clients)**  : Groupes de clients en fonction du risque d’attrition prévu. Vous pouvez éventuellement [créer des segments de clients](prediction-based-segment.md) avec un risque de désabonnement élevé. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graphique montrant la distribution des résultats de désabonnement, divisés en plages de 0 à 100 %":::

- **Facteurs les plus influents :** De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun des facteurs a son importance calculée pour les prédictions regroupées créées par un modèle. Utilisez ces facteurs pour valider les résultats de votre prédiction. Ou bien, utilisez ces informations ultérieurement pour [créer des segments](.//prediction-based-segment.md) qui pourraient contribuer à influer sur le risque de désabonnement des clients.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Liste montrant les facteurs influents et leur importance dans la prévision du résultat du désabonnement.":::

> [!NOTE]
> Dans l’entité de sortie de ce modèle, *ChurnScore* est la probabilité prédite d’attrition et *IsChurn* est une étiquette binaire basée sur *ChurnScore* avec un seuil de 0,5. Si ce seuil par défaut ne fonctionne pas pour votre scénario, [créez un nouveau segment](segments.md) avec votre seuil préféré. Pour voir le score d’attrition, accédez à **Données** > **Entités** et affichez l’onglet de données de l’entité de sortie que vous avez définie pour ce modèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
