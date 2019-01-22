--- 
title: Bearbeta kravbrev
description: "I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: 33d9fd62a780ab109474eefa9e322a9c529f9e72
ms.contentlocale: sv-se
ms.lasthandoff: 12/06/2018

---
# <a name="process-collection-letters"></a>Bearbeta kravbrev

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev. I den här uppgiften används demonstrationsföretaget USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Ställ in en kravbrevsserie för bokföringsprofilen
1. Gå till **Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.
2. Klicka på **Redigera**.
3. Välj en kravbrevssekvens i listrutan. Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.  
4. Expandera registerbegränsningsfliken för att ändra hur kravbrev bearbetas. Om detta fält har satts till **Ja** skapas kravbrev för denna bokföringsprofil.  

## <a name="create-collection-letters"></a>Skapa kravbrev
1. Gå till **Kredit och inkasso > Kravbrev > Skapa kravbrev**.
2. Välj transaktionstyperna för kravbrev. Alla öppna transaktioner för dessa typer inkluderas i beräkningen.  
2. I fältet **Kravbrev** väljer du ett alternativ.
3. Ange datumet för det aktuella kravbrevet.
4. Välj en bokföringsprofil om du har ändrat **Använd bokföringsprofil från** till **Välj**. Det finns två typer av profilalternativ:   
   - **Konto** – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.   
   - **Välj** – Använd den bokföringsprofil som du väljer i fältet **Bokföringsprofil**.  
5. Expandera avsnittet **Poster som ska ingå**.
6. Klicka på **Filter**.
7. I fältet **Kriterier**, ange ett kund-ID. Till exempel "US-001".
8. Klicka på **OK**.
9. Klicka på **OK**.

## <a name="print-collection-letters"></a>Skriv ut kravbrev
1. Gå till **Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.
2. I fältet **Status**, välj **Skapad**.
3. I fältet **Utskrivet**, välj **Ej utskrivet**.
4. Klicka på **Skriv ut**.
5. Klicka på **kravbrevsnotering**.
6. Expandera avsnittet **Poster som ska ingå**.
7. Ange slutdatumet för bokföringar.
8. Klicka på **OK** för att skriva ut kravbrevet.
9. Bokför kravbrevet.
   1. Klicka på **Bokför**.
   2. Ange bokföringsdatumet för kravbrevet.
   3. Expandera avsnittet **Poster som ska ingå**.
   4. Klicka på **OK**.
   5. I fältet **Status**, välj **Bokförd**.
   6. Välj ett alternativ i fältet **Utskriven**.

## <a name="control-collection-letters-at-the-customer-level"></a>Kontrollera kravbrev på kundnivån
Du kan också ställa in kravbrev på kundnivån så att kravbrevskoden spåras för varje transaktion, men bearbetningen av kravbrev ska baseras på en enda kravbrevsnivå som sparats för kunden. Det enda kravbrevet innehåller alla transaktioner som har förfallit för kunden. Eftersom respitdagar nu spåras på kundnivå kommer nästa kravbrev inte att skickas förrän antalet respitdagar har passerat för nästa kravbrev i sekvensen, även om transaktioner blir försenade efter det att sista kravbrevet skickats. Det här alternativet minskar antalet kravbrev som du skickar per kund. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Ställ in kund för att kontrollera kravbrev på kundnivå
1.  Gå till **Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **samlingar**. 
2.  Ändra värdet för **skapa kravbrev per** till **kund**. 
3.  Gå till **Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**. Bara ett kravbrev kommer att skapas för en kund med alla förfallna transaktioner.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorera betalningar och kreditnotor när du beräknar kravbrevskod
Om du inkluderar betalningar och kreditnotor i de transaktioner som ska inkluderas i kravbrev kanske du betalningar eller kreditnotor som kommer att utlösa ett kravbrev. Du kan kontrollera hur betalningar och kreditnotor kontrollerar kravbrevskoden genom att ändra värdet för parametern **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod**. 

Om du vill ignorera betalningar och kreditnotor när du beräknar kravbrevskod, gör följande.
1. Gå till **Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **samlingar**. 
2. Ändra värdet för **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod** till **Ja**.

