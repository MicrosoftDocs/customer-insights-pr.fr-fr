---
title: Utiliser les API
description: Utilisez les API et comprenez leurs limitations.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808503"
---
# <a name="work-with-customer-insights-apis"></a>Utiliser les API de Customer Insights

Dynamics 365 Customer Insights fournit des API pour créer vos propres applications basées sur vos données dans Customer Insights.

> [!IMPORTANT]
> Les détails de ces API sont répertoriés dans la [Référence des API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ils comprennent des informations supplémentaires sur les opérations, les paramètres et les réponses.

Cet article explique comment accéder aux API Customer Insights, effectuer une inscription à Azure App et démarrer avec les bibliothèques clientes.

## <a name="get-started-trying-the-customer-insights-apis"></a>Se familiariser avec les API de Customer Insights

1. [Connectez-vous](https://home.ci.ai.dynamics.com) à Customer Insights. Si vous n’avez pas encore d’abonnement, [inscrivez-vous pour obtenir une version d’évaluation de Customer Insights](https://aka.ms/tryci).

1. Pour activer les API dans votre environnement Customer Insights, accédez à **Administrateur** > **Sécurité**. Des autorisations administrateur sont nécessaires pour effectuer cette opération.

1. Accédez à l’onglet **API** et sélectionnez le bouton **Activer**.    
 
   L’activation des API crée une clé d’abonnement primaire et secondaire pour votre instance qui est utilisée dans les demandes de l’API. Vous pouvez régénérer les clés en sélectionnant **Régénérer la clé primaire** ou **Régénérer la clé secondaire** sous **Administrateur** > **Sécurité** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Sélectionnez **Explorer nos API** pour [essayer les API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Choisissez une opération d’API et sélectionnez **Essayer**.

1. Dans le volet latéral, définissez la valeur dans le menu déroulant **Autorisation** sur **implicite**. L’en-tête `Authorization` est ajouté avec un jeton de porteur. Votre clé d’abonnement sera automatiquement renseignée.
  
1. Vous pouvez, si vous le souhaitez, ajouter tous les paramètres de requête nécessaires.

1. Faites défiler vers le bas du volet latéral et sélectionnez **Envoyer**.

La réponse HTTP apparaîtra bientôt en-dessous.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Créer une nouvelle inscription d’application dans le portail Azure

Ces étapes vous aident à commencer à utiliser les API de Customer Insights dans une application Azure en utilisant les autorisations déléguées. Assurez-vous de compléter au préalable la [section Mise en route](#get-started-trying-the-customer-insights-apis).

1. Connectez-vous au [Portail Azure](https://portal.azure.com) avec le compte pouvant accéder aux données de Customer Insights.

1. Sur la gauche, sélectionnez **Inscriptions d’application**.

1. Sélectionnez **Nouvelle inscription**, indiquez un nom d’application et choisissez le type de compte.

   Vous pouvez, si vous le souhaitez, ajouter une URL de redirection. http://localhost est suffisant pour développer une application sur votre ordinateur local.

1. Dans votre nouvelle inscription d’application, accédez à **Autorisations de l’API**.

1. Sélectionnez **Ajouter une autorisation** et sélectionnez **Dynamics 365 AI for Customer Insights** dans le volet latéral.

1. Pour le **Type d’autorisation**, sélectionnez **Autorisations déléguées**, puis sélectionnez l’autorisation **user_impersonation**.

1. Sélectionnez **Ajouter des autorisations**. Si vous devez accéder à l’API sans connexion de l’utilisateur, consultez la section [Autorisations d’application de serveur à serveur](#server-to-server-application-permissions).

1. Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.

Vous pouvez utiliser l’ID d’application/de client pour cette inscription d’application avec la bibliothèque d’authentification Microsoft (MSAL) pour obtenir un jeton porteur à envoyer avec votre demande à l’API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Pour plus d’informations sur MSAL, consultez [Vue d’ensemble de la bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Pour plus d’informations sur l’inscription d’applications dans Azure, consultez [Inscrire une application](/graph/auth-register-app-v2).

Pour plus d’informations sur l’utilisation des API dans nos bibliothèques clientes, consultez [Bibliothèques clientes de Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Autorisations d’application de serveur à serveur

La [section Inscription d’application](#create-a-new-app-registration-in-the-azure-portal) décrit comment inscrire une application qui nécessite la connexion de l’utilisateur pour l’authentification. Découvrez comment créer une inscription à une application qui ne nécessite aucune interaction utilisateur et peut être exécutée sur un serveur.

1. Dans votre inscription d’application sur le portail Azure, accédez à **Autorisations de l’API**.

1. Sélectionnez **Ajouter une autorisation**. 

1. Sélectionnez l’onglet **API utilisées par mon organisation** et choisissez **Dynamics 365 AI pour Customer Insights** dans la liste. 

1. Pour le **Type d’autorisation**, sélectionnez **Autorisations de l’application**, puis sélectionnez l’autorisation **CustomerInsights.Api.All**.

1. Sélectionnez **Ajouter des autorisations**.

1. Retournez à **Autorisations de l’API** pour votre inscription d’application.

1. Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Pour conclure, nous devons ajouter le nom de l’inscription d’application en tant qu’utilisateur dans Customer Insights.  
   
   Ouvrez Customer Insights, accédez à **Administrateur** > **Sécurité** et sélectionnez **Ajouter un utilisateur**.

1. Recherchez le nom de votre inscription d’application, sélectionnez-le dans les résultats de la recherche, puis sélectionnez **Enregistrer**.

## <a name="sample-queries"></a>Exemples de requêtes

Nous avons compilé une courte liste d’exemples de requêtes OData à utiliser avec les API : [Exemples de requêtes OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Bibliothèques client de Customer Insights

Cette section vous aide à utiliser les bibliothèques client disponibles pour les API de Customer Insights. Tout le code source de la bibliothèque et tous les exemples d’applications se trouvent sur la [page GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Découvrez comment utiliser les bibliothèques client C# de NuGet.org. Pour plus d’informations sur le package NuGet, consultez [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Actuellement, ce package cible les infrastructures netstandard2.0 et netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Ajouter la bibliothèque client C# à un projet C#

1. Dans Visual Studio, ouvrez le **Gestionnaire de package NuGet** pour votre projet.

1. Recherchez **Microsoft.Dynamics.CustomerInsights.Api**.

1. Sélectionnez **Installer** pour ajouter le package au projet.
 
   Vous pouvez également exécuter cette commande dans la **Console du gestionnaire de package NuGet** : `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Utiliser la bibliothèque client C#

1. Utilisez la [Bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pour obtenir un `AccessToken` en utilisant votre [Inscription d’application Azure](#create-a-new-app-registration-in-the-azure-portal) existante.

1. Après avoir réussi à authentifier et à acquérir un jeton, construisez un nouveau `HttpClient` ou utilisez-en un existant avec l’**Autorisation DefaultRequestHeaders** définie sur **jeton d’accès Porteur** et **Ocp-Apim-Subscription-Key** définie sur la [**clé d’abonnement** depuis votre environnement Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Rédéfinissez l’en-tête **Autorisation**, le cas échéant. Par exemple, lorsque le jeton a expiré.

1. Transmettez ce `HttpClient` dans la construction du client `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Utilisez le client pour appeler les « méthodes d’extension », par exemple, `GetAllInstancesAsync`. Si l’accès au `Microsoft.Rest.HttpOperationResponse` sous-jacent est recommandé, utilisez les « méthodes de message http », par exemple `GetAllInstancesWithHttpMessagesAsync`.

1. La réponse sera probablement de type `object`, car la méthode peut renvoyer plusieurs types (par exemple, `IList<InstanceInfo>` et `ApiErrorResult`). Pour vérifier le type de retour, vous devez utiliser les objets dans les types de réponse spécifiés sur la [page de détails de l’API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pour cette opération.    
   
   Si des informations supplémentaires sur la demande sont nécessaires, utilisez les **méthodes de message http** pour accéder à l’objet de réponse brute.

### <a name="nodejs-package"></a>Package NodeJS

Utilisez les bibliothèques clientes NodeJS disponibles via NPM : https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Package Python

Utilisez les bibliothèques clientes Python disponibles via PyPi : https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
