---
title: Åtgärdsmeddelanden
description: Ett åtgärdsmeddelande är ett systemgenererat förslag om att ändra en befintlig planerad eller bekräftad order.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570266"
---
# <a name="action-messages"></a>Åtgärdsmeddelanden

[!include [banner](../includes/banner.md)]

Ett åtgärdsmeddelande är ett systemgenererat förslag om att ändra en befintlig planerad, godkänd eller bekräftad order.

Åtgärdsmeddelanden genereras av huvudplaneringsberäkningen som svar på ändrade krav. Till exempel kanske transportdatum eller kvantit ändras på en försäljningsorder efter det att du redan har skapat en inköpsorder för att uppfylla efterfrågan för den försäljningsordern. I detta fall genererar huvudplaneringsberäkningen ett eller flera åtgärdsmeddelanden som föreslår att du uppdaterar inköpsordern. Du bestämmer om du vill göra ändringarna som föreslås.

Du kan ställa in hur åtgärdsmeddelanden beräknas för en disponeringsgrupp som du kan koppla till en artikel.

## <a name="select-action-messages"></a>Välja åtgärdsmeddelanden

På sidan **Disponeringsgrupper** kan du välja de åtgärdsmeddelanden som du vill att systemet ska generera och de disponeringsgrupper eller artiklar som meddelandena gäller för. I följande tabell visas det åtgärdsmeddelande som du kan välja.

| Meddelande | Beskrivning |
|---|---|
| Förskott | Efter behov genererar systemet åtgärdsmeddelanden för att flytta order till ett tidigare datum. I fältet **Tidigareläggningsmarginal** kan du ange det högsta antalet dagar som får passera mellan en inleverans och en utleverans utan någon tidigareläggningsåtgärd. |
| Senarelägg | Efter behov genererar systemet åtgärdsmeddelanden för att flytta order till ett senare datum. I fältet **Senareläggningsmarginal** kan du ange det högsta antalet dagar som får passera mellan en inleverans och en utleverans utan någon senareläggningsåtgärd. |
| Skriv av | Systemet genererar åtgärdsmeddelanden när tillverkningsorder, inköpsorder och andra inleveranstransaktioner minskas i syfte att förhindra överskottslagernivåer. |
| Ökning | Systemet genererar åtgärdsmeddelanden när tillverkningsorder, inköpsorder och andra inleveranstransaktioner ska minskas i syfte att förhindra lagerunderskott. |
| Härledda åtgärder | Åtgärdsmeddelanden som skapas för inleveranstransaktioner sprids till eventuella härledda behov, och nödvändiga åtgärdsmeddelanden genereras för de inleveranstransaktioner som uppfyller dessa krav. |

Följande avsnitt erbjuder några detaljerade scenarier.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Öka och minska åtgärder med standardorderkvantiteter för produkt

På sidan **Standardorderinställningar** för en artikel kan du konfigurera en lägsta orderkvantitet, maximal orderkvantitet samt flera värden. Systemet beaktar sedan dessa inställningar när det föreslår åtgärder, detta för att säkerställa att förslagen aldrig orsakar underleverans.

Du kanske till exempel har en artikel med följande inställningar på sidan **Standardorderinställningar**:

- **Minsta orderkvantitet:** *0*
- **Största orderkvantitet:** *90*
- **Flera:** *20*

Om det finns efterfrågan på kvantiteten 60 av den här artikeln, skapar huvudplaneringen en planerad inköpsorder med kvantiteten 60. Om efterfrågan ökas med 30 kommer huvudplaneringen att föreslå en ökning med 40, detta eftersom detta värde omfattar multipeln 20 och aldrig kommer förorsaka underleverans.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Åtgärdsmeddelanden för order som rör säkerhetslager

Åtgärdsmeddelanden för order som levererar säkerhetslager föreslår aldrig att kvantiteten understiger den kvantitet som krävs för säkerhetslager. Om det med andra ord finns en order som tillhandahåller säkerhetslager och kundbehov, och efterfrågan minskas eller annulleras, föreslår huvudplaneringen att den planerade ordern minskas med den minskade efterfrågan. Den kommer emellertid aldrig att föreslå ett värde som är lägre än det säkerhetslager som behövs.

Systemet föreslår inte senareläggningsåtgärder för leverans av säkerhetslager, detta eftersom det antas att säkerhetslager måste levereras vid behov samt på behovsdatum.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Tidigare- och senareläggningsåtgärder relaterade till strukturlistor

Åtgärder som är relaterade till komponenter i strukturlistor måste tillämpas före åtgärderna för deras överordnade artiklar, detta eftersom ytterligare order som är relaterade till strukturlistor på högre nivå kan påverkas. Du måste sedan köra huvudplaneringen igen om du vill beräkna om och föreslå lämpliga åtgärder.

Du har exempelvis följande situation:

- Slutligt gods *FG* av typen *produktion* har en strukturlista som innehåller råmaterial *RM*.
- Dagens datum är 21 januari.
- En befintlig, frisläppt tillverkningsorder för *FG* är planerad till den 25 januari.
- Som ett stöd för den befintliga tillverkningsordern har huvudplaneringen skapat en planerad inköpsorder för den råmaterials-*RM* som krävs. Den här ordern har behovsdatumet 25 januari.
- En ny försäljningsorder för *FG* skapas idag. Den har dagens datum som behovsdatum (21 januari).
- 21 januari är stängt för leverans i *RM*-kalendern, men 22 januari är öppet.

När huvudplaneringen körs skapar den åtgärdsmeddelanden som föreslår att den tidigare tidsplanerade produktionen ska tidigareläggas så att du kan uppfylla dagens order.

- För att uppfylla den nya efterfrågan föreslår den att tillverkningsordern för *FG* tidigareläggs till den 21 januari. (detta föreslås utan att det stängda datumet för *RM* beaktas.)
- Eftersom *RM* fortfarande krävs för tillverkningsordern föreslås också att den planerade inköpsordern tidigareläggs. Den här gången kontrolleras dock *RM*-kalendern. Därför föreslås en flytt av den planerade inköpsordern för *RM* till 22 januari (detta eftersom 21 januari är stängd).

Som du ser kommer den råmaterials-*RM* som krävs nu in för sent för den planerade produktionen av *FG*. Därför måste du först tillämpa åtgärden för tidigareläggning på den planerade inköpsordern för *RM* och sedan köra huvudplaneringen igen. Vid den tidpunkten genereras ett nytt åtgärdsmeddelande i huvudplaneringen som föreslår att tillverkningsordern för *FG* flyttas till den 22 januari.
