---
title: Ändra modeller och mappningar för att skapa dokument som omfattar programdata
description: Det här ämnet beskriver hur du utformar rapporteringskonfigurationer för att skapa ett elektroniskt dokument och uppdatera programdata. (Del 2 - Generera dokument).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78b1771d0e01702162192ff20c03facbba4f3513
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751616"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Ändra modeller och mappningar för att skapa dokument som omfattar programdata

[!include [banner](../../includes/banner.md)]

Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)". 

Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument och uppdatera programdata. I den här proceduren ska du ändra ER-konfigurationerna för att börja använda dem för att skapa elektroniska dokument och uppdatera programdata. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF.


## <a name="modify-data-model"></a>Ändra datamodell
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Välj Intrastat (model) i trädet.
    * Du ska utöka hur du använder datamodellen. Förutom att använda den som datakälla för att skapa Intrastat-rapporten, används datamodellen för att samla in information om Intrastat-rapportering. Informationen används sedan för att uppdatera programdata.   
3. Klicka på Designer.
4. Klicka på Nytt om du vill öppna dialogrutan.
5. Ange "Modellrot" i fältet "Ny nod som ett fält...".
6. Skriv "For application data update" i namnfältet.
    * För uppdatering av programdata  
7. Klicka på Lägg till.
8. Välj For application data update i trädet.
    * Det nya rotobjektet läggs till för att ange dataflödet för att flytta data från Intrastat-rapporten (används som datakälla) till programregistren (uppdateringsmålet). Observera att olika rotobjekt måste användas för att hämta data som bokförs till det utgående dokumentet och för att hämta data från det dokument som används för att uppdatera programdata.   
9. Klicka på Nytt om du vill öppna dialogrutan.
10. Skriv "Archive header" i namnfältet.
    * Arkivrubrik  
11. Välj "Postlista" i fältet Artikeltyp.
12. Klicka på Lägg till.
    * Eftersom du vill skapa en post för alla Intrastat-rapporter som skapas måste du skapa ett nytt objekt för detta.  
13. Klicka på Nytt om du vill öppna dialogrutan.
14. Ange "File name" i namnfältet.
    * Filnamn  
15. Välj "Sträng" i fältet Artikeltyp.
16. Klicka på Lägg till.
17. Klicka på Nytt om du vill öppna dialogrutan.
18. Skriv "Number of lines" i namnfältet.
    * Antal rader  
19. Välj Heltal fältet Artikeltyp.
20. Klicka på Lägg till.
    * Lägg till det här objektet för att representera antalet Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.  
21. Klicka på Nytt om du vill öppna dialogrutan.
22. Skriv "Archive lines" i namnfältet.
    * Arkivera rader  
23. Välj "Postlista" i fältet Artikeltyp.
24. Klicka på Lägg till.
    * Lägg till det här objektet för att representera listan med Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.  
25. Klicka på Nytt om du vill öppna dialogrutan.
26. Skriv "Belopp" i fältet Namn.
    * Tid  
27. Välj "Realtal" i fältet Artikeltyp.
28. Klicka på Lägg till.
29. Klicka på Nytt om du vill öppna dialogrutan.
30. Skriv "Commodity rec id" i namnfältet.
    * Artikelpost-ID  
31. Välj "Int64" i fältet Artikeltyp.
32. Klicka på Lägg till.
33. Klicka på Nytt om du vill öppna dialogrutan.
34. Skriv "Item number" i namnfältet.
    * Artikelnummer  
35. Välj "Sträng" i fältet Artikeltyp.
36. Klicka på Lägg till.
37. Klicka på Spara.
38. Stäng sidan.

## <a name="modify-model-mapping"></a>Ändra modellmappning
1. Expandera Intrastat (model) i trädet.
2. Välj Intrastat (model)\Intrastat (mapping) i trädet.
    * Ändra den befintliga modellmappningen om du vill börja använda den för uppdatering av programdata och för att arkivera information om Intrastat-rapportering.  
3. Klicka på Designer.
4. Klicka på Ny.
5. Skriv "Update archive" i namnfältet.
    * Uppdatera arkiv  
6. Välj To mål i fältet Direction.
7. Klicka på Spara.
    * Den nya mappningen anger dataflödet för att flytta data (information om Intrastat-rapportering) från datamodellen till programregistren (uppdateringsmålet). Observera att den andra modellens rotobjekt måste användas för att hämta data från programmet för rapportering och sedan använda data från datamodellen för uppdatering av programdata.   
8. Klicka på Designer.
9. Välj Data model\Data model i trädet.
    * Lägg till datakällan som krävs. Detta är den datamodell som innehåller information om de rapporterade Intrastat-transaktioner som måste arkiveras.  
10. Klicka på Lägg till rot.
11. Skriv "model" i namnfältet.
    * modell  
12. Ange eller välj ett värde för For application data update i fältet Definition.
    * För uppdatering av programdata  
13. Klicka på OK.
14. Expandera "modell" i trädet.
15. Välj Funktioner/Beräknat fält i trädet.
16. Välj model\Archive header i trädet.
17. Klicka på Lägg till.
    * Eftersom du vill räkna upp rapporterade Intrastat-transaktioner för arkivering måste rätt datakälla läggas till.  
18. Skriv "Enumerated lines" i namnfältet.
    * Fasta rader  
19. Klicka på Redigera formel.
20. Välj List\ENUMERATE i trädet.
21. Klicka på funktionen Lägg till.
22. Expandera "modell" i trädet.
23. Expandera model\Archive header i trädet.
24. Välj model\Archive header\Archive lines i trädet.
25. Klicka på Lägg till datakälla.
26. Ange ENUMERATE(model.'Archive header'.'Archive lines') i formelfältet.
    * ENUMERATE(modell.Archive header.Archive lines)  
27. Klicka på Spara.
28. Stäng sidan.
29. Klicka på OK.
30. Klicka på Lägg till mål.
    * Lägg till programregistren som obligatoriska mål som måste uppdateras för att arkivera information om rapporterade Intrastat-transaktioner.  
31. Skriv "Archive" i namnfältet.
    * Arkivera  
32. Skriv "IntrastatArchiveGeneral" i fältet för registernamn.
    * IntrastatArchiveGeneral  
    * Behåll poståtgärden Infoga så att du kan lägga till poster under informationsarkiveringen av respektive Intrastat-rapportering.  
33. Välj Ja i fältet Postinformationslogg.
    * Välj Ja om du vill få information om problem med uppdatering av programdata.  
34. Välj Ja i fältet Hoppa över validering av poståtgärd.
    * Välj Ja om du vill ignorera valideringsfel om det tomma fältet Arkiv-ID - Intrastat. Detta görs efter att poster har lagts till, baserat på serienummerinställningarna som har konfigurerats för detta register i formuläret Utländska handelsparametrar.  
35. Klicka på OK.
    * Bind elementen i den tillagda datakällan (den filtrerade modellen som baseras på det valda rotobjektet) till elementen från det tillagda målet.  
36. Expandera Archive i trädet.
37. Expandera Archive\<Relations i trädet.
38. Expandera Archive\<Relations\IntrastatArchiveDetail i trädet.
39. Välj Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST) i trädet.
40. Expandera model\Archive header\Enumerated lines i trädet.
41. Expandera model\Archive header\Enumerated lines\Value i trädet.
42. Välj model\Archive header\Enumerated lines\Value\Amount i trädet.
43. Klicka på Bind.
44. Välj Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity) i trädet.
45. Välj model\Archive header\Enumerated lines\Value\Commodity rec id i trädet.
46. Klicka på Bind.
47. Välj Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId) i trädet.
48. Välj model\Archive header\Enumerated lines\Value\Item number i trädet.
49. Klicka på Bind.
50. Välj Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber) i trädet.
51. Välj model\Archive header\Enumerated lines\Number i trädet.
52. Klicka på Bind.
53. Välj Archive\<Relations\IntrastatArchiveDetail i trädet.
54. Välj model\Archive header\Enumerated lines.
55. Klicka på Bind.
56. Välj Archive\File name(FileName) i trädet.
57. Välj model\Archive header\File name i trädet.
58. Klicka på Bind.
59. Välj Archive\Number of lines(NumberOfLines) i trädet.
60. Välj model\Archive header\Number of lines i trädet.
61. Klicka på Bind.
62. Välj Archive i trädet.
63. Välj model\Archive header i trädet.
64. Klicka på Bind.
65. Klicka på Spara.
66. Stäng sidan.
67. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]