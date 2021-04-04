---
title: Utforma ER-konfigurationer för att tolka inkommande dokument
description: Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7235d75aee3b8fdf39492cfbc1760bf6eae4b82e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562866"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Utforma ER-konfigurationer för att tolka inkommande dokument

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du utformar ER-konfigurationer (elektronisk rapportering) för att tolka ett inkommande elektroniskt dokument. I den här proceduren ska du importera erforderliga ER-konfigurationer som har skapats för exempelföretaget Litware, Inc. och använda dem för att tolka inkommande elektroniska dokument. För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv".

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.

Stegen kan utföras med hjälp av valfri datauppsättning. Innan du börjar ska du hämta och spara de filer som anges i avsnittet ”Tolka inkommande dokument för att uppdatera programdata” ([Tolka inkommande dokument](../parse-incoming-electronic-documents.md)). Filerna är: EFSTA, model.xml, EFSTA, format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.
2. Välj rapporteringskonfigurationer.
    * Följande scenario används för att visa möjligheterna med tolkning av inkommande elektroniska dokument i XML-format: ERP-programmet begär data från webbtjänsten [(som efsta](http://efsta.org/) deklarationstjänst) och tolkar inkommande svar för att uppdatera programdatan. Det mest effektiva sättet att tolka använder ett enkelt ER-format trots att förväntad struktur på inkommande dokument i XML-format är annorlunda.

## <a name="import-and-review-er-configurations"></a>Importera och granska ER-konfigurationer

Importera ER-modellkonfigurationen som innehåller exempeldatamodellen som är utformad för lagring av information om den importerade filen.

1. Välj kurs
2. Välj Läs in från XML-fil.
    * Välj Bläddra och välj filen EFSTA model.xml.
3. Välj OK.
4. Välj "EFSTA-modell" i trädet.
5. Välj Designer.
    * Granska strukturen i den importerade datamodellen. EnumType-uppräkningen har definierats till att känna igen följande typer av tjänstesvar: att få bekräftelse om transaktionens sändning, få information om senaste skickade transaktionen och identifiera svarstyper stöds inte.
6. Expandera "Svar" i trädet.
    * Rotobjektet "Svar" definieras om du vill ange vilka data som måste tas från det tjänstesvar som stöds för att uppdatera programdata på samma sätt.
7. Stäng sidan.
    * Du importerar ER-formatkonfigurationen som anger hur inkommande dokument ska tolkas för att lagra data i ER-datamodell.
8. Välj kurs
9. Välj Läs in från XML-fil.
    * Välj Bläddra och välj filen EFSTA format.xml.
10. Välj OK.
11. Expandera "EFSTA-modell" i trädet.
12. Välj "EFSTA model\EFSTA format" i trädet.
13. Välj Designer.
14. Växla mellan expandera/komprimera.
    * CASE-formatelementet används som roten och innehåller tre kapslade FILE-element, vilket innebär att formatet har utformats för att analysera inkommande filer i olika format.
15. Välj "Responses\Transaction completion\TraC" i trädet.
    * Svaret om den skickade transaktionen startar från rotelementet "TraC".
16. Välj "Responses\Last transaction request\Tra" i trädet.
    * Svaret om den senast skickade transaktionen startar från rotelementet "Era".
17. Välj "Responses\Unexpected response\Text" i trädet.
    * Det tredje FILE-elementet med kapslade TEXT-element har lagts till andra typer av svar som avviker från ovannämnda känna igen.
18. Välj på Mappnings-format för modell.
    * Den här modellmappningen innehåller definitionen av dataflöde för att lagra information om parsade inkommande dokument med datamodellens artiklar.
19. Välj Designer.
20. Expandera format i trädet.
21. Expandera "format\Responses: Case(Responses)" i trädet.
    * Granska strukturen i datamodellen "format". Alla tre svarstyperna erbjuds separat.
22. Välj "format\Responses: Case(Responses)\aType" i trädet.
    * Datakällaartikeln "aType" har lagts för att ange svarstypen och är bunden till modellartikeln "Typ".
23. Välj fliken Valideringar.
24. Välj "Type = format.Responses.aType" i trädet.
    * ER-valideringen har konfigurerats för att informera användaren om situationen när svarsstrukturen inte matchar bekräftelsen om transaktionens sändning eller information om senaste skickade transaktionen (svarsfall som inte stöds).
25. Stäng sidan.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Kör modellmappning för ER-format som konfigurerats för tolkning av inkommande filer

Du kommer att köra den skapade modellmappningen för testning för att se hur det konfigurerade ER-formatet ska tolka inkommande tjänstesvar. Proceduren använder olika XML-filer för att simulera olika typer av tjänstesvar.

1. Öppna filen Response1.xml i en XML-läsare, till exempel en webbläsare. Den här filen innehåller bekräftelseinformation om avslutade transaktionen (rotelementet är "TraC”).
2. Välj kör.
    * Välj Bläddra och välj filen Response1.xml.
3. Välj OK.
    * Granska den genererade utleveransen. Svarstypen har identifierats korrekt och tolkats (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` innebär slutförande av transaktionsärende).
    * Öppna filen Response2.xml i en XML-läsaren. Den här filen innehåller information om senaste inskickade transaktionen (rotelementet är `Tra`).
4. Välj kör.
    * Välj Bläddra och välj filen Response2.xml.
5. Välj OK.
    * Granska den genererade utleveransen. Svarstypen har identifierats korrekt och tolkats (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` innebär systemomstartsärende).
    * Öppna filen Response3.xml i en XML-läsaren. Den här filen börjar från rotobjektet TraZ och strukturen inte är konfigurerad med ER-format.
6. Välj kör.
    * Välj Bläddra och välj filen Response3.xml.
7. Välj OK.
    * Granska den genererade utleveransen. Svarstypen har identifierats korrekt som att den inte stöds (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Ett likadant meddelande har placerats i informationsloggen (enligt inställningen för ER-validering) och de flesta datamodeller har inte fyllts i.
    * Öppna filen Response4.xml i en XML-läsaren. Strukturen för den här filen är nästan samma som den parsade Response1.xml, förutom de kapslade elementen för rotelementet "TraC".
8. Välj kör.
    * Välj Bläddra och välj filen Response4.xml.
9. Välj OK.
    * Granska den genererade utleveransen. Svarstypen har identifierats korrekt som att den inte stöds (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Ett likadant meddelande har placerats i informationsloggen och de flesta datamodeller har inte fyllts i. Detta beteende beror på att den aktuella inställningen för det här ER-formatet förutsätter ett visst antal kapslade element i artikelroten för den importerade filen.
10. Stäng sidan.
11. Välj "Responses\Transaction completion\TraC" i trädet.
12. I parsingordern för kapslade element, fälj "Något".
    * Markera Något i fältet "Parsningsordning för kapslade element" för att låta flera kapslade element för roten XML-objektet.
13. Välj Spara.
14. Välj på Mappnings-format för modell.
15. Välj kör.
    * Välj Bläddra och välj filen Response4.xml.
16. Välj OK.
    * Granska den genererade utleveransen. Svarstypen har nu korrekt identifierats att överensstämma med Response1.xml-fil.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]