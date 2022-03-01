---
title: FAQ sur la version d’essai - Dynamics 365 Customer Insights
description: Solutions aux questions courantes liées à la configuration et à la gestion de la version d’évaluation de Customer Insights. Découvrez comment résoudre les problèmes spécifiques à la plateforme et aux applications.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642866"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>FAQ sur la version d’évaluation de Dynamics 365 Customer Insights

## <a name="sign-up"></a>Inscription

### <a name="what-are-the-system-requirements-for-the-trial"></a>Quelle est la configuration système requise pour l’essai ?

Cette application est un service basé sur le cloud qui n’a pas besoin de logiciel particulier hormis un navigateur web à jour, bien que certains limitations s’appliquent. Pour la meilleure expérience d’essai, évitez d’accéder au site d’essai en mode navigation privée et choisissez l’emplacement d’essai le plus proche de vous. [En savoir plus sur les critères de l’application web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Comment puis-je m’inscrire à l’essai sans locataire Microsoft 365 ?

Vous pouvez entrer une adresse e-mail non professionnelle et nous créerons un compte et un locataire pour vous.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Puis-je m’inscrire à plusieurs applications Dynamics 365 telles que Sales, Marketing, et Customer Service ?

Oui, vous pouvez. Pour voir tous les essais disponibles, [visitez la page du centre d’essais](https://dynamics.microsoft.com/dynamics-365-free-trial). Vous pouvez utiliser le même compte de messagerie pour vous inscrire à différents essais. Cependant, il n’est pas possible d’avoir plusieurs applications sur le même site d’essai. Chaque essai se déroulera sur une organisation et une URL différentes. Les données d’essai ne seront pas partagées entre les applications.

## <a name="trial-app"></a>Application d’essai

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Je n’ai pas reçu l’e-mail des détails de l’essai après m’être inscrit, que dois-je faire ?

Lorsque vous vous inscrivez pour l’essai, vous recevrez un e-mail avec les détails de l’essai. Si vous ne voyez pas l’e-mail dans votre boîte de réception, vérifiez votre dossier de courrier indésirable. Vous pouvez également suivre les étapes suivantes pour accéder à votre application :

1. Accédez au site d’essai et sélectionnez **Essayer gratuitement**.
1. Entrez l’identifiant de courrier que vous avez utilisé pour vous inscrire à l’essai. Vous serez redirigé vers votre application d’essai.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Comment ajouter des utilisateurs à une version d’essai ?

Pour ajouter des utilisateurs, accédez au [Centre d’administration Microsoft 365](https://admin.microsoft.com) en utilisant le compte administrateur d’essai. Suivez les [conseils du centre d’administration](/microsoft-365/admin/add-users/add-users) pour ajouter des utilisateurs jusqu’à la limite de la licence d’essai. Si l’utilisateur que vous ajoutez possède déjà un compte Microsoft 365, attribuez-lui un rôle de sécurité approprié dans l’organisation d’essai. Pour plus d’informations, consultez [Attribuez un rôle de sécurité à un utilisateur](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Combien d’utilisateurs puis-je ajouter à mon environnement d’évaluation ?

Vous pouvez ajouter un nombre illimité d’utilisateurs à l’environnement d’évaluation.

### <a name="how-do-i-reset-the-trial-environment"></a>Comment réinitialiser l’environnement d’essai ?

Vous ne pouvez pas réinitialiser l’environnement d’essai. Cependant, vous pouvez attendre la fin de la période d’essai, puis vous réinscrire pour un nouvel essai.

## <a name="trial-expiration-and-extension"></a>Expiration et prolongation de l’essai

### <a name="how-do-i-extend-the-trial"></a>Comment prolonger l’essai ?

Vous pouvez prolonger l’essai directement dans l’application. Vous pouvez prolonger votre évaluation une fois.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Puis-je convertir la version d’évaluation en licence payante ?

En règle générale, nous vous recommandons de recommencer avec vos propres données lors de la mise à niveau vers la version payante de Customer Insights. 

Facultativement, si vous utilisez uniquement les insights d’audience, vous pouvez copier vos données à partir d’un environnement d’essai si vous achetez Customer Insights. Vous devez être l’administrateur de la version d’essai de Customer Insights et l’administrateur global de votre client Microsoft 365, ou l’administrateur Dynamics 365 de votre organisation pour migrer les paramètres d’un environnement de version d’essai vers un environnement payant. 

Après vous être connecté à votre instance payante de Customer Insights pour la première fois, vous êtes invité à créer un environnement. Dans ce processus, vous pouvez choisir de copier la configuration à partir d’un environnement existant et de migrer la plupart des paramètres. Si vous disposez des autorisations mentionnées ci-dessus, l’environnement de la version d’essai apparaît dans cette liste. Pour plus d’informations, voir [Copier la configuration de l’environnement](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Quelles sont les limites d’essai et les quotas ?

- Vous ne pouvez pas utiliser votre propre compte Azure Data Lake Storage pour stocker les données de sortie lors d’une version d’essai des insights d’audience. Cependant, vous pouvez ingérer des données à partir d’un compte de Data Lake Storage.
- Vous pouvez stocker jusqu’à 3 Go de données dans l’environnement Dataverse qui est mis en service automatiquement lorsque vous démarrez un essai de Customer Insights.

## <a name="customer-insights-specific-questions"></a>Questions spécifiques à Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Comment puis-je commencer à utiliser l’essai ?

Après vous être inscrit à l’essai, vous arriverez sur l’écran principal de l’application. L’écran principal fournit des liens vers des guides d’utilisation et des didacticiels. Pour en savoir plus, visitez les liens dans la section [Ressources supplémentaires](trial-signup.md#additional-resources) de la page d’inscription à l’essai.

### <a name="what-features-are-available-in-the-trial"></a>Quelles fonctionnalités sont disponibles dans la version d’essai ?

La plupart des fonctionnalités de Customer Insights sont disponibles dans la version d’évaluation.

La fonctionnalité suivante n’est pas disponible : 
- Vous ne pouvez pas créer de nouveaux environnements qui utilisent votre propre compte Azure Data Lake Storage.

### <a name="how-long-does-the-trial-last"></a>Quelle est la durée de l’essai ?

L’essai de Customer Insights dure 30 jours. Vous pouvez prolonger l’essai une fois après 23 jours lorsque vous vous connectez à votre environnement d’essai.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Comment supprimer des exemples de données de l’essai ?

Vous ne pouvez pas supprimer les exemples de données de l’essai.
