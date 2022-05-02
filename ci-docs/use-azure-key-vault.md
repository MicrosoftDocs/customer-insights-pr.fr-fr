---
title: Apportez votre propre coffre de clés Azure pour gérer les secrets
description: Découvrez comment configurer Customer Insights pour utiliser votre propre coffre de clés Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653474"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Apportez votre propre coffre de clés Azure (préversion)

Relier un [coffre de clés Azure](/azure/key-vault/general/basic-concepts) dédié à un environnement Customer Insights aide les organisations à répondre aux exigences de conformité.
Le coffre de clés dédié peut être utilisé pour organiser et utiliser des secrets dans la limite de conformité d’une organisation. Customer Insights peut utiliser les secrets dans Azure Key Vault pour [établir des connexions](connections.md) avec des systèmes tiers.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Relier le coffre de clés à l’environnement Customer Insights

### <a name="prerequisites"></a>Conditions préalables

Pour configurer le coffre de clés dans Customer Insights, les conditions préalables suivantes doivent être remplies :

- Vous devez disposer d’un abonnement Azure actif.

- Vous disposez d’un rôle [Administrateur](permissions.md#admin) dans Customer Insights. En savoir plus sur les [autorisations utilisateur dans Customer Insights](permissions.md#assign-roles-and-permissions).

- Vous disposez des rôles [Contributeur](/azure/role-based-access-control/built-in-roles#contributor) et [Administrateur des accès utilisateur](/azure/role-based-access-control/built-in-roles#user-access-administrator) sur le coffre de clés ou le groupe de ressources auquel appartient le coffre de clés. Pour plus d’informations, accédez à [Ajouter ou supprimer des attributions de rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal). Si vous n’avez pas le rôle Administrateur des accès utilisateur sur le coffre de clés, vous devez configurer les autorisations de contrôle d’accès basé sur les rôles pour le principal de service Azure pour Dynamics 365 Customer Insights séparément. Suivez les étapes pour [utiliser un principal de service Azure](connect-service-principal.md) pour le coffre de clés qui doit être lié.

- Le coffre de clés doit avoir un pare-feu Key Vault **désactivé**.

- Le coffre à clés est dans le même [emplacement Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que l’environnement Customer Insights. La région de l’environnement dans Customer Insights est répertoriée sous **Administrateur** > **Système** > **À propos de** > **Région**.

### <a name="link-a-key-vault-to-the-environment"></a>Lier un coffre de clés à l’environnement

1. Accédez à **Administrateur** > **Sécurité**, puis sélectionnez l’onglet **Coffre de clés**.
1. Sur la vignette **Coffre de clés**, sélectionnez **Installer**.
1. Choisissez un **Abonnement**.
1. Choisissez un coffre de clés dans la liste déroulante **Coffre de clés**. Si trop de coffres de clés s’affichent, sélectionnez un groupe de ressources pour limiter les résultats de la recherche.
1. Acceptez la déclaration **Confidentialité et conformité des données**.
1. Cliquez sur **Enregistrer**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Étapes pour configurer un coffre de clés lié dans Customer Insights.":::

La vignette **Coffre de clés** affiche désormais le nom du coffre de clés, le groupe de ressources et l’abonnement liés. Il est prêt à être utilisé dans la configuration de la connexion.
Pour plus de détails sur les autorisations sur le coffre de clés qui sont accordées à Customer Insights, accédez à [Autorisations accordées sur le coffre de clés](#permissions-granted-on-the-key-vault), plus loin dans cet article.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utiliser le coffre de clés dans la configuration de la connexion

Lors de l’[établissement de connexions](connections.md) à des systèmes tiers, les secrets du coffre de clés lié peuvent être utilisés pour configurer les connexions.

1. Accédez à **Administrateur** > **Connexions**.
1. Sélectionnez **Ajouter une connexion**.
1. Pour les types de connexion pris en charge, un bouton bascule **Utiliser le coffre de clés** est disponible si vous avez lié un coffre de clés.
1. Au lieu de saisir le secret manuellement, vous pouvez choisir le nom du secret qui pointe vers la valeur secrète dans le coffre de clés.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Volet de connexion avec une connexion SFTP qui utilise un secret Key Vault.":::

## <a name="supported-connection-types"></a>Types de connexion pris en charge

Les connexions d’[exportation](export-destinations.md) suivantes sont prises en charge :

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Autorisations accordées sur le coffre de clés

Les autorisations suivantes sont accordées à Customer Insights sur un coffre de clés lié si la [Stratégie d’accès au coffre de clés](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou le [Contrôle d’accès basé sur les rôles Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) sont activés.

### <a name="key-vault-access-policy"></a>Stratégie d’accès au coffre de clés

| Type        | Autorisations          |
| ----------- | -------------------- |
| Touche         | [Obtenir des clés](/rest/api/keyvault/get-keys), [Obtenir une clé](/rest/api/keyvault/get-key)                                 |
| Secret      | [Obtenir des secrets](/rest/api/keyvault/get-secrets), [Obtenir un secret](/rest/api/keyvault/get-secret)                     |
| Certificat | [Obtenir des certificats](/rest/api/keyvault/get-certificates), [Obtenir un certificat](/rest/api/keyvault/get-certificate) |

Les valeurs précédentes sont le minimum à lister et à lire pendant l’exécution.

### <a name="azure-role-based-access-control"></a>Contrôle d’accès basé sur les rôles Azure

Les rôles utilisateur Lecteur Key Vault et Secrets Key Vault seront ajoutés pour Customer Insights. Pour plus de détails sur ces rôles, accédez à [Rôles Azure intégrés pour les opérations de plan de données Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recommandations

- Utilisez un coffre de clés distinct ou dédié qui ne contient que les secrets requis pour Customer Insights. En savoir plus sur le motif de [recommandation de coffres de clés distincts](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Suivez les [bonnes pratiques pour utiliser Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) pour les options de contrôle d’accès, de sauvegarde, d’audit et de récupération.

## <a name="frequently-asked-questions"></a>Questions fréquentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights peut-il écrire des secrets ou écraser des secrets dans le coffre de clés ?

N° Seules les autorisations de lecture et de liste décrites dans la section des [autorisations accordées](#permissions-granted-on-the-key-vault) plus haut dans cet article sont accordées à Customer Insights. Le système ne peut pas ajouter, supprimer ou écraser des secrets dans le coffre de clés. C’est également la raison pour laquelle vous ne pouvez pas entrer d’informations d’identification lorsqu’une connexion utilise Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Puis-je modifier une connexion qui utilise des secrets Key Vault en une authentification par défaut ?

N° Vous ne pouvez pas revenir à une connexion par défaut après l’avoir configurée en utilisant un secret d’un coffre de clés lié. Créez une connexion distincte et supprimez l’ancienne si vous n’en avez plus besoin.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Comment puis-je révoquer l’accès à un coffre de clés pour Customer Insights ?

Selon que [Stratégie d’accès au coffre de clés](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou [Contrôle d’accès basé sur les rôles Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) est activé, vous devez supprimer les autorisations du principal du service `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` portant le nom `Dynamics 365 AI for Customer Insights`. Toutes les connexions qui utilisent le coffre de clés cesseront de fonctionner.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secret utilisé dans une connexion a été supprimé du coffre de clés. Que puis-je faire ?

Une notification apparaît dans Customer Insights lorsqu’un secret configuré à partir du coffre de clés n’est plus accessible. Activez la [suppression réversible](/azure/key-vault/general/soft-delete-overview) sur le coffre de clés pour restaurer les secrets s’ils sont accidentellement supprimés.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Une connexion ne fonctionne pas, mais mon secret est dans le coffre de clés. Quelle pourrait être la raison ?

Une notification apparaît dans Customer Insights lorsqu’il ne peut pas accéder au coffre de clés. La raison pourrait être la suivante :

- Les autorisations du principal de service Customer Insights ont été supprimées. Elles doivent être restaurées manuellement.

- Le pare-feu du coffre de clés est activé. Le pare-feu doit être désactivé pour que le coffre de clés soit à nouveau accessible pour Customer Insights.
