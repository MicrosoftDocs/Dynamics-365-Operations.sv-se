---
title: Livscykel för modellhantering
description: I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: a7b57bc0322e0f9a78dddfb924e379ac05ffca32
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722106"
---
# <a name="model-management-lifecycle"></a>Livscykel för modellhantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.

Vi rekommenderar att du utbildar AI-modellen i en sandbox-miljö och sedan använder hanterade lösningar för att distribuera den till en produktionsmiljö. Denna metod är ett sätt att säkerställa att rätt kontroller finns på plats för hantering av modellens livscykel.

Eftersom AI-modellen baseras på tillgängliga faktura- och kunddata är det viktigt att sandbox-miljön har en aktuell kopia av produktionsdatan. Du kan börja utbilda din modell genom att följa stegen i [Använd kundbetalningsprognoser](use-customer-payment-predictions.md). När du har utbildat om modellen utvärderar du resultaten enligt beskrivningen i [Utvärdera den ursprungliga modellen för kundbetalningsprognos](evaluate-payment-prediction.md). Använd informationen i [Förbättra förutsägelsemodellen](improve-model.md) för att experimentera med funktions- och filterkombinationer som kan förbättra modellen.

När du är nöjd med utbildningsresultaten följer du stegen i [Distribuera din AI-modell](/ai-builder/distribute-model) för att föra över modellen till din produktionsmiljö.
