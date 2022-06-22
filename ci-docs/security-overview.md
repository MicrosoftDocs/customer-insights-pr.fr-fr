---
title: Paramètres de sécurité dans Customer Insights
description: Découvrez les paramètres de sécurité dans Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947412"
---
# <a name="security-settings-in-customer-insights"></a>Paramètres de sécurité dans Customer Insights

La page **Sécurité** répertorie les options pour configurer les autorisations utilisateur et les fonctionnalités qui aident à rendre Dynamics 365 Customer Insights plus sécurisé. Seuls les administrateurs peuvent accéder à cette page.

Accédez à **Administrateur** > **Sécurité** pour configurer les paramètres.

La page **Sécurité** comprend les onglets suivants :

- [Utilisateurs](#users-tab)
- [API](#apis-tab)
- [Liaisons privées](#private-links-tab)
- [Coffre de clés ](#key-vault-tab)
- [Accéder en toute sécurité aux données client avec Customer Lockbox (version préliminaire)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Onglet Utilisateurs

L’accès à Customer Insights est limité aux utilisateurs de votre organisation qui ont été ajoutés à l’application par un administrateur. L’onglet **Utilisateurs** vous permet de gérer l’accès des utilisateurs et leurs autorisations. Pour plus d’informations, consultez les [Autorisations utilisateur](permissions.md).

## <a name="apis-tab"></a>Onglet API

Affichez et gérez les clés pour utiliser les [API Customer Insights](apis.md) avec les données de votre environnement.

Vous pouvez créer de nouvelles clés primaires et secondaires en sélectionnant **Régénérer primaire** ou **Régénérer secondaire**. 

Pour bloquer l’accès de l’API à l’environnement, sélectionnez **Désactiver**. Si les API sont désactivées, vous pouvez sélectionner **Activer** pour accorder à nouveau l’accès.

## <a name="private-links-tab"></a>Onglet Liaisons privées

[Azure Private Link](/azure/private-link/private-link-overview) permet à Customer Insights de se connecter à votre compte Azure Data Lake Storage sur un point de terminaison privé dans votre réseau virtuel. Pour les données d'un compte de stockage, qui n'est pas exposé à l'Internet public, Private Link permet la connexion à ce réseau restreint.

> [!IMPORTANT]
> Rôle minimum requis pour configurer une connexion Private Link :
>
> - Customer Insights : Administrateur
> - Rôle intégré Azure : [Compte de stockage collaborateur](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Autorisations pour le rôle Azure personnalisé : [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

La configuration de Private Link dans Customer Insights est un processus en deux étapes. Tout d'abord, vous initiez la création d'une liaison privée à partir de **Administrateur** > **Sécurité** > **Liaisons privées** dans Customer Insights. Le volet **Ajouter une liaison privée** répertorie les comptes de stockage de votre locataire que vous êtes autorisé à voir. Sélectionnez le compte de stockage et donnez votre consentement pour créer la liaison privée.

Ensuite, vous devez approuver la liaison privée du côté du compte Data Lake Storage. Ouvrez le la liaison présenté à l'écran pour approuver la nouvelle liaison privée.

## <a name="key-vault-tab"></a>Onglet Coffre de clés

L’onglet **Coffre de clés** vous permet de gérer votre propre [Azure Key Vault](/azure/key-vault/general/basic-concepts) et de le lier à l’environnement.
Le coffre de clés dédié peut être utilisé pour organiser et utiliser des secrets dans la limite de conformité d’une organisation. Customer Insights peut utiliser les secrets dans Azure Key Vault pour [établir des connexions](connections.md) avec des systèmes tiers.

Pour plus d’informations, voir [Apportez votre propre coffre de clés Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accéder en toute sécurité aux données client avec Customer Lockbox (version préliminaire)

Customer Insights utilise la fonctionnalité Customer Lockbox pour Power Platform. Customer Lockbox fournit une interface pour examiner et approuver (ou rejeter) les demandes d'accès aux données. Ces demandes se produisent lorsque l'accès aux données client est nécessaire pour résoudre un cas de support. Pour utiliser cette fonctionnalité, Customer Insights doit disposer d'une connexion existante à un environnement Microsoft Dataverse de votre client.

Pour plus d'informations sur Customer Lockbox, consultez le [sommaire](/power-platform/admin/about-lockbox#summary) de la fonctionnalité Customer Lockbox pour Power Platform. L'article décrit également le [flux de travail](/power-platform/admin/about-lockbox#workflow) et la [configuration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) requise pour activer la fonctionnalité Customer Lockbox.

> [!IMPORTANT]
> Les administrateurs globaux pour Power Platform ou les administrateurs de Power Platform peuvent approuver les demandes de Customer Lockbox émises pour Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
