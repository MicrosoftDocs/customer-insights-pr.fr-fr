---
title: Utiliser les API
description: Utilisez les API et comprenez leurs limitations.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 8404515a20529c00708d84813f3a022ad98c45362a2f1e68d7aa890d085071a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033582"
---
# <a name="work-with-customer-insights-apis"></a>Utiliser les API de Customer Insights

Dynamics 365 Customer Insights fournit des API pour créer vos propres applications basées sur vos données dans Customer Insights.

> [!IMPORTANT]
> Les détails de ces API sont répertoriés dans la [Référence des API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ils comprennent des informations supplémentaires sur les opérations, les paramètres et les réponses.

Cet article explique comment accéder aux API de Customer Insights, créer un enregistrement d’application Azure et commencer à utiliser les bibliothèques clientes disponibles.

## <a name="get-started-trying-the-customer-insights-apis"></a>Se familiariser avec les API de Customer Insights

1. [Connectez-vous](https://home.ci.ai.dynamics.com) à Customer Insights. Si vous n’avez pas encore d’abonnement, [inscrivez-vous pour obtenir une version d’évaluation de Customer Insights](https://aka.ms/tryci).

1. Pour activer les API dans votre environnement Customer Insights, accédez à **Administration** > **Autorisations**. Des autorisations administrateur sont nécessaires pour effectuer cette opération.

1. Accédez à l’onglet **API** et sélectionnez le bouton **Activer**.    
 
   L’activation des API crée une clé d’abonnement primaire et secondaire pour votre instance qui est utilisée dans les demandes de l’API. Vous pouvez régénérer les clés en sélectionnant **Régénérer primaire** ou **Régénérer secondaire** sous **Administration** > **Autorisations** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Activez les API de Customer Insights.":::

1. Sélectionnez **Explorer nos API** pour [essayer les API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Choisissez une opération d’API et sélectionnez **Essayer**.

1. Dans le volet latéral, définissez la valeur dans le menu déroulant **Autorisation** sur **implicite**. L’en-tête `Authorization` est ajouté avec un jeton de porteur. Votre clé d’abonnement sera automatiquement renseignée.
  
1. Vous pouvez, si vous le souhaitez, ajouter tous les paramètres de requête nécessaires.

1. Faites défiler vers le bas du volet latéral et sélectionnez **Envoyer**.

La réponse HTTP apparaîtra bientôt en-dessous.

   :::image type="content" source="media/try-apis.gif" alt-text="Comment tester les API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Créer une nouvelle inscription d’application dans le portail Azure

Ces étapes vous aident à commencer à utiliser les API de Customer Insights dans une application Azure en utilisant les autorisations déléguées. Assurez-vous de compléter au préalable la [section Mise en route](#get-started-trying-the-customer-insights-apis).

1. Connectez-vous au [Portail Azure](https://portal.azure.com) avec le compte pouvant accéder aux données de Customer Insights.

1. Sur la gauche, sélectionnez **Inscriptions d’application**.

1. Sélectionnez **Nouvelle inscription**, indiquez un nom d’application et choisissez le type de compte.
 
   Vous pouvez, si vous le souhaitez, ajouter une URL de redirection. http://localhost est suffisant pour développer une application sur votre ordinateur local.

1. Dans votre nouvelle inscription d’application, accédez à **Autorisations de l’API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Comment définir les autorisations de l’API dans l’inscription de l’application.":::

1. Sélectionnez **Ajouter une autorisation** et sélectionnez **Customer Insights** dans le volet latéral.

1. Pour le **Type d’autorisation**, sélectionnez **Autorisations déléguées**, puis sélectionnez l’autorisation **user_impersonation**.

1. Sélectionnez **Ajouter des autorisations**. Si vous devez accéder à l’API sans connexion de l’utilisateur, consultez la section [Autorisations d’application de serveur à serveur](#server-to-server-application-permissions).

1. Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.

Vous pouvez utiliser l’ID d’application/de client pour cette inscription d’application avec la bibliothèque d’authentification Microsoft (MSAL) pour obtenir un jeton porteur à envoyer avec votre demande à l’API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Comment accorder le consentement de l’administrateur.":::

Pour plus d’informations sur MSAL, consultez [Vue d’ensemble de la bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Pour plus d’informations sur l’inscription d’applications dans Azure, consultez [Inscrire une application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Pour plus d’informations sur l’utilisation des API dans nos bibliothèques clientes, consultez [Bibliothèques clientes de Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Autorisations d’application de serveur à serveur

La [section Inscription d’application](#create-a-new-app-registration-in-the-azure-portal) décrit comment inscrire une application qui nécessite la connexion de l’utilisateur pour l’authentification. Découvrez comment créer une inscription d’application qui ne nécessite pas d’interaction de l’utilisateur et qui peut être exécutée sur un serveur.

1. Dans votre inscription d’application sur le portail Azure, accédez à **Autorisations de l’API**.

1. Sélectionnez **Ajouter une autorisation**. 

1. Sélectionnez l’onglet **API utilisées par mon organisation** et choisissez **Dynamics 365 AI pour Customer Insights** dans la liste. 

1. Pour le **Type d’autorisation**, sélectionnez **Autorisations de l’application**, puis sélectionnez l’autorisation **CustomerInsights.Api.All**.

1. Sélectionnez **Ajouter des autorisations**.

1. Retournez à **Autorisations de l’API** pour votre inscription d’application.

1. Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Comment accorder le consentement de l’administrateur.":::

1. Pour conclure, nous devons ajouter le nom de l’inscription d’application en tant qu’utilisateur dans Customer Insights.  
   
   Ouvrez Customer Insights, accédez à **Administration** > **Autorisations** et sélectionnez **Ajouter un utilisateur**.

1. Recherchez le nom de votre inscription d’application, sélectionnez-le dans les résultats de la recherche, puis sélectionnez **Enregistrer**.

## <a name="customer-insights-client-libraries"></a>Bibliothèques client de Customer Insights

Cette section vous aide à utiliser les bibliothèques client disponibles pour les API de Customer Insights. Tout le code source de la bibliothèque et tous les exemples d’applications se trouvent sur la [page GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Découvrez comment utiliser les bibliothèques client C# de NuGet.org. Pour plus d’informations sur le package NuGet, consultez [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Actuellement, ce package cible les infrastructures netstandard2.0 et netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Ajouter la bibliothèque client C# à un projet C#

1. Dans Visual Studio, ouvrez le **Gestionnaire de package NuGet** pour votre projet.

1. Recherchez **Microsoft.Dynamics.CustomerInsights.Api**.

1. Sélectionnez **Installer** pour ajouter le package au projet.
 
   Vous pouvez également exécuter cette commande dans la **Console du gestionnaire de package NuGet** : `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Ajoutez un package NuGet à un projet Visual Studio.":::

#### <a name="use-the-c-client-library"></a>Utiliser la bibliothèque client C#

1. Utilisez la [Bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pour obtenir un `AccessToken` en utilisant votre [Inscription d’application Azure](#create-a-new-app-registration-in-the-azure-portal) existante.

1. Une fois l’authentification et l’acquisition d’un jeton réalisées avec succès, construisez un nouveau jeton ou utilisez un jeton `HttpClient` existant avec le paramètre **DefaultRequestHeaders "Authorisation"** supplémentaire défini sur le **<access token> du porteur** et le paramètre **Ocp-Apim-Subscription-Key** défini sur la [**clé d’abonnement** de votre environnement Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Rédéfinissez l’en-tête **Autorisation**, le cas échéant. Par exemple, lorsque le jeton a expiré.

1. Transmettez ce `HttpClient` dans la construction du client `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exemple de httpclient.":::

1. Utilisez le client pour appeler les « méthodes d’extension », par exemple, `GetAllInstancesAsync`. Si l’accès au `Microsoft.Rest.HttpOperationResponse` sous-jacent est recommandé, utilisez les « méthodes de message http », par exemple `GetAllInstancesWithHttpMessagesAsync`.

1. La réponse sera probablement de type `object`, car la méthode peut renvoyer plusieurs types (par exemple, `IList<InstanceInfo>` et `ApiErrorResult`). Pour vérifier le type de retour, vous pouvez convertir en toute sécurité les objets dans les types de réponse spécifiés sur la [Page des détails de l’API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pour cette opération.    
   
   Si des informations supplémentaires sur la demande sont nécessaires, utilisez les **méthodes de message http** pour accéder à l’objet de réponse brute.

### <a name="nodejs-package"></a>Package NodeJS

Utilisez les bibliothèques clientes NodeJS disponibles via NPM : https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Package Python

Utilisez les bibliothèques clientes Python disponibles via PyPi : https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
