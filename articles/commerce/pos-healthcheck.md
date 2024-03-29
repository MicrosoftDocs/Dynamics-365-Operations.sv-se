---
title: Hälsokontroll för kringutrustning och tjänster för kassa
description: Denna artikel ger en översikt över hälsokontrollåtgärden i kassan (POS).
author: BrianShook
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 44fd4b6246d3d7947527416c2b8b447bd64f179f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863331"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Hälsokontroll för kringutrustning och tjänster för kassa

[!include [banner](includes/banner.md)]

Denna artikel beskriver hälsokontrollåtgärden i kassan (POS).

## <a name="overview"></a>Översikt

Butiker kan vara komplexa miljöer där många program och enheter används. När åtgärder växer kan det bli svårt att se till att åtgärder alltid fungerar smidigt, på grund av beroenden, t.ex. kringutrustning som kan gå sönder eller oavsiktligt bli frånkopplad under en dag. Felsökning av problem som rör enheter och tjänster kan vara kostsamt för större handlare och lika frustrerande för mindre åtgärder.

Microsoft Dynamics 365 Commerce-versionerna 10.0.10 och senare innehåller en hälsokontroll som kan bidra till att undvika en del av denna kostnad och frustration. Den här åtgärden ger en metod för att testa enheter direkt från POS utanför normala åtgärder. Därför kan det hjälpa återförsäljare att identifiera problem innan de inträffar.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | beskrivning |
|---|---|
| Kringutrustning | Alla enheter som kassaprogrammet använder för att underlätta transaktioner och andra åtgärder i butiken. Det kan till exempel vara kassalådor, streckkodsskannrar och betalningsterminaler. |
| Service | I denna artikel är en tjänst ett hjälpprogram som kassaprogrammet är beroende av för att utföra transaktioner och dagliga åtgärder. Bland exemplen finns program som bidrar till beräkning av skatt eller leverans. |

## <a name="health-check-operation"></a>Hälsokontrollåtgärd

Hälsokontrollåtgärden är åtgärd 717 på sidan **kassaåtgärder** i Commerce headquarters. Den kan användas när POS är i läget icke-lådan. En maskinvarustation måste dock vara aktiv.

Som standard testar hälsokontrollen bara enheter som är konfigurerade i maskinvaruprofilen för den maskinvarustation som för närvarande är aktiv för en kassa. Om ett register använder flera maskinvarustationer under en dag för att utföra hälsokontroller för alla, måste de ansluta till en maskinvarustation åt gången. Det finns ingen hälsokontroll på butiksnivå. Det är dock möjligt att den här typen av kontroll kan göras med utökning av Commerce Server.

### <a name="out-of-box-health-checks"></a>Hälsokontroller utanför lådan

| Typ | Anslutning | Information |
|---|---|---|
| Skrivare | OPOS | Den här kontrollen testar funktioner för grundläggande objekt länkning och inbäddning av POS (OPOS). Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Radvisning | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Dubbla bildskärmar | Windows | Den här kontrollen säkerställer att operativsystemet identifierar en andra Windows-skärm. | 
| MSR | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Utställare | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> | 
| Skanner | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> | 
| Våg | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| PIN-knappsats | OPOS | Den här kontrollen testar grundläggande OPOS-funktioner. Nedan följer några exempel:<ul><li>Öppna: **Öppna** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Stäng: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Stäng**</li></ul> |
| Betalningsterminal | Betalningar SDK | Den här kontrollen testar grundläggande terminaler för betalningar som tillhandahålls av SDK:n för betalningar. <ul><li>Lås</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Stäng</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Använda hälsokontrollåtgärden i POS

När hälsokontroll har påbörjats i POS visas ett fönster till höger med de konfigurerade enheterna och visar status för varje enhet. Om du vill utföra en hälsokontroll för en enskild enhet markerar du enheten och väljer **Testen valda**. Om du vill utföra en hälsokontroll för alla enheter välj **Testa alla**. Funktion **Testa alla** funktion testar alla enheter, en åt gången, och uppdaterar statusen för varje enhet i kolumnen **Status**.

Kolumnen **sista kontroll** visar när hälsokontrollen senast utfördes för varje enhet.

Om hälsokontrollen för en enhet passerar (dvs. om inga fel påträffas) kommer enhetens status att vara **OK**. Om hälsokontrollen misslyckas anger statusen att ett fel uppstod. I det här fallet innehåller fönstret till höger information som är relaterad till felet eller uppmanar användaren att kontakta systemadministratören.

Vissa enheter, t.ex. OPOS-låset, har inga hälsokontrolltest utanför lådan. Om ett test av hälsokontroll inte upptäcks för någon enhet som används, stöds **inte status**.

### <a name="extending-health-checks"></a>Utöka hälsokontroller

Färdiga tester av hälsokontroll har konfigurerats för att ge vissa användarvänliga meddelanden för vanliga fel. Alla scenarier täcks dock inte. Med hjälp av utökningsmöjligheter kan handlare mappa användarvänliga meddelanden till fel som kan vara specifika för miljön.

Anpassade hälsokontroller kan också skapas för att testa enheter som inte stöds i rutan eller för att testa tjänster som POS är beroende av.

## <a name="related-articles"></a>Relaterade artiklar

[Utlösare och utskrift för Modern POS (MPOS)](dev-itpro/pos-trigger-printing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]