---
title: Överföra transaktioner till Intrastat
description: I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat.
author: Anasyash
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 919c3cd755458f46a9f083415aa196c703fcf338
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183938"
---
# <a name="transfer-transactions-to-the-intrastat"></a>Överföra transaktioner till Intrastat

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat. Proceduren har skapats med demodataföretaget DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Skapa ny och uppdatera befintlig artikelkod
1. I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier**.
2. I listan markerar du posten **Intrastat-artikelkoder**.
3. Klicka på länken på den valda raden i listan.
4. Välj en post i trädet. Välj t.ex. **Intrastat\högtalare**.  
5. Klicka på **Redigera**.
6. Visa snabbfliken **Utländsk handel**.
7. Ange eller välj ett värde i fältet **Ytterligare enheter**. Välj t.ex. **st**.  
8. Välj **Ja** i fältet **Vikten är inte tillämplig**.
9. Välj **Intrastat** i trädet.
10. Klicka på **Ny kategorinod**.
11. Ange artikelns namn i fältet **Namn**. Skriv till exempel **annan artikel**.  
12. Ange artikelkoden i fältet för **Kod**. Skriv till exempel **995 00 00**.  
13. Skriv ett värde i fältet Eget namn. Skriv till exempel **Annat**.  
14. Klicka på **Spara**.
15. Stäng sidan.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Tilldela artikelkod till produkthierarkin och frisläppt produkt
1. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet **Namn** med värdet **försäljning**.
2. Klicka på länken på den valda raden i listan.
3. Expandera **en kategorinod** i trädet. Visa t.ex. **försäljninghierarki\hemmaljud**.  
4. Välj **kategorin som artikelkoden ska tilldelas** i trädet. Välj t.ex. **försäljninghierarki\hemmaljud\högtalare.  
5. Expandera snabbfliken **Artikelkoder**.
6. Klicka på **Lägg till**.
7. I **Select Välj hierarki**, välj **Intrastat**.
8. Hitta och markera artikelkod i listan. Välj t.ex. **920 20 34 högtalare**.  
9. Klicka på högerpilen för att välja kod.
10. Klicka på **OK**.
11. I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
12. Välj den frisläppta produkten som ska tilldelas artikelkoden i listan. Välj t.ex. **D0001**.  
13. Klicka på **Redigera**.
14. Visa snabbfliken **Utländsk handel**.
15. I fältet **Artikel**, ange artikelkoden. Välj t.ex. värdet **920 20 34 högtalare**.    
16. I fältet **Avgiftsprocent** anger du en siffra. Ange exempelvis **3**.  
17. I fältet **Land/region** ange eller välj ett land eller region. Välj till exempel **AUT**.  
18. Visa snabbfliken **Hantera lager**.
19. I fältet **Nettovikt** anger du en vikt i kg. Ange exempelvis **2,5**.  
20. Klicka på **Spara**.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Ställ in Intrastat-transaktionkoder och utrikeshandelparametrar
1. i navigeringsfönstret, gå till **moduler > moms > inställningar > utrikeshandeln > transaktionskoder**.
2. Klicka på **Ny**.
3. I fältet **Transaktionskod**, skriv ett värde. Ange t.ex. **21** för den transaktionskod som används som retur.  
4. I fältet **Namn** ange namnet på transaktionskoden. Skriv till exempel, ange **Retur**.  
5. Välj ett alternativ i fältet **Statistiskt belopp**. Välj t.ex. **Tom** som anger att det statistiska värdet som ska rapporteras för transaktioner med transaktionskoden **21** är alltid noll.  
6. i navigeringsfönstret, gå till **moduler > moms > inställningar > utrikeshandeln > utländska handelsparametrar**.
7. Ange eller välj ett värde i fältet **Transaktionskod**. Välj till exempel **11**.  
8. Ange eller välj ett värde i fältet **Kreditfaktura**. Det här värdet även identifiera den fysiska returen. Kreditfakturan för fysisk retur ska överföras till Intrastat-journalen med motsatt riktning. Till exempel överförs införselreturen som utskick.   Annars betraktas kreditfakturan som en korrigering och överförs med samma riktning och motsatt tecken. Till exempel överförs korrigeringen av införsel som en införsel med negativt belopp, och den aktiva flaggan anges” till **Korrigering**.  
9. Expandera snabbfliken **Överför**.
10. Välj **Ja** i fältet **Artiklar med artikelkod**. Markera det här alternativet om du endast vill överföra transaktioner med en tilldelad artikelkod. Transaktioner utan en artikelkod kommer inte att överföras till Intrastat.  
11. Välj ett alternativ i fältet **Överför när kriteriet är uppfyllt**. Välj t.ex. **Någon av de valda**.  
12. Expandera avsnittet **Artikelkodhierarki**.
13. Klicka på fliken **Egenskaper för land/region**.
14. Klicka på **Ny**.
15. Ange eller välj ett värde i fältet **Land/region**. Välj till exempel värdet **FRA**.  
16. Ange den ISO-koden för landet i fältet **Intrastat-kod**.  Skriv till exempel **FR**.  
17. I fältet **Lands-/regiontyp**, välj **EU**.
18. Klicka på fliken Nummersekvenser.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Ställ in leveranssätt och regler för att inkludera avgifter i Intrastat
1. I navigeringsfönstret går du till **moduler > försäljning och marknadsföring > inställningar > distribution > leveranssätt**.
2. Hitta och markera önskad post i listan. Välj till exempel **20 Air**.  
3. Visa snabbfliken **Utländsk handel**.
4. Klicka på **Redigera**.
5. Ange eller välj ett värde i fältet **Transport**. Välj till exempel **02**.  
6. I navigeringsfönstret går du till **moduler > kundreskontra > avgiftsinställningar > avgiftskod**.
7. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Kod för avgifter med värdet **frakt**.
8. Visa snabbfliken **Utländsk handel**.
9. Klicka på **Redigera**.
10. Välj **Ja** i fältet **Intrastat-fakturavärde**. Beloppet kommer att överföras till fältet **Fakturaavgifter** och kommer att summeras med det överförda beloppet i fältet Fakturabelopp. Välj **Ja** i fältet **Intrastat statistiskt värde** om beloppet av ändringar måste överföras till fältet **Statistiska avgifter** och summerats med **Statistiskt belopp**.  

## <a name="sell-products-for-eu-customers"></a>Sälja produkter för EU-kunder
1. I navigeringsfönstret går du till **Moduler > Kundreskontra > Order > Alla försäljningsorder**.
2. Klicka på **Ny**.
3. Markera en EU-kund i fältet **Kundkonto**. Markera till exempel **DE-012 Litware butik**.  
4. Expandera snabbfliken **Leverans**.
5. Ange eller välj ett värde i fältet **Leveranssätt**. Välj till exempel **20 Air**.  
6. Klicka på **OK**.
7. Välj den första raden av försäljningsorderrader.
8. I fältet **artikelnummer** anger du eller väljer ett värde. Välj till exempel **D001**.  
9. Visa snabbfliken **Radinformation**.
10. Klicka på fliken **Utländsk handel**. Transporten fylls automatiskt i från det valda leveranssättet  
11. I fältet **Port** anger eller väljer du ett värde.
12. Klicka på **Ekonomi**. I enlighet med inställningarna kommer detta belopp att inkluderas i **Intrastat-fakturavärdet**.  
13. Klicka på **Underhåll avgifter**.
14. Ange eller välj ett värde i fältet **Avgiftskoder**. Välj till exempel **FRAKT**.  
15. Markera kryssrutan **Behåll**.
16. Ange ett nummer i fältet **Avgiftsvärde**. Ange exempelvis **10**.  
17. Klicka på **Spara**.
18. Stäng sidan.
19. I åtgärdsrutan, klicka på **Faktura**.
20. Klicka på **faktura**.
21. Expandera avsnittet **Parametrar**.
22. I fältet **Kvantitet**, välj **Alla**.
23. Expandera snabbfliken **Inställning**.
24. Ange ett datum i fältet **Fakturadatum**. Ange exempelvis **2015-01-31**.  
25. Klicka på **OK**.
26. Klicka på **OK**.
27. Stäng sidan.
28. Klicka på **Ny**.
29. Markera en EU-kund i fältet **Kundkonto**. Välj till exempel **DE-013 Trey Wholesales**.
30. Klicka på **OK**.
31. I fältet **artikelnummer** anger du eller väljer ett värde. Välj till exempel **D0001**.  
32. Klicka på **Spara**.
33. Klicka på **faktura**.
34. Ange ett datum i fältet **Fakturadatum**. Ange till exempel datumet **2015-01-31**.  
35. Klicka på **OK**.
36. Klicka på **OK**.

## <a name="transfer-transactions-to-the-intrastat"></a>Överföra transaktioner till Intrastat
1. i navigeringsfönstret, gå till **moduler > moms > deklarationer > utrikeshandeln > Intrastat**.
2. Klicka på **Överför**.
3. Välj **Ja** i fältet **Kundfaktura**.
4. Klicka på **Filter**.
5. Markera vald rad med **Datum**.
6. I fältet **Kriterier** skriver du ett värde. Ange filtret för perioden januari 2015 (det exakta värdet beror på ditt datumformat), till exempel: 1/1/2015..1/31/2015  
7. Klicka på **OK**.
8. Klicka på **OK**.
9. Hitta och markera den överförda posten.
10. Klicka på fliken **Allmänt**.
    
Granska överförda data, inklusive destinationens/utskickets land/region, ursprungsland, vikt, kvantitet, kvantitet i ytterligare enheter, vara, transaktionskod, fakturabelopp och statistiska belopp. Du kan ändra data om det behövs.  

