---
title: Konfigurera leasingböcker
description: I det här ämnet beskrivs informationen som upprätthålls i leasingböcker. Leasingböcker innehåller redovisningsprinciper som bestämmer hur en leasing redovisas i systemet.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f5eac47448835dae5837b31c59a72833652f63bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249663"
---
# <a name="set-up-lease-books"></a>Konfigurera leasingböcker

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Leasingböcker innehåller redovisningsprinciper som bestämmer hur en leasing redovisas i systemet. Utöver kontantredovisning följer Leasing av tillgångar följande standarder:

- God redovisningssed i USA (US GAAP, Generally Accepted Accounting Principles)
- Accounting Standards Codification Topic 842 (ASC 842)
- ASC 840
- International Financial Reporting Standard 16 (IFRS 16)
- International Accounting Standard 17 (IAS 17)

Följ dessa steg för att skapa en leasingbok.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Leasingböcker**.
2. Välj **Ny** för att lägga till en bok.
3. Ange följande fält.

    | Namn                                     | beskrivning |
    |------------------------------------------|-------------|
    | Bokföringsskikt                            | Välj vilket bokföringsskikt som ska användas. Varje bok som är kopplad till en leasing konfigureras för ett specifikt bokföringsskikt. Varje bokföringsskikt har olika bokföringssyften. |
    | Leasingtyp                               | Välj om leasingen ska klassificeras automatiskt eller om den ska vara fördefinierat som finansiell eller operationell leasing. |
    | Ramverk för redovisning                     | Välj det ramverk som du vill associera boken med. |
    | Konfiguration av leasingperiod/livslängd          | Leasingen klassificeras som finansiell om leasingtypen är inställd på **Automatisk** och om leasingperioden över tillgångens livslängd är större än eller lika med den procentsats som anges i det här fältet.  |
    | Konfiguration av nuvärde/tillgångens verkliga värde   | Ange ett heltal för att definiera tröskeln som bestämmer leasingtypen. Om nuvärdet av framtida minsta leasingbetalningar är mer än det användardefinierade värdet från bokkonfigurationen, och om bokens leasingklassificering är inställd på automatisk, klassificeras leasingen som en finansiell leasing. |
    | Korttidströskel                     | Ange antalet månader som ska användas som ett tröskelvärde för kortfristig leasing. Om leasingperioden är mindre än eller lika med antalet månader som du anger här, klassificeras leasingen som en kortsiktig leasing och behandlingen med uppskov av leasingavgift kommer att tillämpas. |
    | Lågvärdeströskel                      | Ange ett belopp som ska användas som tröskelvärde för lågvärdesleasing. Om tillgångens verkliga värde är mindre än eller lika med värdet som du anger här, klassificeras leasingen som en lågvärdesleasing och behandlingen med uppskov av leasingavgift kommer att tillämpas. |
    | Betala till leverantör                            | Ställ in det här alternativet **Ja** för att låta leasingbetalningar bokföras, som en faktura, till det leverantörskonto som anges för varje leasing. När en leasingbetalning bokförs kommer leverantörskontot att krediteras. Om det här alternativet är inställt på **Nej**, krediteras det konto som anges för bokföringstypen **Leasingbetalning** på sidan **Parametrar för bokföring av leasing** i stället. |
    | Leasingkonvention                       | Välj praxis för startdatum för leasingavtalet:<ul><li><b>Ingen</b> – Använd leasingavtalets startdatum som startdatum.</li><li><b>Hel månad</b> – Använd den första dag i månaden som leasingavtalets startdatum faller inom som startdatum.</li></ul><p>Om du väljer <b>Ingen</b> finns en risk att scheman för skuldamortering och tillgångsavskrivning kommer att ansamla och bokföra utgifter i mitten av månaden istället för i slutet av densamma. Genom att välja <b>Fullständig månad</b> säkerställer du att systemet börjar att redovisa leasingavtalet den första dagen i månaden, och att hela månadens utgift periodiseras och bokförs den sista dagen i månaden.</p><p><strong>Obs!</strong> Funktionen leasingkonventioner måste aktiveras via funktionshanteringen. I arbetsytan <b>Funktionshantering</b> väljer du funktionen kallad <b>Leasingkonvention för tillgångsleasing</b> och sedan <b>Aktivera nu</b>.</p> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]