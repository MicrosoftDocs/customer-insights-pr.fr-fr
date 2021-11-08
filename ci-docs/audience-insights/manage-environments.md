---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2d977ef4eb585e26b36139681552db22d84759c9
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673730"
---
# <a name="manage-environments"></a>Gérer des environnements

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Changer d’environnements

Sélectionnez le contrôle **Environnement** dans le coin supérieur droit de la page pour changer d’environnement.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Capture d’écran du contrôle pour changer d’environnement.":::

Les administrateurs peuvent [créer](create-environment.md) et gérer des environnements.

## <a name="edit-an-existing-environment"></a>Modifier un environnement existant

Vous pouvez modifier certains détails des environnements existants.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’icône **Modifier**.

3. Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour les paramètres de l’environnement.

Pour plus d’informations sur les paramètres d’environnement, consultez [Créer un environnement](create-environment.md).

## <a name="copy-the-environment-configuration"></a>Copier la configuration de l’environnement

Lorsque vous créez un environnement, vous pouvez choisir de copier la configuration à partir d’un environnement existant. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Capture d’écran des options de paramètres dans les paramètres d’environnement.":::

Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

Les paramètres de configuration suivants sont copiés :

- Sources de données ingérées/importées
- Configuration de l’unification des données (mappage, correspondance, fusion)
- Segments
- Mesures
- Relations
- Activités
- Index Rechercher et filtrer
- Destinations d’exportation
- Actualisation planifiée
- Enrichissements
- Gestion des modèles
- Attributions de rôles

Les données suivantes ne sont *pas* copiées :

- Profils client.
- Informations d’identification d’une source de données. Vous devrez fournir les informations d’identification pour chaque source de données et actualiser les sources de données manuellement.

- Sources de données du dossier Common Data Model et Dataverse - lac de données géré. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.

Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste des sources de données qui ont été copiées et qui nécessitent une authentification.":::

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

## <a name="reset-an-existing-environment"></a>Réinitialiser un environnement existant

En tant qu’administrateur, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et supprimer les données ingérées.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application. 

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Réinitialiser**. 

4.  Pour confirmer la suppression, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.

## <a name="delete-an-existing-environment"></a>Supprimer un environnement existant

En tant qu’administrateur, vous pouvez supprimer un environnement que vous administrez.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Supprimer**. 

4.  Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
