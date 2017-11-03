---
title: "Registrering för tillverkningskörning"
description: "I det här avsnittet beskrivs viktiga begrepp och termer som du behöver känna till när du konfigurerar och använder tillverkningskörning."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 939cb219a63a27ee9cb05036041d2722df3b0abc
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="registration-for-manufacturing-execution"></a>Registrering för tillverkningskörning

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs viktiga begrepp och termer som du behöver känna till när du konfigurerar och använder tillverkningskörning. 

Tillverkningskörning är främst avsedd att användas av tillverkningsföretag. Arbetare kan registrera artikelförbrukning och tid för produktionsjobb med hjälp av sidan **Jobbregistrering**. Alla registreringar godkänns och överförs senare till relevanta moduler. Kontinuerligt godkännande och överföring av registreringar ger chefer möjlighet att enkelt spåra faktiska kostnader på produktionsorder.

## <a name="manufacturing-execution-and-registration-terminology"></a>Tillverkningskörning och registreringsterminologi
Följande tabell innehåller termer som gäller för tillverkningskörning och relaterade registreringsuppgifter.

| Villkor                          | beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tillverkningskörning       | En funktion som används för att registrera tid, materialförbrukning, kostnader för produktionsjobb, projekt och indirekta aktiviteter. Registreringen utförs i en tillverkande körningsregistreringsklient.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Jobblista                      | På sidan **Jobbregistrering** får anställda se listan över de jobb de måste utföra för en viss resurs, till exempel en maskin. En arbetare kan registrera tids- och artikelförbrukning för varje jobb eller uppgift i jobblistan.                                                                                                                                                                                                                                                                                                                                                                           |
| Buntning av jobb                  | Om en anställd startar fler än ett jobb samtidigt på sidan **Jobbregistrering** kallas detta för buntning av jobb. Den tid som läggs på buntade jobb kan fördelas mellan de enskilda jobben på olika sätt genom att använda allokeringsnycklar.                                                                                                                                                                                                                                                                                                                                                         |
| Pilot-/assistentregistreringar | En arbetare kan registrera sig som medhjälpare till en resurs och kan skapa ett litet team där flera arbetare arbetar med samma produktionsjobb. Resurser som arbetare är kopplade till som assistenter kallas för ledare. Endast ledarresursen måste göra registreringar. Alla medhjälpare får automatiskt samma registreringar. Om till exempel en dator fungerar som ledare, kan anställda som har registrerats som medhjälpare till den datorn göra registreringar på sidan **Jobbregistrering**, och då får både maskinen och arbetarna som är kopplade som medhjälpare samma registreringar. |
| Indirekt aktivitet             | En aktivitet eller uppgift som inte är direkt relaterad till ett produktionsjobb eller ett projekt, till exempel ett avdelningsmöte, ett lokalvårdsjobb eller ett underhållsjobb på verkstadsgolvet. Arbetstagare kan göra registreringar för indirekta aktiviteter på samma sätt som de kan registrera i produktionsjobb och projekt.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Registreringar i tillverkningskörning
Arbetstagare kan göra olika typer av registreringar i formuläret för utförandet av utfört arbete på produktionsjobb. Beroende på systeminställningarna kan anställda även ha möjlighet att göra registreringar för projektaktiviteter och ickeproduktiva arbetsuppgifter, till exempel frånvaro, raster och indirekta aktiviteter. Här är registreringstyperna:

-   **Instämpling/utstämpling** (finns med tid och närvaro) – Arbetare stämplar in när de kommer till jobbet och stämplar ut när degår hem.
-   **Registrera i produktionsjobb** – Arbetare kan göra registreringar, till exempel starta ett jobb och göra återrapportering för ett jobb för produktionsjobb som visas i deras jobblista. Arbetare kan starta flera jobb på en gång. Detta kallas för buntning av jobb.
-   **Registrera i lager** – Arbetare kan göra registreringar för material som används i fabriken men som inte är direkt relaterade till produktionsjobb. Exempel är fett, smörjmedel eller annat material som används för att köra maskiner. Registreringen utförs i en lagerjournal.
-   **Registrera sig på projekt** (finns med tid och närvaro) – Anställda kan göra registreringar, till exempel starta och avsluta arbete på projekten eller projektaktiviteterna som visas i deras jobblista.
-   **Registrera projektavgifter och projektartiklar** (finns med tid och närvaro) – Arbetare kan registrera avgifter (utgifter) som är kopplade till ett projekt i en projektavgiftsjournal, till exempel reseersättning och broavgift. Arbetare kan också registrera artikelförbrukning för projekt. Detta utförs i en projektartikeljournal.
-   **Registrera som assistent till en annan arbetare** – Om två eller flera anställda ska arbeta tillsammans på ett produktionsjobb eller ett projekt, kan arbetaren registrera sig som medhjälpare till en dator eller en annan anställd, som då agerar som ledare. Ledaren kan välja en annan arbetare som ledare enligt behov.
-   **Registera frånvaro** (finns med tid och närvaro) – Anställda kan registrera tid med olika frånvarokoder som har ställts in. Det är möjligt att ange frånvaro om en anställd ankommer sent, behöver vara frånvarande under arbetsdagen eller gå tidigare än väntat enligt standardprofilen för arbetstid.
-   **Registrera raster** (finns med tid och närvaro) – Under arbetsdagen kan anställda registrera att de lämnar sin arbetsstation om de vill ta en rast. Flera avbrottstyper kan ställas in. När arbetstagaren återvänder och loggar in igen kommer systemet att registrera att arbetstagaren är tillbaka och pausregistreringen stoppas.
-   **Registrera indirekta aktiviteter** (finns med tid och närvaro) – Indirekta aktiviteter är improduktiva aktiviteter som anställda kan arbeta med under en arbetsdag, till exempel ett avdelningsmöte, ett teammöte eller ett underhållsjobb som utförs i fabriken. Arbetstagare kan göra registreringar för indirekta aktiviteter som har ställts in.
-   **Registrera övertid** (finns med tid och närvaro) – Anställda som har tillfrågats att arbeta längre tid, kan välja om de extra timmarna ska registreras som övertid eller flextid.





