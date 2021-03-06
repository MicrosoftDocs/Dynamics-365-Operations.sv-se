---
title: Säkerhetsmarginaler
description: I det här avsnittet beskrivs hur säkerhetsmarginaler kan användas med tillägget planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management .
author: ChristianRytt
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9dc305f46dad6b372721805669529bbc9ac554e8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908303"
---
# <a name="safety-margins"></a>Säkerhetsmarginaler

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur säkerhetsmarginaler kan användas med tillägget planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management .

## <a name="safety-margins-overview"></a>Säkerhetsmarginaler, översikt

Syftet med säkerhetsmarginaler är att aktivera en inställning som ger en viss buffertlängd utöver normal produktionstid. Om material till exempel måste vara uppackat eller inspekterat efter att det har inträffat från leverantören, kan du inte bara lägga till den extra tiden i inköpsproduktionstiden, eftersom den här metoden ger leverantören den extra buffertstorleken. I det här exemplet kan du använda kvittomarginalen för att se till att leverantören levereras tidigare. Den här metoden ger en buffertlängd så att varorna kan hanteras internt.

Det finns tre typer av säkerhetsmarginaler:

- **Beställningsmarginal** – bufferttid för att skicka leveransordern
- **Kvittomarginal** – bufferttid för hantering av inkommande leveranser
- **Ärendemarginal** – buffertens tid för hantering av försändelser

Följande bild visar hur dessa säkerhetsmarginaler gäller över tid.

![Säkerhetsmarginaler](media/safety-margins-1.png)

Alla marginaler anges i dagar. Standardvärde *0* (noll), indikerar att ingen marginal tillämpas. Om du ställer in flera marginaler läggs de till den totala tiden från leveransens *orderdatum* till efterfrågans *behovsdatum* . Till exempel har en inställning ingen produktionstid och alla tre marginaltyperna är inställda på en dag. I det här fallet kommer det att finnas tre dagar mellan leveransorder datumet och behovsdatumet, så om orderdatumet är den 1 juli blir behovsdatumet den 4 juli.

### <a name="receipt-margin"></a>Inleveransmarginal

Kvittomarginalen är antagligen den mest utnyttjade av de tre säkerhetsmarginalerna. Den används på *leveransdatumet* och bakåt från *behovsdatum* . Med andra ord bör produkterna tas emot det angivna antalet dagar för den mottagande marginalen innan de krävs.

På bilden nedan beskrivs kvittomarginalen.

![Inleveransmarginal](media/safety-margins-2.png)

Kvittomarginalen används vanligtvis som buffert för att säkerställa tid för lagerregistrering eller andra tidskrävande processer som inte har registrerats som en del av den allmänna produktionstiden i systemet. För inköp är en fördel att *leveransdatum* för inköpsordern flyttas framåt i enlighet med detta. Om du ökar produktionstiden istället för att använda en säkerhetsmarginal, kommer leverantören fortfarande att bli ombedd att leverera den sista minuten.

Observera att kvittomarginalen inte ändrar *leveransens behovsdatum* . Därför är kvittomarginalen inte direkt synlig när behovsdatum för efterfrågan och tillgången jämförs (t.ex. på sidan **nettobehov**). Till exempel, om inleveransmarginalen är inställd på fyra dagar och en inköpsorderrad planeras för mottagande den femtonde i månaden, beräknar huvudplaneringen det justerade mottagningsdatumet som den nittonde i månaden.

Observera att en inleveransmarginal inte används när lagerbehållning används som leverans. All lagerbehållning antas vara tillgänglig omedelbart, oberoende av när den faktiskt togs emot.

### <a name="reorder-margin"></a>Beställningsmarginal

> [!NOTE]
> **Kommer snart:** den här funktionen stöds inte ännu för planeringsoptimering. Alla värden som anges för **Ändra ordning på marginal som lagts till i artikelledtiden** kommer att behandlas som *0* (noll) tills den stöds.

På bilden nedan beskrivs beställningsmarginalen.

![Beställningsmarginal](media/safety-margins-3.png)

Beställningsmarginalen läggs till före artikelns produktionstid för alla planerade order vid huvudplaneringen. Därför gör det det enklare att placera en leveransorder. Den här marginalen används vanligtvis som buffert för att säkerställa tiden för godkännandeprocesser eller andra interna processer som krävs när leveransorder skapas. Beställningsmarginalen placeras mellan leverans *orderdatum* och *startdatum*.

### <a name="issue-margin"></a>Utleveransmarginal

> [!NOTE]
> **Kommer snart:** den här funktionen stöds inte ännu för planeringsoptimering. Alla värden som anges för **Utleveransmarginal som dragits av från behovsdatum** kommer att behandlas som *0* (noll).

På bilden nedan beskrivs utleveransmarginal.

![Utleveransmarginal](media/safety-margins-4.png)

Utleveransmarginalen dras från behovsdatumet vid behov vid huvudplaneringen. Det säkerställer att du har tid att reagera på och leverera inkommande efterfrågeorder. Den här marginalen används vanligtvis som buffert för att säkerställa tid för leverans och relaterade avgående lagerprocesser.

Observera att när en utleveransmarginal används matchar inte relaterade leverans- och efterfrågebehovsdatum. De skiljer sig i stället från utleveransmarginal, eftersom utleveransmarginal läggs till mellan leveransens *behovsdatum* och efterfrågans *behovsdatum* .

## <a name="set-up-safety-margins"></a>Ställ in säkerhetsmarginaler

### <a name="turn-on-safety-margins-in-feature-management"></a>Aktivera säkerhetsmarginaler i funktionshantering

Innan du kan använda den här funktionen med Planeringsoptimering måste den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** _huvudplanering_
- **Funktionsnamn:** _marginaler för planeringsoptimering_

### <a name="define-safety-margins"></a>Definiera säkerhetsmarginaler

Säkerhetsmarginalerna har en flexibel inställning. De kan ställas in både på *disponeringsgruppen* och i *huvudplanen* . Det är viktigt att du förstår att marginalerna läggs till ovanpå varandra. En kvittomarginal på två dagar i disponeringsgruppen och tre dagar i huvudplanen kommer att skapa en giltig kvittomarginal på fem dagar.

Möjligheten att ställa in marginalen på huvudplanen kan vara användbar när du vill simulera längre produktionstider eller osäkerhet för ett specifikt plan, men utan att påverka den dagliga planeringen.

#### <a name="coverage-group-safety-margins"></a>Disponeringsgrupper med säkerhetsmarginal

Följ de här stegen om du vill tillämpa en säkerhetsmarginal på en disponeringsgrupp.

1. Gå till **huvudplanering \> inställningar \> disponeringsgrupper**.
1. Välj önskad disponeringsgrupp i listrutan.
1. På snabbfliken **Övrig** i avsnittet **säkerhetsmarginaler på dagar** använd följande fält för att ange krävda säkerhetsmarginaler (i dagar):

    - Inleveransmarginal som lagts till för behovsdatum
    - Utleveransmarginal som dragits av från behovsdatum
    - Ändra ordning på marginal som lagts till i artikelledtiden

#### <a name="master-plan-safety-margins"></a>Huvudplaner med säkerhetsmarginaler

Följ de här stegen om du vill tillämpa en säkerhetsmarginal på en huvudplan.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj önskad disponeringsgrupp i huvudplaner.
1. På snabbfliken **säkerhetsmarginaler på dagar** använd följande fält för att ange krävda säkerhetsmarginaler (i dagar):

    - Inleveransmarginal som lagts till för behovsdatum
    - Utleveransmarginal som dragits av från behovsdatum
    - Ändra ordning på marginal som lagts till i artikelledtiden

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Definiera om beräkningar ska baseras på kalenderdagar eller arbetsdagar

Du kan ställa in alla säkerhetsmarginaler så att de beräknas utifrån antingen kalenderdagar eller arbetsdagar.

1. Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**.
1. På fliken **Allmänt** i avsnittet **Säkerhetsmarginaler i dagar** ange alternativet **Arbetsdagar** till *Ja* om du vill beräkna marginaler baserat på arbetsdagar. Ställ in alternativet på *Nej* om du vill beräkna marginaler baserat på kalenderdagar.

En kalender är till exempel öppen från måndag till fredag och stängs från lördag till söndag. Om det finns en kvittomarginal på en dag, ger ett behovsdatum på en måndag ett leveransdatum på föregående fredag eftersom lördag och söndag inte är arbetsdagar.

Vilken kalender som används för att bestämma arbetsdagar beror på inställningarna och leveranstypen. Den kan styras av gruppens kalendrar, lagerstället och leverantören.

> [!NOTE]
> Om *lagerstället* inte ingår i disponeringsdimension (d.v.s. planering endast baseras på *plats*), används inte lagerkalendern.

Systemet kan hantera en inställning där en eller flera kalendrar definieras. Följande underavsnitt beskriver de möjliga kombinationer som kan användas för att styra resultatet.

#### <a name="calendar-that-is-used-for-the-duration"></a>Kalender som används för varaktigheten

I de definierade kalendrarna kontrolleras den faktiska totala produktions tiden i kalenderdagar, från leveransorderdatumet till behovsdatumet. Följande kalenderprioritering används:

- **Produktionstid** – endast disponeringsgruppens kalender beaktas.
- **Kvittomarginal** – disponeringsgruppens kalender används om den har definierats. Annars används kalendern för distributionslager.
- **Utleveransmarginal** – disponeringsgruppens kalender används om den har definierats. Annars används kalendern för distributionslager.
- **Ordermarginal** – endast disponeringsgruppens kalender beaktas.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Kalender som används för slutdatum

Följande regler används för att avgöra om ett visst datum ska användas för planeringsmotorn för en viss datatyp:

- **Datum för inköpsinleverans** – leverantörskalendern används, om den har definierats. Annars kan disponeringsgruppens kalender används om den har definierats. Om ingen av dessa kalendrar definieras används lagerställekalendern.
- **Överföringsinleveransdatum** – disponeringsgruppens kalender används om den har definierats. Annars används kalendern för distributionslager.
- **Produktionsinleveransdatum** – disponeringsgruppens kalender används om den har definierats. Annars används kalendern för distributionslager.
- **Efterfrågan utleverans öppen dag** – lagerställekalendern kalender används om den har definierats. Annars kan disponeringsgruppens kalender används.
- **Order öppen dag** – en kombination (skärningspunkt) på gruppen för disponeringsgrupper och leverantörskalendern används. Båda kalendrarna måste vara öppna för att du ska kunna använda datumet. Om bara en av kalendrarna är definierade används den kalendern ensam.

#### <a name="calendar-setup-overview-matrix"></a>Matris för översikt över kalenderinställningar

Följande bild visar en matris som sammanfattar vilka kalendrar som gäller när säkerhetsmarginaler beräknas. (Markera bilden om du vill öppna en högupplöst version av den.) Följande förkortningar och färger används för att ange var varje typ av kalender anges:

- **Disponeringsgrupp (CG):** grön
- **Lagerställe (WH):** gul
- **Leverantör (V):** blå

[![Matris för översikt över kalenderinställningar](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Beräkna fördröjningar

Alla tre typerna av säkerhetsmarginal tas med när systemet fastställer om en order är försenad.

En artikel har t.ex. produktionstid på en dag och en kvittomarginal på tre dagar. En försäljningsorder för denna artikel ställs in efter behov i dag. I det här fallet beräknas förseningen som *produktionstiden* + *kvittomarginal* = fyra dagar. Om dagens datum är den 14 augusti skapas därför en leverans på 18 augusti för fyra dagars fördröjning. Illustrationen nedan visar ett exempel.

![Exempel på fördröjningsberäkning](media/safety-margins-delays.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Kom igång med planeringsoptimering](get-started.md)

[Bristanalys för planeringsoptimering](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]