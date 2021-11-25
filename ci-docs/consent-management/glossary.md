---
title: Termes et concepts importants pour la capacité de gestion du consentement
description: Découvrez les termes et concepts couramment utilisés dans la capacité de gestion du consentement de Customer Insights.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 80a3a46c2e57470b8154b562ae6e42f23af48fdc
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732999"
---
# <a name="terms-and-concepts"></a>Termes et concepts

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="subscription-consent"></a>Consentement d'abonnement

Le consentement d'abonnement est un type de consentement qu'une personne peut fournir. Cela indique généralement l'intérêt d'une personne à être contactée pour la raison pour laquelle elle s'est abonnée. Par exemple, un bulletin d'informations qui informe sur les mises à jour d'un produit que la personne possède.

## <a name="purpose-consent"></a>Consentement d'objet

Le consentement d'objet est un type de consentement qu'une personne peut fournir. Il indique la finalité de l'utilisation et du traitement des données. Par exemple, une personne peut exprimer son consentement à une politique de cookies de site Web qui utilise le cookie pour une publicité ciblée. 

## <a name="consent-entity"></a>Entité de consentement

Un tableau de données qui résulte de l'importation des données de consentement dans la fonctionnalité de gestion des consentements de Dynamics 365 Customer Insights. Il contient les coordonnées de la personne qui a donné son consentement, le type de consentement, etc. Pour plus d'informations, consultez [Exigences de données pour les données de consentement](import-consent-data.md#data-requirements-for-consent-data).

## <a name="standard-actions"></a>Actions standards

Dans le cadre de [l'étape de mappage des données pour les données de consentement](set-consent-rules.md), les administrateurs définissent des règles qui s'appliquent à un type de consentement. Ils peuvent choisir d'inclure ou d'exclure les données de consentement selon une logique métier. Ces règles sont ensuite utilisées dans d'autres applications pour appliquer des règles de consentement dans les processus métier. Par exemple, une règle pour exclure tous les contacts qui ont défini leurs préférences de contact pour ne recevoir aucune information. Ces contacts sont supprimés de tous les segments d'informations audience utilisées pour l'envoi de newsletters.

