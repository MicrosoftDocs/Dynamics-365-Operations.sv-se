---
title: Importera konfigurationer för att skapa dokument som omfattar programdata
description: För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren ER Skapa en konfigurationsleverantör och markera den som aktiv.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd7a07d041373b266103f313df1bf2810e9c858
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182357"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>Importera konfigurationer för att skapa dokument som omfattar programdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren ER Skapa en konfigurationsleverantör och markera den som aktiv.

Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument. I den här proceduren ska du importera erforderliga ER-konfigurationer som har skapats för exempelföretaget Litware, Inc. och använd dem för att skapa elektroniska dokument. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF. Innan du börjar, se till att ladda ner och spara de filer som anges i hjälpavsnittet "Skapa elektroniska dokument och uppdatera data med ER-verktyget" (skapa-elektroniska-dokument-uppdatera-programdata/). Filerna är Intrastat (model).xml, Intrastat (mapping).xml och Intrastat (format).xml.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.  
    * Stegen i den här proceduren visar hur du använder ER-funktioner för att genomföra en uppdatering av programdata och hur du skapar en Intrastat-rapport. Information om hur du rapporterar arkiveras i programregistren. När processen för Intrastat-rapportering aktiveras från formuläret Intrastat, sker arkivering för närvarande utifrån logiken som programmerats i den befintliga källkoden. I den här proceduren ska du konfigurera en liknande men förenklad logik för programdata genom att bara använda ER-ramverket. Du behöver inte ändra källkoden.   

## <a name="import-er-configurations"></a>Importera ER-konfigurationer
1. Klicka på Reporting configurations.
2. Klicka på Byt.
3. Klicka på Läs in från XML-fil.
    * Importera ER-modellkonfigurationen som innehåller datamodellen som ska användas som datakälla för generering av Intrastat-rapporten. Senare ska du utvidga den här datamodelldefinitionen och använda den för en uppdatering av programdata för att arkivera information om Intrastat-rapporteringen.   
    * Klicka på Bläddra och välj filen Intrastat (model).xml.  
4. Klicka på OK.
5. Välj Intrastat (model) i trädet.
6. Klicka på Designer.
7. Expandera For outgoing document i trädet.
8. Expandera For outgoing document\Transactions i trädet.
    * Granska strukturen i den importerade datamodellen. Observera att rotobjektet "For outgoing document" har definierats för att ange dataflödet för att hämta data från programmet och använda dem som datakälla för att skapa Intrastat-rapporten. "Transactions (Record list)" används för att representera en lista över Intrastat-transaktioner som ska rapporteras. Eftersom du ska arkivera rapporterade artikelkoder behövs den unika identifieraren för en enskild artikelkod "Commodity rec id (Int64)" i det här dataflödet.   
9. Stäng sidan.
10. Klicka på Byt.
11. Klicka på Läs in från XML-fil.
    * Importera ER-mappningskonfigurationen som anger dataflödet för att hämta data från programmet som sedan ska användas för att skapa Intrastat-rapporten. Senare ska du utvidga den här datamappningsdefinitionen till att hämta data från Intrastat-rapporten och använda den för en uppdatering av programdata för att arkivera information om Intrastat-rapporteringen.   
    * Klicka på Bläddra och välj filen Intrastat (mapping).xml.  
12. Klicka på OK.
13. Expandera Intrastat (model) i trädet.
14. Välj Intrastat (model)\Intrastat (mapping) i trädet.
15. Klicka på Designer.
    * Observera att den aktuella mappningen innehåller värdet "To model" i fältet Direction. Detta innebär att den här modellmappningen har utformats för att hämta data från programmet och spara det i datamodellen.  
16. Klicka på Designer.
17. Expandera List i trädet.
18. Expandera Transactions= List i trädet.
    * Granska strukturen av modellmappningen som använder datamodellen som filtreras utifrån rotobjektet ”för utgående dokument”. Observera att den tillagda datakällan "Lista" ger tillgång till den programdata som behövs, som är en lista över poster i Intrastatregistret.  
19. Stäng sidan.
20. Stäng sidan.
21. Klicka på Byt.
22. Klicka på Läs in från XML-fil.
    * Importera ER-formatkonfigurationen som anger layouten för Intrastat-rapporten och hur rapporten ska fyllas med data. Senare ska du utvidga den här formatdefinitionen till att placera data från Intrastat-rapporten i datamodellen och sedan använda dem för att uppdatera programdata för att arkivera informationen i Intrastat-rapporteringen.   
    * Klicka på Bläddra och välj filen Intrastat (format).xml.  
23. Klicka på OK.
24. Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.
25. Klicka på Designer.
26. Klicka på Expandera/Komprimera.
27. Välj File\Declaration i trädet.
28. Klicka på fliken Mappning.
29. Välj File i trädet.
    * Granska strukturen i det format som användes för att skapa Intrastat-rapporten. Observera att det är till för att skapa en XML-fil genom att fylla i data från datamodellen, som baseras på rotobjektet "For outgoing document". Kontrollera att namnet på den skapade filen har definierats i dialogruteformuläret (datakällan "fn" används för det).   
30. Stäng sidan.

