--- 
title: "Skapa en kanban-regel för strukturlistehändelse"
description: "Denna uppgift fokuserar på inställningen som krävs för att skapa en kanban-regel för händelse för att säkerställa leverans till produktionsstrukturlisterader i ett blandat resurssnål och klassisk produktionsmiljö."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a>Skapa en kanban-regel för strukturlistehändelse

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift fokuserar på inställningen som krävs för att skapa en kanban-regel för händelse för att säkerställa leverans till produktionsstrukturlisterader i ett blandat resurssnål och klassisk produktionsmiljö. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.


## <a name="create-a-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Produktionskontroll > Periodiska uppgifter > Kanban-kvantitetsberäkning > Kanban-regler.
2. Klicka på Ny.
3. Välj "Uttag" i fältet Typ.
    * Uttagstypen används för att skapa överföringskanban.  
4. Välj Händelse i fältet för återanskaffningsstrategi.
    * Händelsestrategin markeras om du vill skapa överföringen av kanban baserat på en händelse. Senare i uppgiftsgudien, ska vi utlösa vi den genom att beräkna en tillverkningsorder.  
5. Ange eller välj ett värde i fältet Första planaktivitet.
    * Ange eller välj ReplenishSpeakerComponents. Den här överföringsaktiviteten har mottagande lagerställe (utleverans) och plats 12, vilket innebär att material ska flyttas till plats 12 på lagerställe 12.  
6. Expandera avsnittet Detaljer.
7. Ange eller välj M0001 värde i fältet Produkt.
8. Expandera avsnittet Händelser.
9. Välj Automatisk i fältet Strukturlistehändelse.
    * Med fältet Strukturlisteradhändelse inställt på Automatisk kommer kanban att skapas för att uppfylla materialbehoven för tillverkningsorderns strukturlisterader.  
10. Stäng sidan.

## <a name="create-and-modify-a-new-production-order"></a>Skapa och ändra en ny tillverkningsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
2. Klicka på Ny produktionsorder.
3. Ange eller välj ett värde i fältet Artikelnummer.
    * Ange eller välj "'L0001". Vi använder artikel L0001, eftersom artikel M0001 ingår i strukturlistan för artikel L0001.  
4. Klicka på Skapa.
5. Klicka på länken på raden för L0001
6. Klicka på Strukturlista.
7. Klicka på länken på den valda raden i listan.
8. Klicka på Redigera.
9. Välj "Peggad leverans" i fältet Radtyp.
    * Peggad leverans väljs för att utlösa leveransskapelse av en kanban.  
10. Välj Nej i fältet Resursförbrukning.
    * Om du avmarkerar kryssrutan för Resursförbrukning kan du ändra lagerstället.  
11. Visa avsnittet Lagerdimensioner.
12. Skriv "12" i fältet Lagerställe.
    * Lagret har är inställd på 12 eftersom det är utleveranslagerstället för uttagsaktiviteten.  
13. Skriv "12" i fältet Plats.
    * Åöatsen är inställd på 12 eftersom det är utleveransplatsen för uttagsaktiviteten.  
14. Stäng sidan.
15. Stäng sidan.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Beräkna tillverkningsordern och visa den skapade kanban
1. Klicka på Uppskattning.
    * Beräkning av tillverkningsordern kommer att utlösa skapandet av associerade kanban för att leverera artikel M0001.  
2. Klicka på OK.
3. Stäng sidan.
4. Stäng sidan.
5. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
6. Klicka på länken på den valda raden i listan.
    * Välj den kanban-regel för händelse som skapades för artikel M0001.  
7. Expandera avsnittet Kanbans.
8. Markera vald rad i listan.
    * Observera de kanban som skapats för att leverera M0001 för den uppskattade tillverkningsordern.  
    * Detta är det sista steget!  


