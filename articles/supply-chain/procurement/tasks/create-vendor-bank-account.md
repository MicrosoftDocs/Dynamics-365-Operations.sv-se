--- 
title: "Skapa ett leverantörsbankkonto"
description: "Den här proceduren visar hur du skapar ett bakkonto för en leverantör."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-vendor-bank-account"></a>Skapa ett leverantörsbankkonto

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar ett bakkonto för en leverantör. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.

1. Gå till Anskaffning och källa > Leverantörer > Alla leverantörer.
2. Markera leverantören som du vill skapa ett bankkonto för, och klicka sedan på länken för leverantörskonto-ID.
3. Klicka på Leverantör i åtgärdsfönstret.
4. Klicka på bankkonton.
5. Klicka på Ny.
6. I fältet Bankkonto, skriv ett värde.
    * Detta ID ska användas för att identifiera bankkontot på leverantörsposten.  
7. Skriv ett värde i fältet Namn.
8. Ange eller välj ett värde i fältet Bankgrupper.
9. Välj ett alternativ i fältet Organisationsnummertyp.
    * Det är denna typ av organisationsnummer som används för internationella betalningar.  
10. Skriv ett värde i fältet Bankkontonummer.
11. Skriv ett värde i fältet SWIFT-kod.
12. Ange ett värde i fältet IBAN.
    * IBAN-numret måste vara i rätt format. Till exempel kan du använda DE89370400440532013000.  
    * Statusen på bankkontot är Aktiv, om det aktiva datumet har nåtts och utgångsdatumet inte har överskridits. Den är också aktiv om båda fälten Aktivt datum och Utgångsdatum är tomma. Om datumen i båda fälten Aktivt datum och Utgångsdatum infaller senare är elektroniska betalningar inte tillgängligt. Andra betalningstyper är tillgängliga och bankkontot är aktivt.  
13. Expandera avsnittet Inställningar.
14. Skriv ett värde i fältet Textkod.
    * Det här fältet anger en kod som ska visas på mottagarens bankutdrag.  
15. Skriv ett värde i fältet Meddelande till bank.
16. Ange ett värde i fältet Kursreferens.
    * Detta är referensnumret för terminskurser eller fasta kurser.  
17. Ange eller välj ett värde i fältet Valuta.
    * När förauktoriseringar utfärdas ger det här avsnittet en översikt över deras status (väntande eller godkänd).  
18. Expandera avsnittet Adresser.
19. Expandera avsnittet Förauktoriseringar.
20. Expandera avsnittet Kontaktinformation.
21. Ange ett värde i fältet Telefon.
22. Stäng sidan.
23. Klicka på Redigera.
24. Expandera avsnittet Betalning.
25. Välj det konto som du nyss skapat i fältet Bankkonto.
26. Klicka på Spara.
    * Adressen kan ärvas från bankgruppen, om en sådan har angetts, eller så kan du lägga till den här.  


