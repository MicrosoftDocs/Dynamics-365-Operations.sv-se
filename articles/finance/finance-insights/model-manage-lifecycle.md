---
title: Livscykelhantering för modellhantering (förhandsversion)
description: I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 3daec03b7ba349d8f72863317e2d601a83417d58
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638402"
---
# <a name="model-management-lifecycle-preview"></a>Livscykelhantering för modellhantering (förhandsversion)

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.

Vi rekommenderar att du utbildar AI-modellen i en sandbox-miljö och sedan använder hanterade lösningar för att distribuera den till en produktionsmiljö. Denna metod är ett sätt att säkerställa att rätt kontroller finns på plats för hantering av modellens livscykel.

Eftersom AI-modellen baseras på tillgängliga faktura- och kunddata är det viktigt att sandbox-miljön har en aktuell kopia av produktionsdatan. Du kan börja utbilda din modell genom att följa stegen i [Använd kundbetalningsprognoser](use-customer-payment-predictions.md). När du har utbildat om modellen utvärderar du resultaten enligt beskrivningen i [Utvärdera den ursprungliga modellen för kundbetalningsprognos](evaluate-payment-prediction.md). Använd informationen i [Förbättra förutsägelsemodellen](improve-model.md) för att experimentera med funktions- och filterkombinationer som kan förbättra modellen.

När du är nöjd med utbildningsresultaten följer du stegen i [Distribuera din AI-modell](https://docs.microsoft.com/ai-builder/distribute-model) för att föra över modellen till din produktionsmiljö.
