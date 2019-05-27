---
title: Ändra format för att generera dokument som omfattar programdata
description: 'Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 3: Ändra modell och mappning)".'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: a095d0326835b0ae7322d5d58307216ee828649e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544551"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Ändra format för att generera dokument som omfattar programdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 3: Ändra modell och mappning)".

Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument och uppdatera programdata. I den här proceduren ska du ändra ER-konfigurationerna inte bara för att använda dem för att skapa elektroniska dokument, utan även för att uppdatera programdata. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Ändra format för att samla in information om rapportering
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera Intrastat (model) i trädet.
3. Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.
4. Klicka på Designer.
5. Expandera File i trädet.
6. Expandera FileDeclaration i trädet.
7. Välj File\Declaration\Data i trädet.
8. Välj Ett många i fältet Sammansatt.
    * Konfigurera det här formatelementet om du vill arkivera information om Intrastat-rapporteringen. Det här objektet representerar arkivets rubrikpost.  
9. Expandera File\Declaration\Data i trädet.
10. Välj File\Declaration\Data\Item i trädet.
11. Välj Noll många i fältet Sammansatt.
    * Konfigurera det här formatelementet om du vill arkivera information om Intrastat-rapporteringen. Det här objektet representerar listan med arkiverade rader.  
12. Expandera File\Declaration\Data\Item i trädet.
13. Välj File\Declaration\Data\Item\Dim1 i trädet.
14. Välj Ja i fältet Exkluderad.
    * Du ska inte att arkivera dessa data, så du kan utelämna detta formatelement från datakällan i informationen för Intrastat-rapportering.  
15. Expandera File\Declaration\Data\Item\Dim1 i trädet.
16. Välj File\Declaration\Data\Item\Dim1\property i trädet.
17. Välj Ja i fältet Exkluderad.
18. Välj File\Declaration\Data\Item\Dim1\date i trädet.
19. Välj Ja i fältet Exkluderad.
20. Välj File\Declaration\Data\Item\Dim2 i trädet.
21. Välj Ja i fältet Exkluderad.
22. Expandera File\Declaration\Data\Item\Dim2 i trädet.
23. Välj File\Declaration\Data\Item\Dim2\property i trädet.
24. Välj Ja i fältet Exkluderad.
25. Välj File\Declaration\Data\Item\Dim2\code i trädet.
26. Välj Ja i fältet Exkluderad.
27. Välj File\Declaration\Data\Item\Dim3 i trädet.
    * Flera formatelement kan ha samma namn. Till exempel Dim. Du kan inte identifiera dem explicit när du använder detta format som en datakälla för att arkivera rapporteringsinformation för Intrastat. Därför måste du definiera alternativa namn för dessa formatelement.   
28. Skriv "Belopp" i fältet Namn.
    * Tid  
29. Välj Exakt ett i fältet Sammansatt.
30. Välj File\Declaration\Data\Item\Dim4 i trädet.
31. Skriv "Artikel" i fältet Namn.
    * Artikel  
32. Välj Exakt ett i fältet Sammansatt.
    * Förutom designformatelementen måste följande information för Intrastat-rapportering arkiveras: unik postidentifiering för varje rapporterad vara och namnet på den skapade filen. Eftersom dessa data inte att fylls i i Intrastat-rapporten, måste du lägga till det format som hör till dessa informationselement som datakällsartiklar.  
33. Välj File\Declaration\Data i trädet.
34. Klicka på Lägg till för att öppna dialogrutan.
35. Välj Data source\Item i trädet.
36. Ange "File name" i namnfältet.
    * Filnamn  
37. Välj Datatyp i fältet Artikeltyp.
38. Klicka på OK.
39. Välj File\Declaration\Data\Item i trädet.
40. Klicka på Lägg till artikel.
41. Skriv "Commodity rec id" i namnfältet.
    * Artikelpost-ID  
42. Välj Int64 i fältet Datatyp.
43. Klicka på OK.
44. Klicka på fliken Mappning.
45. Välj File\Declaration\Data\File name i trädet.
46. Klicka på Bind.
47. Expandera "modell" i trädet.
48. Expandera model\Transactions i trädet.
49. Välj File\Declaration\Data\Item =  model.Transactions\Commodity rec id i trädet.
50. Välj model\Transactions\Commodity rec id i trädet.
51. Klicka på Bind.
52. Klicka på Spara.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Ändra format för att memorera information om rapportering
1. Klicka på Mappa format till modell.
2. Klicka på Ny.
3. Ange eller välj ett värde för rotobjektet For application data update i fältet Definition.
    * För uppdatering av programdata  
4. Skriv "Mapping to update data" i namnfältet.
    * Mappning för att uppdatera data  
5. Klicka på Spara.
    * Den här mappningen avgör hur information om Intrastat-rapporten samlas in i datamodellen, strukturen som anges av det valda rotobjektet "For application data update". Dessa uppgifter, modellmappningen med samma rotobjekt "For application data update" och riktningen "To mål" används för uppdatering av programdata. Uppdateringen av programdata inleds omedelbart efter att den utgående Intrastat-rapporten har skapats. Observera att uppdateringen av programdata kan hoppas över under körning, men datamodellen måste vara tom (innehåller en tom postlista).   
6. Klicka på Designer.
    * Observera att formatet för den utgående Intrastat-rapporten läggs till som standard som datakälla för den här modellmappningen.  
    * Bind elementen i den utformade rapporten (visas som datakälla) till elementen i datamodellen, som filtreras utifrån den valda modellens rotobjekt.  
7. Expandera Archive header i trädet.
8. Expandera Archive header\Archive lines i trädet.
9. Expandera format i trädet.
10. Expandera format\Declaration: XML Element(Declaration) i trädet.
11. Expandera format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data) i trädet.
12. Expandera format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item) i trädet.
13. Expandera format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount) i trädet.
14. Expandera format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item) i trädet.
15. Välj Archive header\Number of lines i trädet.
16. Klicka på Redigera.
17. Välj ListCOUNT i trädet.
18. Klicka på funktionen Lägg till.
19. Expandera format i trädet.
20. Expandera format\Declaration: XML Element(Declaration) i trädet.
21. Expandera format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data) i trädet.
22. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item) i trädet.
23. Klicka på Lägg till datakälla.
24. Skriv "COUNT(format.Declaration.Data.Item)" i formelfältet.
    * COUNT(format.Declaration.Data.Item)  
25. Klicka på Spara.
26. Stäng sidan.
27. Välj Archive header\File name i trädet.
28. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name) i trädet.
29. Klicka på Bind.
30. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number) i trädet.
31. Välj Archive header\Archive lines\Item number i trädet.
32. Klicka på Bind.
33. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value) i trädet.
34. Välj Archive header\Archive lines\Amount i trädet.
35. Klicka på Bind.
36. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec id: Item Int64(Commodity rec id) i trädet.
37. Välj Archive header\Archive lines\Commodity rec id i trädet.
38. Klicka på Bind.
39. Välj Archive header\Archive lines i trädet.
40. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item) i trädet.
41. Klicka på Bind.
42. Välj Archive header i trädet.
43. Välj format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data).
44. Klicka på Bind.
45. Klicka på Spara.
46. Stäng sidan.
47. Stäng sidan.
48. Stäng sidan.

