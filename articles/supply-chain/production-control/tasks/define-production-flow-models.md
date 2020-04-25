---
title: Definiera produktionsflödesmodeller
description: Produktionsflödesmodeller beskriver hur kapaciteten i lean manufacturing-arbetsgrupper beräknas och hanteras.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e029790ae09ccf9b2eae399db358c599b78031c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210650"
---
# <a name="define-production-flow-models"></a>Definiera produktionsflödesmodeller

[!include [banner](../../includes/banner.md)]

Produktionsflödesmodeller beskriver hur kapaciteten i lean manufacturing-arbetsgrupper beräknas och hanteras. Därför är definitionen av en produktionsflödesmodell en förutsättning för definitionen av arbetsgrupper. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="define-a-production-flow-model"></a>Definiera en produktionsflödesmodell. 
1. Gå till Produktionskontroll > Ställ in > Lean-produktionsflöde > Produktionsflödesmodeller.
2. Klicka på Ny.
3. Ange ett id för produktionsflödesmodellen i fältet Produktionsflödesmodell.
4. Välj ett alternativ i fältet Modelltyp.
    * Det finns två modelltyper: Genomflöde och Timmar. För genomflödetypen kommer kapaciteten för arbetsgrupper som använder den här produktionsflödesmodell uttryckas och beräknas i produktkvantiteter. För typen Timmar kommer kapaciteten för arbetsgrupper som använder den här produktionsflödesmodell uttryckas och beräknas i timmar. Observera att egenskapen inte kan ändras för en befintlig produktionsflödesmodell. När en arbetsgrupp har kapacitetsreservationer går det inte att ändra produktionsflödesmodelltypen.  
5. Ange antal dagar i EPE-cykel.
    * Intervallet beskriver perioden då varje del som framställs i ett produktionsflöde eller en arbetsgrupp ska produceras minst en gång. Ju kortare EPE-cykeln, desto flexiblare blir produktionsprocessen. Om EPE-cykeln = 0 kan alla behov produceras under samma dag. EPE-cykeln används för att kunna tidsplanera effektiva processjobb. När du planerar ett jobb i en arbetsgrupp med EPE-cykeln = 5, söker planeringsprocessen efter kapacitet i arbetsgruppen på förfallodatumet minus EPE-cykeln (fem dagar före förfallodatumet) för att säkerställa att produkten kan produceras i cykeln. Lagerproduktionstiden för en produkt är vanligtvis lika med eller längre än EPE-cykeln i den relaterade produktionsprocessen.  
6. Markera ett alternativ i fältet Planeringsperiodtyp.
    * När en arbetsgrupp har kapacitetsreservationer går det inte att ändra planeringsperiodstypen. Du kan bara välja produktionsflödesmodeller med samma periodtyp för en arbetsgrupp.  
7. Ange ett värde i fältet Planeringstidsgräns.
    * Planläggningstidsgränsen beskriver antal dagar där kapacitetsreservationer kan göras för de relaterade arbetsgrupperna. Ange antalet dagar i Planeringstidsgräns.   Kanban-processjobb som ligger utanför denna period planläggs inte med automatisk planering. Planläggningstidsgränsen är normalt två gånger den genomsnittliga lagerledtiden för produkterna som produceras i ett produktionsflöde eller en arbetsgrupp. EPE-cykeln ska inte vara mer halva planläggningstidsgränsen.     
8. Markera ett alternativ i fältet Reaktion på kapacitetsbrist.
    * Alternativen omfattar: senarelägga - senarelägga det fullständiga behovet av planläggningshändelsen på nästa tillgängliga produktionsdag med tillgängligt genomflöde. Avbryt - Avsluta automatisk planläggning för planläggningshändelsen och lämna relaterade jobb oplanerade.   Lägga till begärd dag - Planera de begärda jobben för den begärda perioden. Detta överbelastar cellen för den aktuella dagen och kräver att planeraren gör en granskning och manuell åtgärd.   Fördela till tillgängliga perioder - fördela olika jobb i planläggningshändelsen till alla aktuella produktionsorderdagar med start från den första tillgängliga dagen. Den minsta distributionskvantiteten är Kanban-jobbkvantiteten. Fördelningen tilldelas den minsta planeringskvantiteten (kanbankvantitet) för varje dag med tillräckligt tillgängligt genomflöde.  

