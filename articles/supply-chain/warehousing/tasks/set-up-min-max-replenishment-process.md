---
title: Ställ in en min-max-process för lagerpåfyllnad
description: Den här proceduren visar hur du ställer in en ny process för lagerpåfyllnad som använder den minsta/största lagerpåfyllnadsstrategin.
author: perlynne
ms.date: 10/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, InventItemIdLookupSimple, WMSLocationIdLookup, WHSLocDirTable, InventLocationIdLookup, SysQueryForm, WHSWorkTemplateTable, WHSReplenishmentTemplates, UnitOfMeasureLookup, SysQueryTableLookUp, SysQueryFieldLookUp, SysRecurrence, WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cdbcf9b63f5277c0d2db8e3db62ca429700b5f71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830820"
---
# <a name="set-up-a-min-max-replenishment-process"></a>Ställ in en min-max-process för lagerpåfyllnad

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du ställer in en ny process för lagerpåfyllnad som använder den minsta/största lagerpåfyllnadsstrategin. När lager faller under den lägsta nivån kommer arbete att skapas för att fylla på platsen. Proceduren visar även hur du använder fasta plockplatser om du vill tillåta att fylla på lager även om lager faller under den lägsta nivån, och hur du aktiverar processen för lagerpåfyllnad att köras regelbundet med hjälp av ett batchjobb. Dessa uppgifter utförs vanligtvis av en lagerchef. Du kan köra den här proceduren i demonstrationsdataföretaget USMF som använder exempelvärdena nedan eller så kan du köra det på dina egna data. Om du använder dina egna data ska du kontrollera att du har ett lagerställe som aktiveras för Lagerstyrningsprocesser.


## <a name="create-a-fixed-picking-location"></a>Skapa en fast plockplats
1. Gå till **Navigeringsfönstret > Moduler > Lagerstyrning > Inställningar > Lagerställe > Fasta lagerplatser**. Detta är en valfri uppgift för en min-max process för lagerpåfyllnad, men om du använder fast plockplats låter detta lagret fyllas på även om det är under den lägsta nivån eftersom systemet kan bestämma vilka artiklar som måste fyllas på även om det inte finns något kvar.
2. Klicka på **Ny**.
3. I fältet **artikelnummer** anger du eller väljer ett värde. Om du använder USMF kan du välja artikeln A0001.  
4. i fältet **Plats** anger eller väljer du ett värde. Om du använder USMF kan du välja site 2.  
5. Ange eller välj ett värde i fältet **Lagerställe**. Om du använder USMF kan du välja lager 24.  
6. Ange eller välj ett värde i fältet **Plats**. Om du använder USMF kan du välja CP-003.  
7. Stäng sidan.

## <a name="create-a-replenishment-location-directive"></a>Skapa en platsdirektiv för lagerpåfyllnad
1. Gå till **Lagerstyrning > Inställningar > Platsdirektiv**. Platsdirektiv används för att bestämma var artiklarna ska plockas från i processen för lastlagerpåfyllnad.
2. Välj "Lagerpåfyllnad" i fältet **Typ av arbetsorder**.
3. Klicka på **Nytt** i **Åtgärdsfönstret**.
4. Skriv ett värde i fältet **Namn**.
5. Välj Välj i fältet **Arbetstyp**.
6. i fältet **Plats** anger eller väljer du ett värde. Om du använder USMF kan du välja site 2.  
7. Ange eller välj ett värde i fältet **Lagerställe**. Om du använder USMF kan du välja lager 24.  
8. Klicka på **Spara**.
9. I avsnittet **Rader**, klicka på **Ny**.
10. Markera vald rad i listan.
11. Ange ett värde i fältet **Till kvantitet**. Till exempel kan du ställa in den på 9999.  
12. Markera kryssrutan **Tillåt delningar**. Om du väljer det här alternativet kommer processen för att skapa arbete tillåta att kvantiteter på arbetsrader delas av flera platser.  
13. Klicka på **Spara**.
14. I avsnittet **Åtgärder för platsdirektiv** klickar dy på **Ny**.
15. Markera vald rad i listan.
16. Skriv ett värde i fältet **Namn**.
17. Klicka på **Spara**.
18. Klicka på **Redigera fråga** i **åtgärdsfönstret**. Du kan redigera den här frågan för att lägga till begränsningar som lager kan väljas från i processen för lagerpåfyllnad. Till exempel kan det hända att lagret bara används från lagerställets bulkområde.
19. Klicka på **OK**.
20. Stäng sidan.

## <a name="create-a-replenishment-work-template"></a>Skapa en arbetsmall för lagerpåfyllnad.
1. Gå till **Lagerstyrning > Inställningar > Arbete > Arbetsmallar**. Arbetsmallen används för att guida systemet hur det minsta/största lagerpåfyllnadsarbetet måste skapas. Det måste åtminstone finnas en arbetsmallrad för en plockplats och en läggplats. Arbetsmallen kommer att säga att den är ogiltig, tills all nödvändig information har fyllts i. 
2. Välj "Lagerpåfyllnad" i fältet **Typ av arbetsorder**.
3. Klicka på **Nytt** i **Åtgärdsfönstret**.
4. Skriv ett värde i fältet **Arbetsmall.**
5. Klicka på **Spara**.
6. I **Arbetsmallinformation**, klicka på **Ny**.
7. Välj Välj i fältet **Arbetstyp**.
8. Ange eller välj ett värde i fältet **Arbetsklass-ID**. Detta ska vara en arbetsklass som är relaterad till lagerpåfyllnad. Välj Lagerpåfyllnad om du använder USMF.  
9. I **Arbetsmallinformation**, klicka på **Ny**.
10. Markera vald rad i listan.
11. Välj Placera i fältet **Arbetstyp**.
12. Ange eller välj ett värde i fältet **Arbetsklass-ID**.
13. Klicka på **Spara**.
14. Stäng sidan.

## <a name="create-a-new-replenishment-template"></a>Skapa en ny mall för lagerpåfyllnad
1. Gå till **Lagerstyrning > Inställningar > Lagerpåfyllnad > Mall för lagerpåfyllnad**. Lagerpåfyllnadsmallen används för att definiera artiklarna och kvantiteterna och platsen som ska fyllas på.
2. Klicka på **Nytt** i **Åtgärdsfönstret**.
3. Skriv ett värde i fältet **Lagerpåfyllnadsmall**. Namnge mallen för att ange att den är för minsta/största för påfyllnad.  
4. I fältet **Beskrivning** anger du ett värde.
5. Markera kryssrutan **Tillåt påfyllnadsbegäran för att använda ej reserverade kvantiteter**. Om du markerar det här alternativet, aktiverar den lagerpåfyllnadsbegäran för att använda kvantiteter som är relaterade till minsta/största lagerpåfyllnad. Detta kan t.ex. vara praktiskt om det minsta/största lagerpåfyllnadsarbetet inte bearbetas på en gång för att undvika att onödigt påfyllnadsbegäransarbete skapas.
6. I **mall för lagerpåfyllnad**, klicka på **Ny**.
7. Ange ett nummer i fältet **Sekvensnummer**.
8. I fältet **Beskrivning** anger du ett värde.
9. Markera vald rad i listan.
10. Ange eller välj ett värde i fältet **Lagerpåfyllnadsenhet**. Välj till exempel st. Denna inställning är obligatorisk. Den låter dig ange olika måttenheter för lagerpåfyllnadsarbete jämfört med de enheter som anges för de lägsta och högsta lagernivåerna i den här mallen.
11. Ange eller välj ett värde i fältet **Arbetsmall**. Välj den arbetsmall som du skapade tidigare.  
12. Ange ett nummer i fältet **Minsta kvantitet**. Välj den minsta kvantitet som ska utlösa lagerpåfyllnaden. Ange den t.ex. till 50. Det går att ange detta till noll om du fyller på en fast plats och alternativet **Fyll på tomma fasta lagerplatser** är angett till Ja. Vi rekommenderar även att du väljer alternativet **Fyll endast på fasta lagerplatser** av prestandaskäl.
13. Ange ett nummer i fältet **Högsta kvantitet**. Ange t.ex. detta till 100.  
14. Ange eller välj ett värde i fältet **Enhet**. Tilldela enheten för de minsta och högsta kvantiteterna. Ange t.ex. detta till st.  
15. Markera kryssrutan **Fyll på tomma fasta lagerplatser**. Markera den här kryssrutan för att fylla på fasta lagerplatser när de är tomma. Annars kommer bara platserna där det finns en kvantitet i lager att fyllas på.
16. Markera kryssrutan **Fyll endast på tomma fasta lagerplatser**.
17. Klicka på **Välj produkter**. Detta är platsen för att definiera vilka produkter som ska fyllas på. Om alternativet Fasta plockplatser markeras, måste du även definiera platserna i den här frågan. Variantspecifika frågor är tillgängliga, liksom produktspecifika frågor.
18. Markera raden **Artiklar**.
19. I fältet **Kriterier** skriver du ett värde. Välj de artiklar som ska fyllas på de fasta platserna. Ange t.ex. A* för att markera alla artikelnummer som börjar med A.
20. Klicka på **Lägg till**. Lägg till Platsenheten (såvida den inte redan finns) för att kunna begränsa lagerpåfyllnadsarbete till de fasta plockplatserna inom ett specifikt område på lagerstället.
21. Markera vald rad i listan.
22. Ange fältet **Tabell** till Platser.
23. Välj Platsprofil-ID i fältet **Fält**.
24. I fältet **Kriterier** anger du eller väljer ett värde.
25. Klicka på **OK**.
26. Stäng sidan.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Ange att processen för lagerpåfyllnad ska köras som ett batchjobb
1. Gå till **Lagerstyrning > Lagerpåfyllnad > Lagerpåfyllnad**. Sidan Lagerpåfyllnad Återanskaffningarna låter dig ange påfyllnad som ska köras som ett batchjobb eller om du vill att den startas manuellt.
2. Klicka på **Filter**.
3. Markera vald rad i listan.
4. I fältet **Kriterier** anger du eller väljer ett värde.
5. Klicka på **OK**.
6. Expandera avsnittet **Kör i bakgrunden**.
7. Ange alternativet **Batchbearbetning** till Ja.
8. Klicka på **Upprepning.**
9. Välj alternativet **Slutdatum saknas**.
10. Ange **Upprepningsmönstret**. Välj till exempel Dagar.  
11. Klicka på **OK**.
12. Klicka på **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]