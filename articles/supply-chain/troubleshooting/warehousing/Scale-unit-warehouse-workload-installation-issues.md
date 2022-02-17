---
title: Bearbetningsproblem uppstår efter att lasten i en skalenhet har installerats
description: Det här ämnet beskriver problem som kan inträffa en kort tid efter det att en distributionslagerhantering i en skalningsenhet har installerats och ger ett tips om hur du rättar till dem.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071652"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Bearbetningsproblem uppstår efter att lasten i en skalenhet har installerats

Det här ämnet beskriver problem som kan inträffa en kort tid efter det att en distributionslagerhantering i en skalningsenhet har installerats och ger ett tips om hur du rättar till dem.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problem 1: Fel efter att en belastning har frisläppts från en beläggningsplanering

### <a name="symptoms-of-issue-1"></a>Symptom på problem 1

När du frisläpper en last från sidan **Workbench för lastplanering** eller **Workbench för utgående lastplanering**, visas ett felmeddelande som har följande formulär:

> Ett undantag uppstod när lasten %1 bokfördes. Det gick inte att frisläppa lasten.
> 
> UPPDATERA WHSSHIPMENTTABLE SET...
> 
> Det går inte att redigera en post i Leveranser (WHSShipmentTable). Leverans-ID:...

Här är ett faktiskt exempel som inkluderar exempeldata:

> Ett undantag uppstod när lasten USMF-000033 bokfördes. Det gick inte att frisläppa lasten.
session 5133 (Admin)
>
> UPPDATERA WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? VAR ((RECID=?) OCH (RECVERSION=?))  
> [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Scale Unit @@ försökte uppdatera poster som ägs av skalningsenhet @A.  
> Objektserver Azure:
>
> Det går inte att redigera en post i Leveranser (WHSShipmentTable). Leverans-ID: USMF-000031, USMF-000033. SQL-databasen har genererat ett fel.

### <a name="cause-of-issue-1"></a>Orsak till problem 1

Det här problemet kan uppstå om följande kombination av villkor finns när du installerar distributionslagerhantering i en skalningsenhet:

- Systemet inkluderar en ej frisläppt last där flera rader associeras med olika order, och vissa beläggningsrader associeras inte med en leverans.
- Systemet är inställt för att använda leveranskonsolidering.

I en distribuerad distribution topologidistribution markeras varje beläggning och försändelsepost som ägd av en specifik skalningsenhet eller försändelse. När du frisläpper en inläsning från sidan **Workbench för lastplanering**, ändrar systemet den tilldelade äganderätten. På grund av villkoren i den tidigare listan kanske systemet inte kan lösa äganderätten för data. Därför misslyckas den att frisläppa beläggningen till lagerstället.

### <a name="resolution-of-issue-1"></a>Lösning av problem 1

Dela upp lasten i två mindre laster innan du frisläpper den till lagerstället.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Problem 2: Fel när en cykel bearbetas på en skalningsenhet

### <a name="symptoms-of-issue-2"></a>Symptom på problem 2

När du bearbetar en våg på en vågenhet visas ett felmeddelande som innehåller följande formulär:

> Du kan inte ändra beläggningsrad med RecId = %1, last-ID= %2 eftersom den fortfarande ägs av företagsnavet. Kontrollera att motsvarande utgående last har frisläppts till en skalningsenhet och därmed skapas orderrader för lagerstället.

Här är ett faktiskt exempel som inkluderar exempeldata:

> Informationslogg för jobb kör cykel USMF-000000012 (9223377668365210)  
> Informationslogg för uppgift kör cykel USMF-000000012 (9223377668370462)  
> Du kan inte ändra beläggningsrad med RecId = 68719478242, last-id= USMF-000034 eftersom den fortfarande ägs av företagsnavet. Kontrollera att motsvarande utgående last har frisläppts till en skalningsenhet och därmed skapas orderrader för lagerstället.

### <a name="cause-of-issue-2"></a>Orsak till problem 2

I en distribuerad distribution topologidistribution tilldelas äganderätt av lasten och leveransdata en specifik skalningsenhet eller hubb. Som en del av den cykelbearbetningen förväntas ägarskapet för data tilldelas en skalningsenhet.

När du installerar en skalningsenhet för lagerstyrning kan systemet inte styra dataansvaret om en öppen försändelse är kopplad till en last och en cykel. Därför misslyckas cykelbearbetningen på skalningsenhet.

### <a name="resolution-of-issue-2"></a>Lösning av problem 2

Frisläpp lasten till lagerstället från navet.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Felsöka problem genom att visa äganderätt och destination för en post

I en distribuerad distribution topologidistribution många typer av poster är markeras som ägd av en specifik skalningsenhet eller försändelse. När du har växlat till en distribuerad topologi och/eller ställt in en ny lagerstyrningsenhet, tilldelas ägarskapet till varje relevant post. Denna process kan ibland orsaka fel eller oväntade resultat. Därför kan informationen om en posts äganderätt och överföringsdestination hjälpa dig att felsöka problem som inträffar när du har gjort dessa typer av ändringar.

Följ anvisningarna nedan och visa ägarskap och överföringsdestination för en post.

1. Öppna den relevanta posten.
1. I åtgärdsfönstret, på fliken **Alternativ** i gruppen **Postinfo** markerar du **Visa alla fält**.
1. Sidan som visas visar värden för alla fält som är tillgängliga för den valda posten. Granska följande fält:

    - **SYSSCALEUNITID** – I det här fältet visas postens aktuella ägare.
    - **SYSTARGETSCALEUNITID** – I det här fältet visas skalningsenhets-ID för skalningsenheten som posten ska överföras till när den aktuella ägaren har arbetat med den. Värdet i det här fältet används i batchjobb som hanterar den här typen av process. Även om det här fältet inte är direkt relaterat till äganderätt kan äganderätten ändras när posten överförs. I vissa fall kommer detta fält att vara tomt.
