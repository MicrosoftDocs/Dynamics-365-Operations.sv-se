---
title: Skapa ett leverantörsbankkonto
description: Den här proceduren visar hur du skapar ett bakkonto för en leverantör.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb3587667ac13b95617ec219995bfef931df00c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "360634"
---
# <a name="create-a-vendor-bank-account"></a>Skapa ett leverantörsbankkonto

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

