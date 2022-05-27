---
title: Modul för hemtagningskostnad
description: Modulen hemtagningskostnad gör det enklare för företagen att strömlinjeforma inkommande leveransoperationer genom att ge användarna fullständig ekonomisk kontroll och kontroll över importerade frakter, från tillverkare till lagerstället.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: aa6f3baf6e6d980ac3c15e2045d1fcdef08ec296
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694639"
---
# <a name="landed-cost-module"></a>Modul för hemtagningskostnad

[!include [banner](../../includes/banner.md)]

Modulen **hemtagningskostnad** gör det enklare för företagen att strömlinjeforma inkommande leveransoperationer genom att ge användarna fullständig ekonomisk kontroll och kontroll över importerade frakter, från tillverkare till lagerstället. För importerade varor kan hemtagningskostnader redovisa 40 procent eller mer av den totala kostnaden för varje importerad artikel. Därför ska företaget tillhandahålla korrekta uppskattningar av hemtagningskostnader.

Företag kan använda hemtagningskostnader för att utföra följande uppgifter:

- Uppskatta hemtagningskostnader vid skapandet av färd.
- Fördela hemtagningskostnader för flera artiklar och inköpsorder eller överföringsorder i en enda färd.
- Stödja överföring av varor mellan fysiska platser genom att beakta hemtagningskostnader.
- Beakta periodiseringar för varor på väg.

Hemtagningskostnader ger korrekta och aktuella kostnadsuppskattningar för omkostnader för hemtagningskostnader. Samtidigt ökar den ekonomiska och logistiska synligheten i den utökade leveranskedjan. Det minskar också administrationen av kostnadsredovisning och kostnadsfel.

## <a name="highlights"></a>Höjdpunkter

### <a name="voyages"></a>Sjötransporter

I hemtagningskostnad är en färd en viss rörelse från en utlastningsplats, via en viss uppsättning destinationer över en angiven period, till en angiven inlastningsplats för lagerstället. Inköpsorder och orderrader kan läggas till i antingen en enda behållare eller flera behållare för en färd, och kostnaderna fördelas korrekt tillbaka till artikelraden. 

### <a name="item-ownership"></a>Ägare av artikel

I Microsoft Dynamics 365 Supply Chain Management levereras varor vanligtvis till lagerställets destination och sedan faktureras. I de flesta internationella handelsavtal tar dock ett företag ansvar för varor från den tid då de lämnar den ursprungliga porten innan de fysiskt har mottagits. Med hemtagningskostnad kan företag fakturera varor innan de fysiskt har mottagits. Detta begrepp kallas för order för varor på väg. Den skapar en ny typ av order för att hantera inleveransen av varor efter att den ursprungliga inköpsordern har fakturerats.

### <a name="costs"></a>Kostnader

När du skapar en färd i hemtagningskostnad kan du automatiskt lägga till kostnader i den. Dessa kostnader anges i hemtagningskostnad och olika kostnadsalternativ och kostnadsbaser är tillgängliga för dem. Varje kostnad kan ställas in för olika nivåer i en färd och fördelas på artikelnivån med hjälp av fördelningsregler som stöder kvantitet, volym, vikt, belopp och definierade volymetriska delare. Dessa uppskattade kostnader ger en korrekt uppskattning av alla kostnader för en färd.

Hemtagningskostnad kör sedan en preliminär bokföring/periodisering av de uppskattade emtagningskostnaderna för att säkerställa att en korrekt beräkning av uppskattade kostnader anges när färden skapas. När dessa automatiska kostnader faktureras återförs de uppskattade kostnaderna och ersätts med faktiska kostnader baserat på kostnadsfakturor.

Faktiska kostnader återförs uppskattade kostnader som bokförs vid tiden för kostnadsfakturering genom att använda clearingkonton som har ställts in för varje typ av kostnad (till exempel avgift, frakt och försäkring). Dessa bokföringar följer det bokföringssätt som associeras med den specifika artikeln. De uppdaterar lagerbokföring automatiskt, oavsett om bokföringstypen är först in, först ut (FIFO), sist in, först ut (LIFO), flytta viktat medelvärde eller flytta medelvärde. Alla bokföringstyper för lagermodeller stöds. För bokföring av rörlig medelvärde och standardkostnad är inköpsprisavvikelsekonton tillgängliga för bokföring av skillnaderna mellan uppskattade kostnader och faktiska kostnader.

### <a name="item-and-order-tracking"></a>Artikel- och orderspårning

När en färd flyttar från den ursprungliga utgående platsen till det slutliga destinationslagret kan användare uppdatera varje steg, eller *sträcka*, av dess resa efter behov. För varje del identifieras en ledtid och en leveransstatus. Bekräftade leveransdatum för förflyttning till nästa del av programmet identifieras också. Tillsammans ger dessa leveransdatum ett uppskattat leveransdatum för varorna till det inkommande lagerstället. Användarna kan ändra dessa leveransdatum. I detta fall uppdateras det uppskattade leveransdatumet för varorna automatiskt, baserat på ledtiderna och den uppskattade leveranstiden för varorna. Synligheten i varor på väg och fartyg är tillgänglig per behållare före inleverans av varorna. Eftersom datumen uppdateras på varje inköpsorderrad har företagen mer kontroll över logistik- och lagerställeplaneringen.

## <a name="landed-cost-concepts"></a>Koncept för hemtagningskostnad

I följande tabell sammanfattas några kärnbegreppen om hemtagningskostnad.

| Begrepp | beskrivning |
|---|---|
| Sjötransport | Vanligtvis är en färd ett fartyg. Beroende på vad du använder och vilka procedurer du har kan det dock vara en leverantör eller en inköpsorder. Det finns inga begränsningar för hur det här begreppet används. |
| Folio | En folio avgörs ofta av tullregleringar. Den består av en leverantörs varor för en enhet eller ett företag per leverans. Varorna i en folio kan läggas i en behållare eller spridas bland flera behållare. |
| Fraktcontainer | Leveransbehållare lagrar inköpsorderrader. De ligger på en nivå under leveransnivån. De används vanligtvis om kostnaderna fördelas per behållare eller om inleveransen görs per behållare. |
| Typ av fraktcontainer | Typer av leveransbehållare kan bestämma priset för en kostnadstyp (till exempel frakt). De ger också användbar försändelseinformation. |
| Kostnadstyp | Kostnadstyper identifierar kostnader som är associerade med import, till exempel avgifter, frakt och försäkring. |
| Automatisk kostnad | Automatiska kostnader fungerar som handelsavtal. En automatisk kostnad kopplas till en viss färdnivå. |
| Lastningsplats | Portar är områden där varor tas emot och förs över från. |
| Fartyg | Ett fartyg är det medium som används för att transportera gods, till exempel ett skepp eller ett flyg. |
| Varor på väg | Beroende på inställningarna sätts varor in i ett lagerställe för varor på väg när en faktura har uppdaterats. |
| Aktivitet | Aktiviteter kan användas för att lagra varje viktigt steg av resan mellan två portar. De kan användas för att uppdatera datum. |
| Resemall | Resemallar är flöden som varor tar mellan två portar. |

En jämförelse av terminologin och funktionerna i modulerna **Hemtagningskostnad** och **Transporthantering** (TMS) moduler, se [Hemtagningskostnad jämfört med transporthantering](landed-cost-vs-tms.md).
