--- 
title: "Generera elektroniska dokument för betalningar med en formatkonfiguration för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan använda en ny formatkonfiguration för Elektronisk rapportering (ER) för att generera elektroniska dokument för bearbetning av betalningar."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a5d958d3b55bfa76f3cfbb3c1a289e4e89c49146
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a>Generera elektroniska dokument för betalningar med en formatkonfiguration för elektronisk rapportering (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan använda en ny formatkonfiguration för Elektronisk rapportering (ER) för att generera elektroniska dokument för bearbetning av betalningar. Dessa steg kan utföras i GBSI-exempelföretaget.

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

## <a name="test-the-format-of-generated-payment-files"></a>Testa formatet för genererade betalningsfiler
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
17. Klicka på Generera betalningar.
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


