---
title: Ställ in efterdaterade checkar
description: I det här avsnittet beskrivs hur du anger om du vill bokföra journalposter för postdaterade checkar och vilka bokföringsjournaler som ska användas för att rensa poster och leverantörsbetalningar.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b677056f11a8733bf90f18110b8ee47f6447503b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976301"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]