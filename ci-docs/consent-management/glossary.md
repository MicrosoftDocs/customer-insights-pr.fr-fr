---
title: Termes et concepts de la gestion du consentement
description: Découvrez les termes et concepts couramment utilisés dans la capacité de gestion du consentement de Dynamics 365 Customer Insights.
ms.date: 09/30/2021
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-consent
- customerInsights
ms.openlocfilehash: bbe1e37d22d4ae2691187f16116f2fa07c55ab78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353524"
---
# <a name="terms-and-concepts"></a>Termes et concepts

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="subscription-consent"></a>Consentement d’abonnement

Le consentement d’abonnement est l’un des deux types de consentement qu’une personne peut fournir. Cela indique généralement l’intérêt d’une personne à être contactée pour la raison pour laquelle elle s’est abonnée. Par exemple, une personne peut consentir à recevoir une newsletter qui l’informe des mises à jour d’un produit qu’elle possède.

## <a name="purpose-consent"></a>Consentement d'objet

Le consentement d’objet est le deuxième type de consentement qu’une personne peut fournir. Il indique la finalité de l'utilisation et du traitement des données. Par exemple, une personne peut consentir à une politique de cookies de site Web qui utilise le cookie pour une publicité ciblée. 

## <a name="consent-entity"></a>Entité de consentement

Une entité de consentement est un tableau de données qui résulte de l’importation des données de consentement dans la fonctionnalité de gestion des consentements de Dynamics 365 Customer Insights. Elle contient les coordonnées de la personne qui a donné son consentement, le type de consentement, etc. Pour plus d’informations, accédez à [Exigences de données pour les données de consentement](import-consent-data.md#data-requirements-for-consent-data).

## <a name="standard-actions"></a>Actions standards

Dans le cadre de [l’étape de mappage des données pour la définition des règles des données de consentement](set-consent-rules.md), les administrateurs définissent des règles qui s’appliquent à un type de consentement. Ils peuvent choisir d'inclure ou d'exclure les données de consentement selon une logique métier. Ces règles sont ensuite utilisées dans d’autres applications pour appliquer des règles de consentement à des processus métier. Par exemple, une règle peut être définie pour exclure tous les contacts qui ont défini leurs préférences pour ne recevoir aucune information. Ces contacts sont ensuite supprimés de tous les segments d’informations audience utilisées pour l’envoi de newsletters.

