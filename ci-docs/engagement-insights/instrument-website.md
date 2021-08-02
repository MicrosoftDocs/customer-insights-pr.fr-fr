---
title: Ajouter du code à votre site Web
description: Comment ajouter un extrait de code pour capturer des événements sur votre site Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1c66e0ef1293926d81e3fdb4a83362e944c1e5d8
ms.sourcegitcommit: 27dbe0668e623f1895108655cdd66ac4311c82e1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639772"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installer l’extrait de code sur un site Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Cet article décrit comment un administrateur installe l'extrait de code sur un site Web. Vous verrez des événements dans votre espace de travail peu de temps après avoir ajouté le script à votre site Web. Pour plus d'informations, consultez [Gérer les espaces de travail et les environnements](manage-environments-workspaces.md). Pour capturer des événements dans les applications mobiles, consultez [Vue d’ensemble des ressources du développeur](developer-resources.md).


### <a name="prerequisites"></a>Conditions préalables

* Vous devez disposer des autorisations Administrateur pour l'espace de travail afin de stocker les données.
* Votre site Web ou votre projet doit être hébergé en ligne pour envoyer des données d'activité. Les données envoyées à partir d'un fichier local ne seront pas acceptées par le serveur.


## <a name="add-code-to-your-website"></a>Ajouter du code à votre site Web
1.  Allez dans **Administrateur** > **Espace de travail**, puis sélectionnez **Guide d'installation**.
1. Sélectionnez **Copier le code** pour copier l'extrait de code. Par défaut, la clé d'ingestion de votre espace de travail est intégrée dans l'extrait de code.
:::image type="content" source="media/copy-code.png" alt-text="Capture d'écran de la page Extrait de code.":::
3. Ajoutez l'extrait de code copié à votre site Web, à côté <head> de la balise et avant tout autre script ou balises CSS.
4.  Publiez votre site Web mis à jour et attendez quelques minutes pour capturer le trafic Web entrant.
5.  Pour voir vos données, sélectionnez votre espace de travail dans le sélecteur d'espace de travail dans le volet de navigation. Ensuite, sélectionnez l'un des rapports dans la section **Découvrir**.

## <a name="configuration-options"></a>Options de configuration

Vous pouvez modifier les options de configuration suivantes dans l'extrait de code :

- **ingestionKey** : Clé d'ingestion utilisée pour envoyer des événements à votre espace de travail. Vous pouvez modifier la clé d'ingestion pour envoyer des événements vers un autre espace de travail. Une clé d'ingestion est propre à chaque espace de travail. 
- **autoCapture** : Spécifie si les vues et les interactions de page avec le site Web sont capturées. Deux options sont disponibles :
    - **afficher** : Définissez sur *true* pour capturer les vues de pages. Les vues de pages sont capturées comme *Vue* [événements](glossary.md#event), un type d'[événement de base](glossary.md#base-event).
    - **cliquer** : Définissez sur *true* pour capturer les interactions des visiteurs sur le site Web. Les interactions sont capturées comme *Action* [événements](glossary.md#event), un type d'[événement de base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
