---
title: Configurer l'utilisation des données client et les préférences de consentement
description: Créez des règles de consentement et configurez les règles de consentement par défaut.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9f24072e2c315695fd810944c5e660453e577761
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753099"
---
# <a name="set-consent-data-rules-and-apply-consent-preferences"></a>Définir des règles de données de consentement et appliquer des préférences de consentement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Définissez la manière dont les données client sont utilisées en fonction des préférences de consentement d’un client. Vous pouvez choisir d'inclure ou d'exclure les données client des activités commerciales qui impliquent l'utilisation de données client. Par exemple, vous pouvez exclure des clients de vos annonces de produits s'ils n'ont pas donné leur consentement pour les e-mails marketing.

## <a name="start-the-consent-rules-setup-process"></a>Démarrer le processus de configuration des règles de consentement

D'abord, [importez les données de consentement](import-consent-data.md) avant de configurer les règles de consentement. 

Une fois les données de consentement dans le système, accédez à la page **Consentement** dans le Centre de consentement, puis sélectionnez **Définir des règles**.

:::image type="content" source="media/set-rules-control.png" alt-text="Page de consentement dans le Centre de consentement avec contrôle pour définir des règles.":::

## <a name="set-up-rules"></a>Configurer des règles

Les règles de données de consentement seront disponibles dans les informations d'audience où vous pourrez les appliquer en tant que règles à des segments ou des exportations individuels. Vous pouvez affecter ces règles aux objectifs et aux abonnements en tant que règles par défaut qui s'appliquent automatiquement à tous les segments. L'application vous guide à travers les étapes à suivre pour mapper les données de consentement. 

1. Dans le Centre de consentement, accédez à **Sources d'information** et sélectionnez **Définir des règles** pour commencer le processur de **Mappage des données de consentement**.

### <a name="set-rules"></a>Définir des règles

La première étape définit comment les clients doivent être inclus ou exclus en fonction de leurs préférences de contenu. Chaque source de données importée avec des données de consentement doit faire partie d'un mappage de règle. Par exemple, vous avez importé deux sources de données de consentement pour les offres de produits et les actualités de l'entreprise. Votre mappage de règles peut avoir deux mappages de règles. L'un comprend les contacts qui ont accepté de recevoir les offres de produits. L'autre exclut les contacts qui se sont désabonnés des actualités de l'entreprise.

1. À l'étape **Définir les règles**, créez la première règle.
   :::image type="content" source="media/set-up-rules-step.png" alt-text="Étape de configuration des règles avec les options disponibles."::: 
    1. Sous **Sélectionner les actions**, précisez si vous souhaitez **Inclure** ou **Exclure** des contacts. 
    1. Sous **Sélectionner les données**, choisissez les objectifs ou les abonnements auxquels appliquer la logique. 
    1. Sous **Sélectionner des valeurs**, sélectionnez les valeurs pour finaliser la règle.

1. Vous pouvez aussi sélectionner **Ajouter un autre mappage** pour définir plus de règles.

1. Lorsque vous avez terminé de définir les règles, sélectionnez **Suivant**.

### <a name="apply-rules-as-default-optional"></a>Appliquer les règles par défaut (facultatif)

Dans cette étape, vous choisissez les objectifs et les abonnements auxquels les mappages de règles seront appliqués à tous les segments dans les informations d'audience. Les règles pour les données de consentement importées sont automatiquement synchronisées avec les informations d'audience. Les administrateurs doivent [activer les règles de consentement](../audience-insights/activate-consent.md) et peut permettre aux utilisateurs de remplacer la sélection par défaut.

1. À l'étape **Appliquer les règles par défaut (facultatif)**, choisissez les objectifs et les abonnements auxquels appliquer la règle. Ces règles sont ensuite appliquées aux segments dans les informations d'audience.

   :::image type="content" source="media/apply-rules-default.png" alt-text="Sélectionnez les données auxquelles les règles s'appliquent par défaut.":::

1. Sélectionnez **Suivant**.

### <a name="review-and-finish"></a>Passer en revue et terminer

1. Vérifiez la configuration et sélectionnez **Définir des règles** pour terminer le processus. 

1. Si vous avez sélectionné certaines règles à appliquer comme règles par défaut, sélectionnez **Activer les règles de consentement dans Customer Insights** pour accéder aux informations d'audience et [activer les règles par défaut](../audience-insights/activate-consent.md). Sinon, sélectionnez **Terminé** pour compléter l'expérience guidée et appliquer la cartographie dans les processus métier.

## <a name="activate-rules-in-audience-insights"></a>Activer les règles dans les informations d'audience

Avant que les règles ne soient appliquées aux processus métier via les informations d'audience, un administrateur doit les activer. Pour plus d'informations, consultez [Activer les règles de consentement](../audience-insights/activate-consent.md).
