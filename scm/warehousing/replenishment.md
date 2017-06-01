---
title: "Lagerpåfyllnad"
description: "Den här artikeln innehåller en beskrivning av strategier för lagerpåfyllnad som är tillgängliga för lagerställen som använder funktioner i Lagerstyrning."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 83111c4d2b41f6e2fba41d550f153174d72d4710
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="replenishment"></a>Lagerpåfyllnad

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller en beskrivning av strategier för lagerpåfyllnad som är tillgängliga för lagerställen som använder funktioner i Lagerstyrning.

Den här artikeln innehåller en beskrivning av strategier för lagerpåfyllnad som är tillgängliga för lagerställen som använder funktioner i Lagerstyrning. Informationen gäller inte för den lagerställelösning som är tillgänglig i Lagerhantering. Det finns tre lagerpåfyllnadsstrategier:

-   **Lagerpåfyllnad baserad på efterfrågan** – Denna strategi skapar lagerpåfyllnadsarbete för utgående order eller laster om lagret inte är tillgängligt när påfyllnad skapar arbete. Lagerpåfyllnadsarbete kan till exempel skapas om kvantiteten som krävs för en försäljningsorder inte är tillgänglig när en påfyllnad bearbetas.
-   **Minsta/största lagerpåfyllnad** – Denna strategi använder trösklar för minsta och största lager för att avgöra när platser ska fyllas på. Artikel- och platsvillkoren definierar lagret som ska bedömas för påfyllnaden. Mallar för minsta/största lagerpåfyllnad är den primära mekanismen för att bibehålla optimala nivåer på plockplatser. För att garantera att det finns tillräckligt med yta för plockning för att tillgodose plockningsbehovet kan du använda Lagerpåfyllnad baserat på efterfrågan som komplement mellan cykler för Minsta/största lagerpåfyllnad.
-   **Lagerpåfyllnad för lastefterfrågan** – Den här strategin summerar behovet av flera laster och skapar de påfyllnadsarbeten som krävs för att fylla på relevanta plockplatser. Denna strategi hjälper till att garantera att lasterna som skapas kan plockas på lagerstället när de har släppts.

Alla de tre strategierna skapar lagerpåfyllnadsarbete, baserat på en mall för lagerpåfyllnad.

## <a name="wave-demand-replenishment"></a>Lagerpåfyllnad baserad på efterfrågan
Lagerpåfyllnad baserad på efterfrågan skapar lagerpåfyllnadsarbete baserat på efterfrågan om kvantiteten för utgående order eller laster inte är tillgänglig när en påfyllnad skapar arbete. Lagerpåfyllnadsmallen innehåller information om kriterierna för artikeln, måttenheten, efterfråganökningen och platsen. 

Platsdirektiven används för att fastställa vilket lagerställe som ska fyllas på. Du länkar platsdirektiven till lagerpåfyllnadsmallen med hjälp av fältet **Direktivkod**. Om fältet **Direktivkod** inte har markerats används frågor för att fastställa vilket platsdirektiv som ska användas. Observera att om ingen direktivkod anges i lagerpåfyllnadsmallen och platsdirektivet har en direktivkod kommer platsdirektivet att ignoreras även om frågan om platsdirektivet är korrekt. Platsdirektiv för plockning används för att fastställa var lagret för påfyllning finns. 

Utöver att skapa en mall ska du specificera vissa inställningar för lagerpåfyllnad i påfyllnadsmallen. Påfyllnadsmallen ska innehålla ett påfyllnadssteg för lagerpåfyllnad som enbart körs om tilldelning av en artikel misslyckas. Det här steget för lagerpåfyllnad använder en påfyllnadskod som fastställer vilken lagerpåfyllnadsmall som ska användas. Utöver ett steg för påfyllnad ska du se till att **Fyll på** väljs i avsnittet **Metoder** i påfyllnadsmallen. 

Sidan **Lagerpåfyllnadsmall** innehåller kryssrutan **Tillåt påfyllnadsbegäran för att använda ej reserverade kvantiteter**. Du ska markera den här kryssrutan om du vill tillåta begäran om lagerpåfyllnad för att dra av oreserverade kvantiteter från arbete som genereras från den valda lagerpåfyllnadsmallen. Om du vill aktivera att mallar för begäran om lagerpåfyllnad ska använda denna logik ska du markera kryssrutan för varje befintlig lagerpåfyllnadsmall. När begäran om påfyllnad aktiveras på lagerstället dras begäran av från befintligt lagerpåfyllnadsarbete som har oreserverade kvantiteter, om arbetet härrör från mallar för lagerpåfyllnad där kryssrutan **Tillåt påfyllnadsbegäran att använda oreserverade kvantiteter** har markerats.

## <a name="minmax-replenishment"></a>Minsta/största lagerpåfyllnad
I Minsta/största lagerpåfyllnad fylls lagret på så att behållningen ligger inom de gränser för minsta och största lager som har markerats. Vanligtvis utförs den här processen en gång om dagen för att garantera att alla plockplatser fylls på till maximal nivå innan plockningen inleds. 

Minimi- och maximinivåerna ställs in i en lagerpåfyllnadsmall. Många av de andra inställningarna i mallen liknar inställningarna i mallarna som används i Lagerpåfyllnad baserad på efterfrågan. Mallen ska innehålla en rad för varje artikel och plats. När du kör lagerpåfyllnad med hjälp av batchjobbet, utvärderar Microsoft Dynamics 365 for Operations om påfyllnad krävs, i den sekvens som raderna är ordnade i. 

Observera att strategin Minsta/största lagerpåfyllnad inte kan fylla på en tom plats om inte platsen är markerad som fast lagerplats för artikeln. Om platsen som måste fyllas på inte är en fast plats, kan Dynamics 365 for Operations inte fastställa vilken artikel som ska fyllas på. Därför krävs åtminstone en viss lagerbehållning innan lagerpåfyllnad utförs.

## <a name="load-demand-replenishment"></a>Lagerpåfyllnad för lastefterfrågan
Lagerpåfyllnad för lastefterfrågan summerar behovet av flera laster och skapar de lagerpåfyllnadsarbeten som krävs för att fylla på relevanta plockplatser. Lagerpåfyllnad för lastefterfrågan liknar Lagerpåfyllnad baserad på efterfrågan på många sätt. Den största skillnaden är hur och när Lagerpåfyllnad för lastefterfrågan och Lagerpåfyllnad baserad på efterfrågan körs. I likhet med Minsta/största lagerpåfyllnad körs Lagerpåfyllnad för lastefterfrågan med hjälp av ett batchjobb. Om du vill ställa in batchjobbet på sidan **Lagerpåfyllnad för lastefterfrågan**, välj vilken lagerpåfyllnadsmall som ska användas och markera en filterfråga för att ange vilka laster som ska användas för att fastställa behovet. Platsfrågan definierar de platser som tillgänglig kvantitet kommer att dras av ifrån för att tillgodose det sammanlagda behovet av laster.

## <a name="replenishment-prerequisites"></a>Förutsättningar för lagerpåfyllnad
| Förutsättning            | Beskrivning                                                                                                                                                                                                                                        |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Artikel                    | Artikeln måste aktiveras för lagerhanteringsprocesser.                                                                                                                                                                                       |
| Lagerställe               | Lagerstället måste aktiveras för lagerhanteringsprocesser. Om du vill aktivera lagerstället för lagerhanteringsprocesser, väljer du lagerstället på sidan **Lagerställen** och markerar sedan alternativet **Använd lagerstyrningsprocesser**. |
| Mallar för lagerpåfyllnad | Minst en lagerpåfyllnadsmall måste markeras för Minsta/största lagerpåfyllnad, Lagerpåfyllnad baserad på efterfrågan eller Lagerpåfyllnad för lastefterfrågan.                                                                                                             |
| Platser               | Platser måste skapas och anslutas till en platsprofil.                                                                                                                                                                                     |
| Platsprofiler       | Platsprofiler krävs för att skapa platser.                                                                                                                                                                                       |
| Platsdirektiv     | Platsdirektiven krävs för att leda arbetet till de platser där påfyllnad krävs och till de platser som lager hämtas ifrån.                                                                                     |
| Arbetsmallar          | Arbetsmallar av typen **Lagerpåfyllnad** krävs för att skapa lagerpåfyllnadsarbete så att lagret kan flyttas till valfria platser.                                                                                           |






