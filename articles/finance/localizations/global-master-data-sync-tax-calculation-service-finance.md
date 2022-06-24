---
title: Synkronisera momskonfigurationen från momsberäkningstjänsten till Dynamics 365 Finance
description: I den här artikeln beskrivs hur du synkroniserar momsinställningarnas huvuddata från skatteberäkningstjänsten Microsoft Dynamics 365 Finance.
author: wangchen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegration, TaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b017a19834998e1c493b0a38c1b50accd8c7e630
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853169"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Synkronisera momskonfigurationen från momsberäkningstjänsten till Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du synkroniserar momsinställningarnas huvuddata från skatteberäkningstjänsten Microsoft Dynamics 365 Finance.

När du har slutfört de nödvändiga installationsstegen in [Kom igång med skatteberäkning](global-get-started-with-tax-calculation-service.md), följande skatteinställningar synkroniseras automatiskt från skatteberäkningstjänsten till Finance.

## <a name="sales-tax-code"></a>Momskod

| Skatteberäkningstjänst           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Momskod                          | Momskod                      |
| Beskrivning                       | Namn                                |
| Användarindata                        | Kvittningsperiod                   |
| Användarindata                        | Redovisningsbokföringsgrupp                |
| Användarindata                        | Momsvaluta                  |
| En negativ momssats konfigureras | Tillåt negativ momsprocent |

## <a name="tax-value"></a>Momsvärde

| Skatteberäkningstjänst | Finance                   |
| ----------------------- | ------------------------- |
| Från transaktionsdatum   | Från-datum                 |
| Till transaktionsdatum     | Till-datum                   |
| Minimibelopp          | Minimigräns             |
| Maxtid          | Maximigräns             |
| Momssats                | Värde                     |
| Ej avdragsgill kurs     | Ej avdragsgill procentsats |

## <a name="tax-limits"></a>Momsbegränsningar

| Skatteberäkningstjänst | Finance           |
| ----------------------- | ----------------- |
| Från transaktionsdatum   | Från-datum         |
| Till transaktionsdatum     | Till-datum           |
| Minsta momsbelopp      | Minimal moms |
| Högsta momsbelopp      | Maximal moms |

## <a name="sales-tax-group"></a>Momsgrupp

| Skatteberäkningstjänst                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Skattegrupp                                       | Momsgrupp                            |
| Momskoder under den här momsgruppen                  | Momskoder under den här momsgruppen |
| Momskoden har markerats som **Är undantagen**         | Momsbefrielse                                     |
| Momskoden har markerats som **Är undantagen**         | Momsbefrielsekod                                |
| Skattekoden är markerad som **Är återförd avgift** | Omvänd skattskyldighet                             |
| Momskoden har markerats som **Är importavgift**        | Använd moms                                    |

## <a name="item-sales-tax-group"></a>Artikelmomsgrupp

| Skatteberäkningstjänst             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Artikelmomsgrupp                      | Artikelmomsgrupp                            |
| Momskoder under den här artikelmomsgruppen | Momskoder under den här artikelmomsgruppen |

När synkroniseringen är klar fortsätter du att underhålla parametrarna i Finance för bokförings- och rapporteringsändamål.

> [!NOTE]
> Synkronisering av momsinställningarna från Finance till Skatteberäkningstjänst som inte stöds. Om du vill ha en befintlig Finance-miljö måste du först skapa momsinställningarna i Skatteberäkningstjänst. Synkronisera sedan inställningsdata till Finance-miljön.
