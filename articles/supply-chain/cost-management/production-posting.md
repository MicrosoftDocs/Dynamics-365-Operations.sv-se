---
title: "Produktionsbokföring"
description: "Det här avsnittet innehåller information om andra typer av bokföringar i produktionsprocessen."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f965fd7fc4386665befedd89f33c6d32401c9132
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="production-posting"></a>Produktionsbokföring

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om andra typer av bokföringar i produktionsprocessen.

Produktionsbokföringsaktiviteter följer listor som beskrivs i avsnitten nedan.

## <a name="material-consumption"></a>Materialförbrukning
Material registreras som förbrukade under produktionen, när produktionens plocklistejournal bokförs. Den här processen genererar utleveranstransaktioner som drar av lagerbehållningen. I produktionsparametrarna kan du ange om värdet av råmaterial som pågår (produkter i arbete \[PIA\])) ska bokföras i redovisningen. Värdet av råmaterial som pågår (PIA) bokförs sedan på ett dedikerat plocklistekonto och ett dedikerat plocklistemotkonto.

## <a name="time-consumption"></a>Tidsförbrukning
Den tid som arbetare spenderar på produktionsjobb registreras i flödeskortjournalen eller i jobbkortjournalen. När dessa journaler bokförs bearbetas redovisningsbokföringen till ett dedikerat konto för resurser som pågår (PIA). Denna bokföring representerar värdet av den tid som har använts för produktionsordern. När produktionsordern har registrerats som avslutad kvittas PIA-kontona.

## <a name="reporting-finished-goods-and-error-quantities"></a>Rapportera färdiga varor och felkvantiteter
När en produktionsorder rapporters som färdig, uppdateras kvantiteten av de slutförda varorna som har avslutats i Lagerhantering genom journalen Raporterad som avslutad. Om du använder PIA-redovisning, som kan ställas in i produktionsparametrarna, skapas en redovisningsjournal för att minska PIA-kontona och öka lagret av färdiga varor, med hjälp av standardkostnaden från artikelformuläret. Journalen använder standardkostnaden som definierats för produkten.

## <a name="ending-the-production-order"></a>Avsluta produktionsordern
Innan en produktionsorder avslutas beräknas faktiska kostnader för den kvantitet som producerats. Alla uppskattade kostnader för material, arbete och omkostnader återställs och ersätts med faktiska kostnader. Den sammanlagda kostnaden för den färdiga artikeln debiteras kontot Lagerinleverans och krediteras kontot Lagerutleverans. Om du markerar kryssrutan **Avsluta jobb** när du kör kostnadsberäkningen, ändras produktionsorderns status till **Avslutad**. Denna status förhindrar att ytterligare kostnader oavsiktligt bokförs på en slutförd produktionsorder. Du kan ange att värdet för antal fel som rapporteras under rapportering som färdigt ska fördelas till de goda kvantiteterna som rapporteras som färdiga. Alternativt kan du ange att värdet av felkvantiteter ska bokföras på ett dedikerat kassationkonto.

## <a name="controlling-the-level-of-ledger-posting"></a>Kontrollera nivån för redovisningsbokföring
I **Produktionkontrollparametrar**kan du använda fältet **Redovisningsbokföring** för att ange nivån för redovisningsbokföring för produktionsprocesserna. Följande värden finns:

-   **Artikel och resurs** – Använd redovisningskonton som har ställts in i artikelgrupperna för råmaterial och färdiga produkter. PIA för tidsförbrukning hämtas från resursen eller resursgruppen från flödesoperationer.
-   **Artikel och kategori** – Använd redovisningskonton som har ställts in i artikelgrupperna för råmaterial och färdiga produkter. PIA för tidsförbrukning tas från de kostnadskategorier som associeras med flödesoperationer.
-   **Produktionsgrupper** – Använd redovisningskonton som har ställts in för produktionsgrupper för både material- och tidsförbrukning. Produktiongrupperna är associerade till de frisläppta produkterna och kopieras till produktionsordern när dessa order skapas. Bokföringen för produktionsorder ska sedan följa produktionsgrupper som är kopplade till produktionsordern.

**Obs!** Om standardmetoden för att beräkna kostnaden för den färdiga artikeln användes reflekterar de slutliga transaktionerna denna fakta. Om de faktiska kostnaderna och de kostnader som beräknas med hjälp av standardmetoden skiljer sig, kommer mellanskillnaden att bokföras på det konto som visar vinst eller förlust.




