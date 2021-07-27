---
title: Livscykelhantering för modellhantering (förhandsversion)
description: I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: d5566bde97a2e60d050f4a7b499b554df4848bf9
ms.sourcegitcommit: f6050b444e636ba662c00d0443c94a99f8ea0b0d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309800"
---
# <a name="model-management-lifecycle-preview"></a>Livscykelhantering för modellhantering (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs olika sätt att underhålla organisationens maskininlärningsmodeller för att optimera de förutsägelser som dessa genererar.

Vi rekommenderar att du utbildar AI-modellen i en sandbox-miljö och sedan använder hanterade lösningar för att distribuera den till en produktionsmiljö. Denna metod är ett sätt att säkerställa att rätt kontroller finns på plats för hantering av modellens livscykel.

Eftersom AI-modellen baseras på tillgängliga faktura- och kunddata är det viktigt att sandbox-miljön har en aktuell kopia av produktionsdatan. Du kan börja utbilda din modell genom att följa stegen i [Använd kundbetalningsprognoser](use-customer-payment-predictions.md). När du har utbildat om modellen utvärderar du resultaten enligt beskrivningen i [Utvärdera den ursprungliga modellen för kundbetalningsprognos](evaluate-payment-prediction.md). Använd informationen i [Förbättra förutsägelsemodellen](improve-model.md) för att experimentera med funktions- och filterkombinationer som kan förbättra modellen.

När du är nöjd med utbildningsresultaten följer du stegen i [Distribuera din AI-modell](https://docs.microsoft.com/ai-builder/distribute-model) för att föra över modellen till din produktionsmiljö.
