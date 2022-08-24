---
title: Omberäkna radens nettobelopp när du importerar försäljningsorder, offerter och returer
description: I den här artikeln beskrivs om och hur systemet räknar om radens nettobelopp när försäljningsorder, offerter och returer importeras. Det förklarar också hur du kan kontrollera beteendet i olika versioner av Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/08/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ce34a6be7bc3d14e23bdd8769aa71dc035b983b3
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220621"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-quotations-and-returns"></a>Omberäkna radens nettobelopp när du importerar försäljningsorder, offerter och returer

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs om och hur systemet räknar om radens nettobelopp när försäljningsorder, offerter och returer importeras. Det förklarar också hur du kan kontrollera beteendet i olika versioner av Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Så här uppdateras nettoradbeloppen vid import

Supply Chain Management version 10.0.23 introducera [felkorrigering 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Detta, ändrade villkoren för att fältet **Nettobelopp** på en rad ska kunna uppdateras eller räknas om när uppdateringar av befintliga försäljningsorder, returer och offerter importeras. I version 10.0.29 kan du ersätta denna felkorrigering genom att aktivera funktionen *Beräkna nettobelopp för rad på import*. Funktionen har liknande effekt, men innehåller en global inställning som gör att du kan återgå till det gamla beteendet om du måste. Det nya beteendet gör att systemet fungerar på ett mer oväntat sätt, men det kan leda till oväntade resultat i specifika scenarier där alla följande villkor uppfylls:

- Data som uppdaterar befintliga poster importeras via entiteten *Försäljningsorderrader V2*, *Försäljningsoffertrader V2* eller *Returorderrader* entity genom att använda Open Data Protocol (OData), inklusive situationer där du använder dubbelriktad skrivning, import/export genom Excel och vissa tredjepartsintegrationer.
- [Policyer för utvärdering av handelsavtal](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper) som är på plats upprättar en policy som begränsar uppdateringar till fältet **Nettobelopp** på försäljningsorderrader, försäljningsoffertrader och/eller returorderrader.
- Importerade data innehåller ändringar i fältet **Nettobelopp** på rader eller ändringar (till exempel enhetspris, kvantitet eller rabatt) som gör att värdet i fältet **nettobelopp** på raderna räknas om för en eller flera befintliga radposter.

I dessa specifika scenarier innebär effekten av policy för handelsavtalsutvärdering att sätta en begränsning vid uppdateringar av fältet **Nettobelopp** på raden. Den här begränsningen kallas för *ändringspolicy*. Därför uppmanas du att bekräfta om du vill göra ändringen när du använder användargränssnittet för att redigera eller räkna om fältet. När du importerar en post, måste systemet dock välja bland dig. Före version 10.0.23 lämnade systemet alltid radens nettobelopp oförändrat, om inte inkommande rads nettobelopp är 0 (noll). I nyare versioner uppdaterar eller räknar systemet alltid om nettobeloppet efter behov, såvida det inte explicit uppmanas att inte göra det. Det nya beteendet är mer logiskt men det kan skapa problem för dig om du redan kör processer eller integrationer som förutsätter att beteendet var äldre. I den här artikeln beskrivs hur du återställer till det gamla beteendet om du måste.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Kontrollera beräkningar av radens nettobelopp i versioner 10.0.29 och senare

Supply Chain Management 10.0.29 innehåller en funktion med namnet *Beräkna radens nettobelopp vid import*. Den här funktionen lägger till ett alternativ som kallas **Beräkna radens nettobelopp** på sidan **Parametrar för kundreskontra**. Med det här alternativet kan du välja mellan nya och gamla beteenden för beräkning av nettobelopp på raden vid import.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Slå på eller av funktionen Beräkna radens nettobelopp vid import

När du uppdaterar till version 10.0.29 aktiveras funktionen *Beräkna radens nettobelopp för import* som standard och det nya alternativet **Beräkna radens nettobelopp** ställs in första gången till *Ja*. Inställningen *Ja* motsvarar det nya standardbeteendet. Det matchar systemets beteende när funktionen är avstängd, förutom när det gäller funktionaliteten hos [parametern CalculateLineAmount](#CalculateLineAmount), som beskrivs längre fram i den här artikeln. Inställningen *Nej* matchar systembeteendet före version 10.0.23 och tillhandahålls huvudsakligen för att stödja äldre integrationsscenarier.

Administratörer kan aktivera eller inaktivera funktionen *Beräkna radens nettobelopp vid import* med [Arbetsytan Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Ange alternativet Beräkna radens nettobelopp

När funktionen *Beräkna radens nettobelopp vid import* är aktiverad kan du ställa in alternativet **Beräkna radens nettobelopp** genom att följa stegen nedan.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. Ställ in fliken **Priser** på snabbflik **Beräkning av nettobelopp för rad via integrering** ange alternativet **Beräkna radens nettobelopp** till något av följande värden:

    - *Ja* – Systemet räknar alltid om och uppdaterar radbelopp vid behov. (Därför ignoreras utvärderingspolicyn för handelsavtalet.)
    - *Nej* – Om det befintliga eller inkommande nettobeloppet för en rad är 0 (noll) omberäknas värdet för den raden baserat på andra värden (till exempel enhetspris, kvantitet och rabatt). Om det befintliga eller inkommande nettobeloppet skiljer sig från 0 (noll) och en ändringspolicy ställs in på fältet **Nettobelopp** på raden, omräknas eller uppdateras fältet inte, även när inkommande ändringar av radens pris, kvantitet och/eller rabatt skulle innebära att radsumman bör beräknas om. Detta beteende matchar beteendet i version 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Hur funktionen Beräkna radens nettobelopp på import påverkar parametern CalculateLineAmount

När funktionen *Calculate line net amount on import* aktiveras påverkas inte värdet för parametern `CalculateLineAmount` för `SalesLine` och `SalesQuotationLine` tabellerna påverkas inte. i stället styrs beteendet globalt av alternativet **Beräkna radens nettobelopp** som beskrivs i det föregående avsnittet. När funktionen är aktiverad får du därför inte ta något beroende av `CalculateLineAmount` värdet.

När funktionen *Beräkna radens nettobelopp vid import* är inaktiverad kommer parametern `CalculateLineAmount` för tabellerna `SalesLine` och `SalesQuotationLine` fungera som i Supply Chain Management versioner 10.0.23 till 10.0.28, enligt beskrivningen i nästa avsnitt.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Kontrollera beräkning av nettobelopp för rad i version 10.0.28 och tidigare

När [felkorrigering 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) introducerades i version 10.0.23, blev det möjligt att välja hur varje relevant dataenhet skulle bete sig när ett radnettobelopp redigerades eller måste räknas om på grund av andra ändringar (som ett uppdaterat artikelpris). Du kan styra detta beteende genom att ställa in den nya `CalculateLineAmount` parametern för varje rad på ett av följande värden i den importerade filen:

- **`CalculateLineAmount` = *1*** – Fältet **Nettobelopp** på raden omräknas och uppdateras alltid, oavsett om en ändringspolicy är inställd för fältet, och oavsett värdet på det inkommande eller befintliga radens nettobelopp.
- **`CalculateLineAmount` = *0*** – Om det befintliga eller inkommande nettobeloppet för en rad är 0 (noll) omberäknas värdet för den raden baserat på andra värden (till exempel enhetspris, kvantitet och rabatt). Om det befintliga eller inkommande nettobeloppet är ett annat än 0 (noll) och en ändringspolicy har ställts in i fältet **Nettobelopp** på raden, räknas inte fältet om eller uppdateras.  

Systembeteendet beror på din version av Supply Chain Management:

- I version 10.0.22 och tidigare fungerar systemet alltid som om `CalculateLineAmount` anges till *0* och det finns inget sätt att få det att bete sig som om `CalculateLineAmount` anges till *1*.
- I versionerna 10.0.23 till 10.0.28 beter sig systemet som om `CalculateLineAmount` anges till *1* för alla rader där det inte uttryckligen är inställt på *0* i importfilen.
