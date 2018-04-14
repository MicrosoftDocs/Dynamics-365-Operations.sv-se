---
title: "Konfigurera kontantbenämningar för kassa"
description: "Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån kassan."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: afe7c359f284fde10ada377fb19add9819a8dd21
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="configure-cash-denominations-for-pos"></a>Konfigurera kontantbenämningar för kassa

[!INCLUDE [banner](includes/banner.md)]

Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån kassan. Dessa benämningar kan användas vid beräkning av kontanter i kassaavstämningar i slutet av dagen eller för att genomföra en försäljning snabbt.

## <a name="define-denominations"></a>Definiera benämningar
Benämningar ställs in per butik i alternativet **Ställ in** > **kontantavstämning från sidan butiksegenskaper**. 

![kontantbenämningar](./media/image1-denomination.png)

För att definiera en benämning:
1. Klicka på **Ny**.
1. Ange typen (mynt eller sedel).
1. Ange beloppet (värde).

![kontantbenämningar](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Konfigurera funktionsprofilen
Vid betalning av kontanter i kassan kan användaren använda sedelbenämningar för att snabbt ange det belopp som betalats av kunden. Du kan konfigurera två alternativ för visning av benämningen i kassan i funktionsprofilen.

**Större eller lika med det förfallna beloppet**: som standard visar kassan endast de sedelbenämningar som är större än beloppet som förfaller till betalning, vilket gör det möjligt för snabb genomföring av transaktionen. Om till exempel det förfallna beloppet är 7,50 visar kassan följande benämningar: 10, 20, 50 och 100. Om du rör något av dessa belopp kommer försäljningaen att genomföras automatiskt för detta belopp. Sedlarna 1 och 5 visas inte eftersom dessa belopp är mindre än beloppet som förfaller.

**Alla benämningar**: Markera det här alternativet för att alltidvisa alla sedelbenämningar i kassan, oavsett hur mycket förfaller. Detta innebär att användaren kan använda en kombination av sedlar till det förfallna beloppet. Om till exempel det förfallna beloppet är 25,00 kan användaren välja 20 och 5 för att slutföra försäljningen.

