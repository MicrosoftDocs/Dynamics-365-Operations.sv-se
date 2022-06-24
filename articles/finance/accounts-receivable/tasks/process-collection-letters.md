---
title: Bearbeta kravbrev
description: I den här artikeln visas hur du skapar, skriver ut och bokför kravbrev.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: fbca4acf30e2c58d8bb615d659b883b574a12aa7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909139"
---
# <a name="process-collection-letters"></a>Bearbeta kravbrev

[!include [banner](../../includes/banner.md)]

I den här artikeln visas hur du skapar, skriver ut och bokför kravbrev. I den här uppgiften används demonstrationsföretaget USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Ställ in en kravbrevsserie för bokföringsprofilen
1. Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.
2. Klicka på **Redigera**.
3. Välj en kravbrevssekvens i listrutan. Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.  
4. Expandera fliken **Registerbegränsningar** för att ändra hur kravbrev bearbetas. Om detta fält har satts till **Ja** skapas kravbrev för denna bokföringsprofil.  

## <a name="create-collection-letters"></a>Skapa kravbrev
1. Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Skapa kravbrev**.
2. Välj transaktionstyperna för kravbrev. Alla öppna transaktioner för dessa typer inkluderas i beräkningen.  
3. I fältet **Kravbrev** väljer du ett alternativ.
4. Ange datum för kravbrevet i fältet **Datum för kravbrev**.
5. Välj en bokföringsprofil om du har ändrat **Använd bokföringsprofil från** till **Välj**. Det finns två typer av profilalternativ:   

   - **Konto** – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.   
   - **Välj** – Använd den bokföringsprofil som du väljer i fältet **Bokföringsprofil**.  

6. Expandera avsnittet **Poster som ska ingå**.
7. Välj **filter**.
8. I fältet **Kriterier**, ange ett kund-ID. Till exempel "US-001".
9. Välj **OK**.
10. Välj **OK**.

## <a name="print-collection-letters"></a>Skriv ut kravbrev
1. Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.
2. I fältet **Status**, välj **Skapad**.
3. I fältet **Utskrivet**, välj **Ej utskrivet**.
4. Välj **Skriv ut**.
5. Välj **Kravbrevsnotering**.
6. Ange sista datum för bokföring i avsnittet **Parametrar**.
7. Expandera avsnittet **Poster som ska ingå** och ange information om kravbrevsnoteringen.
8. Välj **OK** för att skriva ut kravbrevet.
9. Bokför kravbrevet.

    1. Vald **bokföring**
    1. Ange bokföringsdatumet för kravbrevet.
    1. Expandera avsnittet **Poster som ska ingå**.
    1. Välj **OK**.
    1. I fältet **Status**, välj **Bokförd**.
    1. Välj ett alternativ i fältet **Utskriven**.

## <a name="control-collection-letters-at-the-customer-level"></a>Kontrollera kravbrev på kundnivån
Om kravbrev ställs in på transaktionsnivå kan flera bokstäver genereras för en kund, baserat på transaktionsåldrande. Om transaktioner visas i olika brevserier skapas separata kravbrev för varje grupp av förfallna transaktioner för kunden. Därför kan en enskild kund få till exempel ett kravbrev för transaktioner som är 60 dagar och ett annat kravbrev för transaktioner som är 90 dagar. 

Varje kravbrev är också kopplat till en kravbrevskod. Kravbrevskoden är kopplad till enskilda transaktioner och används för att bestämma när nästa kravbrev ska skapas för varje transaktion. Om till exempel en transaktion är mer än 30 dagar försenad, avgör kravbrevskoden att nästa kravbrev ska skickas när transaktionen blir 60 dagar för sent, om den inte betalas före. 

Kravbrev kan också ställas in på kundnivå. I det här fallet spåras kravbrevskoden för varje transaktion, men bearbetningen av kravbrev ska baseras på en enda kravbrevsnivå som sparats för kunden. Det enda kravbrevet innehåller alla transaktioner som har förfallit för kunden. Eftersom respitdagar nu spåras på kundnivå kommer nästa kravbrev inte att skickas förrän antalet respitdagar har passerat för nästa kravbrev i sekvensen, även om transaktioner blir försenade efter det att sista kravbrevet skickats. Det här alternativet hjälper tilt minska antalet kravbrev som du måste skicka till varje kund.

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Ställ in kund för att kontrollera kravbrev på kundnivå
1.  Gå till **navigeringfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och välj fliken **samlingar**. 
2.  Ändra värdet för **skapa kravbrev per** till **kund**. 
3.  Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**. Bara ett kravbrev kommer att skapas för en kund med alla förfallna transaktioner.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorera betalningar och kreditnotor när du beräknar kravbrevskod
Om du inkluderar betalningar och kreditnotor i de transaktioner som ska inkluderas i kravbrev kanske du betalningar eller kreditnotor som kommer att utlösa ett kravbrev. Du kan kontrollera hur betalningar och kreditnotor kontrollerar kravbrevskoden genom att ändra värdet för parametern **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod**. 

Om du vill ignorera betalningar och kreditnotor när du beräknar kravbrevskod, gör följande.

1. Gå till **navigeringfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **Samlingar**. 
2. Ändra värdet för **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod** till **Ja**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
