---
title: Visa ekonomiska rapporter
description: Den här ämnet innehåller en beskrivning av hur du visar och utforskar ekonomiska rapporter i Microsoft Dynamics 365 for Finance and Operations. Den innehåller information om de olika alternativ du kan tillämpa på ekonomiska rapporter för att ändra deras utseende och de data de innehåller.
author: kweekley
manager: AnnBe
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bce7c1b5e5780d68bde2130c25099cbaee1fa451
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834669"
---
# <a name="view-financial-reports"></a>Visa ekonomiska rapporter

[!include [banner](../includes/banner.md)]

Den här ämnet innehåller en beskrivning av hur du visar och utforskar ekonomiska rapporter i Microsoft Dynamics 365 for Finance and Operations. Den innehåller information om de olika alternativ du kan tillämpa på ekonomiska rapporter för att ändra deras utseende och de data de innehåller.

<a name="financial-reporting-overview"></a>Översikt över ekonomisk rapportering
----------------------------

## <a name="open-a-financial-report"></a>Öppna en ekonomisk rapport
Välj ett rapportnamn om du vill öppna en rapport. Första gången rapporten öppnas skapas den automatiskt för föregående månad. Om du exempelvis öppnar en rapport för första gången i augusti 2015 genereras rapporten för den 31 juli 2015. När en rapport har öppnats kan du börja utforska den mer ingående genom att titta närmare på specifika delar av data och ändra rapportsalternativ.

## <a name="drill-down-on-a-financial-report"></a>Söka nedåt i en ekonomisk rapport
Ekonomiska rapporter kan innehålla flera detaljnivåer. Den ekonomiska nivån är den första nivån som visas när du öppnar en ekonomisk rapport. Om du vill gå till kontonivån markerar du uppgifterna du vill söka nedåt i. Om du exempelvis vill visa kontodetaljer för försäljning markerar du försäljningsuppgifterna du vill utforska. Från kontonivån kan du söka nedåt för att visa transaktionerna som utgör kontosaldot. Det finns två sätt att visa transaktioner på: rapporttransaktioner och verifikationstransaktioner.

-   **Rapporttransaktioner** – transaktioner visas i en formaterad vy som ingår i den ekonomiska rapporten. Visa transaktioner i den formaterade vyn genom att markera uppgifterna du vill detaljgranska och sedan klicka på **Detaljgranska till rapporttransaktionsnivå**.
-   **Verifikationstransaktioner** – en verifikationstransaktionsförfrågan öppnas där du kan visa transaktioner. Visa transaktioner i verifikationstransaktionsförfrågan genom att markera uppgifterna du vill detaljgranska och sedan klicka på **Öppna verifikationstransaktioner**.

Om informationen är budgetdata, kan du välja att öppna budgetkontoposter. Om du vill stänga någon av nivåerna i rapporten och gå tillbaka till starten, kan du antingen trycka på Esc eller klicka på knappen **Stäng** (**X**) överst till höger.

## <a name="change-report-options"></a>Ändra rapportalternativ
Du kan lägga till attribut och dimensionsfilter samt ändra budgetscenariot i rapporten **Utfall kontra budget**. I åtgärdsfönstret klickar du på **Rapportalternativ** och sedan följer du något eller några av följande steg:

-   Välj attributfilter till en rapport genom att markera **Lägg till ett attributfilter**. Välj attributet, skriv attributvärdet och klicka sedan på **OK**. Om du t.ex. väljer attributet **Kontokategori** anger du **FÖRSÄLJNING** som attributvärde. Ta bort ett attributfilter genom att klicka på **Ta bort**.
-   Välj dimensionsfilter till en rapport genom att markera **Lägg till ett dimensionsfilter**. Välj dimension och skriv sedan dimensions-ID eller välj dimensionen i listan. Ta bort ett dimensionsfilter genom att klicka på **Ta bort**.
-   Ändra scenariot i rapporten **Utfall kontra budget** genom att väja ett nytt scenario och sedan klicka på **OK**. Om det valda scenariot är ett annat räkenskapsår kommer inga resultat att returneras. Till exempel om en rapport genereras för FY2015 och det aktuella scenariot för FY2015 och det nya valda scenariot är FY2016, returneras inga resultat. Om ett nytt scenario för ett annat räkenskapsår behövs, generera en ny version av rapporten för verksamhetsåret relaterat till scenariot.

När du klickar på **OK** sparas alla alternativ du har valt i rapporten. Om du inte vill använda de valda alternativen klickar du på **Avbryt**.

## <a name="update-a-financial-report"></a>Uppdatera en ekonomisk rapport
Du kan uppdatera en ekonomisk rapport så att den visar den senaste informationen för perioden och året som rapporten har skapats för. Om du exempelvis uppdaterar en ekonomisk rapport som skapades för oktober 2015 visar rapporten alla nya transaktioner som har bokförts för oktober 2015. Om du vill uppdatera en ekonomisk rapport kan du klicka på **Uppdatera** i åtgärdsfönstret. En uppdaterad rapporten är bara tillgänglig för den person som uppdaterade den. För att andra personer ska kunna se samma data, måste rapporten publiceras.

## <a name="publish-a-financial-report"></a>Publicera en ekonomisk rapport
När du har uppdaterat en ekonomisk rapport kan du publicera den. Andra personer i organisationen kan sedan visa den. Publicera en rapport genom att klicka på **Publicera** i åtgärdsfönstret.

## <a name="display-a-financial-report-in-a-different-currency"></a>Visa en ekonomisk rapport i en annan valuta
En ekonomisk rapport kan visas i vilken valuta som helst när som helst. Visa en rapport i en annan valuta genom att klicka på **Valuta** i åtgärdsfönstret och sedan välja en valuta. Rapporten översättas till den valutan, och resultaten visas. Valutakoder eller symboler som ingår i rapportdesignen uppdatears för att återspegla den nya valutan. De valutor som visas i listan är rapporteringsvalutor som har konfigurerats i Finance and Operations.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Visa en summerad vy av den ekonomiska rapporten
En ekonomisk rapport kan innehålla detaljrader och sammanfattningsrader. Detaljrader är rader som innehåller huvudkonton eller dimensioner. Sammanfattningsrader innehåller beskrivningar, summor och beräkningar. Visa bara sammanfattningsraderna genom att klicka på **Visa** och sedan på **Endast sammanfattningsrader**. Rapporten komprimeras och visar bara sammanfattningsraderna. Om du vill visa detaljraderna tillsammans med sammanfattningsraderna klickar du på **Visa** och sedan på **Endast sammanfattningsrader** igen.

## <a name="print-a-financial-report"></a>Skriva ut en ekonomisk rapport
Om du skriver ut en ekonomisk rapport skapas en PDF-fil som sedan kan skrivas ut manuellt. För att skapa en utskriftsbar ekonomisk rapport, klicka på **Skriv ut** i åtgärdsfönstret och sedan ställa in utskriftsalternativen genom att följa ett eller flera av stegen nedan:

-   Ta med olika detaljnivåer i den utskrivna rapporten genom att ställa in skjutreglaget på **Ja** eller **Nej**. Om en rapport använder en rapportträd, kan du välja att inkludera alla rapporteringsenheter eller bara den aktuella rapporteringsenheten.
-   Välj en sidstorlek genom att välja en storlek i listan.
-   Välj layout genom att välja layout i listan. Om du vill att rapportinnehållet ska passa bredd du valde, ställer du in skjutreglaget på **Ja**.
-   Ange sidmarginalerna genom att skriva storleken på den övre, nedre, vänstra och högra marginalen i tum.

När du har angett utskriftsalternativen klickar du på **Skriv ut** för att fortsätta och tillfrågas om du vill hämta filen eller spara filen till OneDrive eller SharePoint. Om du inte vill fortsätta klickar du på **Avbryt**. När du fortsätter kommer rapporten börja återgivningen på servern och du uppmanas att hämta rapporten i PDF-format. Du kan nu visa rapporten i ditt PDF-visningsprogram och härifrån välja att skicka rapporten till skrivaren och göra eventuella ytterligare justeringar för utskriftsalternativen.

## <a name="export-a-financial-report"></a>Exportera en ekonomisk rapport
Exportera en ekonomisk rapport genom att klicka på **Exportera** i åtgärdsfönstret. Rapporten exporteras till Microsoft Excel och webbläsaren uppmanar dig att öppna eller spara den exporterade filen. Exportinställningarna som definieras i rapportdesignen används i den exporterade rapporten.    

<a name="additional-resources"></a>Ytterligare resurser
--------

[Ekonomisk rapportering](../../dev-itpro/analytics/financial-reporting-intro.md)




