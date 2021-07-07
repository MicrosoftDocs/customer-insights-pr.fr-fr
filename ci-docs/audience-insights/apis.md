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
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304739"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="98b67-103">Utiliser les API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="98b67-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="98b67-104">Dynamics 365 Customer Insights fournit des API pour créer vos propres applications basées sur vos données dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b67-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98b67-105">Les détails de ces API sont répertoriés dans la [Référence des API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="98b67-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="98b67-106">Ils comprennent des informations supplémentaires sur les opérations, les paramètres et les réponses.</span><span class="sxs-lookup"><span data-stu-id="98b67-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="98b67-107">Cet article explique comment accéder aux API de Customer Insights, créer un enregistrement d’application Azure et commencer à utiliser les bibliothèques clientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="98b67-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="98b67-108">Se familiariser avec les API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="98b67-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="98b67-109">[Connectez-vous](https://home.ci.ai.dynamics.com) à Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b67-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="98b67-110">Si vous n’avez pas encore d’abonnement, [inscrivez-vous pour obtenir une version d’évaluation de Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="98b67-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="98b67-111">Pour activer les API dans votre environnement Customer Insights, accédez à **Administration** > **Autorisations**.</span><span class="sxs-lookup"><span data-stu-id="98b67-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="98b67-112">Des autorisations administrateur sont nécessaires pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="98b67-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="98b67-113">Accédez à l’onglet **API** et sélectionnez le bouton **Activer**.</span><span class="sxs-lookup"><span data-stu-id="98b67-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="98b67-114">L’activation des API crée une clé d’abonnement primaire et secondaire pour votre instance qui est utilisée dans les demandes de l’API.</span><span class="sxs-lookup"><span data-stu-id="98b67-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="98b67-115">Vous pouvez régénérer les clés en sélectionnant **Régénérer primaire** ou **Régénérer secondaire** sous **Administration** > **Autorisations** > **API**.</span><span class="sxs-lookup"><span data-stu-id="98b67-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Activer les API de Customer Insights":::

1. <span data-ttu-id="98b67-117">Sélectionnez **Explorer nos API** pour [essayer les API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="98b67-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="98b67-118">Choisissez une opération d’API et sélectionnez **Essayer**.</span><span class="sxs-lookup"><span data-stu-id="98b67-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="98b67-119">Dans le volet latéral, définissez la valeur dans le menu déroulant **Autorisation** sur **implicite**.</span><span class="sxs-lookup"><span data-stu-id="98b67-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="98b67-120">L’en-tête `Authorization` est ajouté avec un jeton de porteur.</span><span class="sxs-lookup"><span data-stu-id="98b67-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="98b67-121">Votre clé d’abonnement sera automatiquement renseignée.</span><span class="sxs-lookup"><span data-stu-id="98b67-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="98b67-122">Vous pouvez, si vous le souhaitez, ajouter tous les paramètres de requête nécessaires.</span><span class="sxs-lookup"><span data-stu-id="98b67-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="98b67-123">Faites défiler vers le bas du volet latéral et sélectionnez **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="98b67-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="98b67-124">La réponse HTTP apparaîtra bientôt en-dessous.</span><span class="sxs-lookup"><span data-stu-id="98b67-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Comment tester les API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="98b67-126">Créer une nouvelle inscription d’application dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="98b67-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="98b67-127">Ces étapes vous aident à commencer à utiliser les API de Customer Insights dans une application Azure en utilisant les autorisations déléguées.</span><span class="sxs-lookup"><span data-stu-id="98b67-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="98b67-128">Assurez-vous de compléter au préalable la [section Mise en route](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="98b67-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="98b67-129">Connectez-vous au [Portail Azure](https://portal.azure.com) avec le compte pouvant accéder aux données de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b67-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="98b67-130">Sur la gauche, sélectionnez **Inscriptions d’application**.</span><span class="sxs-lookup"><span data-stu-id="98b67-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="98b67-131">Sélectionnez **Nouvelle inscription**, indiquez un nom d’application et choisissez le type de compte.</span><span class="sxs-lookup"><span data-stu-id="98b67-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="98b67-132">Vous pouvez, si vous le souhaitez, ajouter une URL de redirection.</span><span class="sxs-lookup"><span data-stu-id="98b67-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="98b67-133">http://localhost est suffisant pour développer une application sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="98b67-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="98b67-134">Dans votre nouvelle inscription d’application, accédez à **Autorisations de l’API**.</span><span class="sxs-lookup"><span data-stu-id="98b67-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Comment définir les autorisations de l’API dans l’inscription de l’application.":::

1. <span data-ttu-id="98b67-136">Sélectionnez **Ajouter une autorisation** et sélectionnez **Customer Insights** dans le volet latéral.</span><span class="sxs-lookup"><span data-stu-id="98b67-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="98b67-137">Pour le **Type d’autorisation**, sélectionnez **Autorisations déléguées**, puis sélectionnez l’autorisation **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="98b67-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="98b67-138">Sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="98b67-138">Select **Add permissions**.</span></span> <span data-ttu-id="98b67-139">Si vous devez accéder à l’API sans connexion de l’utilisateur, consultez la section [Autorisations d’application de serveur à serveur](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="98b67-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="98b67-140">Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.</span><span class="sxs-lookup"><span data-stu-id="98b67-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="98b67-141">Vous pouvez utiliser l’ID d’application/de client pour cette inscription d’application avec la bibliothèque d’authentification Microsoft (MSAL) pour obtenir un jeton porteur à envoyer avec votre demande à l’API.</span><span class="sxs-lookup"><span data-stu-id="98b67-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Comment accorder le consentement de l’administrateur.":::

<span data-ttu-id="98b67-143">Pour plus d’informations sur MSAL, consultez [Vue d’ensemble de la bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="98b67-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="98b67-144">Pour plus d’informations sur l’inscription d’applications dans Azure, consultez [Inscrire une application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="98b67-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="98b67-145">Pour plus d’informations sur l’utilisation des API dans nos bibliothèques clientes, consultez [Bibliothèques clientes de Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="98b67-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="98b67-146">Autorisations d’application de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="98b67-146">Server-to-server application permissions</span></span>

<span data-ttu-id="98b67-147">La [section Inscription d’application](#create-a-new-app-registration-in-the-azure-portal) décrit comment inscrire une application qui nécessite la connexion de l’utilisateur pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="98b67-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="98b67-148">Découvrez comment créer une inscription d’application qui ne nécessite pas d’interaction de l’utilisateur et qui peut être exécutée sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="98b67-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="98b67-149">Dans votre inscription d’application sur le portail Azure, accédez à **Autorisations de l’API**.</span><span class="sxs-lookup"><span data-stu-id="98b67-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="98b67-150">Sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="98b67-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="98b67-151">Sélectionnez l’onglet **API utilisées par mon organisation** et choisissez **Dynamics 365 AI pour Customer Insights** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="98b67-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="98b67-152">Pour le **Type d’autorisation**, sélectionnez **Autorisations de l’application**, puis sélectionnez l’autorisation **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="98b67-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="98b67-153">Sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="98b67-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="98b67-154">Retournez à **Autorisations de l’API** pour votre inscription d’application.</span><span class="sxs-lookup"><span data-stu-id="98b67-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="98b67-155">Sélectionnez **Accorder un consentement d’administrateur pour...** pour terminer l’inscription de l’application.</span><span class="sxs-lookup"><span data-stu-id="98b67-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Comment accorder le consentement de l’administrateur.":::

1. <span data-ttu-id="98b67-157">Pour conclure, nous devons ajouter le nom de l’inscription d’application en tant qu’utilisateur dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b67-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="98b67-158">Ouvrez Customer Insights, accédez à **Administration** > **Autorisations** et sélectionnez **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="98b67-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="98b67-159">Recherchez le nom de votre inscription d’application, sélectionnez-le dans les résultats de la recherche, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="98b67-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="98b67-160">Bibliothèques client de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="98b67-160">Customer Insights client libraries</span></span>

<span data-ttu-id="98b67-161">Cette section vous aide à utiliser les bibliothèques client disponibles pour les API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98b67-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="98b67-162">Tout le code source de la bibliothèque et tous les exemples d’applications se trouvent sur la [page GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="98b67-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="98b67-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="98b67-163">C# NuGet</span></span>

<span data-ttu-id="98b67-164">Découvrez comment utiliser les bibliothèques client C# de NuGet.org. Pour plus d’informations sur le package NuGet, consultez [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="98b67-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="98b67-165">Actuellement, ce package cible les infrastructures netstandard2.0 et netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="98b67-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="98b67-166">Ajouter la bibliothèque client C# à un projet C#</span><span class="sxs-lookup"><span data-stu-id="98b67-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="98b67-167">Dans Visual Studio, ouvrez le **Gestionnaire de package NuGet** pour votre projet.</span><span class="sxs-lookup"><span data-stu-id="98b67-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="98b67-168">Recherchez **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="98b67-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="98b67-169">Sélectionnez **Installer** pour ajouter le package au projet.</span><span class="sxs-lookup"><span data-stu-id="98b67-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="98b67-170">Vous pouvez également exécuter cette commande dans la **Console du gestionnaire de package NuGet** : `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="98b67-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Ajouter un package NuGet à un projet Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="98b67-172">Utiliser la bibliothèque client C#</span><span class="sxs-lookup"><span data-stu-id="98b67-172">Use the C# client library</span></span>

1. <span data-ttu-id="98b67-173">Utilisez la [Bibliothèque d’authentification Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) pour obtenir un `AccessToken` en utilisant votre [Inscription d’application Azure](#create-a-new-app-registration-in-the-azure-portal) existante.</span><span class="sxs-lookup"><span data-stu-id="98b67-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="98b67-174">Une fois l’authentification et l’acquisition d’un jeton réalisées avec succès, construisez un nouveau jeton ou utilisez un jeton `HttpClient` existant avec le paramètre **DefaultRequestHeaders "Authorisation"** supplémentaire défini sur le **<access token> du porteur** et le paramètre **Ocp-Apim-Subscription-Key** défini sur la [**clé d’abonnement** de votre environnement Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="98b67-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="98b67-175">Rédéfinissez l’en-tête **Autorisation**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="98b67-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="98b67-176">Par exemple, lorsque le jeton a expiré.</span><span class="sxs-lookup"><span data-stu-id="98b67-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="98b67-177">Transmettez ce `HttpClient` dans la construction du client `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="98b67-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exemple de httpclient":::

1. <span data-ttu-id="98b67-179">Utilisez le client pour appeler les « méthodes d’extension », par exemple, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="98b67-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="98b67-180">Si l’accès au `Microsoft.Rest.HttpOperationResponse` sous-jacent est recommandé, utilisez les « méthodes de message http », par exemple `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="98b67-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="98b67-181">La réponse sera probablement de type `object`, car la méthode peut renvoyer plusieurs types (par exemple, `IList<InstanceInfo>` et `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="98b67-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="98b67-182">Pour vérifier le type de retour, vous pouvez convertir en toute sécurité les objets dans les types de réponse spécifiés sur la [Page des détails de l’API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pour cette opération.</span><span class="sxs-lookup"><span data-stu-id="98b67-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="98b67-183">Si des informations supplémentaires sur la demande sont nécessaires, utilisez les **méthodes de message http** pour accéder à l’objet de réponse brute.</span><span class="sxs-lookup"><span data-stu-id="98b67-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="98b67-184">Package NodeJS</span><span class="sxs-lookup"><span data-stu-id="98b67-184">NodeJS package</span></span>

<span data-ttu-id="98b67-185">Utilisez les bibliothèques clientes NodeJS disponibles via NPM : https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="98b67-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="98b67-186">Package Python</span><span class="sxs-lookup"><span data-stu-id="98b67-186">Python package</span></span>

<span data-ttu-id="98b67-187">Utilisez les bibliothèques clientes Python disponibles via PyPi : https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="98b67-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
