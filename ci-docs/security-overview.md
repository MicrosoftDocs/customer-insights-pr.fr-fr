---
title: Configurer les paramètres de sécurité
description: Découvrez les paramètres de sécurité dans Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246059"
---
# <a name="configure-security-settings"></a>Configurer les paramètres de sécurité

Gérez les clés API, accédez aux données client et configurez une liaison privée Azure.

## <a name="manage-api-keys"></a>Gérer les clés API

Affichez et gérez les clés pour utiliser les [API Customer Insights](apis.md) avec les données dans votre environnement.

1. Accédez à **Système** > **Sécurité** et sélectionnez l’onglet **API**.

1. Si l’accès API à l’environnement n’a pas été configuré, sélectionnez **Activer**. Ou, pour bloquer l’accès de l’API à l’environnement, sélectionnez **Désactiver** et confirmer l'opération.

1. Gérez les clés API primaire et secondaire :

   1. Pour afficher la clé API primaire ou secondaire, sélectionnez le symbole **Afficher**.

   1. Pour copier la clé API primaire ou secondaire, sélectionnez le symbole **Copier**.

   1. Pour créer des clés API primaires ou secondaires, sélectionnez **Régénérer primaire** ou **Régénérer secondaire**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accéder en toute sécurité aux données client avec Customer Lockbox (version préliminaire)

Customer Insights utilise la fonctionnalité Customer Lockbox pour Power Platform. Customer Lockbox fournit une interface pour examiner et approuver (ou rejeter) les demandes d'accès aux données. Ces demandes se produisent lorsque l'accès aux données client est nécessaire pour résoudre un cas de support. Pour utiliser cette fonctionnalité, Customer Insights doit disposer d'une connexion existante à un environnement Microsoft Dataverse de votre client.

Pour plus d'informations sur Customer Lockbox, consultez le [sommaire](/power-platform/admin/about-lockbox#summary) de la fonctionnalité Customer Lockbox pour Power Platform. L'article décrit également le [flux de travail](/power-platform/admin/about-lockbox#workflow) et la [configuration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) requise pour activer la fonctionnalité Customer Lockbox.

> [!IMPORTANT]
> Les administrateurs globaux pour Power Platform ou les administrateurs de Power Platform peuvent approuver les demandes de Customer Lockbox émises pour Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurer une liaison privée Azure

[Azure Private Link](/azure/private-link/private-link-overview) permet à Customer Insights de se connecter à votre compte Azure Data Lake Storage sur un point de terminaison privé dans votre réseau virtuel. Pour les données d'un compte de stockage, qui n'est pas exposé à l'Internet public, Private Link permet la connexion à ce réseau restreint.

> [!IMPORTANT]
> Rôle minimum requis pour configurer une connexion Private Link :
>
> - Customer Insights : Administrateur
> - Rôle intégré Azure : [Compte de stockage collaborateur](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Autorisations pour le rôle Azure personnalisé : [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Dans Customer Insights, accédez à **Admin** > **Sécurité** et sélectionnez l'onglet **Liaisons privées**.

1. Sélectionnez **Ajouter une liaison privée**.

   Le volet **Ajouter une liaison privée** répertorie les comptes de stockage de votre locataire que vous êtes autorisé à voir.

1. Sélectionnez l'abonnement, le groupe de ressources et le compte de stockage.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Cliquez sur **Enregistrer**.

1. Accédez à votre compte Data Lake Storage et ouvrez le lien présenté à l’écran.

1. Approuvez la liaison privée.


[!INCLUDE [footer-include](includes/footer-banner.md)]
