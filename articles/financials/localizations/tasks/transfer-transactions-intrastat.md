--- 
title: "Överföra transaktioner till Intrastat"
description: "I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat."
author: Anasyash
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cc21497a6905cdb57bd687b7bff0d9dc810ba9eb
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-transactions-to-the-intrastat"></a>Överföra transaktioner till Intrastat

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat. Proceduren har skapats med demodataföretaget DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Skapa ny och uppdatera befintlig artikelkod
1. Gå till Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier.
2. I listan markerar du posten "Intrastat-artikelkoder".
3. Klicka på länken på den valda raden i listan.
4. Välj en "post" i trädet.
    * Välj t.ex. ”Intrastat\högtalare”.  
5. Klicka på Redigera.
6. Visa avsnittet Utländsk handel.
7. Ange eller välj ett värde i fältet Ytterligare enheter.
    * Välj t.ex. "st".  
8. Välj Ja i fältet Vikten är inte tillämplig.
9. Välj "Intrastat" i trädet.
10. Klicka på Ny kategorinod.
11. Ange artikelns namn i fältet Namn.
    * Skriv till exempel ”annan artikel”.  
12. Ange artikelkoden i fältet för Kod.
    * Skriv till exempel "995 00 00".  
13. Skriv ett värde i fältet Eget namn.
    * Skriv till exempel "Annat".  
14. Klicka på Spara.
15. Stäng sidan.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Tilldela artikelkod till produkthierarkin och frisläppt produkt
1. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Namn med värdet "försäljning".
2. Klicka på länken på den valda raden i listan.
3. Expandera "en kategorinod" i trädet.
    * Visa t.ex. ”försäljninghierarki\hemmaljud".  
4. Välj kategorin som artikelkoden ska tilldelas i trädet.
    * Välj t.ex. ”försäljninghierarki\hemmaljud\högtalare".  
5. Expandera avsnittet Artikelkoder.
6. Klicka på Lägg till.
7. Välj "Intrastat" i fältet Välj hierarki.
8. Hitta och markera artikelkod i listan.
    * Välj t.ex. ”920 20 34 högtalare”.  
9. Klicka på SelectCodes.
10. Klicka på OK.
11. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
12. Välj den frisläppta produkten som ska tilldelas artikelkoden i listan.
    * Välj t.ex. "D0001".  
13. Klicka på Redigera.
14. Visa avsnittet Utländsk handel.
15. Ange artikelkoden i fältet för Artikel.
    * Välj t.ex. värdet ”920 20 34 högtalare”.    
16. Välj en siffra i fältet Avgiftsprocent.
    * Välj t.ex. "3".  
17. Ange eller välj ett land eller region i fältet Land/region.
    * Välj till exempel "AUT".  
18. Visa avsnittet Hantera lager.
19. Ange en vikt i kg i fältet Nettovikt.
    * Välj t.ex. "2,5".  
20. Klicka på Spara.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Ställ in Intrastat-transaktionkoder och utrikeshandelparametrar
1. Gå till Moms > Inställningar > Utländsk handel > Transaktionskoder
2. Klicka på Ny.
3. Skriv ett värde i fältet Transaktionskod.
    * Ange t.ex. "21 "för den transaktionskod som används som retur.  
4. Ange namnet på transaktionskoden i fältet Namn.
    * Skriv till exempel "Retur".  
5. Välj ett alternativ i fältet Statistiskt belopp.
    * Välj t.ex .”Tom” som anger att det statistiska värdet som ska rapporteras för transaktioner med transaktionskoden "21 "är alltid noll.  
6. Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.
7. Ange eller välj ett värde i fältet Transaktionskod.
    * Välj till exempel "11".  
8. Ange eller välj ett värde i fältet Kreditfaktura.
    * Det här värdet även identifiera den fysiska returen. Kreditfakturan för fysisk retur ska överföras till Intrastat-journalen med motsatt riktning. Till exempel överförs införselreturen som utskick.   Annars betraktas kreditfakturan som en korrigering och överförs med samma riktning och motsatt tecken. Till exempel överförs korrigeringen av införsel som en införsel med negativt belopp, och den aktiva flaggan anges” till ”Korrigering".  
9. Expandera alternativet Överför.
10. Välj Ja i fältet Artiklar med artikelkod.
    * Markera det här alternativet om du endast vill överföra transaktioner med en tilldelad artikelkod. Transaktioner utan en artikelkod kommer inte att överföras till Intrastat.  
11. Välj ett alternativ i fältet Överför när kriteriet är uppfyllt för.
    * Välj t.ex. ”Någon av de valda”,  
12. Expandera avsnittet Artikelkodhierarki.
13. Klicka på fliken Egenskaper för land/region.
14. Klicka på Ny.
15. Ange eller välj ett värde i fältet Land/region.
    * Välj till exempel värdet "FRA".  
16. Ange den ISO-koden för landet i Intrastat-kodfältet.
    * Skriv till exempel "FR".  
17. Välj EU i fältet Lands-/regiontyp.
18. Klicka på fliken Nummersekvenser.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Ställ in leveranssätt och regler för att inkludera avgifter i Intrastat
1. Gå till Försäljning och marknadsföring > Inställningar > Distribution > Leveransmetod
2. Hitta och markera önskad post i listan.
    * Välj till exempel "20-Air".  
3. Visa avsnittet Utländsk handel.
4. Klicka på Redigera.
5. Ange eller välj ett värde i fältet Transport.
    * Välj till exempel "02".  
6. Gå till Kundreskontra > Ställa in avgifter > Avgiftskod
7. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Kod för avgifter med värdet "frakt".
8. Visa avsnittet Utländsk handel.
9. Klicka på Redigera.
10. Välj Ja i fältet Intrastat-fakturavärde.
    * Beloppet kommer att överföras till fältet Fakturaavgifter och kommer att summeras med det överfördabeloppet i fältet Fakturabelopp.    Välj Ja i fältet Intrastat statistiskt värde, om beloppet av ändringar måste överföras till fältet Statistiska avgifter och summerats med Statistiskt belopp.  

## <a name="sell-products-for-eu-customers"></a>Sälja produkter för EU-kunder
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. Markera en EU-kund i fältet Kundkonto
    * Markera till exempel ”DE-012 Litware Butik”.  
4. Expandera avsnittet Leverans.
5. Ange eller välj ett värde i fältet Leveranssätt.
    * Välj till exempel "20-Air".  
6. Klicka på OK.
7. Placera markören på den första raden av försäljningsorderrader.
8. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj till exempel "D001".  
9. Expandera avsnittet Radinformation.
10. Klicka på fliekn Utrikeshandel.
    * Transporten fylls automatiskt i från det valda leveranssättet.  
11. Ange eller välj ett värde i fältet Port.
12. Klicka på Ekonomi.
    * I enlighet med inställningarna kommer detta belopp att inkluderas i Intrastat-fakturavärdet.  
13. Klicka på Underhåll avgifter.
14. Ange eller välj ett värde i fältet Avgifter.
    * Välj till exempel "FRAKT".  
15. Markera kryssrutan Behåll.
16. I fältet Avgiftsvärde, ange ett värde.
    * Ange t.ex. "10".  
17. Klicka på Spara.
18. Stäng sidan.
19. Klicka på Faktura i åtgärdsfönstret.
20. Klicka på Faktura.
21. Expandera avsnittet Parametrar.
22. Välj Alla i fältet Kvantitet.
23. Expandera avsnittet Inställningar.
24. Ange ett datum i fältet Fakturadatum.
    * Ange till exempel "2015-01-31".  
25. Klicka på OK.
26. Klicka på OK.
27. Stäng sidan.
28. Klicka på Ny.
29. Markera en EU-kund i fältet Kundkonto.
    * Välj till exempel "DE-013 Trey Wholesales"  
30. Klicka på OK.
31. Ange eller välj ett värde i fältet Artikelnummer.
    * Välj till exempel "D0001".  
32. Klicka på Spara.
33. Klicka på Faktura.
34. Ange ett datum i fältet Fakturadatum.
    * Ange till exempel datumet "2015-01-31".  
35. Klicka på OK.
36. Klicka på OK.

## <a name="transfer-transactions-to-the-intrastat"></a>Överföra transaktioner till Intrastat
1. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
2. Klicka på Överför.
3. Välj Ja i fältet Kundfaktura.
4. Klicka på Filter.
5. Markera vald rad med datum.
6. Ange ett värde i fältet Kriterier.
    * Ange filtret för perioden januari 2015 (det exakta värdet beror på ditt datumformat), till exempel: 1/1/2015..1/31/2015  
7. Klicka på OK.
8. Klicka på OK.
9. Hitta och markera den överförda posten.
10. Klicka på fliken Allmänt.
    * Granska överförda data, inklusive destinationens/utskickets land/region, ursprungsland, vikt, kvantitet, kvantitet i ytterligare enheter, vara, transaktionskod, fakturabelopp och statistiska belopp.   Du kan ändra data om det behövs.  


