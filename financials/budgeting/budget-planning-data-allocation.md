---
title: "Dataallokering för budgetplanering"
description: "Det här avsnittet beskriver de olika allokeringsmetoder som är tillgängliga i Microsoft Dynamics 365 for Operations och hur de kan användas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 753b5c18d9b062ca4f799fd5690b4df3f7b71993
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="budget-planning-data-allocation"></a>Dataallokering för budgetplanering

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver de olika allokeringsmetoder som är tillgängliga i Microsoft Dynamics 365 for Operations och hur de kan användas.  

Du kan fördela data i en budgetplan på många sätt för att exakt att beskriva de projekterade beloppen.

## <a name="allocation-methods"></a>Allokeringsmetoder
Tre allokeringsmetoder (Allokera över perioder, Allokera över dimensioner Använd allokeringsregler för redovisning kan skapa budgetplanrader som baseras på rader i samma budgetplan. Tre andra metoder (Aggregera, Distribuera och Kopiera från budgetplan) kan skapa budgetplanrader i andra budgetplaner. För alla sex allokeringmetoder anger du målscenariot. Målscenariot kan antingen vara samma som källscenariot eller skilja sig från källscenariot. Dessutom kan du ange om nya rader bifogas till budgetplanen eller om de aktuella raderna i budgetplanen ska ersättas.

[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allokera över flera perioder** – En kategori för periodallokering används för att allokera budgetplanraderna från källbudgetplanscenariot över perioder i målscenariot. Källbeloppet tilldelas flera rader i målscenariot baserat på den procentsats och det datum som har anges i kategorin för periodallokering.         

[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allokera över dimensioner** – budgetplanraderna allokeras från källbudgetplaneringsscenariot till en eller flera rader i målscenariot baserat på de procentsatser och ekonomiska dimensioner som har definierats i ett valt budgetallokeringsvillkor.           

![AggregateChart](./media/aggregatechart-300x230.png)
**Aggregera** – budgetplansraderna aggregeras från källbudgetplansscenariot i den associerade (underordnade) budgetplanen till målscenariot i den överordnade budgetplanen. Den här metoden aktiverar budgetbelopp som förbereds på lägre nivå i organisationen att konsolideras på en högre nivå.          

[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Fördela** - Budgetplanraderna fördelas från källbudgetplaneringsscenariot i den överordnade i budgetplanen till målscenariot i de associerade (underordnade) budgetplanerna baserat på organisationsenheternas ekonomiska dimensioner av de associerade planerna. Den här metoden aktiverar budgetbelopp som förbereds på högre nivå i organisationen att fördelas ut för mer lokaliserad granskning.           

[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Använd allokeringsregler för redovisning** – Budgetplanraderna distribueras från källbudgetplaneringsscenariot till målscenariot baserat på vald allokeringsregel för redovisning. 

[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Kopiera från budgetplan** – På samma sätt som med metoden Fördela allokering skapas budgetplanrader i målet baserat på rader i en relaterad budgetplan. Men för den här metoden behöver inte källbudgetplanen vara den överordnade utan kan vara på en högre nivå i budgetplanshierarkin. Denna allokeringsmetod är användbar om konsoliderade belopp ursprungligen budgeteras på en mycket högre nivå och måste överföras till en lägre nivå i organisationen för detaljerad granskning och justering, innan de kan få överordnat godkännande.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Använda allokeringsmetoder i en budgetplan
För att utföra allokeringar på sidan Budgetplan, välj raderna som ska allokeras och klicka sedan på **Allokera budget**

[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Sedan väljer du en allokeringsmetod. De återstående fälten ställs sedan in, baserat på den metod som du har valt. Fälten inkluderar källa och mål för budgetplanen och ett alternativ som låter dig multiplicera källan för en angiven faktor när målbeloppen skapas, om du vill förenkla bulkjustering. Du kan även ange alternativet **Bifoga till plan**. Välj **Nej** om du vill ersätta befintliga budgetplanrader eller välj **Ja** för att behålla de befintliga budgetplanraderna och för att lägga till nya rader för de allokerade beloppen.

## <a name="automating-allocations-during-a-workflow"></a>Automatisera allokering under ett arbetsflöde
En kraftfull funktion låter allokeringar utföras automatiskt som en del av en budgetplaneringsarbetsflöde. Som en budgetplan flyttas genom sin arbetsflödet, kan automatiska uppgifter aktivera en allokering vid en specifik budgetplaneringsfas. 

Om du vill ställa in automatiserad allokering måste du först skapa ett allokeringsschema på sidan **Budgetplaneringskonfiguration**. Allokeringsschemat definierar den allokeringsmetod som ska användas när den automatiserade allokeringen körs och värdena i de olika allokeringsalternativen (se det tidigare avsnittet för beskrivningar). 

Därefter skapar du en fasallokering på sidan **Budgetplaneringskonfiguration**. Fasallokeringen tilldelar ett allokeringsschema till budgetplaneringsarbetsflödet och -fasen. 

Lägg slutligen till en automatisk uppgift för allokeringsfas för budgetplanering på önskad arbetsflödefas. I följande exempel har två fasallokeringar för budgetplanering (anges i rött) infogats i arbetsflödet.

[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)




