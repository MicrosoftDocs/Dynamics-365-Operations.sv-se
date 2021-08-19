---
title: Bokföring av försäljningar och betalningar online
description: Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.
author: psimolin
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58af31464768e988bfa8727bcd836032d06b3a9dcfb416c3b9ed274af3285c79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720914"
---
# <a name="posting-of-online-sales-and-payments"></a>Bokföring av försäljningar och betalningar online

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.

Att bokföra både försäljning och betalningar online är en process i två steg.

- Dra in transaktionsdata för onlinehandel i huvudkontor.
- Synkronisera order för att skapa försäljningsorder i huvudkontor.

Du kan dra in transaktionsdata online manuellt genom att köra P-jobbet eller genom att skapa ett återkommande batchjobb.

### <a name="manually-running-the-p-job"></a>Köra P-jobbet manuellt

1. Gå till alla arbetsytor > Butik och handel-IT.
2. Klicka på Distributionsschema.
3. Välj P-0001.
4. Justera kanaldatabasgrupper om det behövs.
5. Klicka på Kör nu.
6. Klicka på Ja.

### <a name="scheduling-a-recurring-p-job"></a>Schemalägga ett återkommande P-jobb

1. Gå till alla arbetsytor > Butik och handel-IT.
2. Klicka på Distributionsschema.
3. Välj P-0001.
4. Klicka på Skapa batchjobb.
5. Klicka på Kör i bakgrunden.
5. Aktivera Batchbearbetning.
6. Klicka på Upprepning.
7. Välj alternativet Slutdatum saknas.
8. I fältet Antal anger du intervall mellan körningarna i minuter. Detta är vanligtvis 5-10.
9. Klicka på OK.
10. Klicka på OK.

Order kan synkroniseras antingen genom att köra "Synkronisera order"-jobbet manuellt eller genom att skapa ett återkommande batchjobb.

### <a name="manually-running-order-synchronization"></a>Köra ordersynkronisering manuellt 

Följ dessa steg om du vill köra "Synkronisera order"-jobb manuellt en gång.

1. Gå till alla arbetsytor > butiksekonomi.
2. Klicka på Synkronisera order.
3. Välj Butiker efter region i fältet Organisationshierarki.
    * Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.  
    * Klicka på pilen om du vill lägga till ditt val.  
4. Klicka på fliken Kör i bakgrunden ...
5. Inaktivera Batchbearbetning
6. Klicka på Upprepning.
7. Välja alternativet Sluta efter
8. Ange 1 i fältet Sluta efter.
9. Klicka på OK.
10. Klicka på OK.

### <a name="scheduling-recurring-order-synchronization"></a>Tidsplanera synkronisering av återkommande order

Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner. I proceduren används demonstrationsföretaget USRT.

1. Gå till alla arbetsytor > butiksekonomi.
2. Klicka på Synkronisera order.
3. Välj Butiker efter region i fältet Organisationshierarki.
    * Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.  
    * Klicka på pilen om du vill lägga till ditt val.  
4. Klicka på fliken Kör i bakgrunden ...
5. Aktivera Batchbearbetning
6. Klicka på Upprepning.
7. Välj alternativet Slutdatum saknas.
8. I fältet Antal anger du intervall mellan körningarna i minuter. Detta är vanligtvis 2-20
9. Klicka på OK.
10. Klicka på OK.

## <a name="data-entities-involved-in-the-process"></a>Dataenheter som är inblandade i processen

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans


[!INCLUDE[footer-include](../../includes/footer-banner.md)]