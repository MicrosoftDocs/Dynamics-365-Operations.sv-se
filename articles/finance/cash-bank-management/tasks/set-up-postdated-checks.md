---
title: Ställ in efterdaterade checkar
description: I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 645b474b8b4bd13cd47bef404cda002e6b29a1ba
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724854"
---
# <a name="set-up-postdated-checks"></a>Ställ in efterdaterade checkar

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar. Du kan även ange clearingkonton för Betalda checkar, Mottagna checkar och källskatt. Efterdaterade checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Du kan ange om checken ska återspeglas i dina redovisningsböcker före dess förfallodag.



Rollen för den här proceduren är Kassaförvaltare. I den här proceduren används demonstrationsföretaget USMF.


## <a name="set-up-postdated-checks"></a>Ställ in efterdaterade checkar
1. Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.
2. Klicka på fliken Efterdaterade checkar.
3. Markera eller avmarkera kryssrutan Aktivera efterdaterade checkar.
4. Markera eller avmarkera kryssrutan Bokför journalposter för efterdaterade checkar.
5. I fältet Clearingkonto för utfärdade checkar, ange de önskade värdena.
6. I fältet Clearingkonto för mottagna checkar, ange de önskade värdena.
7. I fältet Allmän journal för clearingposter, skriv ett värde.
8. I fältet Överför efterdaterade checkar till den här leverantörsbetalningsjournalen, skriv ett värde.
9. I fältet Clearingkonto för källskattebelopp, ange de önskade värdena.
10. Klicka på Spara.
11. Stäng sidan.
12. Gå till Leverantörsreskontra > Betalningsinställning > Betalsätt.
13. Klicka på Ny.
14. Skriv ett värde i fältet Betalningsmetod.
15. Välj alternativet Clearingbokföring av efterdaterad check om du vill ange att checkbeloppet bokförs på ett clearingkonto.
16. Välj "Bank" i fältet Kontotyp.
    * Motkontot för betalsättet kommer att vara en bank.  
17. I fältet Betalningskonto, ange önskade värden.
    * Välj det bankkonto som används för att dra av fakturabeloppet.  
18. Klicka på Spara.
19. Stäng sidan.
> [!NOTE]
> Om du vill kunna bokföra en bokförd check på ett bankkonto när sessionsdatumet är större än eller lika med förfallodagen, måste du aktivera funktionen **Förfallodatumvalidering för bokföring av betalningsjournal med bokförda checkar på bankkonto**. Med den här funktionen kan du bokföra betalningsjournaler för leverantörer eller kunder med efterbokade checkar när sessionsdatum är större än eller lika med förfallodatumet.
> 
> När du ställer in **Betalningsmetod** (**leverantörsreskontra > Betalningsinställning > Betalningsmetoder**) ska du inte fylla i **Bryggningskonto**. I det här fallet fylls motkontot i med bankkontot, som ställs in i **Betalningsmetod**.
>  
> När funktionen är aktiverad och sessionsdatum är mindre än förfallodagen visas följande felmeddelande när en betalningsjournal bokförs, "Förfallodagen måste vara mindre eller lika med sessionsdatum om motkontotypen är Bank". Om funktionen inte är aktiverad kan du bokföra en betalningsjournal med en bokförd check när sessionsdatum är mindre än förfallodatumet.
> Den här funktionen finns i version 10.0.21 eller senare.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
