---
title: Compléter des données partielles avec des prédictions
description: Utilisez des prédictions pour remplir des données client incomplètes.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: e2cace3547a0b584dbf26ae5eecf86f3b256649f
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740716"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Complétez vos données partielles avec des prédictions (plus disponible)

> [!IMPORTANT]
> Cette fonctionnalité ne sera **plus disponible** à partir de **5 novembre 2021**. Les implémentations actuelles continueront de fonctionner jusqu’à ce que la fonctionnalité soit supprimée, mais vous ne pourrez pas créer de nouvelles intégrations à l’aide des instructions ci-dessous.

Les prédictions vous permettent de créer facilement des valeurs prédites qui peuvent améliorer votre compréhension d’un client. Sur la page **Intelligence** > **Prévisions**, vous pouvez sélectionner **Mes prévisions** pour voir les prévisions que vous avez configurées dans d’autres parties de Customer Insights, et vous permet de les personnaliser davantage.

> [!NOTE]
> Vous ne pouvez pas utiliser cette fonctionnalité si votre environnement utilise le stockage Azure Data Lake Gen 2.
>
> La fonctionnalité de prédictions utilise des moyens automatisés pour évaluer les données et faire des prédictions sur la base de ces données, et a donc la capacité d’être utilisée comme méthode de profilage, comme ce terme est défini par le Règlement général sur la protection des données (« RGPD »). L’utilisation par le client de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment les prédictions, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

## <a name="prerequisites"></a>Conditions préalables

Avant que votre organisation ne puisse utiliser la fonction de prévisions, les conditions préalables suivantes doivent être remplies :

1. Votre organisation a une instance [mise en place dans Microsoft Dataverse](/ai-builder/build-model#prerequisites) qui se trouve dans la même organisation que Customer Insights.

2. Votre environnement Customer Insights est attaché à votre instance de Dataverse.

Pour plus d’informations, consultez [Créer un environnement](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Créer une prédiction dans l’entité Client

1. Accédez à **Données** > **Entités**.

2. Sélectionnez l’entité **Client**.

3. Dans l’entité **Client : CustomerInsights**, sélectionnez l’onglet **Champs**.

4. Recherchez le nom d’attribut pour lequel vous souhaitez prédire des valeurs, puis sélectionnez l’icône **Aperçu** dans la colonne **Résumé**.
   > [!div class="mx-imgBorder"]
   > ![Icône de présentation.](media/intelligence-overviewicon.png "Icône de présentation")

5. S’il y a un taux élevé de valeurs manquantes pour votre attribut, sélectionnez **Prédire les valeurs manquantes** pour continuer votre prédiction.
   > [!div class="mx-imgBorder"]
   > ![Aperçu du statut avec bouton de prédiction des valeurs manquantes affiché.](media/intelligence-overviewpredictmissingvalues.png "Aperçu du statut avec bouton de prédiction des valeurs manquantes affiché")

6. Fournissez un **Nom d’affichage** et un **Nom d’entité de sortie** pour les résultats de la prédiction.

7. Une liste d’options préremplie indique où vous pouvez mapper les valeurs à une catégorie prédite. Dans ce cas, vos seules options de catégorie seront 0 ou 1, car elles correspondent à la nature vraie/fausse ou binaire de la prédiction. Dans la colonne Catégorie, mappez les valeurs de champ que vous souhaitez classer comme « 0 » dans la prédiction finale à « 0 » et les éléments que vous souhaitez classer comme « 1 » dans la prédiction finale à « 1 ».
   > [!div class="mx-imgBorder"]
   > ![Exemple montrant des valeurs de champ mappées à des catégories.](media/intelligence-categorymapping.png "Exemple montrant des valeurs de champ mappées à des catégories")

8. Sélectionnez **Terminé** et la prédiction sera traitée. Le traitement prendra un certain temps, selon la taille et la complexité des données. Les résultats seront disponibles dans une nouvelle entité basée sur la prédiction **Nom de l’entité de sortie** que vous avez créée.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Créer une prédiction tout en créant un segment

La prédiction de valeurs manquantes pour un attribut spécifique de choix est également possible lors de la création d’un segment. Plus précisément, lorsque vous créez rapidement un segment en fonction de votre entité client unifiée ou de l’entité Customer_Measure.

Dans le cadre de ce flux, vous choisissez un attribut spécifique sur lequel baser votre segment, comme la satisfaction du client ou le montant de l’achat. Lors de la création du segment, le système proposera une méthode pour prédire toute valeur manquante pour cet attribut.

1. Accédez à **Segments** et sélectionnez la vignette **Profils**.

2. Choisissez un **champ** pour créer un segment et sélectionner un **Opérateur**, puis sélectionnez **Réviser**.

3. Fournissez un **Nom** et un **Nom d’affichage** pour le segment.

4. Sélectionnez **Enregistrer**.

5. Si le segment que vous avez créé contient des données incomplètes dans le champ source, vous pouvez choisir de prédire les valeurs manquantes.
   > [!div class="mx-imgBorder"]
   > ![Bouton Prédiction.](media/segments-predictoption.png "Bouton Prédiction")

6. Fournissez un **Nom d’affichage** et un **Nom d’entité de sortie** pour les résultats de la prédiction.

7. Sélectionnez **Terminé**. Votre prédiction sera générée sous peu dans une nouvelle entité avec le nom que vous avez fourni pour le **Nom de l’entité de sortie**.

## <a name="view-a-prediction"></a>Afficher une prédiction

1. Accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.

2. Sélectionnez la prédiction à réviser.

3. Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Vue**.

4. Vous verrez un certain nombre de points de données dans la vue de votre prédiction.
   > [!div class="mx-imgBorder"]
   > ![Page Prédictions.](media/intelligence-predictionsviewpage.png "Page Prédictions")

   - **Valeurs prédites** affiche le mappage que vous avez créé pendant la phase de mappage de la valeur du champ à la catégorie. Il s’agit des valeurs de votre jeu de données qui ont été mappées à une catégorie spécifique.
   -**Principaux influenceurs** sont les facteurs au sein de votre jeu de données qui étaient les plus susceptibles d’influencer la confiance de la prédiction quant à la valeur de votre champ mappé à une catégorie spécifique.
   - **Performance** indique comment les prédictions se portent. Sélectionnez le lien pour en savoir plus.
   - **Aperçu** montre des échantillons du jeu de données de sortie de votre prédiction et la probabilité, ou notre confiance, de la valeur prédite où 0 est incertain et 1 est certain.

## <a name="update-a-prediction"></a>Mettre à jour une prédiction

1. Accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.

2. Sélectionnez la prédiction que vous souhaitez mettre à jour et sélectionnez l’icône **Mise à jour**.

3. La prédiction sera planifiée pour traitement. Vous pouvez voir l’heure de sa dernière mise à jour dans la colonne **Mis à jour** de la page **Prédictions**.

## <a name="edit-a-prediction"></a>Modifier une prédiction

Après avoir créé une prédiction, vous pouvez personnaliser le modèle dans AI Builder pour augmenter son efficacité.  

1. Accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.

2. Sélectionnez la prédiction que vous souhaitez modifier.

3. Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Vue**.

4. Sélectionnez **Personnaliser dans AI Builder**.

5. Mettez à jour votre modèle dans AI Builder. [En savoir plus sur la gestion des modèles dans AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

La prochaine exécution de votre prédiction utilisera le modèle mis à jour que vous avez créé.

> [!NOTE]
> Les nouveaux modèles créés dans AI Builder ne s’afficheront pas dans Customer Insights, sauf si le modèle a été créé à partir des expériences répertoriées ci-dessus.

## <a name="remove-a-prediction"></a>Supprimer une prédiction

1. Accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.

2. Sélectionnez la prédiction à supprimer.

3. Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Supprimer**.

4. Confirmez la suppression.

## <a name="troubleshooting"></a>Dépannage

Si vous ne pouvez pas terminer le processus d’attachement Dataverse en raison d’une erreur, vous pouvez essayer de terminer le processus manuellement. Deux problèmes connus peuvent survenir dans le processus d’attachement :

- La solution Complément de carte client n’est pas installée.
    1. Suivez les instructions pour [installer et configurer la solution](customer-card-add-in.md).

- Les autorisations de l’application ne sont pas accordées.
    1. Accédez à [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Sélectionnez **Environnements**.
    1. Sélectionnez les points de suspension en regard de l’environnement auquel vous souhaitez ajouter l’autorisation et sélectionnez **Paramètres**.
    1. Développez **Utilisateurs + autorisations** et sélectionnez **Utilisateurs**.
    1. Sélectionnez **+ Nouveau** et sélectionnez **Utilisateur**.
    1. Sélectionnez **Utilisateur de l’application** s’il n’est pas déjà sélectionné et entrez les informations suivantes :
        - **Nom d’utilisateur :** cihelp@microsoft.com
        - **ID d’application** : 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Prénom** : Client
        - **Nom** : Informations
        - **E-mail principal** : cihelp@microsoft.com
    1. Cliquez sur **Enregistrer et fermer**.
    1. Sélectionnez l’utilisateur que vous venez de créer.
    1. Sélectionnez **Gérer les rôles** dans la barre de menus supérieure.
    1. Sélectionnez **Administrateur système**, puis sélectionnez **OK**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
