---
title: Felsöka huvudplanering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med huvudplanering.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1492854b7d2da480942800e378be9d2bb60bb1f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645075"
---
# <a name="troubleshoot-master-planning"></a>Felsöka huvudplanering

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med huvudplanering.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>Nedbrytning av strukturlistor fungerar annorlunda för fasta produktionsorder och för uppskattade tillverkningsorder för manuellt skapat arbete.

### <a name="issue-description"></a>Problembeskrivning

När en tillverkningsorder bekräftas bryts artiklarna inte ned när du bryter ned strukturlistan. Men när du skapar en arbetsorder manuellt och sedan uppskattar tillverkningsordern, bryts artiklarna ned.

### <a name="issue-resolution"></a>Problemlösning

Systemet fungerar som förväntat. Nedbrytningen som inträffar när tillverkningsordern bekräftas pekar på den planerade ordern, men den visas inte om den planerade ordern för närvarande är bekräftad i detta fall. Om tillverkningsordern har uppskattats utlöses nedbrytningen från den släppta produktionsordern där det inte finns någon planerad order.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>Värdet för fördröjningen uppdateras inte när jag planerar om en planerad order.

Om du vill uppdatera fördröjningen för planerade order öppnar du dialogrutan **Omplanering** för den planerade ordern. På snabbfliken **Nedbrytning** ser du till att alternativet **Utför explosion efter omplanering** anges till *Ja*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>Vid produktionsplaneringen beaktas inte de säkerhetsmarginaler som ställs in för artikeldisponering för peggad leverans.

### <a name="issue-description"></a>Problembeskrivning

Huvudplaneringen tar hänsyn till säkerhetsmarginalerna. Säkerhetsmarginalerna ignoreras dock när planerade tillverkningsorder planeras.

### <a name="issue-resolution"></a>Problemlösning

Marginaler beaktas endast vid huvudplanering, inte vid manuell tidsplanering. Marginaler är utformade för att fungera som buffert under planeringsfasen, vilket ger en del "marginal" för den faktiska processen.

Du kan få önskat resultat genom att ta bort marginalen. Flödet måste sedan uppdateras så att det innehåller önskad tid (t.ex. kötid). Samma resultat skapas då i både huvudplanering och manuell planering.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>Planerade order skapas trots att det redan finns artiklar i lager- och tillverkningsorder för dem.

Du kanske kan åtgärda det här problemet genom att öka värdet för **Positiva dagar** för relevanta grupper på sidan **Disponeringsgrupp**. Den här ändringen gör att systemet avgör om lagerbehållning kan användas för efterfrågan. Sedan genereras en ny planerad order för de artiklar som finns i lager.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>Huvudplaneringen verkar inte respektera kapacitetsbegränsningarna och tidsplaneringen överstiger den tillgängliga kapaciteten.

### <a name="issue-description"></a>Problembeskrivning

När du använder operationsplanering där det finns ändlig kapacitet och där flödet anger en blandning av behov för både en resursgrupp och enskilda resurser, finns det en liten chans att göra en del av med överordningen på grund av det sätt på vilket algoritmen validerar kapacitetskonflikter. Denna bokning kan ske om du använder hjälpprogram för att köra huvudplanering. Det är mest sannolikt att det uppstår om det finns många jobb med en relativt kortkörning.

### <a name="issue-resolution"></a>Problemlösning

Om det är viktigt att ingen överbokning inträffar för grovplanering kan du göra schemaläggningen till en del av huvudplaneringen genom att aktivera alternativet **Rätt begränsad kapacitet för grovplanering** på sidan **Huvudplaneringsparametrar**. Det här alternativet är inte tillgängligt som standard. Du måste lägga till den manuellt på sidan genom att använda anpassningsfunktioner. När du använder det här alternativet körs tidsplanering långsammare på grund av brist på parallell bearbetning.

## <a name="planned-orders-take-a-long-time-to-update"></a>Planerade order tar lång tid att uppdatera.

### <a name="issue-description"></a>Problembeskrivning

Vid uppdatering av kravkvantitet och/eller leveransdatum på en planerad order tar det vanligtvis minst 30 sekunder per order för att spara uppdateringen.

### <a name="issue-resolution"></a>Problemlösning

Detta är ett känt problem med den inbyggda huvudplaneringsmotorn. Det beror på den underliggande automatiska nedbrytningen genom strukturlistan under redigeringar. Det här problemet åtgärdas i planeringsoptimering, där en planering kan uppdatera och godkänna relevanta order och, när så önskas, utlösa en planeringskörning för att uppdatera planerade order för den underliggande strukturlistan.

Ett sätt att förbättra prestanda med den inbyggda huvudplaneringsmotorn är att göra följande:

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en plan.
1. Expandera snabbfliken **Tidsgräns i dagar**.
1. Ställ in **Nedbrytning** till *Ja* och ange fältet under den här inställningen till 0 (noll).

> [!NOTE]
> Detta begränsar tidsperioden för nedbrytningar som utförs för denna huvudplan till en enda dag.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]