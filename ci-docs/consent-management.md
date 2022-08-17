---
title: Utiliser le consentement du client
description: Respectez les préférences de consentement de vos clients dans Customer Insights en important les données de consentement.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245692"
---
# <a name="use-customer-consent"></a>Utiliser le consentement du client

Les réglementations sur la protection des données et la confidentialité donnent aux individus le droit de régir la manière dont une organisation utilise leurs données personnelles. Des exemples de telles réglementations sont le Règlement général sur la protection des données dans l'Union européenne ou le California Consumer Privacy Act aux États-Unis. Ces réglementations permettent aux personnes de refuser que leurs données personnelles soient collectées, traitées ou partagées avec des tiers.  

Les clients peuvent choisir de retirer ou de refuser leur consentement pour des formes de contact spécifiques. Ils peuvent également vous demander de refuser la collecte, le stockage, l'utilisation ou la vente de leurs données personnelles. Il est important que votre organisation respecte le consentement et les préférences de confidentialité de tous les clients.  

Dynamics 365 Customer Insights vous aide à honorer les demandes de vos clients en important et en stockant leurs préférences dans le cadre des profils client unifiés.

Si les données de consentement sont stockées séparément de vos profils clients, [ajoutez vos données de consentement en tant que nouvelle source de données](#import-and-unify-consent-data). La source de données qui contient les données de consentement est ajoutée au processus d'unification des données. L'unification réussie des données de consentement et des profils client conduit ensuite à des profils client unifiés qui contiennent les informations de consentement. Pour les profils client qui contiennent déjà des informations de consentement, accédez directement à la section [Utiliser les données de consentement](#use-consent-data).

## <a name="prerequisites"></a>Conditions préalables

Les informations suivantes doivent être disponibles dans vos données source pour unifier les données de consentement avec d'autres profils client :

- Clé secondaire pour mapper les informations de consentement aux profils utilisateur dans Customer Insights. Par exemple, une adresse e-mail ou un numéro de téléphone.
- Valeur de consentement pour déterminer le statut du consentement du client.

Pensez à ajouter les éléments *facultatifs* suivants :

- Clé primaire pour mettre à jour le statut de consentement si un client demande une modification.
- Type de consentement, s'il existe plusieurs façons de traiter les informations client.
- Date de consentement ou tout autre type de données pertinentes pour vos scénarios de consentement.

Exemple de tableau d'une base de données de consentement simple avec plusieurs options de consentement :

|ID de consentement (clé primaire)   |E-mail (clé secondaire)  |Possibilité de consentement  |Valeur de consentement  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Bulletin d’informations       |  False       |
|2    |  holly@contoso.com       |  Mises à jour du produit       |  Vrai       |
|3    |  frank@contoso.com       |  Bulletin d’informations       | Vrai        |
|4    |  frank@contoso.com       |  Mises à jour du produit       |  False       |

## <a name="import-and-unify-consent-data"></a>Importer et unifier les données de consentement

Importez des données de consentement de la même manière que vous ingérez d’autres sources de données dans Customer Insights. Pour plus d'informations sur les sources de données prises en charge et sur la manière de les importer, consultez [Présentation des sources de données](data-sources.md).

Pour plus d'informations sur l'unification de vos sources de données, consultez [Présentation de l'unification des données](data-unification.md).

## <a name="use-consent-data"></a>Utiliser les données de consentement

Une fois que vos données de consentement font partie de vos profils client unifiés, vous pouvez les utiliser dans Customer Insights. Par exemple, créez un segment avec une règle pour vous assurer que vous respectez les préférences de confidentialité et de protection des données de vos clients. Les règles prenant en charge les préférences de consentement sont utilisées pour exclure les utilisateurs d'un segment en fonction des attributs de profil. Ajoutez une règle à un segment qui exclut les profils clients qui n’ont pas donné leur consentement au contact.

En vous référant à l'exemple de tableau ci-dessus, un segment peut contenir cette règle : `Consent option=Newsletter & Consent value=True`. Cette configuration se traduit par un segment qui respecte les préférences de contact pour l'envoi d'une newsletter.

Pour plus d’informations sur la création de segments, consultez la section [Créer des segments](segment-builder.md).

Une fois le segment créé, vous pouvez utiliser l'une des nombreux [options d'exportation](export-destinations.md) pour utiliser le segment dans d'autres applications.

## <a name="ensure-updated-consent-status"></a>Assurez-vous que le statut de consentement est mis à jour

Il est important de maintenir à jour le statut de consentement de vos clients. L'actualisation planifiée dans Customer Insights importe toujours le dernier état de vos sources de données. Ces informations sont ensuite traitées par l'unification des données et aboutissent à des profils clients mis à jour. Ces profils mis à jour sont ensuite utilisés pour actualiser les segments afin de s'assurer que vous travaillez avec les informations les plus récentes.

En d'autres termes, assurez-vous que les données sources importées dans Customer Insights disposent toujours des informations les plus récentes.

Pour plus d'informations, voir [Actualiser les segments manuellement](segments.md#refresh-segments) ou [configurer une actualisation planifiée](schedule-refresh.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
