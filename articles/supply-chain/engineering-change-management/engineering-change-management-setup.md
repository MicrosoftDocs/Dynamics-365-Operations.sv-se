---
title: Fastställa gemensamma värden för konstruktionsändringshantering
description: I det här avsnittet beskrivs hur du upprättar vanliga värden som används för parametrar i olika delar av konstruktionsändringshantering.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c2ff21490dc71859d75923dd757e264096d4fcba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565937"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Fastställa gemensamma värden för konstruktionsändringshantering

[!include [banner](../includes/banner.md)]

När du ställer in konstruktionsändringshantering måste du upprätta flera uppsättningar med värden som ska användas för att fylla i nedrullningsbara listor i andra delar av användargränssnittet (UI). Du bör ange dessa värden enligt de produkttyper som du tillverkar och dina specifika affärsbehov.

## <a name="engineering-change-categories"></a>Konstruktionsändringskategorier

Du använder kategorier för teknisk ändring för att organisera dina tekniska ändringsorder, så att de är enklare att hantera och granska. Det kan till exempel vara praktiskt att ställa in ett arbetsflöde där en viss avdelning måste granska de föreslagna ändringarna, beroende på kategorin. Därför innehåller teknikändringsorder ett fält för **kategori**.

För att fastställa samlingen av tekniska förändringskategorier som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> Konstruktionsändringskategorier**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="engineering-change-priorities"></a>Prioriteter för konstruktionsändring

Du använder teknikändringsprioriteringar när du vill ange hur viktigt eller brådskande en teknisk ändringsorder är. De kan hjälpa dig att hålla reda på hur viktigt en teknisk ändringsorder är, så att du enkelt kan identifiera vilka order som ska behandlas först och hur snabbt.

För att fastställa samlingen av tekniska förändringsprioriteter som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> Konstruktionsändringsprioriteter**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="engineering-change-reasons"></a>Konstruktionsändringsorsaker

Teknik förändrings orsaker anger ändringsorderns orsak eller karaktär.

För att fastställa samlingen av tekniska förändringsorsaker som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> tekniska förändringsorsaker**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="material-disposal-codes"></a>Koder för materialavyttrande

Du använder koder för materialavyttrande när du vill kategorisera material som används i färdiga varor, eller komponenter som måste avyttras på ett visst sätt eller kräva en viss behandling innan de kan läggas till på din vanliga papperskorg. När du lägger till en relevant produkt i en teknisk ändringsorder kan du tilldela en kod för avyttrande som en del av ändringsdetaljerna.

För att fastställa samlingen av koder för materialavyttrande som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> koder för materialavyttrande**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="received-customer-approval"></a>Mottog kundgodkännande

När du designar produkter för en viss kund måste design och specifikationer ofta valideras innan produkten kan ställas in som färdig. Fältet **Mottaget kundgodkännande** kan du ange hur långt i kundgodkännandeprocessen som produkten är och/eller om godkännandet har mottagits.

För att fastställa samlingen av värden för mottagna kundgodkännande som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> mottagna kundgodkännande**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Konstruktionsändring – miljö- och säkerhetskoder

Om en standardmiljö- och säkerhetsföreskrifter eller företagsspecifika regler eller förfaranden måste anses vara framställda av en produkt kan du använda miljöhälso- och säkerhetskoden för att definiera dem. I den tekniska ändringsordern kan du ange vilka koder som gäller för tillverkningen av en produkt medan du redigerar informationen för den berörda produkten.

För att fastställa samlingen av hälso- och säkerhetsvärden som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> Konstruktionsändring - miljöhälso- och säkerhetskoder**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

## <a name="engineering-change-severities"></a>Allvarlighetsgrader för konstruktionsändring

Du använder allvarlighetsgrader för teknisk ändring för att ange vilken effekt nivå som gäller för produkterna i en teknisk ändringsorder.

För att fastställa samlingen av allvarlighetsgrader för teknisk ändring som används i ditt företag, gå till **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> Allvarlighetsgrader för teknisk ändring**. Du kan sedan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera värden och för att ordna dem i den ordning de visas i listrutorna.

Du kan upprätta regler som gäller för varje allvarlighetsnivå som du skapar. Mer information om hur du tilldelar dessa regler finns i nästa avsnitt.

## <a name="engineering-change-severity-rule-sets"></a>Regeluppsättningar för allvarlighetsgrad för konstruktionsändring

Du använder teknik för att ändra allvarlighetsregeluppsättningar för att skapa en grupp regler som du kan använda för att automatiskt beräkna hur allvarliga ändringsordern är, baserat på den typ av ändringar som berörs av produkterna. För att använda allvarlighetsreglerna, öppna sidan **Parametrar för konstruktionsändringshantering** ange fältet **Allvarlighetsregel** till *Beräkna* eller *Beräkna automatiskt*.

När systemet utvärderar allvarlighetsgrad, bearbetar det reglerna i den ordning de visas på sidan, uppifrån och ned. Om en regel ska väljas och dess prioritet ska kunna fastställas måste alla regler i regeluppsättningen uppfyllas.

Gå till för att ställa in de allvarlighetsregler som gäller för varje nivå som du har definierat **Konstruktionsändringshantering \> Inställningar \> Konstruktionsändringshantering \> Regeluppsättningarna för allvarlighetsgrad**. Gör sedan något av följande.

- Om du vill skapa en ny regeluppsättning väljer du **ny** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen senare i detta avsnitt.
- Om du vill redigera en befintlig regeluppsättning markerar du den i listvyn, väljer **Redigera** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen senare i detta avsnitt.
- Om du vill ta bort en befintlig regeluppsättning markerar du den i listrutan och väljer sedan **ta bort** i åtgärdsfönstret.
- Om du vill ordna om listan med regeluppsättningar väljer du en regeluppsättning i listfönstret och använder sedan knapparna **Upp** och **Ned** i åtgärdsfönstret för att flytta den.

För varje regeluppsättning anger du följande fält:

- **Allvarlighetsgrad** – Välj den allvarlighetsgrad som du vill fastställa regler för. Du använder sidan **Allvarlighetsgrader för teknisk ändring** när du vill skapa och namnge nivåerna. (För mer information, se föregående avsnitt).

Använd knapparna på snabbfliken **regler** om du vill lägga till eller ta bort en regel för den aktuella allvarlighetsinställningen. Varje regel har ett fält för **regel** och ett fält för **namn**. Reglerna upprättas i systemet och anger vilka typer av ändringar som en produkt kan ha. Namnet anger typen av ändring.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]