---
title: Skapa ett leverantörsbankkonto
description: Den här proceduren visar hur du skapar ett bakkonto för en leverantör.
author: kamaybac
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4fcf15d798d2ca8e1d36556fbe2c9603f12d2b03
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812024"
---
# <a name="create-a-vendor-bank-account"></a>Skapa ett leverantörsbankkonto

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du skapar ett bakkonto för en leverantör. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.

1. Gå till **navigeringsfönstret > Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.
2. Markera leverantören som du vill skapa ett bankkonto för, och klicka sedan på länken i fältet **Leverantörskonto-ID.**
3. I **åtgärdsfönstret**, klicka på **Leverantör**.
4. Klicka på **Bankkonton**.
5. Klicka på **Nytt** i **Åtgärdsfönstret**.
6. Ange ett värde i fältet **Bankkonto**. Detta ID ska användas för att identifiera bankkontot på leverantörsposten.  
7. Skriv ett värde i fältet **Namn**.
8. Ange eller välj ett värde i fältet **Bankgrupper.**
9. Välj ett alternativ i fältet **Organisationsnummertyp.** Det är denna typ av organisationsnummer som används för internationella betalningar.  
10. Skriv ett värde i fältet **Bankkontonummer.**
11. Skriv ett värde i fältet **SWIFT-kod.**
12. Ange ett värde i fältet **IBAN**.
    - IBAN-numret måste vara i rätt format. Till exempel kan du använda DE89370400440532013000.  
    - Statusen på bankkontot är Aktiv, om det aktiva datumet har nåtts och utgångsdatumet inte har överskridits. Den är också aktiv om båda fälten Aktivt datum och Utgångsdatum är tomma. Om datumen i båda fälten Aktivt datum och Utgångsdatum infaller senare är elektroniska betalningar inte tillgängligt. Andra betalningstyper är tillgängliga och bankkontot är aktivt.  
13. Expandera avsnittet **Inställningar**.
14. Skriv ett värde i fältet **Textkod.** Det här fältet anger en kod som ska visas på mottagarens bankutdrag.  
15. Skriv ett värde i fältet **Meddelande till bank.**
16. Ange ett värde i fältet **Kursreferens.** Detta är referensnumret för terminskurser eller fasta kurser.
17. Ange eller välj ett värde i fältet **Valuta.** När förauktoriseringar utfärdas ger det här avsnittet en översikt över deras status (väntande eller godkänd).  
18. Expandera avsnittet **Adress.**
19. Expandera avsnittet **Förauktoriseringar.**
20. Expandera avsnittet **Kontaktinformation.**
21. Ange ett värde i fältet **Telefon.**
22. Stäng sidan.
23. Klicka på **Redigera**.
24. Expandera avsnittet **Betalning.**
25. Välj det konto som du nyss skapat i fältet **Bankkonto**.
26. Klicka på **Spara**. Adressen kan ärvas från bankgruppen, om en sådan har angetts, eller så kan du lägga till den här.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]