---
title: Lagerpåfyllnad – översikt
description: Denna artikel beskriver de lagerpåfyllnadsstrategier som erbjuds för lager som använder funktionerna i Warehouse management.
author: Mirzaab
ms.date: 02/19/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSReplenishmentTemplates, WHSInventFixedLocation, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "90043"
- intro-internal
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 075e74845eb8e0363cdb706f1f3af0dc9cfddfaa
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069195"
---
# <a name="replenishment-overview"></a>Lagerpåfyllnad – översikt

[!include [banner](../includes/banner.md)]

Denna artikel beskriver de lagerpåfyllnadsstrategier som erbjuds för lager som använder funktionerna i Warehouse management. Informationen i denna artikel gäller ej den lagerlösning som erbjuds i lagerhanteringen.

Det finns följande strategier för lagerpåfyllnad:

- **Lagerpåfyllnad baserad på efterfrågan** – Denna strategi skapar lagerpåfyllnadsarbete för utgående order eller laster om lagret inte är tillgängligt när påfyllnad skapar arbete. Lagerpåfyllnadsarbete kan till exempel skapas om kvantiteten som krävs för en försäljningsorder inte är tillgänglig när en påfyllnad bearbetas.
- **Minsta/största lagerpåfyllnad** – Denna strategi använder trösklar för minsta och största lager för att avgöra när platser ska fyllas på. Artikel- och platsvillkoren definierar lagret som ska bedömas för påfyllnaden. Mallar för minsta/största lagerpåfyllnad är den primära mekanismen för att bibehålla optimala nivåer på plockplatser. För att garantera att det finns tillräckligt med yta för plockning för att tillgodose plockningsbehovet kan du använda Lagerpåfyllnad baserat på efterfrågan som komplement mellan cykler för Minsta/största lagerpåfyllnad.
- **Lagerpåfyllnad för lastefterfrågan** – Den här strategin summerar behovet av flera laster och skapar de påfyllnadsarbeten som krävs för att fylla på relevanta plockplatser. Denna strategi hjälper till att garantera att lasterna som skapas kan plockas på lagerstället när de har släppts.
- **Omedelbar påfyllning** – Denna strategi fyller på lagret innan en omgång körs om tilldelning misslyckas för en platsdirektivsrad med påfyllnadsmall. 

Samtliga fyra strategier skapar påfyllnadsarbete, baserat på en påfyllnadsmall.

## <a name="wave-demand-replenishment"></a>Lagerpåfyllnad baserad på efterfrågan
Påfyllnad av omgångsbehov skapar påfyllnadsarbete baserat på behov om den kvantitet som krävs för produktionsorder, kanban, utgående order eller laster inte finns tillgängliga när en omgång skapar arbete. Lagerpåfyllnadsmallen innehåller information om kriterierna för artikeln, måttenheten, efterfråganökningen och platsen. 

Platsdirektiven används för att fastställa vilket lagerställe som ska fyllas på. Du länkar platsdirektiven till lagerpåfyllnadsmallen med hjälp av fältet **Direktivkod**. Om fältet **Direktivkod** inte har markerats används frågor för att fastställa vilket platsdirektiv som ska användas. Observera att om ingen direktivkod anges i lagerpåfyllnadsmallen och platsdirektivet har en direktivkod kommer platsdirektivet att ignoreras även om frågan om platsdirektivet är korrekt. Platsdirektiv för plockning används för att fastställa var lagret för påfyllning finns. 

Utöver att skapa en mall ska du specificera vissa inställningar för lagerpåfyllnad i påfyllnadsmallen. Omgångsmallen bör innehålla ett omgångssteg för påfyllnad som endast körs om en vara inte tilldelas korrekt. Det här steget för lagerpåfyllnad använder en påfyllnadskod som fastställer vilken lagerpåfyllnadsmall som ska användas. Förutom att ha ett omgångssteg för påfyllnad måste du även se till att **Fyll på** har valts i avsnittet **Metoder** i omgångsmallen. 

Sidan **Lagerpåfyllnadsmall** innehåller kryssrutan **Tillåt påfyllnadsbegäran för att använda ej reserverade kvantiteter**. Välj denna kryssruta om behovspåfyllnad ska kunna dra av icke-reserverade kvantiteter från arbete som genereras av vald påfyllnadsmall. Om du vill aktivera att mallar för begäran om lagerpåfyllnad ska använda denna logik ska du markera kryssrutan för varje befintlig lagerpåfyllnadsmall. När begäran om påfyllnad aktiveras på lagerstället dras begäran av från befintligt lagerpåfyllnadsarbete som har oreserverade kvantiteter, om arbetet härrör från mallar för lagerpåfyllnad där kryssrutan **Tillåt påfyllnadsbegäran att använda oreserverade kvantiteter** har markerats.

**Påfyllningsenhet** är den minsta enhet som ska fyllas på. Måste vara ett heltal som är en multipel av enheten. Systemet kommer att avrundas upp till den högsta möjliga enheten när arbete skapas.

Lagerpåfyllnadsbegäran stöds för försäljningsorder, överföringsorder, produktionsorder och kanbans. 

## <a name="minmax-replenishment"></a>Minsta/största lagerpåfyllnad
I Minsta/största lagerpåfyllnad fylls lagret på så att behållningen ligger inom de gränser för minsta och största lager som har markerats. Denna process sker som regel en gång varje dag i syfte att säkerställa att samtliga plockplatser fylls maximalt innan plocket inleds. 

Minimi- och maximinivåerna ställs in i en lagerpåfyllnadsmall. Många av de andra inställningarna i mallen liknar inställningarna i mallarna som används i Lagerpåfyllnad baserad på efterfrågan. Mallen ska innehålla en rad för varje artikel och plats. När du kör lagerpåfyllnad med hjälp av batchjobbet utvärderar systemet om påfyllnad krävs, i den sekvens raderna är ordnad i. 

Observera att strategin Minsta/största lagerpåfyllnad inte kan fylla på en tom plats om inte platsen är markerad som fast lagerplats för artikeln. Om platsen som måste fyllas på inte är fast, kan systemet inte avgöra vilken vara som ska fyllas på. Därför krävs åtminstone en viss lagerbehållning innan lagerpåfyllnad utförs.

## <a name="load-demand-replenishment"></a>Lagerpåfyllnad för lastefterfrågan
Lagerpåfyllnad för lastefterfrågan summerar behovet av flera laster och skapar de lagerpåfyllnadsarbeten som krävs för att fylla på relevanta plockplatser. Lagerpåfyllnad för lastefterfrågan liknar Lagerpåfyllnad baserad på efterfrågan på många sätt. Den största skillnaden är hur och när Lagerpåfyllnad för lastefterfrågan och Lagerpåfyllnad baserad på efterfrågan körs. I likhet med Minsta/största lagerpåfyllnad körs Lagerpåfyllnad för lastefterfrågan med hjälp av ett batchjobb. Om du vill konfigurera batchjobbet på sidan **Lagerpåfyllnad för lastefterfrågan**, välj vilken lagerpåfyllnadsmall som ska användas och markera en filterfråga för att ange vilka laster som ska användas för att fastställa behovet. Platsfrågan definierar de platser som tillgänglig kvantitet kommer att dras av ifrån för att tillgodose det sammanlagda behovet av laster.

## <a name="immediate-replenishment"></a>Omedelbar påfyllnad
Du kan applicera en omedelbar påfyllnadsstrategi istället för att behöva sammanställa behovet i slutet av en allokeringsprocess och sedan fylla på baserat på den sammanställda kvantiteten. När du använder denna teknik kan lagret fyllas på omedelbart efter det att en direktivrad för plats misslyckas. Du kan därför konfigurera påfyllnaden som att den begränsas av specifika enheter, samt på så sätt att den använder kvantiteter angivna för specifika platser.

## <a name="replenishment-prerequisites"></a>Förutsättningar för lagerpåfyllnad

|      Förutsättning       |                                                                                                                                beskrivning                                                                                                                                 |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Artikel           |                                                                                                        Artikeln måste aktiveras för lagerstyrningsprocesser (WMS).                                                                                                        |
|        Lagerställe        | Lagerstället måste aktiveras för lagerstyrningsprocesser (WMS). Om du vill aktivera ett lagerställe för WMS väljer du lagerstället på sidan <strong>Lagerställen</strong> och markerar sedan alternativet <strong>Använd lagerstyrningsprocesser</strong>. |
| Mallar för lagerpåfyllnad |                                                                   Minst en lagerpåfyllnadsmall måste markeras för Minsta/största lagerpåfyllnad, Lagerpåfyllnad baserad på efterfrågan eller Lagerpåfyllnad för lastefterfrågan.                                                                   |
|        Platser        |                                                                                                       Platser måste skapas och anslutas till en platsprofil.                                                                                                       |
|    Platsprofiler    |                                                                                                        Platsprofiler krävs för att skapa platser.                                                                                                        |
|   Platsdirektiv   |                                                       Platsdirektiv krävs för att dirigera arbete till de platser där påfyllnad krävs, samt till de platser lager hämtas ifrån.                                                        |
|     Arbetsmallar      |                                                   Arbetsmallar av typen <strong>Lagerpåfyllnad</strong> krävs för att skapa lagerpåfyllnadsarbete så att lagret kan flyttas till valfria platser.                                                    |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]