---
title: Ajouter du code à votre site Web
description: Comment ajouter un extrait de code pour capturer des événements Dynamics 365 Customer Insights sur votre site Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231019"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installer le SDK Web sur un site Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cet article décrit comment un administrateur installe le kit de développement logiciel (SDK) Web sur un site Web. Vous commencerez à voir des événements dans votre espace de travail peu après l’instrumentation de votre site Web. Pour plus d'informations, consultez [Gérer les espaces de travail et les environnements](manage-environments-workspaces.md). Pour capturer des événements dans les applications mobiles, consultez [Vue d’ensemble des ressources du développeur](developer-resources.md).


### <a name="prerequisites"></a>Conditions préalables

* Vous devez disposer des autorisations Administrateur pour l'espace de travail afin de stocker les données.
* Votre site Web ou votre projet doit être hébergé en ligne pour envoyer des données d'activité. Les données envoyées à partir d'un fichier local ne seront pas acceptées par le serveur.


## <a name="add-web-sdk-to-your-website"></a>Ajouter le SDK Web à votre site Web

Allez dans **Administrateur** > **Espace de travail**, puis sélectionnez **Guide d'installation**. Deux options sont disponibles pour installer le SDK Web. La première consiste à utiliser un lien de téléchargement et la seconde à installer un package du gestionnaire de packages de nœuds (NPM).

### <a name="option-1-using-the-download-link"></a>Option 1 : utilisation du lien de téléchargement

1. Sélectionnez **Copier le code** pour copier l'extrait de code. Par défaut, la clé d'ingestion de votre espace de travail est intégrée dans l'extrait de code.
  :::image type="content" source="media/copy-code.png" alt-text="Capture d'écran de la page Extrait de code.":::

1. Ajoutez le code copié à votre site Web, à proximité <head> de la balise et avant tout autre script ou balises CSS.
1. Publiez votre site Web mis à jour et attendez quelques minutes pour capturer le trafic Web entrant.
1. Pour voir vos données, sélectionnez votre espace de travail dans le sélecteur d'espace de travail dans le volet de navigation. Ensuite, sélectionnez l'un des rapports dans la section **Découvrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Option 2 : utilisation du package NPM (recommandé pour les applications Web basées sur JavaScript)

1. Accédez à notre [Page Web NPM](https://www.npmjs.com/package/engagementinsights-web) et suivez les instructions pour installer et configurer le package NPM du SDK Web.
1. Publiez votre site Web mis à jour et attendez quelques minutes pour capturer le trafic Web entrant.
1. Pour voir vos données, sélectionnez votre espace de travail dans le sélecteur d'espace de travail dans le volet de navigation. Ensuite, sélectionnez l'un des rapports dans la section **Découvrir**.

## <a name="configuration-options"></a>Options de configuration

Vous pouvez modifier les options de configuration suivantes dans l'extrait de code :

- **ingestionKey** : Clé d'ingestion utilisée pour envoyer des événements à votre espace de travail. Vous pouvez modifier la clé d'ingestion pour envoyer des événements vers un autre espace de travail. Une clé d'ingestion est propre à chaque espace de travail.
- **autoCapture** : Spécifie si les vues et les interactions de page avec le site Web sont capturées. Deux options sont disponibles :
    - **afficher** : Définissez sur *true* pour capturer les vues de pages. Les vues de pages sont capturées comme *Vue* [événements](glossary.md#event), un type d'[événement de base](glossary.md#base-event).
    - **cliquer** : Définissez sur *true* pour capturer les interactions des visiteurs sur le site Web. Les interactions sont capturées comme *Action* [événements](glossary.md#event), un type d'[événement de base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
