---
title: Hälsokontroll för kringutrustning och för kassa och tjänster
description: Det här ämnet ger en översikt över hälsokontrollåtgärden i kassan (POS).
author: rubendel
manager: AnnBe
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: b818553b7763ad03e2e23b869b364bb21c8afd57
ms.sourcegitcommit: 267864eb0dccd6e26d49d280bd4ad1b770a73a77
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "3515821"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Hälsokontroll för kringutrustning och för kassa och tjänster

[!include [banner](includes/banner.md)]

Det här ämnet beskriver hälsokontrollåtgärden i kassan (POS).

## <a name="overview"></a>Översikt

Butiker kan vara komplexa miljöer där många program och enheter används. När operationer växer kan det bli svårt att se till att operationer alltid fungerar smidigt, på grund av beroenden, t.ex. kringutrustning som kan gå sönder eller oavsiktligt bli frånkopplad under en dag. Felsökning av problem som rör enheter och tjänster kan vara kostsamt för större handlare och lika frustrerande för mindre operationer.

Microsoft Dynamics 365 Commerce-versionerna 10.0.10 och senare innehåller en hälsokontroll som kan bidra till att undvika en del av denna kostnad och frustration. Den här åtgärden ger en metod för att testa enheter direkt från kassan utanför normala operationer. Därför kan det hjälpa återförsäljare att identifiera problem innan de inträffar.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | beskrivning |
|---|---|
| Kringutrustning | Alla enheter som kassaprogrammet använder för att underlätta transaktioner och andra operationer i butiken. Det kan till exempel vara kassalådor, streckkodsskannrar och betalningsterminaler. |
| Service | I det här avsnittet är en tjänst ett hjälpprogram som kassaprogrammet är beroende av för att utföra transaktioner och dagliga operationer. Bland exemplen finns program som bidrar till beräkning av skatt eller leverans. |

## <a name="health-check-operation"></a>Hälsokontrollåtgärd

Hälsokontrollåtgärden är operation 717 på sidan **kassaoperationer** i Commerce-administration. Den kan användas när kassan är i läget icke-lådan. En maskinvarustation måste dock vara aktiv.

Som standard testar hälsokontrollen bara enheter som är konfigurerade i maskinvaruprofilen för den maskinvarustation som för närvarande är aktiv för en kassa. Om ett register använder flera maskinvarustationer under en dag för att utföra hälsokontroller för alla, måste de ansluta till en maskinvarustation åt gången. Det finns ingen hälsokontroll på butiksnivå. Det är dock möjligt att den här typen av kontroll kan göras med utökning av Commerce Server.

### <a name="out-of-box-health-checks"></a>Hälsokontroller utanför lådan

| Typ | Anslutning | Information |
|---|---|---|
| Skrivare | OPOS | Den här kontrollen testar funktioner för grundläggande objekt länkning och inbäddning av kassan (OPOS). Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Radvisning | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Dubbla bildskärmar | Windows | Den här kontrollen säkerställer att operativsystemet identifierar en andra Windows-skärm. | 
| MSR | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Utställare | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> | 
| Skanner | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> | 
| Våg | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| PIN-knappsats | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Betalningsterminal | Betalningar SDK | Den här kontrollen testar grundläggande terminaler för betalningar som tillhandahålls av SDK:n för betalningar. <ul><li>Lås</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Stäng</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Använda hälsokontrollåtgärden i kassan

När hälsokontroll har påbörjats i kassan visas ett fönster till höger med de konfigurerade enheterna och visar status för varje enhet. Om du vill utföra en hälsokontroll för en enskild enhet markerar du enheten och väljer **Testen valda**. Om du vill utföra en hälsokontroll för alla enheter välj **Testa alla**. Funktion **Testa alla** funktion testar alla enheter, en åt gången, och uppdaterar statusen för varje enhet i kolumnen **Status**.

Kolumnen **sista kontroll** visar när hälsokontrollen senast utfördes för varje enhet.

Om hälsokontrollen för en enhet passerar (dvs. om inga fel påträffas) kommer enhetens status att vara **OK**. Om hälsokontrollen misslyckas anger statusen att ett fel uppstod. I det här fallet innehåller fönstret till höger information som är relaterad till felet eller uppmanar användaren att kontakta systemadministratören.

Vissa enheter, t.ex. OPOS-låset, har inga hälsokontrolltest utanför lådan. Om ett test av hälsokontroll inte upptäcks för någon enhet som används, stöds **inte status**.

### <a name="extending-health-checks"></a>Utöka hälsokontroller

Färdiga tester av hälsokontroll har konfigurerats för att ge vissa användarvänliga meddelanden för vanliga fel. Alla scenarier täcks dock inte. Med hjälp av utökningsmöjligheter kan handlare mappa användarvänliga meddelanden till fel som kan vara specifika för miljön.

Anpassade hälsokontroller kan också skapas för att testa enheter som inte stöds i rutan eller för att testa tjänster som kassan är beroende av.

## <a name="related-articles"></a>Relaterade artiklar

[Utlösare och utskrift för Modern POS (MPOS)](https://docs.microsoft.com/en-us/dynamics365/commerce/dev-itpro/pos-trigger-printing)
