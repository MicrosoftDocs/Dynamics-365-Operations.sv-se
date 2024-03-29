---
title: ER skapa elektroniska handlingar för betalningar med en formatkonfiguration
description: I den här artikeln beskrivs hur du använder en ny konfiguration av elektronisk rapporteringsformat (ER) för att generera elektroniska dokument för bearbetning av betalningar.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
ms.openlocfilehash: b70b246e3618e8f083e5f6757ee8a97d8072a635
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290887"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER skapa elektroniska handlingar för betalningar med en formatkonfiguration

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan använda en ny formatkonfiguration för Elektronisk rapportering (ER) för att skapa elektroniska dokument för bearbetning av betalningar. Dessa steg kan utföras i GBSI-exempelföretaget.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfiguration med formatet betalningsdokument”.


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Ändra konfigurationen för den elektroniska betalningsmetoden
1. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.
2. Växla avsnittet filformat för att visa det vid behov.
3. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Betalningsmetod med värdet "Electronic".
4. Klicka på Redigera.
5. Ange Allmän elektronisk rapportering till Ja.
    * Välj Ja om du vill använda det allmänna elektroniska rapporteringmönstret för generering av betalningsfil.  
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
7. Välj formatkonfigurationen BACS (fiktiv från Storbritannien).
8. Klicka på Spara.
9. Stäng sidan.

## <a name="test-the-format-of-generated-payment-files"></a>Testa formatet för skapade betalningsfiler
1. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
5. Klicka på länken på den valda raden i listan.
    * Välj VendPay.  
6. Klicka på Spara.
7. Klicka på Rader.
8. Ange "DEMF" i fältet Företag.
    * DEMF  
9. Ange värdet "DE-0100" i fältet Konto.
    * DE - 01001  
10. Ange "Betalning" i fältet Beskrivning.
    * Betalning  
11. Ange ett tal i fältet Debet.
    * 1 000  
12. Klicka på fliken Betalning.
13. I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.
14. Hitta och markera önskad post i listan.
    * Välj det elektroniska värdet.  
15. Klicka på länken på den valda raden i listan.
16. Klicka på Spara.
17. Klicka på Skapa betalningar.
18. I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.
19. Hitta och markera önskad post i listan.
    * Välj det elektroniska värdet.  
20. Klicka på länken på den valda raden i listan.
    * Välj det elektroniska värdet.  
21. Ange ett värde i fältet Filnamn.
    * Skriv till exempel "betalningar".  
22. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Bankkonto.
23. Klicka på länken på den valda raden i listan.
    * Välj värdet GBSI OPER.  
24. Klicka på OK.
25. Klicka på OK.
    * Analysera den skapade betalningsfilen i XML-format. Jämför den med den designade dokumentlayouten och de definierade betalningstransaktionsattributen.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
