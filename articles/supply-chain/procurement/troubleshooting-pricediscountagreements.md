---
title: Felsöka priser, rabatter, avtal och avdrag
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med priser, rabatter, avtal och avdrag.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 5d17f2ec594901404fcd251e463f293258af051c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237165"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Felsöka priser, rabatter, avtal och avdrag

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med priser, rabatter, avtal och avdrag.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>Jag kan inte länka ett inköpsavtal till en inköpsorderrad efter att inköpsordern har skapats.

Ett inköpsavtal måste vara kopplat till en inköpsorder när inköpsordern skapas. Annars kan inte inköpsorderrader kopplas till inköpsavtalsrader.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Vilken kontroll utlöser meddelandet "uppdatera priser och rabatter som angetts manuellt eller i det externa dokumentet"?

När du ändrar leveransdatumet kan du få ett meddelande om att "uppdatera priser och rabatter som angetts manuellt eller i ett externt dokument". Det här meddelandet visas om leveransdatumet ändras, kan ett annat handels- eller försäljningsavtal utlösas och orsaka prisändringar. En ändring av leveransdatumet kan också påverka lagerplaner och annan information.

Meddelandet utlöses när något av datumen eller några andra parametrar ändras. Syftet med meddelandet är att säkerställa att du är medveten om de prisändringar som kan uppstå på grund av dessa ändringar.

Meddelandet är TAE-dialog (handelsavtalets utvärdering). En fullständig beskrivning finns i [policyer för utvärdering av handelsavtal](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>En inleverans för inköpsorder inkluderar inte alla avgifter.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. På sidan **Anskaffnings- och källparametrar** på fliken **Leverans** se till att alternativet **Skapa ändringar i produktinleverans** anges till *Ja*.
1. Skapa en inköpsorder som inkluderar avgifter.
1. Bekräfta inköpsordern.
1. Få en inköpsorder.
1. Granska den totala inleveransen och jämför den med den förväntade totala summan.
1. Lägg märke till att inte alla avgifter tas med i inleveransen för inköpsordern.

### <a name="issue-resolution"></a>Problemlösning

Lösningen beror på hur tilläggen har ställts in. Information om hur du ställer in tillägg för att uppfylla dina krav finns i följande blogginlägg: [Bokför tillägg vid tiden för produktinleveransen](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>Priser och rabatter för handelsavtal tillämpas inte på försäljnings- eller inköpsorderrader som importeras via datahantering.

### <a name="issue-description"></a>Problembeskrivning

Handelsavtal som tillämpas på försäljnings- eller inköpsorderrader tillämpas inte på rader som importeras via datahantering. Samma handelsavtal tillämpas emellertid på försäljnings- eller inköpsorderrader som skapas manuellt.

### <a name="reason-for-the-issue"></a>Orsak till problemet

Om inköpsorderrader som importeras via datahantering redan inkluderar prisinformation kommer handelsavtalet inte att utvärderas igen för dessa rader. Om t.ex. **Radrabatt i procent** eller om något av pris- och rabattvärdena är inställda för en rad, kommer inte handelsavtalen att letas upp för den raden.

### <a name="issue-workaround"></a>Problemlösning

Det här beteendet förväntas och används på liknande sätt för både försäljningsorder och inköpsorder.

Importera inköpsorderraderna utan att ange någon prisinformation. Handelsavtalen kommer sedan att tillämpas och inköpsorderraderna uppdateras baserat på de definierade handelsavtalen.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>En leverantörsrabatt ackumuleras inte utifrån fakturor.

### <a name="issue-description"></a>Problembeskrivning

Om fakturor som bokförs har olika förfallodatum, återspeglas dessa fakturor inte i leverantörsrabatter som genereras från dem.

### <a name="issue-resolution"></a>Problemlösning

Efter design beaktas inte förfallodatumet när leverantörsrabatten beräknas. Överväg att anpassa systemet så att förfallodatumet och relationen till fakturan blir mer uppenbara när det gäller den faktiska leverantörsrabatten.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Enhetspris på inköpsorder beräknas inte utifrån enhetskonverteringen.

### <a name="issue-description"></a>Problembeskrivning

När en enhet ändras på en inköpsorder räknas inte handelsavtalets priser om enligt enhetskonverteringens definitioner.

### <a name="issue-resolution"></a>Problemlösning

Priser hämtas alltid från handelsavtal (eller andra prisinställningar i systemet, t.ex. försäljningsavtal eller artikelpriser) och ställs in för en enhet.

Om enheten ändras på en orderrad letar systemet efter ett pris för den nya enheten och tillämpar det priset. Om det inte finns något pris för enheten tillämpar inte systemet priset. Enhetskonverteringen kan inte användas för att räkna om priset till en annan enhet. Teoretiskt sett får priset för en ruta på tio inte vara lika med tio gånger priset för en ruta.

### <a name="issue-workaround"></a>Problemlösning

Ett sätt att undvika det här problemet är att se till att det finns handelsavtal för enheterna som du förväntar dig kommer att använda på orderrader för artikeln.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Valutakonverteringsproblem uppstår i handelsavtal.

Handelsavtalspriser räknas inte om enligt valutan när valutan skiljer sig åt på en inköpsorder.

Med funktionen *allmän valuta* kan du definiera priser och rabatter i bara en valuta. Du kan sedan konvertera till andra valutor efter behov. När konverteringen är klar kan funktionen dessutom automatiskt tillämpa smart avrundning.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>När jag öppnar sidan för inköpsavtal i ett radvisningsläge kan jag inte anpassa sidan genom att lägga till fältet prisenhet i översikten för raden.

Vissa delade fält i avtalsramverket kan inte inkluderas i anpassningar. Den här begränsningen beror på den datamodell som implementeras. Därför kan du inte personanpassa fältet **Prisenhet**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>Den maximala gränsen från ett inköpsavtal är inte effektiv på en inköpsrekvisition.

### <a name="issue-description"></a>Problembeskrivning

När en inköpsrekvisition är kopplad till ett inköpsavtal gäller inte den maximala gränsen från inköpsavtalet på inköpsrekvisitionen. Standard prisinformationen anges korrekt, men mer än den högsta gränsen från inköpsavtalet kan beställas i inköpsrekvisitionen.

### <a name="issue-resolution"></a>Problemlösning

Detta är ett förväntat beteende. Eftersom rekvisitioner inte alltid godkänns ska en kvantitet eller ett belopp inte reserveras i inköpsavtalet. Därför kommer du inte att uppfylla den högsta gränsen från inköpsavtalet.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>Handelsavtal kan skapas från avvisade anbudsförfrågan. Därför hindrar systemet inte handelsavtalsjournaler från att skapas om raden i anbudsförfrågan inte har accepterats.

Du kan skapa handelsavtal för alla svar på en anbudsförfrågan, oavsett om de har accepterats eller avvisats. För mer information, se [översikt över begära offert (anbudsförfrågan)](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]