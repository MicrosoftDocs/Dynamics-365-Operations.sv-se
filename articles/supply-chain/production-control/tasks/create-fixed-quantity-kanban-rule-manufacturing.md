---
title: Skapa en kanban-regel för fast kvantitet för tillverkning
description: Den här proceduren fokuserar på inställningarna som krävs för att skapa en fast kanban-regel för tillverkning som utlöser omvandlingsaktiviteter, i en arbetsgrupp, i en resurssnål miljö.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16299427a8a6c74e43d7f0eb3ecb3edf4a8f08f0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576890"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Skapa en kanban-regel för fast kvantitet för tillverkning

[!include [banner](../../includes/banner.md)]

Den här proceduren fokuserar på inställningarna som krävs för att skapa en fast kanban-regel för tillverkning som utlöser omvandlingsaktiviteter, i en arbetsgrupp, i en resurssnål miljö. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.


## <a name="create-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Kanban-regler.
2. Klicka på Ny.
    * Observera att standardtypen för strategin Tillverkning och återanskaffning är Fast. Du behöver inte ändra dessa parametrar.  
3. Ange eller välj ett värde i fältet Första planaktivitet.
    * Detta är den aktivitet som ska utföras för kanban som baseras på den här kanban-regeln.  Välj ”SpeakerTestAndPackaging”.  
4. Expandera avsnittet Detaljer.
5. Ange eller välj ett värde i fältet Produkt.
    * Välj L0050.  
6. Ange eller välj ett värde i fältet Måttenhet.
    * Välj minuter.  
7. Ange ett värde i fältet Produktionstid.
    * Ange 5.  

## <a name="set-quantities"></a>Ställ in kvantiteter
1. Expandera avsnittet Kvantiteter.
2. Ange standardkvantiteten till "10".
    * Detta är kvantiteten som ska överföras för varje kanban.  
3. Markera kryssrutan Produktkvantitetsavvikelse.
    * Med detta kan vald kanban slutföras med en avvikelse från standardkvantiteten.  Ange båda avvikelserna till 2 om du vill tillåta att kanban slutförs med en kvantitet från 8 till 12.  
4. Ange Avvikelse nedan till "2 ".
    * Detta tillåter att den slutförs ned till 10 - 2 = 8  
5. Ange Avvikelse ovan till "2 ".
    * Detta tillåter att den slutförs upp till 10 + 2 = 12  
6. Ange ett nummer i fältet Fast kanban-kvantitet.
    * Detta är antalet kanban som ska vara aktiva. I det här fallet 5 kanbans som bearbetar 10 var.  
7. Ange "2" i fältet Notifieringsgränsminimum.
    * Används för att hålla reda på den minsta mängd fullständiga kanbans som ska finnas på destinationen. Detta används till exempel i översikten över kanban-kvantitet.  
8. Ange "4" i fältet Notifieringsgränsmaximum.
    * Används för att hålla reda på den största mängd fullständiga kanbans som ska finnas på destinationen. Detta används till exempel i översikten över kanban-kvantitet.  
9. Ange "1" i fältet Automatisk planeringskvantitet.
    * När du anger detta till 1 innebär det att varje kanban planeras automatiskt.   Om du anger 3 planeras inte kanbans förrän 3 tomma kanbans är redo för planering. Detta kan användas för att gruppera arbete och undvika för många inställningar.  

## <a name="create-kanbans"></a>Skapa kanbans
1. Expandera avsnittet Kanbans.
2. Klicka på Spara.
    * Kanban-regeln måste sparas innan kanbans kan skapas.  
3. Klicka på Lägg till.
    * Lägg märke till att det inte finns några aktiva kanbans, därför är det föreslagna antalet nya kanban 5. Detta är lika med den fasta kanban-kvantiteten.  
4. Klicka på Skapa.
    * Detta skapar 5 kanbans.  
    * Observera att 5 kanbans, för 10 vardera, skapades för den här kanban-regeln för tillverkning. Detta är det sista steget i den här proceduren.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]