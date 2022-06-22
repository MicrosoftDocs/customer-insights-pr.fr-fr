---
title: Enrichir les profils clients avec des données de Microsoft Office 365
description: Utilisez les données propriétaires de Microsoft Office pour enrichir vos profils clients avec des données d’engagement.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954130"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enrichir les profils clients avec des données d’engagement (version préliminaire)

Utilisez les données de Microsoft Office 365 pour enrichir vos profils de compte client avec des informations sur les engagements dans les applications Office 365. Les données d’engagement se composent de l’activité d’e-mail et de réunion, qui est regroupée au niveau du compte. Par exemple, le nombre d’e-mails d’un compte professionnel ou le nombre de réunions avec le compte. Aucune donnée sur les utilisateurs individuels n’est disponible.

## <a name="supported-countries-or-regions"></a>Pays ou régions pris en charge

Nous prenons actuellement en charge les régions suivantes : Royaume-Uni, Europe, Amérique du Nord.

## <a name="prerequisites"></a>Conditions préalables

- Une licence cloud Office 365 active.
- [Profils clients unifiés](customer-profiles.md) sur la base des [comptes professionnels](work-with-business-accounts.md).
- Une [organisation Microsoft Dataverse jointe](create-environment.md#step-3-connect-to-microsoft-dataverse) dans votre environnement Customer Insights.
- Autorisations d’[administrateur](permissions.md#admin).
- Obtenez le consentement de votre administrateur client Office 365 pour utiliser les données Office 365 pour fournir des **Informations pour l’organisation** dans les applications Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Engagement du compte**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Vignette Engagement du compte.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Saisissez les adresses e-mail de votre organisation pour laquelle les données Office seront regroupées. Seules les données des adresses e-mail répertoriées sont traitées pour la communication appropriée. Une pratique recommandée consiste à utiliser des groupes d’e-mails, par exemple, *Équipe de vente pour les États-Unis*, que vous pouvez gérer dans Office 365. Le nombre d’adresses e-mail dans les groupes est résolu et affiché. Le nombre total d’adresses e-mail doit être d’au moins 2 et ne peut pas dépasser 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adresses e-mail d’engagement de compte.":::

1. Examinez et donnez votre consentement pour le [Consentement de l’administrateur client Office 365](#office-365-tenant-administrator-consent) en sélectionnant **J'accepte**.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données de contact**, puis choisissez le profil que vous souhaitez enrichir. Cliquez sur **Suivant**.

1. Mappez le champ d’adresse e-mail du contact et sélectionnez **Suivant**.

1. Fournissez un **Nom** pour l’enrichissement et pour l’**Entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Fermer** pour revenir à la page **Enrichissements**

### <a name="office-365-tenant-administrator-consent"></a>Consentement de l’administrateur client Office 365

Le consentement d’un administrateur client Office 365 est nécessaire pour activer l’enrichissement. Un e-mail est envoyé aux administrateurs client Office 365 lors de l’enregistrement de l’enrichissement, pour leur demander d’examiner l’enrichissement et de donner leur consentement pour que les applications Dynamics 365 puissent utiliser les données Office 365 de votre entreprise pour fournir des **Informations pour l’organisation**. L’administrateur client Office 365 peut également donner son consentement directement dans sa console d’administration Office 365 en sélectionnant **Informations pour l’organisation**.

## <a name="running-the-enrichment-for-the-first-time"></a>Exécution de l’enrichissement pour la première fois

Lorsque l’enrichissement est démarré pour la première fois, une fois que l’administateur client Office 365 a donné son consentement, le téléchargement des données depuis Office 365 commence. Ce processus prend un certain temps. La première exécution de l’enrichissement sera programmée avec un délai de six heures. Vous pouvez voir le nombre de jours couverts par les données sur la page de présentation de l’engagement du compte une fois l’enrichissement terminé. Avec un volume de données important, exécutez à nouveau l’enrichissement après quelques jours. Cela garantit que les données sont complètes pour toute la période, qui correspond à un an.

Selon la taille de vos données Office, une exécution d’enrichissement peut prendre plusieurs heures.

Lorsque vous exécutez un enrichissement, Microsoft traitera les données dans les limites de conformité d’Office 365 pour créer des informations regroupées, qui sont ensuite ajoutées à votre environnement Customer Insights. Aucune donnée à un niveau individuel (par exemple, le corps d’un e-mail ou une invitation du calendrier) n’est disponible pour les utilisateurs de Customer Insights.

Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Il s'agit de l'entité *Office*. *Office_UserEntity* contient les ID Active Directory des adresses e-mail choisies lors de la configuration de l’enrichissement.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Aperçu des résultats après l’exécution du processus d’enrichissement.":::

Toutes les données sont regroupées au niveau du compte. Le système calcule un score d’engagement, qui varie entre 0 et 100, pour chaque compte. Le score d’engagement fournit une mesure composée de l’engagement du compte dans les e-mails et les réunions relatifs à vos autres comptes. La liste suivante contient les données regroupées fournies par l’enrichissement de l’engagement du compte :

| Données                                                                              | Nom de colonne                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Score d’engagement                                                                  |  EngagementScore                         |
| Nombre d’e-mails au compte                                                       |  NoOfEmails_ToAccount                    |
| Nombre d’e-mails provenant du compte                                                     |  NoOfEmails_FromAccount                  |
| Nombre de réunions lancées par le compte                                           |  NoOfMeetings_FromAccount                |
| Nombre de réunions lancées par votre organisation                                 |  NoOfMeetings_ToAccount                  |
| Nombre de personnes de votre organisation dans les réunions avec le compte                  |  NoOfContactsInvolved_Meetings           |
| Nombre de personnes de votre organisation dans les conversations par e-mail avec le compte       |  NoOfContactsInvolved_Emails             |
| Nombre de personnes de votre compte dans les réunions avec votre organisation                  |  NoOfAccountContactsInvolved_Meetings    |
| Nombre de personnes de votre compte dans les conversations par e-mail avec votre organisation       |  NoOfAccountContactsInvolved_Emails      |
| Date de début de l’engagement (premier e-mail ou première réunion dans les données)                        |  EngagementStartDate                     |
| Jours depuis le dernier e-mail                                                             |  DaysSinceLastEmail                      |
| Jours depuis la dernière réunion                                                           |  DaysSinceLastMeeting                    |
| Durée moyenne des réunions                                                      |  AverageDuration_Of_Meetings             |
| Durée moyenne des réponses par e-mail à partir du compte                                    |  AverageDuration_Of_AccountEmailReplies  |
| Date de début de l’agrégation                                                            |  AggregationStartDate                    |
| Niveau d’agrégation (année, mois ou semaine)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Voir les données d’enrichissement sur la carte client

L’engagement du compte peut également être visualisé sur les fiches client individuelles. Accédez à **Clients** et sélectionnez un profil client. Dans la fiche client, vous trouverez le score d’engagement du compte, le nombre total d’e-mails et le nombre total de réunions regroupées au cours de la dernière année. Vous trouverez également des graphiques qui affichent l’historique des e-mails et des réunions.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Carte client avec données enrichies.":::

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Par exemple, un segment contenant tous les clients qui ont une valeur supérieure à 60 pour *jours depuis le dernier e-mail* et *jours depuis la dernière réunion*. Ce segment contient des comptes obsolètes que vous pouvez essayer de réactiver.

[!INCLUDE [footer-include](includes/footer-banner.md)]
