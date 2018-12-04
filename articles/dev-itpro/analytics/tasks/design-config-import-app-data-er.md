--- 
title: "Utforma ER-konfigurationer för att tolka inkommande dokument"
description: "Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 9e5f826afa141c0851a963b33e40c58513e60a07
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Utforma ER-konfigurationer för att tolka inkommande dokument

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument. I den här proceduren ska du importera erforderliga ER-konfigurationer som har skapats för exempelföretaget Litware, Inc. och använda dem för att tolka inkommande elektroniska dokument. För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv."

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. 

Stegen kan utföras med hjälp av valfri datauppsättning. Innan du börjar, hämta och spara de filer som anges i avsnittet ”Tolka inkommande dokument för att uppdatera programdata” (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents). Filerna är: EFSTA, model.xml, EFSTA, format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.  
2. Klicka på Reporting configurations.
    * Följande scenario används för att visa möjligheterna med tolkning av inkommande elektroniska dokument i XML-format: ERP-programmet (Dynamics 365 for Finance and Operations) begär data från webbtjänsten (t ex http://efsta.org/ räkenskapstjänsten EFSTA) och tolkar inkommande svar för att uppdatera programdatan. Det mest effektiva sättet att tolka använder ett enkelt ER-format trots att förväntad struktur på inkommande dokument i XML-format är annorlunda.   

## <a name="import-and-review-er-configurations"></a>Importera och granska ER-konfigurationer
Importera ER-modellkonfigurationen som innehåller exempeldatamodellen som är utformad för lagring av information om den importerade filen.  
1. Klicka på Byt.
2. Klicka på Läs in från XML-fil.
    * Klicka på Bläddra och välj filen EFSTA model.xml-  
3. Klicka på OK.
4. Välj "EFSTA-modell" i trädet.
5. Klicka på Designer.
    * Granska strukturen i den importerade datamodellen. Observera att enumType-uppräkning har definierats till att känna igen följande typer av tjänstesvar: att få bekräftelse om transaktionens sändning, få information om senaste skickade transaktionen och identifiera svarstyper stöds inte.   
6. Expandera "Svar" i trädet.
    * Observera att rotobjektet "Svar" definieras om du vill ange vilka data som måste tas från det tjänstesvar som stöds för att uppdatera programdata på samma sätt.   
7. Stäng sidan.
    * Du importerar ER-formatkonfigurationen som anger hur inkommande dokument ska tolkas för att lagra data i ER-datamodell.   
8. Klicka på Byt.
9. Klicka på Läs in från XML-fil.
    * Klicka på Bläddra och välj filen EFSTA format.xml.  
10. Klicka på OK.
11. Expandera "EFSTA-modell" i trädet.
12. Välj "EFSTA model\EFSTA format" i trädet.
13. Klicka på Designer.
14. Klicka på Expandera/Komprimera.
    * Observera att CASE-formatelementet används som roten och innehåller tre kapslade FILE-element, vilket innebär att formatet har utformats för att analysera inkommande filer i olika format.  
15. Välj "Responses\Transaction completion\TraC" i trädet.
    * Observera att svaret om den skickade transaktionen startar från rotelementet "TraC".   
16. Välj "Responses\Last transaction request\Tra" i trädet.
    * Observera att svaret om den senast skickade transaktionen startar från rotelementet "Tra".   
17. Välj "Responses\Unexpected response\Text" i trädet.
    * Det tredje FILE-elementet med kapslade TEXT-element har lagts till andra typer av svar som avviker från ovannämnda känna igen.   
18. Klicka på Mappa format till modell.
    * Den här modellmappningen innehåller definitionen av dataflöde för att lagra information om parsade inkommande dokument med datamodellens artiklar.  
19. Klicka på Designer.
20. Expandera format i trädet.
21. Expandera "format\Responses: Case(Responses)" i trädet.
    * Granska strukturen i datamodellen "format". Observera att alla tre svarstyper erbjuds separat.   
22. Välj "format\Responses: Case(Responses)\aType" i trädet.
    * Datakällaartikeln "aType" har lagts för att ange svarstypen och är bunden till modellartikeln "Typ".  
23. Klicka på fliken Valideringar.
24. Välj "Type = format.Responses.aType" i trädet.
    * Observera att ER-valideringen har konfigurerats för att informera användaren om situationen när svarsstrukturen inte matchar bekräftelsen om transaktionens sändning eller information om senaste skickade transaktionen (svarsfall som inte stöds).   
25. Stäng sidan.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Kör modellmappning för ER-format som konfigurerats för tolkning av inkommande filer
Du kommer att köra den skapade modellmappningen för testning för att se hur det konfigurerade ER-formatet ska tolka inkommande tjänstesvar. Proceduren använder olika XML-filer för att simulera olika typer av tjänstesvar.   
1. Öppna filen Response1.xml i en XML-läsare, till exempel en webbläsare. Observera att den här filen innehåller bekräftelseinformation om avslutade transaktionen (rotelementet är "TraC”).   
2. Klicka på Kör.
    * Klicka på Bläddra och välj filen Response1.xml.  
3. Klicka på OK.
    * Granska den skapade utleveransen. Observera att svarstypen har identifieras korrekt och parsad (ERModelEnumDataSourceHandler#EFSTA model#enumType#C betyder transaktion avslutat fall).   
    * Öppna filen Response2.xml i en XML-läsaren. Observera att den här filen innehåller information om senaste inskickade transaktionen (rotelementet är "Tra”).   
4. Klicka på Kör.
    * Klicka på Bläddra och välj filen Response2.xml.  
5. Klicka på OK.
    * Granska den skapade utleveransen. Observera att svarstypen har identifieras korrekt och parsad (ERModelEnumDataSourceHandler#EFSTA model#enumType#C betyder systemomstart-fall).   
    * Öppna filen Response3.xml i en XML-läsaren. Observera att den här filen börjar från rotobjektet TraZ och att det här inte är konfigurerad med ER format.   
6. Klicka på Kör.
    * Klicka på Bläddra och välj filen Response3.xml.  
7. Klicka på OK.
    * Granska den skapade utleveransen. Observera att svarstypen har identifieras korrekt och inte stöds (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). Ett likadant meddelande har placerats i informationsloggen (enligt inställningen för ER-validering) och de flesta datamodeller har inte fyllts i.   
    * Öppna filen Response4.xml i en XML-läsaren. Observera att strukturen för den här filen är nästan samma som den parsade Response1.xml, förutom de kapslade elementen för rotelementet "TraC".   
8. Klicka på Kör.
    * Klicka på Bläddra och välj filen Response4.xml.  
9. Klicka på OK.
    * Granska den skapade utleveransen. Observera att svarstypen har identifieras korrekt och inte stöds (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)). Ett likadant meddelande har placerats i informationsloggen och de flesta datamodeller har inte fyllts i. Detta beror på att den aktuella inställningen för det här ER-formatet förutsätter ett visst antal kapslade element i artikelroten för den importerade filen.   
10. Stäng sidan.
11. Välj "Responses\Transaction completion\TraC" i trädet.
12. I parsingordern för kapslade element, fälj "Något".
    * Markera Något i fältet "Parsningsordning för kapslade element" för att låta flera kapslade element för roten XML-objektet.  
13. Klicka på Spara.
14. Klicka på Mappa format till modell.
15. Klicka på Kör.
    * Klicka på Bläddra och välj filen Response4.xml.  
16. Klicka på OK.
    * Granska den skapade utleveransen. Observera att svarstypen nu korrekt har erkänts att överensstämma med Response1.xml-fil.  


