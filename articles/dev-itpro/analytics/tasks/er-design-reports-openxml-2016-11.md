--- 
title: "Utforma en konfiguration för rapportgenerering i OpenXML-format för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att generera elektroniska betalningsdokument i OPENXML-format."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 09789957839097ba2898544102af908c198090c7
ms.contentlocale: sv-se
ms.lasthandoff: 11/14/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a>Utforma en konfiguration för rapportgenerering i OpenXML-format för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att generera elektroniska betalningsdokument i OPENXML-format. Denna konfiguration kommer att användas för att bearbeta leverantörsbetalningar.



I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i GBSI-företag.



För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”. Du måste också hämta och spara Microsoft Excel-filen [mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266). 

## <a name="upload-the-payments-data-model-configuration"></a>Överför konfigurationen för betalningdatamodellen
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Markera vald rad i listan.
    * Välj konfigurationsleverantören för exempelföretaget "Litware, Inc." Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.  
3. Klicka på Ställ in aktiv.
4. Klicka på Databaser.
    * Välj en databas för resurstypen Verksamhetsresurs, om det är tillämpligt. Om detta är tillgängligt hoppar du över stegen om att skapa en ny databas.  
5. Klicka på Lägg till för att öppna dialogrutan.
6. Ange "Operations resources" i fältet Configuration repository type.
7. Klicka på Skapa en databas.
8. Klicka på OK.
9. Klicka på Öppna.
10. Välj "Betalningsmodell" i trädet.
11. Klicka på Importera.
    * Importera den här datamodell. Den används som en datakälla i en ny formatkonfiguration. Hoppa över detta steg om den här konfigurationen redan har importerats.  
12. Klicka på Ja.
13. Stäng sidan.
14. Stäng sidan.

## <a name="create-a-new-format-configuration"></a>Skapa en ny formatkonfiguration
1. Klicka på Reporting configurations.
2. Välj "Betalningsmodell" i trädet.
3. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
4. Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.
    * Skapa ett format som baseras på datamodellen PaymentModel.  
5. Skriv "Rapport över exempelkalkylblad" i fältet Namn.
    * Rapport över exempelkalkylblad  
6. Skriv in "Rapport över exempelkalkylblad för leverantörer"i fältet Beskrivning.
    * Rapport över kalkylblad prov för leverantörers betalningar.  
7. Ange eller välj ett värde i fältet Data model definition.
    * Välj definitionen "CustomerCreditTransferInitiation".  
8. Klicka på Skapa konfiguration.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Designa ett nytt dokument i OPENXML-kalkylbladformat
1. Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.
2. Klicka på Designer.
3. Klicka på Importera i åtgärdsfönstret.
4. Klicka på Importera från Excel.
5. Klicka på Bilagor.
    * Koppla det befintliga Excel-dokumentet som en mall.  
6. Klicka på Ny.
7. Klicka på Arkiv.
    * Peka på den befintliga Excel-filen.  
8. Stäng sidan.
9. Ange eller välj ett värde i fältet Template.
    * Välj den bifogade Excel-filen som ska användas som en mall.  
10. Klicka på OK.
    * Observera att ER-formatkomponenter har skapats i designformatet baserat på strukturen i det refererande MS Excel-dokumentet (namngivna intervall).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Skapa en ny datakälla för att beräkna summor per valutakoder
1. Klicka på fliken Mappning.
2. Klicka på Lägg till rot för att öppna dialogrutan.
3. Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.
4. Ange "PaymentByCurrency" i fältet Namn.
    * PaymentByCurrency  
5. Klicka på Redigera grupp efter.
6. Expandera "modell" i trädet.
7. Välj "modell\Betalningar" i trädet.
8. Klicka på Lägg till fält i.
9. Klicka på Vad ska grupperas.
10. Expandera "modell\Betalningar" i trädet.
11. Välj "modell\Betalningar\Valuta" i trädet.
12. Klicka på Lägg till fält i.
13. Klicka på Grupperade fält.
14. Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.
15. Klicka på Lägg till fält i.
16. Klicka på Sammansättningsfält.
17. Markera ett alternativ i fältet Metod.
    * Välj den sammansatta funktionen SUMMA.  
18. Skriv "TotalInstructuredAmount" i fältet Namn.
    * TotalInstructuredAmount  
19. Klicka på Spara.
20. Stäng sidan.
21. Klicka på OK.

## <a name="map-format-components-to-data-sources"></a>Mappa formatkomponenter till datakällor
1. Expandera "modell" i trädet.
2. Expandera "modell\Betalningar" i trädet.
3. Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)" i trädet.
4. Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)\Namn" i trädet.
5. Expandera "Excel\ReportHeader" i trädet.
6. Välj "Excel\ReportHeader\CompanyName" i trädet.
7. Klicka på Bind.
8. Expandera "modell\Betalningar\Betalningsmottagare" i trädet.
9. Expandera "modell\Betalningar\Betalningsmottagare\Identifiering" i trädet.
10. Välj "modell\Betalningar\Betalningsmottagare\Identifiering\Käll-ID(SourceID)" i trädet.
11. Expandera "Excel\PaymLines" i trädet.
12. Välj "Excel\PaymLines\VendAccountName" i trädet.
13. Klicka på Bind.
14. Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.
15. Välj "Excel\PaymLines\VendName" i trädet.
16. Klicka på Bind.
17. Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.
18. Välj "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)\Namn" i trädet.
19. Välj "Excel\PaymLines\Bank" i trädet.
20. Klicka på Bind.
21. Välj "modell\Betalningar\Betalningsmottagaragent\CreditorAgent)\Clearingnummer(RoutingNumber)" i trädet.
22. Välj "Excel\PaymLines\RoutingNumber" i trädet.
23. Klicka på Bind.
24. Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.
25. Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering" i trädet.
26. Välj "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering\Nummer" i trädet.
27. Välj "Excel\PaymLines\AccountNumber".
28. Klicka på Bind.
29. Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.
30. Välj "Excel\PaymLines\Debit" i trädet.
31. Klicka på Bind.
32. Expandera "modell\Betalningar\Betalningsmottagare" i trädet.
33. Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.
34. Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.
35. Välj "modell\Betalningar\Valuta" i trädet.
36. Välj "Excel\PaymLines\Currency" i trädet.
37. Klicka på Bind.
38. Expandera "PaymentByCurrency" i trädet.
39. Expandera "PaymentByCurrency\grupperad" i trädet.
40. Välj "PaymentByCurrency\grupperad\Valuta" i trädet.
41. Expandera "Excel\SummaryLines" i trädet.
42. Välj "Excel\SummaryLines\SummaryCurrency" i trädet.
43. Klicka på Bind.
44. Expandera "PaymentByCurrency\sammansatt" i trädet.
45. Välj "PaymentByCurrency\sammansatt\TotalInstructuredAmount" i trädet.
46. Välj "Excel\SummaryLines\SummaryAmount" i trädet.
47. Klicka på Bind.
48. Välj "PaymentByCurrency" i trädet.
49. Välj "Excel\SummaryLines" i trädet.
50. Klicka på Bind.
51. Välj "modell\Betalningar" i trädet.
52. Välj "Excel\PaymLines" i trädet.
53. Klicka på Bind.
54. Klicka på Spara.
55. Stäng sidan.

## <a name="use-the-created-configuration-for-payments-processing"></a>Använd den skapade konfigurationen för bearbetning av betalningar
1. Klicka på Ändra status.
2. Klicka på Slutför.
3. Klicka på OK.
4. Stäng sidan.
5. Stäng sidan.
6. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.
7. Använd snabbfiltret för att filtrera på Betalsätt med värdet "Elektroniskt".
    * Elektronisk  
8. Klicka på Redigera.
9. Expandera avsnittet Filformat.
10. Välj Ja i fältet Allmän elektronisk rapportering.
11. Ange eller välj ett värde i fältet Exportera formatkonfiguration.
    * Markera konfigurationen "Rapport över exempelkalkylblad".  
12. Klicka på Spara.
13. Stäng sidan.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Använd den skapade konfigurationen för att testa bearbetning av betalningsjournaler
1. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
    * Skapa en ny betalningsjournal.  
3. Skriv ”VendPay” i fältet Namn.
    * VendPay  
4. Klicka på Rader.
5. Ange värdena "GB_SI_000001" i fältet Konto.
    * GB_SI_000001  
6. Ställ in debet på "1000".
7. Klicka på Ny.
8. Ange värdena "GB_SI_000005" i fältet Konto.
    * GB_SI_000005  
9. Ställ in debet på "2000".
10. Ange "EUR" i fältet Valuta.
    * Euro  
11. Ange värdet "GBSI OPER" i fältet Motkonto.
    * GBSI-OPERATION  
12. Skriv ett värde i fältet "Elektonisk".
    * Elektronisk  
13. Klicka på Spara.
14. Klicka på Generera betalningar.
15. Skriv ett värde i fältet "Elektonisk".
    * Elektronisk  
16. Ange "Betalningar" i fältet för filnamn.
    * Skriv till exempel "betalningar".  
17. Skriv "GBSI OPER" i fältet Bankkonto.
    * GBSI-OPERATION  
18. Klicka på OK.
19. Klicka på OK.
    * Granska det skapade kalkylbladet, inklusive information om betalningsrader samt summan för varje valutakod som används i detta betalningmeddelande.  


