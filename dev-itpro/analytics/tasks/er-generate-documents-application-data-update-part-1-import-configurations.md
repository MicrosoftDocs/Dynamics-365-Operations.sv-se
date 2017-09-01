--- 
title: "Importera konfigurationer för att skapa dokument med programdatauppdatering för elektronisk rapportering (ER)"
description: "För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren ER Skapa en konfigurationsleverantör och markera den som aktiv."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7085e92b85a5003334c19598de632fcaf08da49e
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="import-configurations-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Importera konfigurationer för att skapa dokument med programdatauppdatering för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren ER Skapa en konfigurationsleverantör och markera den som aktiv.

Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att generera ett elektroniskt dokument. I den här proceduren ska du importera erforderliga ER-konfigurationer som har skapats för exempelföretaget Litware, Inc. och använd dem för att generera elektroniska dokument. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF. Innan du börjar ska du hämta och spara filerna som anges i hjälpavsnittet "Skapa elektroniska dokument och uppdatera programdata med hjälp av verktyget Elektronisk rapportering" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/generate-electronic-documents-update-application-data/). Filerna är Intrastat (model).xml, Intrastat (mapping).xml och Intrastat (format).xml.

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
    * Granska strukturen i den importerade datamodellen. Observera att rotobjektet "For outgoing document" har definierats för att ange dataflödet för att hämta data från programmet och använda dem som datakälla för att generera Intrastat-rapporten. "Transactions (Record list)" används för att representera en lista över Intrastat-transaktioner som ska rapporteras. Eftersom du ska arkivera rapporterade artikelkoder behövs den unika identifieraren för en enskild artikelkod "Commodity rec id (Int64)" i det här dataflödet.   
9. Stäng sidan.
10. Klicka på Byt.
11. Klicka på Läs in från XML-fil.
    * Importera ER-mappningskonfigurationen som anger dataflödet för att hämta data från programmet som sedan ska användas för att generera Intrastat-rapporten. Senare ska du utvidga den här datamappningsdefinitionen till att hämta data från Intrastat-rapporten och använda den för en uppdatering av programdata för att arkivera information om Intrastat-rapporteringen.   
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
    * Granska strukturen i det format som användes för att generera Intrastat-rapporten. Observera att det är till för att generera en XML-fil genom att fylla i data från datamodellen, som baseras på rotobjektet "For outgoing document". Kontrollera att namnet på den genererade filen har definierats i dialogruteformuläret (datakällan "fn" används för det).   
30. Stäng sidan.

