---
title: Redovisningsfördelningar
description: Det här ämnet innehåller information om redovisningsfördelningar och beskriver de alternativ som är tillgängliga för att bearbeta dem.
author: sunfzam
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: roschlom
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f81444e0865715925dad2483e8c789221bccb2b
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595324"
---
# <a name="accounting-distributions"></a>Redovisningsfördelningar

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om redovisningsfördelningar och beskriver de alternativ som är tillgängliga för att bearbeta dem. Redovisningsfördelningar används för att fördela penningbelopp för ett källdokument till specifika redovisningskonton. 

Redovisningsfördelningar är en programomfattande funktion som används och utökas med varje källdokument, till exempel inköpsorder, leverantörsfaktura, utgiftsrapport och fritextfaktura. Som standard skapas en redovisningsfördelning för varje källdokumentrad och penningbelopp och den är villkorad för ändring. 

> [!NOTE] 
> Vissa dokument har även stöd för penningbelopp för huvuddokument, till exempel avgifter för order och fakturor. 

De allmänna redovisningsfördelningsfunktionerna innehåller följande alternativ för bearbetning av redovisningsfördelningar:

-   **Fördela belopp** – visa och ändra redovisningsfördelningar för ett enskilt dokumenthuvud eller en enskild rad och eventuella underordnade rader, till exempel moms eller avgifter.
    -   För de översta penningbeloppsfördelningarna (överordnade fördelningar), kan huvudkontot och ekonomiska dimensioner vara redigerbara direkt i den segmenterade postkontrollen i rutnätet. Det slutliga priset är ett typiskt exempel på en sådan överordnad distribution.
    -   Fördelningsbeloppen baseras på termvalutan för dokumentet. Generellt är denna valuta transaktionsvalutan. Redovisnings – och rapporteringsvalutabelopp skapas i underredovisning.
    -   Fördelningarna visar redovisningsdatumet och redovisningshändelsen. Vanligtvis ställs redovisningshändelsen in på **Ingen** tills dokumentet bokförs/journalförs. I det här läget blir redovisningshändelsen **Original**. När fördelningarna har bokförts, kan du inte ändra dem.
    -   Knappen **Dela** kan aktiveras för överordnade fördelningar. **Dela** genererar nya redovisningsfördelningar, och delningen kan baseras på procentsats, belopp eller kvantitet.
    -   Knappen **Fördela lika** kan användas i kombination med **Dela** för att automatiskt fördela beloppet lika mellan alla fördelningar.
    -   Knappen **Återställ** kan aktiveras för överordnade fördelningar när det finns mer än en fördelning. **Återställ** återför alla manuella ändringar av fördelningen genom att ta bort alla befintliga fördelningar och regenerera standardfördelningarna igen.
    -   Alla underordnade fördelningar, som rabatt, avgift och moms, kommer efter den överordnade fördelningen. Du kan visa den överordnade/underordnade relationen via **Referens** &gt; **Överordnad information**.
    -   Huvudkontot och ekonomiska dimensionen kan även vara redigerbara för underordnade.
    -   Den ekonomiska dimensionerna i redovisningsfördelningarna följer ett standardmönster som ett dokument kan utöka.
    -   Avvikelsefördelningar kan genereras i att matchande scenarier, till exempel matchning mellan en leverantörsfaktura och en inköpsorder. Du kan visa matchande relationer mellan redovisningsfördelningen via **Referens** &gt; **Information om dokument**.
    -   Knappen **Korrekt** visas och kan aktiveras för dokument som stöder korrigeringar. **Korrekt** skapar nya fördelningar. Först skapas fördelningar som återför ursprungliga fördelningar. Dessa fördelningar kan inte ändras. Därnäst skapas nya och korrekta redovisningsfördelningar. Dessa fördelningar kan ändras, om de ursprungliga fördelningarna kunde ändras.
    -   Knappen **Projektinformation** aktiveras som ett tillägg när en rad hör till ett projekt. Projektredovisningsfördelningar gör att du kan ändra detaljer som finansieringskälla och radegenskap.
    -   Du kan visa aktuell redovisningsstatus för dokumentet under **Referens**. Statusen är för hela dokumentet och anger om dokumentet är pågående eller slutfört.
-   **Visa fördelningar** – Visa redovisningsfördelningarna för alla rader och penningbelopp i dokumentet. Du kan inte ändra redovisningsfördelningarna från den här vyn.

I version 10.0.13 har en funktion lagts till som validerar registret för redovisningsfördelning för att se till att nya fält ställs in korrekt. Den här funktionen kallas för **Aktivera ytterligare validering av data för dokument med hjälp av källdokumentets redovisningsramverk**. Om du vill använda funktionen måste du aktivera den med hjälp av arbetsytan **funktionshantering**. Aktivera funktionen genom att söka efter funktionsnamnet i fältet **Sök** på sidan **Funktionshantering** och välj sedan **Aktivera nu**.

Mer information finns i [Redovisningsfördelningar och redovisningsjournalposter för leverantörsfakturor](accounting-distributions-subledger-journal-entries-vendor-invoices.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
