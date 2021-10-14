---
title: Finplanering
description: Det här avsnittet innehåller information om Jobbplanering, som är ett mer detaljerat formulär för att schemaläggning än Grovplanering. Du kan använda finplaneringen för att planera individuella jobb eller arbetsorder och för att styra din tillverkningsmiljö.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 698fb31b1a2790b737b30f15b50f0f8ecdd59286
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570259"
---
# <a name="job-scheduling"></a>Finplanering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om Jobbplanering, som är ett mer detaljerat formulär för att schemaläggning än Grovplanering. Du kan använda finplaneringen för att planera individuella jobb eller arbetsorder och för att styra din tillverkningsmiljö.

Du kan använda finplaneringen för att planera individuella jobb eller arbetsorder och för att styra din tillverkningsmiljö. Finplanering delar upp varje operation i enskilda uppgifter eller jobb. Dessa jobb fördelas sedan till verksamhetsresurserna som ska utföra dem. Finplanering låter dig också synkronisera alla jobb som refereras av det valda jobbet. Du kan specificera start- och slutdatum samt start- och sluttid för jobbet och sedan köra planering. Tiden som du anger är kan vara start- eller sluttiden beroende på valet av planeringsriktning. Den här funktionen är användbar när till exempel ett jobb endast kan köras på en maskin åt gången, eller när du vill optimera det jobb som körs för varje resurs.

## <a name="tasks-in-the-job-scheduling-process"></a>Uppgifter i finplaneringsprocessen
Finplaneringsprocessen inkluderar följande uppgifter:

-   Dela upp operationer i jobb.
-   Tidsplanera jobb baserat på datum och tider för resurserna som anges för de relaterade operationerna.
-   Beräkna start- och sluttid för varje jobb. Du kan använda ändlig kapacitet för att säkerställa att det inte finns några överlappande tider.
-   Bestäm vilka resurser i resursgruppen som jobbet ska köras på. Den här uppgiften kräver att en resursgrupp anges för en åtgärd. Finplanering väljer resurser eller resursgrupperar baserat på den kortaste produktionstiden och tar också hänsyn till eventuella tidigare reservationer för resurserna.
-   Bryt ned operationer till jobb, när du kör finplanering. Jobben planeras efter datum och tid i den ordning som anges av produktionsflödet. Inställning av operationen avgör de jobb som ska utföras under planeringsprocessen. Flödesgruppen som är tilldelas operationkontrollerna om jobb genereras. Ett jobb genereras endast om det har en specifik varaktighet. Till exempel genereras ett transporttidsjobb om en transporttid har angivits för de valda operationerna.

## <a name="scheduling-direction"></a>Planeringsriktning
Du kan tidsplanera jobb antingen framåt eller bakåt.

-   **Framåt** – Använd planeringsriktningen Framåt om du vill börja produktionen så tidigt som möjligt. Med den här metoden förflyttas produktionen framåt genom produktionsprocessen. Produktionen är planerad att börja och sluta på så tidigt som möjligt.
-   **Bakåt** – Använd planeringsriktningen Bakåt om du vill börja produktionen så sent som möjligt. Detta kallas även drag-metoden eftersom, den baseras på datumet då produktionen måste vara slutförd. Bakåtplanering räknar bakåt till det senast möjliga datum då produktionen kan inledas utan att missa deadline.

## <a name="finite-capacity"></a>Begränsad kapacitet
Du kan tidsplanera jobb, genom att använda begränsad kapacitet. När du använder begränsad kapacitet, kan planerad kapacitet inte vara större än den kapacitet som är tillgänglig för resursen. Tillgänglig tid definieras som intervallet när resursen är tillgänglig och när det inte finns några andra kapacitetsreservationer. Planering som baseras på begränsad kapacitet säkerställer att det inte finns någon överlappning vid en operations start- och sluttid. Resurskapaciteten som redan reserverats för resursen beaktas och överlappningar mellan start- och sluttider beaktas. Begränsad kapacitet fastställer den kapacitetsmängd som måste vara tillgänglig för en resurs för att uppnå optimal användning av den resursen. Detta beslut balanseras mot en beräkning av den kortast möjliga ledtiden mellan operationer.

## <a name="finite-materials"></a>Begränsat material
Finplanering som baseras på begränsat material säkerställer att det nödvändiga materialet är tillgängligt när operationen inleds. Disponeringreglerna för artiklar definierar dessa gränser. Tidsplaneringen använder behovsnedbrytning för att avgöra när komponentartiklarna är tillgängliga. Om du planerar utan att ange begränsat material, sker planeringen utifrån förutsättningen att alla artiklar är tillgängliga när de behövs.

## <a name="finite-properties"></a>Begränsad egenskap
Vid finplanering med speciella egenskaper måste egenskaperna anges för produktionens flödesoperationer. De här egenskaperna måste uppfyllas för att kapacitet ska reserveras.

## <a name="references"></a>Referenser
Vid finplaneringen planeras all referensproduktion som är associerad med den aktuella produktionen. Om en produktion har en eller flera delproduktioner, ska delproduktionerna planeras samtidigt med huvudproduktionen, eftersom huvudproduktionen inte kan startas förrän de relaterade delproduktionerna har avslutats.

## <a name="schedule-resources"></a>Tidsplanera resurser
Planeringsmotorn undersöker kombinationer av resurser för att identifiera de kombinationer som kan motsvara behoven. Du kan ange urvalskriterier genom att välja ett av följande värden i fältet **Primärt resursval** på sidan **Tidsplanera parametrar**:

-   **Tidslängd** - Planeringsmotorn väljer resursen som har den kortaste produktionstiden. **Obs!** Planering efter varaktighet kan orsaka minskad prestanda när samma resursgrupp innehåller många resurser och sekundära operationer används. Du kan tidsplanera maximalt 32 resurser per operation. Om du överskrider denna kvantitet, visas ett meddelande i informationslogg och finplaneringen hittar inte den bästa alternativa resursen.
-   **Prioritet** - Planeringsmotorn väljer resursen som har högst prioritet, om två eller flera resurser har identiska kvalifikationer och nivåer. Resurser som har det lägsta numeriska värdet i detta fält, har högst prioritet.

När finplaneringen körs planerar systemet de resurser som behövs för produktionen som definieras i resursparametrarna. Du kan kontrollera resursernas kapacitet, genom att använda kalenderinställningarna. Systemet beräknar lasterna för resurserna under planeringsprocessen. **Obs!** För produktioner där grovplaneringsfunktionen används kan du köra finplaneringen efter grovplaneringen. Om du inte använder grovplaneringen går det att köra enbart finplaneringen.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Maximikapaciteter för resurser per jobborder
Resurser tilldelas jobb genom finplanering. Du kan fastställa maximikapaciteter för resurser per jobborder Du kan till exempel ställa in systemet för att schemalägga inte mer än 50 procent av den totala kapaciteten för en produktionsorder. Det här är dig mer kontroll över planeringen av resurser på finplaneringsnivån. Därför kan det hjälpa att förebygga problem om det finns tillräcklig kapacitet för att utföra flera produktioner samtidigt.

## <a name="resource-efficiency"></a>Resurseffektivitet
Vid finplaneringen används även de effektivitetsprocent som angetts för resurserna. Effektivitetsprocent minskar eller ökar den tid som reserverats för resursen. Det innebär att produktionstiden ökar eller minskar. Denna formel används för beräkningen: Planeringstid = Tid × 100 ÷ Effektivitet i procent i denna formel, *Tid* innefattar både körtiden och ställtider.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]