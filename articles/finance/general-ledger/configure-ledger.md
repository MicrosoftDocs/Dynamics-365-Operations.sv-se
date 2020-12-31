---
title: Konfigurera redovisningar
description: Det här ämnet innehåller information om hur du konfigurerar redovisningar för varje juridisk person. Det innehåller information om hur du väljer valutor, räkenskapskalendrar, kontoplanen och de kontostrukturer som ska användas för varje juridisk person.
author: kweekley
manager: ''
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 929ab7ae66a217de836ce49373faed76325c4d3a
ms.sourcegitcommit: ac0a676c91e3053ad7f9432d576c9af3ff98a99a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2020
ms.locfileid: "4448225"
---
# <a name="configure-ledgers"></a>Konfigurera redovisningar

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om hur du konfigurerar redovisningar för varje juridisk person. Det innehåller information om hur du väljer valutor, räkenskapskalendrar, kontoplanen och de kontostrukturer som ska användas för varje juridisk person.

## <a name="selecting-the-chart-of-accounts"></a>Välja kontoplanen

För varje juridisk person i Microsoft Dynamics 365 Finance måste information om redovisningen konfigureras. På sidan **Redovisning** kan du välja kontoplanen och de kontostrukturer som ska användas för den valda juridiska personen. Du kan dela kontoplanen och kontostrukturer genom att konfigurera sidan **Redovisning** för varje juridisk person så att den använder samma kontoplan och kontostrukturer. Du kan även dela en del av konfigurationen i varje juridisk person och ha särskilda konfigurationer i varje juridisk person.

Om dina juridiska personer måste ha olika kontoplaner eller olika kontostrukturer kan det vara praktiskt att använda funktionen för att åsidosätta juridiska enheter. Genom att använda samma kontoplan och kontostrukturer för flera juridiska personer och sedan hantera eventuella undantag via en åsidosättningar av juridisk enhet kan du förenkla underhåll över tiden.

Om du vill konfigurera kontoplanen för en juridisk person går du till **Redovisning \> Redovisningsinställning \> Transaktionsregister**. På sidan **Redovisning** väljer du **Kontoplan** och i listan väljer du sedan den kontoplan som du vill använda. Observera att kontoplanen inte kan ändras när du har valt ett värde och bokför transaktioner i den juridiska personen.

Mer information om hur du planerar och konfigurerar kontoplanen och huvudkontona finns i [Planera kontoplanen](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Välja kontostrukturer

Varje juridisk person i Dynamics 365 Finance kan konfigureras att använda en eller flera kontostrukturer. Varje kontostruktur definierar de ekonomiska dimensionerna och kombinationerna av huvudkonton och ekonomiska dimensioner som kommer att tillåtas när transaktionerna bokförs. Du kan använda samma kontostrukturer i mer än en juridisk person.

Observera att om du har flera kontostrukturer kan du bara välja kontostrukturer som inte har överlappande kombinationer av huvudkonton och ekonomiska dimensioner. Till exempel konfigureras en av dina kontostrukturer för att lägga till en affärsenhet för huvudkonton mellan 1000 och 1999. I en annan kontostruktur har du lagt till en ekonomisk avdelningsdimension för huvudkonton som börjar med 1. I det här fallet kan endast en av kontostrukturerna läggas till i samma juridiska person.

Om du vill konfigurera kontostrukturer för din redovisning väljer du snabbfliken **Kontostrukturer** på sidan **Redovisning**, väljer **Lägg till**, väljer en kontostruktur i listan och väljer till sist **Välj**. Det kan ta några minuter innan kontostrukturerna har lagts till och sparats. Observera att den kontostruktur du väljer måste vara aktiv. Annars kommer inte informationen för kontostrukturerna att vara effektiv i de juridiska personer där de är kopplade.

Om du vill ta bort en kontostruktur väljer du **Ta bort** på snabbfliken **Kontostrukturer** på sidan **Redovisning**. Observera att om du tar bort en kontostruktur från redovisningen tar du inte bort några transaktioner som har bokförts med hjälp av den kontostrukturens konfiguration.

Mer information om hur du ställer in dina kontostrukturer finns i [Konfigurera kontostrukturer](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Konfigurera kalendrar för redovisningen

En annan komponent i redovisningen är räkenskapskalendern. Du måste välja en räkenskapskalender för varje juridisk person. Du kan använda samma räkenskapskalender i mer än en juridisk person. När du väljer en räkenskapskalender för redovisningen görs en kopia. Den här kopian kallas för redovisningskalender. I redovisningskalendern kan du välja status för perioderna och modulerna för varje period.

Om du vill öppna och uppdatera kalendern för den valda juridiska personen väljer du **Redovisningskalender** i åtgärdsfönstret på sidan **Redovisning**.

Om du vill välja kalendern väljer du **Räkenskapskalendrar** och väljer sedan kalendern i listan. Om du ändrar räkenskapskalendern efter att transaktionerna har bokförts i den juridiska personen måste du välja **Beräkna om redovisningsperioder**. I den dialogruta som visas kan du sedan uppdatera redovisningssaldon för perioderna i kalendern. Vi rekommenderar att du kör processen **Beräkna om redovisningsperioder** i **Batch**-läge, och att du kör den när icke-kritiska processer inträffar i systemet. Beroende på antalet transaktioner och kombinationer av ekonomiska dimensioner kan denna process ta en stund.

Om ingen räkenskapskalender har valts för en juridisk person visas ett felmeddelande när du försöker att bokföra en transaktion i den juridiska personen.

Mer information finns i [Räkenskapskalendrar, räkenskapsår och perioder](../budgeting/fiscal-calendars-fiscal-years-periods.md)

## <a name="using-a-balancing-financial-dimension"></a>Använda en balanserande ekonomisk dimension

När du har valt kontoplanen och lagt till en eller flera kontostrukturer kan du alternativt välja en enskild ekonomisk dimension som ska användas som balanserande ekonomisk dimension. Dimensionen du väljer måste finnas i alla kontostrukturer. Den måste också balanseras i alla redovisningsposter. Med andra ord måste debet och kredit vara lika för huvudkontot och den balanserande ekonomiska dimensionen. Systemet skapar automatiskt transaktioner som balanserar transaktionerna, baserat på de huvudkonton som har angetts i fälten **Enhetsintern – kredit** och **Enhetsintern – debet** på sidan **Konton för automatiska transaktioner**.

Mer information om balansposter finns i [Balanserade journaler för internredovisning](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Konfigurera valutor för redovisningen

Sidan **Redovisning** används också för att kontrollera och definiera de valutor som ska användas när transaktioner bokförs i redovisningen. Du måste ange redovisningsvalutan, som är den valuta som används i kolumnen **Redovisningsvaluta** i redovisningen på alla verifikationer. I kolumnen **Rapporteringsvaluta** kan du välja en andra valuta om du vill. Om du väljer en rapporteringsvaluta kommer alla transaktioner att registreras i den valutan i kolumnen **Rapporteringsvaluta** i redovisningen på alla verifikationer.

Om transaktioner bokförs i en annan valuta, omvandlar systemet automatiskt transaktionsbeloppet från transaktionsvalutan till redovisningsvalutan och rapporteringsvalutan på verifikationen. På sidan **Redovisning**, i fältet **Redovisningsvalutans valutakurstyp**, väljer du den typ av valutakurs som har konfigurerats för de valutakurser som ska användas för att konvertera transaktionsvalutan till redovisningsvalutan på en verifikation. Om du har valt en rapporteringsvaluta måste du även ställa in fältet **Rapporteringsvalutans valutakurstyp** för att ange den valutakurs som ska användas för att konvertera värden från transaktionsvalutan till rapporteringsvalutan på en verifikation.

Om du använder budgetfunktionen kan du också ställa in fältet **Valutakurs för budget** för att ange den valutakurs som ska användas för att konvertera budgettransaktioner från en valuta till en annan.

Om du använder två valutor, eller om du använder en enskild valuta men transaktioner bokförs i en annan valuta, måste du konfigurera snabbfliken **Konton för valutaomräkning** på sidan **Redovisning**. På den här snabbfliken definierar du de realiserade och orealiserade vinst- och förlustkonton som ska användas som standard när transaktioner bokförs, om inget konto har angetts på sidan **Valutaomvärderingskonton**. (Sidan **Valutaomvärderingskonton** används för att konfigurera olika konton för realiserade och orealiserade vinster och förluster för respektive valuta.)

Realiserade vinster och förluster är vinster och förluster som görs från slutförda transaktioner. De registreras på vinst- och förlusträkningen. Orealiserade vinster och förluster är vinster och förluster som har materialiserats, men transaktionen är inte slutförd. Med andra ord, du har till exempel bokfört en faktura, men fakturan har inte kvittats och betalats ännu. Orealiserade vinster och förluster redovisas i balansräkningen.

Mer information om att använda två valutor finns i [Dubbel valuta](dual-currency.md).
