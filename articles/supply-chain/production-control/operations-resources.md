---
title: Operations-resurser
description: Verksamhetsresurser utför aktiviteter för ett projekt eller en produktionsprocess. De kan vara av olika typer och kan ha olika förmågor.
author: sorenva
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability, WrkCtrResourceGroup, WrkCtrResourceAbilityMap, OpResCapacityPlanningWorkspace, WrkCtrCapResGraph, WrkCtrResourceRequirementPart, WrkCtrCapResGraphDialog, WrkCtrResourceCopy, WrkCtrCapResStatistic
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 205906e8c7495df9a60585d0a79d6cbb0a73a49c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437480"
---
# <a name="operations-resources"></a>Operations-resurser

[!include [banner](../includes/banner.md)]

Verksamhetsresurser utför aktiviteter för ett projekt eller en produktionsprocess. De kan vara av olika typer och kan ha olika förmågor. 

<a name="operations-resources"></a>Operations-resurser
--------------------

Verksamhetsresurser är de datorer, verktygen, arbetarna, lättheterna, fysiska områdena eller leverantörer som utför aktiviteter för ett projekt eller en produktionsprocess. De kan vara av andra typer och kan ha olika förmågor.

-   **Leverantör** – En extern resurs som utför projektaktiviteter eller en produktionsprocess. Ett exempel är en underleverantör. Genom att länka leverantörresurser till ett leverantörskonto, kan du generera inköp för underleverantörer som baseras på strukturlisterader eller produktionsrader.
-   **Personal** Ett projekt eller en produktionsarbetare som genomför en aktivitet, antingen ensam eller som en operator för ett verktyg eller en maskin. Om du använder funktionen Personalresurser kan du länka personal till en arbetare. Planeringsmotorn kan sedan fördela resurserna som baseras på kompetenserna som definieras för motsvarande arbetare.
-   **Maskin** – En maskin eller annan produktionsutrustning som krävs i produktionen.
-   **Verktyg** Ett instrument eller en enhet som normalt används tillsammans med en annan resurs för att utföra en aktivitet i ett projekt eller i produktion.
-   **Plats** – En fysisk plats av en viss storlek som krävs för att utföra en aktivitet. Ett exempel är ett monteringsområde.
-   **Lokal** – En byggnad eller en viss struktur som krävs för att utföra en aktivitet.

## <a name="calendars"></a>Kalendrar
En kalender kan tilldelas en verksamhetsresurs och beskrivs i den resursens kunskapen (i timmar). Verksamhetsresursens arbetstider bestäms av kalendern som används till den resursgrupp som verksamhetsresursen är en del av. Du kan ange ett giltighetsdatum och ett utgångsdatum för den tilldelade kalendern. Du kan sedan tilldela fler än en kalender till en verksamhetsresurs. Du kan dock inte överlappa data för de tilldelade kalendrarna och verksamhetsresursen kan bara tilldelas en kalender i taget. **Obs!** Om det inte finns någon gällande arbetskalender för en resursgrupp, till exempel om senaste tilldelade kalendern eller den enda tilldelade kalendern har förfallit, kan du inte längre komma åt de verksamhetsresurser som har tilldelats resursgruppen för produktionsplaneringen och grovplanering. Du kan också tilldela en kalender till en resursgrupp för att ange arbetstider för både resursgruppen och alla verksamhetsresurser som tilldelas resursgruppen. Resursgruppens kunskap beräknas som summan av kunskaper för varje verksamhetsresurs som tilldelats den resursgruppen. Kalenderns som är tilldelad en resursgrupp kan ändras med tiden.

## <a name="resource-capabilities"></a>Resurskunskaper
En kunskap är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Du kan sedan tilldela en eller fler kunskaper till en verksamhetsresurs. Planeringsmotorn allokerar sedan resurser genom att matcha resurskrav för varje aktivitet mot kunskaper hos de tillgängliga verksamhetsresurserna. kunskap kan tilldelas alla typer av verksamhetsresurser (**Verktyg**, **Leverantör**, **Maskin**, **Personal**, **Plats**, eller **Lokal**). Om du vill tilldela funktioner till verksamhetsresurser för en begränsad tid definierar du ett startdatum och en förfallodag på kunskapen. Mer information finns i [Resurskunskaper](resource-capabilities.md).

## <a name="resource-groups"></a>Resursgrupper
En resurs grupp är en uppsättning verksamhetsresurser som representerar nivån som du vill tidsplanera resurserna med när du använder grovplaneringsmetoden. Därför motsvarar resursgrupper normalt den fysiska organisationen av arbetsgrupper som avgränsas av gula rader i produktionsarbete. Resursgruppen definierar plats, produktionsenhet och lagerställeskontext för verksamhetsresurser som är tilldelade gruppen. När du tilldelar en verksamhetsresurs till en resursgrupp, kan resursen planeras på den plats där resursgruppen finns. Du måste inte tilldela verksamhetsresurserna som du skapar till en resursgrupp. Men en verksamhetsresurs måste tilldelas en resursgrupp, innan den kan planeras till att utföra arbete. En verksamhetsresurs kan tilldelas en resursgrupp under en begränsad tid. Du kan också tilldela en verksamhetsresurs till flera resursgrupper, så att du sedan kan dela resursen mellan platser. Däremot kan giltighetsdatum och förfallodatum inte överlappas. Du kan inte tilldela en verksamhetsresurs till två olika resursgrupper samtidigt. Ändringar i resursgrupptilldelningar gäller endast för nya resurstilldelning. Kapacitetsreservationer för jobb, operationer och projekttimmeprognoser, som redan har status, kommer inte att påverkas. **Obs!** När du tilldelar verksamhetsresurser av typen **Leverantör** till en resursgrupp, måste alla verksamhetsresurser som tilldelats den resursgruppen vara av typen **Leverantör** och länkad till samma leverantörskonto.

## <a name="production-units"></a>Produktionsenheter
En produktionsenhet är en administrativ enhet som är en samling av resursgrupper. En produktionsenhet kan innehålla flera resursgrupper, men en resursgrupp kan bara tilldelas en produktionsenhet. En produktionsenhet avspeglar den fysiska utformningen av produktionsresurser och har inte någon effekt på transaktioner eller hur de bearbetas. Du måste associera en produktionsenhet med en site. Du kan tilldela ett lagerställe för plockning och ett lagerställe för lagring till en produktionsenhet. Du kan använda en produktionsenhet om du vill konsolidera och filtrera produktionsrelaterade data. Till exempel kan en arbetsstyrningsansvarig visa en översikt över utestående arbetsbördan, och den tillgängliga kapaciteten för en viss produktionsenhet. Du kan ändra produktionsenheten som är tilldelad till en resursgrupp. Du kan även ta bort en produktionsenhet. Dessa förändringar av produktionsenheten gäller dock enbart för nya order som skapas efter att huvudplaneringen körs. Om du vill tillämpa ändringen av produktionsenheten på befintliga order, måste du göra det manuellt.

## <a name="resource-scheduling"></a>Resursplanering
Verksamhetsresurser tilldelas till aktiviteter, när ett projekt eller en produktion inplaneras. Två tidsplaneringsmetoder finns: grovplanering och finplanering. När du använder grovplanering, tidsplaneras varje operation- eller projektaktivitet på resursgruppen som innehåller verksamhetsresurser som matchar de resurskrav som angetts för operationen. Om en specifik verksamhetsresurs krävs för operationen och finplanering endast reserverar kapacitet på en viss verksamhetsresurs i gruppen. Finplanering är ett mer detaljerad form av tidsplanering än grovplanering. Den delar upp varje operation i enskilda uppgifter eller jobb. Dessa jobb fördelas sedan till verksamhetsresurserna som ska utföra dem. Tidsplanering reserverar kapacitet för resursgrupperna baserat på operationtiderna som anges i produktionsflödet eller projektaktiviteter. Om du arbetar med begränsad kapacitet, är tidsplanen beroende av resurstillgängligheten för verksamhetsresurserna som krävs för att utföra aktiviteten. För grovplanering är kapaciteten för resursgruppen summan av den tillgängliga kapaciteten för verksamhetsresurserna som ingår i gruppen. Kapacitetsreservationer som redan finns för verksamhetsresurserna beaktas som otillgänglig kapacitet. Om det inte finns tillräcklig kapacitet för produktion, kan produktionsorder senareläggas eller stoppas. På sidan **Resurser** kan du definiera flera egenskaper som styr hur kapacitetsreservationer görs:

-   **Kapacitet** – Ange verksamhetsresursens kapacitet per timme när det gäller kapacitetmåttenheten.
-   **Gruppera kapacitet** – Ange det maximala antalet enheter som verksamhetsresursen kan bearbeta per körning.
-   **Effektivitet i procent** – Ange effektiviteten som du förväntar dig från verksamhetsresursen. Effektivitetsprocentsatsen justerar genomflödet från verksamhetsresursen och påverkar den tid som reserverats för resursen. Produktionstiderna för operationer som använder verksamhetsresursen justeras även efter detta. Här är formeln som används för beräkningen: planeringstid = tid × 100 ÷ effektivitetsprocenten. *Tid*  innehåller både körtid och ställtid.
-   **Grovplaneringsprocent** – Ange högsta procentandelen av kapaciteten för verksamhetsresursen som du vill använda i grovplaneringen. Procentsatsen bör vara lägre än 100 procent vilket medger flexibilitet för kapaciteten under finplanering.
-   **Begränsad kapacitet** – Ange det här alternativet som **Ja** om verksamhetsresursen ska planeras utifrån verklig kapacitet som är tillgänglig och om befintliga kapacitetsreservationer ska inkluderas. Om det här alternativet är **Nej**, antas verksamhetsresursen ha obegränsad kapacitet och resursen kan överbokas.
-   **Begränsad egenskap** – Ange det här alternativet som **Ja** om du vill att verksamhetsresursen ska tidsplaneras baserat på den aktuella kapaciteten med hänsyn till krävda tidsplaneringsegenskaper för arbetstid.
-   **Exklusiv** - Ange det här alternativet som **Ja** om du inte vill att verksamhetsresursen är tillgänglig för andra jobb eller operationer, tills den aktuella produktionen har slutförts. Detta innebär att resursen inte kan användas även om det finns luckor i resursens körtid.
-   **Flaskhalsresurs** Definiera – verksamhetsresursen som en flaskhalsresurs. En sådan resurs planeras med begränsad kapacitet när alternativen **Begränsad kapacitet** och **Schemaläggning för flaskhalsar** på sidan **Huvudplaner** har valts.

För att tidsplanera flera verksamhetsresurser att utföras samtidigt, till exempel en operation i produktionen, måste du ange kraven för de olika resurserna genom att använda primära och sekundära operationer. Du kan då också reservera flera verksamhetsresurser som har annan kapacitet. Verksamhetsresursen som har tidsplanerats för den primära operationen, bestämmer aktivitetens varaktighet.

## <a name="lean-work-cells"></a>Lean-arbetsgrupper
Du kan ange att en resursgrupp är en lean-arbetsgrupp. Resursgruppen sedan kan ingå i ett produktionsflöde. Genom att ange en resurs grupp som en lean-arbetsgrupp, kan du också förhindra att resursgruppen och de tilldelade verksamhetsresurserna allokeras till operationerna i en produktionsorder eller en timprognos för projekt. För varje resursgrupp som fungerar som en lean-arbetsgrupp, måste du ange följande information:

-   **Kalender** - Arbetskalendern för arbetsgruppen som måste ha egenskapen standardarbetsdag.
-   **Ange indatalagerställe och plats** – Standardplatsen som används för att plocka material för en aktivitet.
-   **Utleveranslagerställe och plats** - Standardplatsen där alla utleveranser av arbetsgruppen görs.
-   **Kostnadskategori för körtid** – Den här kategorin måste definieras för arbetsgruppen om direkt arbete spåras i kostnadsredovisningen.

När en arbetsgrupp används som en lean-arbetsgrupp, anges kapaciteten för arbetsgruppen direkt på resursgruppen. Du måste inte tilldela verksamhetsresurserna som du skapar till en resursgrupp. Endast när arbetsgruppen hanteras av en underleverantör, måste en verksamhetsresurs av typen **Leverantör** tilldelas arbetsgruppen. Om du tilldelar en verksamhetsresurs till en resursgrupp som har markerats som en arbetsgrupp, påverkas inte kapaciteten för arbetsgruppen.

## <a name="costing-resources"></a>Kostnadsredovisningsresurser
När du definierar en aktivitet som till exempel en flödesoperation eller en timprognos för projekt, kan du ange behovet av en viss verksamhetsresurs eller resursgrupp. Du kan emellertid också ange behovet av en verksamhetsresurs av en viss typ eller en verksamhetsresurs som har en specifik kapacitet eller kompetens. Av denna anledning görs den verkliga resurstilldelningen inte förrän aktiviteten tidsplaneras och kapaciteten reserveras. Därför kan du på en flödesoperation ange att uppskattningen och strukturlisteberäkningen måste baseras på en viss verksamhetsresurs. Den här verksamhetsresurs kallas för kostnadsredovisningresursen. Du kan också överföra kostnadskategorier och arbetstider från kostnadsredovisningresursen till aktiviteten. När operationen tidsplaneras görs uppskattnings- och strukturlisteberäkningen genom att använda operationsresursen som faktiskt har tidsplanerats.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]