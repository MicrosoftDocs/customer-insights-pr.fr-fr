---
title: Configurer et appliquer des règles de données de consentement
description: Avec la capacité de gestion du consentement de Dynamics 365 Customer Insights, vous pouvez définir la manière dont les données sont utilisées en fonction des préférences de consentement d’un client.
ms.date: 11/03/2021
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ba14bfbf1b459f5cb407d1f27b12d29cd14fc932
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232421"
---
# <a name="set-consent-data-rules-and-apply-consent-preferences"></a>Définir des règles de données de consentement et appliquer des préférences de consentement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Définissez la manière dont les données client sont utilisées en fonction des préférences de consentement d’un client. Vous pouvez choisir d’inclure ou d’exclure les données client des activités commerciales qui impliquent l’utilisation de données client. Par exemple, vous pouvez exclure des clients de vos annonces de produits s’ils n’ont pas donné leur consentement pour recevoir les courriers électroniques de marketing.

## <a name="start-the-consent-rules-setup-process"></a>Démarrer le processus de configuration des règles de consentement

D'abord, [importez les données de consentement](import-consent-data.md) avant de configurer les règles de consentement. 

Une fois les données de consentement dans le système, accédez à la page **Consentement** dans le Centre de consentement, puis sélectionnez **Définir des règles**.

:::image type="content" source="media/set-rules-control.png" alt-text="Page de consentement dans le Centre de consentement avec contrôle pour définir des règles.":::

## <a name="set-up-rules"></a>Configurer des règles

Les règles de données de consentement seront disponibles dans les informations d'audience où vous pourrez les appliquer en tant que règles à des segments ou des exportations individuels. Vous pouvez affecter ces règles par défaut aux objectifs et aux abonnements qui s’appliquent automatiquement à tous les segments. L’application vous guide à travers les étapes à suivre pour le mappage des données de consentement. 

1. Dans le Centre de consentement, accédez à **Sources d'information** et sélectionnez **Définir des règles** pour commencer le processur de **Mappage des données de consentement**.

### <a name="set-rules"></a>Définir des règles

La première étape définit comment les clients doivent être inclus ou exclus en fonction de leurs préférences de consentement. Chaque source de données importée avec des données de consentement doit faire partie d'un mappage de règle. Par exemple, vous avez importé deux sources de données de consentement pour les offres de produits et les actualités de l’entreprise, donc vous pouvez avoir deux mappages de règles. L’un pourrait inclure les contacts qui ont accepté les offres de produits et l’autre pourrait exclure les contacts qui ont refusé les actualités de l’entreprise.

1. À l'étape **Définir les règles**, créez la première règle.
   :::image type="content" source="media/set-up-rules-step.png" alt-text="Étape de configuration des règles avec les options disponibles."::: 
    1. Sous **Sélectionner les actions**, précisez si vous souhaitez **Inclure** ou **Exclure** des contacts. 
    1. Sous **Sélectionner les données**, choisissez les objectifs ou les abonnements auxquels appliquer la logique. 
    1. Sous **Sélectionner des valeurs**, sélectionnez les valeurs pour finaliser la règle.

1. Vous pouvez aussi sélectionner **Ajouter un autre mappage** pour définir plus de règles.

1. Lorsque vous avez terminé de définir les règles, sélectionnez **Suivant**.

### <a name="apply-rules-as-default-optional"></a>Appliquer les règles par défaut (facultatif)

Dans cette étape, vous pouvez choisir les objectifs et les abonnements auxquels les mappages de règles seront appliqués à tous les segments dans les informations d’audience. Les règles pour les données de consentement importées sont automatiquement synchronisées avec les informations d'audience. Les administrateurs doivent [activer les règles de consentement](../audience-insights/activate-consent.md) et peut permettre aux utilisateurs de remplacer la sélection par défaut.

1. À l’étape **Appliquer les règles par défaut (facultatif)**, choisissez les objectifs et/ou les abonnements auxquels appliquer la règle par défaut. Ces règles sont ensuite appliquées à tous les segments dans les informations d’audience.

   :::image type="content" source="media/apply-rules-default.png" alt-text="Sélectionnez les données auxquelles les règles s'appliquent par défaut.":::

1. Sélectionnez **Suivant**.

### <a name="review-and-finish"></a>Passer en revue et terminer

1. Vérifiez la configuration et sélectionnez **Définir des règles** pour terminer le processus. 

1. Si vous avez sélectionné certaines règles à appliquer par défaut, sélectionnez **Activer les règles de consentement dans Customer Insights** pour accéder aux informations d’audience et [activer les règles de consentement par défaut](../audience-insights/activate-consent.md). Sinon, sélectionnez **Terminé** pour compléter l'expérience guidée et appliquer la cartographie dans les processus métier.

## <a name="activate-rules-in-audience-insights"></a>Activer les règles dans les informations d'audience

Avant que les règles ne soient appliquées aux processus métier via les informations d'audience, un administrateur doit les activer. Pour plus d'informations, consultez [Activer les règles de consentement](../audience-insights/activate-consent.md).
