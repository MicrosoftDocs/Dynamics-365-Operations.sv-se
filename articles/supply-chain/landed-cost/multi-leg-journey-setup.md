---
title: Inställning av resor med flera sträckor
description: I denna artikel beskrivs hur du konfigurerar resor med flera sträckor för modulen Hemtagningskostnad.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: dcb536c03d09d51b247d9060d87db64e2b80383b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905846"
---
# <a name="multi-leg-journey-setup"></a>Inställning av resor med flera sträckor

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar resor med flera sträckor för modulen **Hemtagningskostnad**.

## <a name="legs"></a>Etapper

Sträckor används för att identifiera separata delar av en resa. Varje sträcka byggs genom att man väljer "till" och "från" försändelseportar, och den transportmetod som används för det. Ledtider kan kopplas till varje sträcka. Med ledtider kan en försändelse spåras, och den kan även användas vid beräkning av det uppskattade leveransdatumet för varorna på en färd. När en sträcka på en resa slutförs kan statusen för färd, leveransbehållare och tillhörande inköpsorderrader uppdateras med hjälp av spårningskontrollinställningarna. Sträckor kan användas av en enda resmall, eller så kan de återanvändas av flera resmallar. Containerlastning, tull och lokal transport ställs i allmänhet in som sträckor och en icke-specifik leveransport används för dem.

Om du vill arbeta med sträckor, gå till **Hemtagningskostnad \> Inställning av resa med flera sträckor \> Sträckor**. Där kan du visa, öppna, skapa och ta bort poster för sträckor. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Etapp | Ange ett unikt ID-namn/nummer för resans sträcka. |
| beskrivning | Ange en kort beskrivning av resans sträcka. Denna beskrivning identifierar vanligtvis portarna "till" och "från" eller "från"-portarna, eller steget i företaget. |
| Från hamn | Ange ursprungspunkt för varorna på sträckan. |
| Till hamn | Ange destinationspunkt för varorna på sträckan. |
| Leveransmetod | Ange transportmetod för sträckan. |

## <a name="journey-templates"></a>Resemallar

En resmall definierar ett flerdimensionellt samband mellan två portar som varor reser under en färd. Resans sträckor används för att identifiera hur lång tid det tar för varor som ska levereras från leverantörens ursprungspunkt till den slutliga lagerställedestinationen. När sträckorna på en resmall som är specifik för den, identifierar ledtiderna datumet för varje sträcka och status för färd, behållare och inköpsrader för färden. Med [spårningskontrollcentret](delivery-information-setup.md) kan du konfigurera ledtiderna som associeras med varje del som utgör resmallen. Resmallen används också när de automatiska kostnaderna för en färd konfigureras. När en resa definieras kan kostnaden som associeras med transporten av varorna definieras på sidan Automatisk kostnad.

Om du vill arbeta med resmallar, gå till **Hemtagningskostnad \> Inställning av resa med flera sträckor \> resmallar**. Där kan du visa, öppna, skapa och ta bort poster för resmallar.

Ställ in följande fält i sidhuvudet för varje resmall.

| Fält | beskrivning |
|---|---|
| Resemall | Ange ett unikt ID-namn/nummer för resmallen. Resmallen beskriver vanligtvis ursprunget och destinationens plats för företaget. |
| beskrivning | Ange en beskrivning för resmallen. Beskrivningen anger vanligtvis portarna "till" och "från" samt typen av resor. |

I avsnittet **Rader**, lägg till en rad för varje sträcka på resan och ordna raderna. Använd pilarna **Upp** och **Ned** i verktygsfältet om du vill ändra radernas ordning. Följande register beskriver de fält som är tillgängliga för varje rad.

| Fält | beskrivning |
|---|---|
| Etapp | Välj en sträcka att lägga till resan. |
| beskrivning | Beskrivningen av sträckan. |
| Från hamn | Porten som är ursprungspunkt för varorna på sträckan. Denna port är den "till"-port som används för att bestämma automatiska kostnaderna för en annan port. |
| Till hamn | Den slutliga destinationsporten för varorna på sträckan. |
| Leveranssätt | Leveranssättet som används för sträckan. |
| Resa från hamn | Om den port som angetts för delen används för att bestämma automatiska kostnaderna markerar du denna kryssruta för att identifiera den som porten "resa från". Den här porten visas i färdens sidhuvud. |
| Resa till hamn | Om den port som angetts för delen används för att bestämma automatiska kostnaderna markerar du denna kryssruta för att identifiera den som porten "resa till". Den här porten visas i färdens sidhuvud. |
| Speditör | Välj transportföretaget som används för sträckan. |

## <a name="activities"></a>Aktiviteter

Inställningarna på sidan **Aktiviteter** gör att de typer av aktiviteter som kan ske vid destinationsporten för en sträcka. Användare som arbetar på sidan **Alla leveransbehållare** kan välja bland dessa värden när de uppskattar varaktigheten för varje aktivitet och registrerar den faktiska längden för jämförelse.

Om du vill konfigurera dina aktiviteter går du till **Hemtagningskostnad \> Inställning av resor med flera sträckor \> Aktiviteter**. Där kan du lägga till, ta bort och redigera aktiviteter genom att använda knapparna i åtgärdsfönstret.

Följande register beskriver de fält som är tillgängliga för varje aktivitet i rutnätet.

| Fält | beskrivning |
|---|---|
| Aktivitet | Namnet på aktiviteten. |
| beskrivning | En beskrivning av aktiviteten. |
| Speditör | Leverantörskontot för det fraktföretag som är associerat med aktiviteten. |
