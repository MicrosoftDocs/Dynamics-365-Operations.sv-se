---
title: 'Definiera rullande inventering av del av platser '
description: När du använder planer för rullande inventering för att skapa inventeringsarbete kan du styra den faktiska inventeringen genom att begära att enbart vissa produkter eller produktvarianter inventeras i stället för all lagerbehållning på platsen.
author: Mirzaab
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c179b7f6e0b8546e20204a971cb2951c7b62d7b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579986"
---
# <a name="define-partial-location-cycle-counting-process"></a>Definiera rullande inventering av del av platser  

[!include [banner](../../includes/banner.md)]

När du använder planer för rullande inventering för att skapa inventeringsarbete kan du styra den faktiska inventeringen genom att begära att enbart vissa produkter eller produktvarianter inventeras i stället för all lagerbehållning på platsen. Genom att filtrera efter specifika produkter kan lagerchefen minska granskningsomkostnaderna, undvika konsolideringsmisstag och spara tid. Vanligtvis utför en lagerchef inställningsuppgifterna. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.


## <a name="create-a-cycle-counting-work-template"></a>Skapa en arbetsmall för rullande inventering
1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.
2. Välj Rullande inventering i fältet Typ av arbetsorder.
3. Klicka på Ny.
4. Ange ett nummer i fältet Sekvensnummer.
    * Sorteringsordningen är från det lägsta talet till det högsta talet. Värdet måste vara större än 0 (noll).  
5. Markera vald rad i listan.
6. Skriv ett värde i fältet Arbetsmall.
7. Skriv ett värde i fältet Beskrivning av arbetsmall.
8. Ange eller välj ett värde i fältet ID för arbetspool.
9. Välj ett tal i fältet Arbetsprioritet.
10. Klicka på Spara.
11. Klicka på Ny.
12. Markera vald rad i listan.
13. Välj Inventering i fältet Arbetstyp.
14. I fältet Arbetsklass-ID, ange eller välj ett värde.
15. Klicka på Spara.
16. Klicka på Arbetsradsuppdelningar.
17. Klicka på Ny.
18. Ange ett nummer i fältet Sekvensnummer.
    * Sorteringsordningen är från det lägsta talet till det högsta talet. Värdet måste vara större än 0 (noll).  
19. Klicka på Spara.
20. Stäng sidan.
21. Stäng sidan.

## <a name="create-a-cycle-counting-plan"></a>Skapa en plan för rullande inventering
1. Gå till Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering.
2. Klicka på Ny.
3. Skriv ett värde i fältet Plan-ID för rullande inventering.
4. Skriv ett värde i fältet Beskrivning.
5. Ange ett värde i fältet Högsta antal rullande inventeringar.
6. Ange eller välj ett värde i fältet Arbetsmall.
7. Klicka på Ny.
8. Ange ett nummer i fältet Sekvensnummer.
    * Sorteringsordningen är från det lägsta talet till det högsta talet. Värdet måste vara större än 0 (noll).  
9. Ange ett värde i fältet Beskrivning.
10. Klicka på Spara.
11. Klicka på Definiera produktfråga.
12. Markera vald rad i listan.
13. Ange eller välj ett värde i fältet Kriterier.
14. Klicka på OK.
15. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]