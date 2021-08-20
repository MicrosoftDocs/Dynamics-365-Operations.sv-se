---
title: Registrera försäljningsprovisioner
description: I det här avsnittet beskrivs hur försäljningsprovision beräknas och registreras.
author: omulvad
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c55c289ae3cbfd959c26ede48553a1dbd51450ec007ea68c970d58ceffe86151
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774763"
---
# <a name="register-sales-commissions"></a>Registrera försäljningsprovisioner

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur försäljningsprovision beräknas och registreras. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Innan du startar guiden kör du guiden ”Ställ in regler för försäljningsprovision” för att vara säker på att alla nödvändiga inställningar för provisionsberäkningen har gjorts.

Skriv upp kundnumren och artikelnumret du har valt för provisionsprocessen, och använd dem när du ska skapa en försäljningsorder i den här guiden.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fakturera en försäljningsorder som kvalificerar en säljare för provision
1. I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Välj **Ny**.
3. I fältet **Kundkonto** välj önskad post i den nedrullningsbara menyn.
4. Välj **OK**.
5. Välj **Alternativ** i åtgärdsfönstret.
6. Välj **Byt visning**.
7. Välj **Huvudvy**.
8. Expandera avsnittet **Inställningar**.

    - Värdet i fältet **Försäljningsgrupp** representerar en grupp med en eller flera säljare som det tilldelats. Människorna i gruppen är de som ska få provision när ordern är fakturerad enligt fördefinierade frekvenser och distribution.   
    - Värdet kopieras från kund-kort, men du kan ändra det om du vill.  
    - Försäljningsgruppen finns också kopieras till kundorderraden. Du kan ändra den, så att den kan skilja sig från den i huvudet och/eller mellan raderna.  
    - Värdet i fältet **Provisionsgrupp** representerar en grupp som du har skapat för en eller flera kunder i syfte att spåra provisioner.   
    - Värdet kopieras från kund-kort, men du kan ändra det om du vill.   

9. Välj **Alternativ** i åtgärdsfönstret.
10. Välj **Byt visning**.
11. Välj **Radvy**.
12. I den nedrullningsbara menyn i fältet **Artikelnummer** väljer du den artikel som du har ställt in för provisioner. 
13. Ange ett nummer i fältet **Kvantitet**. Observera radens nettobelopp. Det representerar försäljningsintäkten, som i det här exemplet är grunden för provisionsberäkningen.  
14. Välj **Spara**.
15. Välj **Faktura** i åtgärdsfönstret.
16. Välj **Faktura**.
17. Expandera avsnittet **Parametrar**.
18. I fältet **Kvantitet**, välj **Alla**.
19. Välj **Ja** i fältet **Bokför**.
20. Välj **OK** och välj **OK** i nästa ruta. Den kan ta minut eller så att bokföra transaktionen. Tillåt processen att slutföras och stäng inte sidan.  

## <a name="review-the-registered-sales-commissions"></a>Granska de registrerade försäljningsprovisionerna
1. I åtgärdsfönstret väljer du **Faktura**, och sedan **Faktura**.
2. I åtgärdsfönstret väljer du **Faktura**, och sedan **Provisionstransaktioner**.

    - Fliken **Översikt** visar rader som representerar provisionsbelopp som betalas till säljarna som är associerade med fakturerad försäljningsorder. Vi tar en titt på detaljerna.  
    - Om du använde guiden ”Ställ in regler för försäljningsprovision” när du ställde in gruppen **Provisionsförsäljning**, finns det två säljare som får provision och provisionen fördelas lika mellan dem.  
    - I det här exemplet beräknas provisionens totala belopp som procent av försäljningsintäkten (nettobeloppet på orderraden).  
3. Stäng sidan.
4. Välj **Verifikation**. Du kan granska de verifikationstransaktionerna för provisionsbeloppen som har bokförts på de fördefinierade kontona för provisionsutgiften och provisionsskulden.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]