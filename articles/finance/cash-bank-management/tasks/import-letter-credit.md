---
title: Importera remburs
description: I den här proceduren förklaras processen för att importera en remburs.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9f9c73ec1347e72f8cd4ae8eec580bb8fe3df8ed
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141774"
---
# <a name="import-letter-of-credit"></a>Importera remburs

[!include [banner](../../includes/banner.md)]

I den här proceduren förklaras processen för att importera en remburs. Följande måste ställas in innan du avslutar den här proceduren: bankkreditlimiter, bokföringsprofiler, kreditlimitavtal för bank och säljarens bankdetaljer.

I den här proceduren används demonstrationsföretaget USMF.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Skapa en inköpsorder med remburs
1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Leverantörskonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Expandera avsnittet Allmänt.
7. Ange eller välj ett värde i fältet Plats.
8. Klicka på länken på den valda raden i listan.
9. Ange eller välj ett värde i fältet Lagerställe.
10. Klicka på länken på den valda raden i listan.
11. Ange ett datum i fältet Redovisningsdatum.
12. I fältet Leveransdatum, ange ett datum.
    * Obs! Fältet Bankdokumenttyp bör väljas med värdet Remburs.  
13. Klicka på OK.
14. Ange eller välj ett värde i fältet Artikelnummer.
15. Hitta och markera önskad post i listan.
16. Klicka på länken på den valda raden i listan.
17. Expandera raddetaljavsnittet.
18. Klicka på fliken Leverans.
19. I fältet Leveransdatum, ange ett datum.
20. I fältet Bekräftat leveransdatum, ange ett datum.
21. Ange ett tal i fältet Enhetspris.
    * Definiera detaljer om rembursen.  
22. Klicka på Hantera i åtgärdsfönstret.
23. Klicka på Remburs/importinkasso.
24. I fältet Ansökningsdatum, ange datum och tid.
    * Kontrollera att fältet Bankkonto har ett aktivt bankkonto som standard, baserat på ansökningsdatumet.  
25. Skriv ett värde i fältet Bankdokumentnummer.
26. Ange datum och tid i fältet Inleveransdatum.
27. Expandera bankdokumentavsnittet.
28. I fältet Utgångsdatum anger du datum och tid.
29. Expandera avsnittet Bankdetaljer.
30. Ange eller välj ett värde i fältet Aviserande bank.
31. Klicka på länken på den valda raden i listan.
32. Klicka på Spara.
33. Klicka på Hämta inköpsorderförsändelser.
34. Stäng sidan.
35. Klicka på Inköp i åtgärdsfönstret.
36. Klicka på Bekräfta.
37. Klicka på Hantera i åtgärdsfönstret.
38. Klicka på Remburs/importinkasso.
39. Klicka på Process.
40. Klicka på Bekräfta.
    * Kontrollera att lokalsaldot minskar inköpsorderbeloppet.  I det här exemplet är Inköpsbelopp = 500,00 och Kreditlimitgräns = 10000,00 vilket ger Lokalsaldo = 9500,00.  
41. Stäng sidan.
42. Ange ett tal i fältet Enhetspris.
43. Klicka på Spara.
44. Klicka på Inköp i åtgärdsfönstret.
45. Klicka på Bekräfta.
    * Ändra rembursen till följd av ändringen i enhetspris.  
46. Klicka på Hantera i åtgärdsfönstret.
47. Klicka på Remburs/importinkasso.
    * Ändra rembursen till följd av ändringen i inköpsenhetspris.  
48. Klicka på Process.
49. Klicka på Ändra.
50. Klicka på Ta bort.
51. Klicka på Ja.
52. Klicka på Hämta inköpsorderförsändelser.
53. Klicka på Process.
54. Klicka på Bekräfta.
    * Kontrollera att lokalsaldot minskar inköpsorderbeloppet.  I det här exemplet är det redigerade Inköpsbelopp = 600,00 och Kreditlimitgräns = 10000,00 vilket ger Lokalsaldo = 9400,00.  
55. Stäng sidan.

## <a name="post-packing-slip"></a>Bokför följesedel
1. Klicka på Ta emot i åtgärdsfönstret.
2. Klicka på Produktinleverans.
3. Ange ett värde i fältet PurchParmTable_Num.
    * Välj försändelsenumret som skapas med hänvisning till rembursen.  
4. Klicka på länken på den valda raden i listan.
5. I fältet Produktinleveransdatum, ange ett datum.
6. Klicka på OK.
7. Stäng sidan.
8. Stäng sidan.

## <a name="verify-import-letter-of-credit-status"></a>Kontrollera statusen för Importremburs.
1. Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Kontrollera statusen för Importremburs.     
4. Stäng sidan.
5. Stäng sidan.

## <a name="post-purchase-invoice"></a>Bokför Inköpsfaktura
1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
    * Välj den inköpsorder som skapades med rembursen.  
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Faktura i åtgärdsfönstret.
5. Klicka på faktura.
6. Ange ett värde i fältet Antal.
7. Ange eller välj ett värde i fältet Försändelsenummer.
8. Klicka på länken på den valda raden i listan.
9. Ange ett datum i fältet Fakturadatum.
10. Klicka på Uppdatera matchningsstatus.
11. Klicka på Bokför.
12. Stäng sidan.
13. Stäng sidan.

## <a name="verify-import-letter-of-credit-status"></a>Kontrollera statusen för Importremburs.
1. Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Kontrollera importrembursen.  
    * Kontrollera: Försändelsestatus = information om fakturerade bankkreditlimiter  
4. Klicka på Visa.
5. Klicka på Skriv ut ansökning.
6. Klicka på OK.
    * Kontrollera att rembursansökningen skrivs ut.  
7. Stäng sidan.
8. Stäng sidan.
9. Stäng sidan.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Bokför leverantörsbetalningsjournalen för den skapade inköpsfakturan med remburs
1. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
4. Klicka på länken på den valda raden i listan.
5. Klicka på Rader.
6. Ange ett datum i fältet Datum.
7. Ange önskade värden i fältet Konto.
8. Klicka på Kvitta transaktioner.
9. Expandera avsnittet Summor.
10. I fältet Visa, välj ett alternativ.
    * Kontrollera att fälten Bankdokumentnummer och Försändelsenummer har uppdaterats.  
11. Markera kryssrutan Markera.
12. Klicka på OK.
13. Klicka på fliken Betalning.
    * Kontrollera att fälten Bankdokumentnummer och Försändelsenummer har uppdaterats.  
14. Klicka på Bokför.
15. Stäng sidan.
16. Stäng sidan.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Kontrollera importrembursens status när fakturan är betald
1. Gå till Kassa- och bankhantering > Remburser > Importremburs och importinkasso.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
    * Kontrollera statusen för Importremburs.   
4. Stäng sidan.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Verifiera rapporten över bankkreditlimiter och utnyttjande
1. Gå till Kassa- och bankhantering > Förfrågningar och rapporter > Remburser eller garantier > Rapport om bankkreditlimiter och utnyttjande.
2. Expandera avsnittet Poster som ska ingå.
3. Klicka på Filter.
    * Definiera fältet Kriterier med det obligatoriska bankkontot.  
4. Ange eller välj ett värde i fältet Kriterier.
5. Klicka på länken på den valda raden i listan.
6. Klicka på OK.
7. Klicka på OK.
    * Kontrollera rapport som innehåller transaktionerna.  
    * Kontrollera att rapporten innehåller transaktionerna med bankdokumentnummer, kreditlimitgräns, utnyttjat belopp och lokalsaldobeloppet.  
8. Stäng sidan.

