--- 
title: "Ställ in manuell förpackning (enbart februari och maj 2016)"
description: "Förpackningsprocessen låter dig validera och packa produkter i behållare."
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a>Ställ in manuell förpackning (enbart februari och maj 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Förpackningsprocessen låter dig validera och packa produkter i behållare. I denna process plockar lagerarbetare produkter från lagringsplatserna och flyttar dem till en förpackningsstation där de kontrollerar artikelkvantiteterna och typerna och tilldelar dem en lämplig behållare. När en behållare är helt ilastad, kan du stänga den och flytta den till utlastningsplatserna och produkterna är redo att skeppas. I den här proceduren används demonstrationsföretaget USMF.


## <a name="set-up-location-profiles"></a>Konfigurera platsprofiler
1. Gå till Lagerstyrning > Inställningar > Lagerställe > Platsprofiler.
2. Klicka på Ny.
    * Platsprofilen används för emballagestationer och innehåller information och regler för en plats.  
3. Skriv ett värde i fältet Platsprofil-ID.
4. Skriv ett värde i fältet Namn.
5. Ange eller välj ett värde i fältet Platsformat.
6. Ange eller välj ett värde i fältet Platstyp.
7. Välj Ja i fältet Tillåt blandade artiklar.
8. Välj Ja i fältet Tillåt blandade lagerstatusar.
9. Välj Ja i fältet Åsidosättningsregler för batchdagar.
10. Stäng sidan.

## <a name="set-up-warehouse-management-parameters"></a>Ställ in parametrar för lagerstyrning 
1. Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.
2. Klicka på fliken Förpackning.
3. Ange eller välj ett värde i fältet Profil-ID för förpackningsplats.
    * Välj vilken platsprofil som du vill använda till förpackning.  
4. Stäng sidan.

## <a name="set-up-container-types"></a>Ställ in behållartyper
1. Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.
2. Klicka på Ny.
    * Du kan definiera vilka typer av behållare som ska användas. Du kan ange de fysiska dimensionerna på behållaren, inklusive taravikt, högsta vikt, högsta volym, längd, bredd och vikt.  Attribut är anpassade fält som gör att du kan lägga till fler dimensioner på behållaretypen.     
3. Ange ett värde i fältet Behållartypkod.
4. Ange ett värde i fältet Beskrivning.
5. Ange ett nummer i fältet Taravikt.
6. Ange ett värde i fältet Högsta vikt.
7. Välj ett nummer i fältet Volym.
8. I fältet Längd, ange ett tal.
9. Ange ett värde i fältet Bredd.
10. Ange ett värde i fältet Höjd.
11. Klicka på Spara.
12. Stäng sidan.

## <a name="set-up-packing-profiles"></a>Ställa in förpackningsprofiler
1. Gå till Lagerstyrning > Inställningar > Förpackning > Förpackningsprofiler.
2. Klicka på Ny.
3. Ange ett värde i fältet Förpackningsprofil-ID.
4. Ange ett värde i fältet Beskrivning.
5. Ange eller välj ett värde i fältet Profil-ID för behållarstängning.
    * Ett profil-ID för stäng behållare är valfri och är standardprofil för stängd behållare för denna förpackningsprofil.  
6. Ange ett alternativ i fältet Läge för behållar-ID.
    * Det här alternativet bestämmer om en behållar-ID genereras automatiskt när en behållare skapas, eller om en behållar-ID ska skapas manuellt.  
7. Ange eller välj ett värde i fältet Attributtyp.
    * Behållaretypen ska användas som standard när en ny behållare skapas.  
8. Markera kryssrutan Skapa behållare automatiskt när behållare stängs.
9. Klicka på Spara.
10. Stäng sidan.

## <a name="set-up-container-closing-profiles"></a>Ställa in en profiler för behållarstängning
1. Gå till Lagerstyrning > Inställningar > Behållare > Profiler för behållarstängning.
    * Profiler för behållarstängning definierar vad som händer när en behållare stängs. Du kan ställa in flera profiler för slutna behållare.       
2. Klicka på Ny.
3. Ange ett värde i fältet Profil-ID för behållarstängning.
4. Ange ett värde i fältet Beskrivning.
5. Markera ett alternativ i fältet Manifest.
    * Ange om ett manifest ska utföras när du stänger behållare eller när du bekräftar försändelsen. Observera att manifest kräver Transporthantering. Manifest måste implementeras i transportmotorerna för att den ska fungera.  
6. Ange eller välj ett värde i fältet Lagerställe.
7. Ange eller välj ett värde i fältet Standardplats för slutgiltig leverans.
    * Detta kommer att vara platsen till vilken produkterna ska flyttas till, efter att behållarna har stängts. Denna plats måste ha en platsprofil definierad i lagerställeparametrar.  
8. Ange eller välj ett värde i fältet Viktenhet.
9. Klicka på Spara.


