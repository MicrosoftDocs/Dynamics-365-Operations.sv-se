---
title: Formalisera affärsprocesser
description: Det här avsnittet förklarar hur du använder funktionen affärsprocess för att skapa affärsprocessmallar för processer som behöver slutföras inom organisationen.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.openlocfilehash: 51f8102afc28b3836d5fee13aa1e950351af3c4f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008394"
---
# <a name="formalize-business-processes"></a>Formalisera affärsprocesser

[!include[banner](includes/banner.md)]

Funktionen affärsprocess låter dig skapa affärsprocessmallar för processer som behöver slutföras inom organisationen. Exempelvis slutför ditt företag en årligen återkommande personalgranskning (HR). I det här fallet kan du skapa en mall som spårar uppgifter som revisionen består av. Den här mallen kan hjälpa till att garantera att alla uppgifter utförs varje gång revisionen utförs. Dessutom om uppgifterna som måste slutföras i en viss ordning kan mallen garantera att de görs i rätt ordning.

Mallar kan återanvändas för återkommande processer. De kan också kopieras och användas som utgångspunkt för att skapa nya mallar.

När du har skapat en mall kan en process startas och spåras i arbetsytan **Affärsprocess** När en affärsprocess startas kommer uppgifterna tilldelas till rätt personer och innehålla ett förfallodatum.

## <a name="business-process-templates"></a>Affärsprocessmallar
En affärsprocessmall visar en grupp med aktiviteter som utgör en affärsprocess. Personalchefer och medhjälpare kan skapa affärsprocesser som standard. Du kan emellertid ändra de roller som kan skapa affärsprocesser genom att ändra **upprätthålla allmänna affärsprocesser** i säkerhetskonfigurationen.

En processägare kan definieras för varje affärsprocess. Processägaren kommer att ha insyn i alla uppgifter för processen kan tilldela om uppgifter eller ändra förfallodatum. T.ex. personalchefen skapar affärsprocessmallar för att granska förmåner och kompensationer och anger kompensation- och förmånschef som processägare. Kompensation- och förmånschef har sedan insyn i de uppgifter som måste slutföras som en del av granskningen.

En processägare kan inte skapa nya affärsprocesser eller affärsprocessmallar eller ta bort aktiva processer eller affärsprocessmallar.

## <a name="tasks"></a>Uppgifter
En affärsprocess består ofta av flera uppgifter. Vissa uppgifter, till exempel en granskning av interna kursutbud, kan slutföras i Microsoft Dynamics 365 Talent. I det här fallet välj sett alternativ i fältet **aktivitetslänk**. Andra uppgifter kan omfatta granska eller komplettera sidor på en webbplats. I det här fallet väljs **URL** i fältet **aktivitetslänk** och webbadressen kan anges. Du kan ange URL:er för både externa och interna webbplatser i det här fältet. Du kan också skapa uppgifter för aktiviteter som du slutför manuellt, till exempel granska tillgänglighet av alla strukturer. I detta fall krävs inte en uppgiftslänk. Denna flexibilitet låter dig spåra flera typer av uppgifter i en omfattande process.

Uppgifter kan tilldelas till en särskild arbetare eller till en befattning. Exempelvis ska en chef över kompensationer och förmåner alltid vara den person som utför en granskning av försäkringspremier. När du skapar denna uppgift, välj **Befattning** i fältet **Uppgiftstyp** och välj sedan **Chef över kompensationer och förmåner** i listan **Befattning** När processen startar tilldelas uppgiften till den anställde som har befattningen **chef över kompensationer och förmåner**. Du kan också tilldela en uppgift till en särskild **arbetare** i fältet **Tilldelningstyp** och sedan välja rätt person.

Uppgiftens förfallodatum datum beror på måldatumet som anges i början av affärsprocessen. Vissa uppgifter måste slutföras före måldatumet och vissa kan slutföras efter måldatumet. När du definierar en uppgift anger du ett förfallodatum som är i relation till datumet i fältet **Förfallodatum förskjutet från måldatum**. Anta till exempel att chefen över kompensationer och förmåner måste utföra en granskning av försäkringspremier 10 dagar innan personalgranskningen är klar. Då aktiviteten som skapas för granskningen har en **Förfallodatum förskjutet från måldatum** värdet av **-10**. Om affärsprocessen har startat 13 maj kommer uppgiften därför att förfalla 3 maj.

> [!NOTE]
> Förfallodatum kan också justeras när affärsprocessen startas.

Komplicerade uppgifter kanske kräver flera steg eller kräver att personen som utför uppgifter tillhandahåller ytterligare information. För dessa scenarion kan du lägga till instruktioner till en uppgift. Instruktionerna kan ge ytterligare information om hur du slutför uppgiften till den person som har tilldelats för att slutföra den. Du kan även inkludera RTF-formatering i instruktionerna.

## <a name="starting-a-business-process"></a>Starta en affärsprocess
I en affärsprocessmall kan du starta en affärsprocess genom att välja **Starta process**. När en process startas skapas uppgifter för valda arbetare och/eller befattningar som definierats i de uppgifter som ingår i mallen. Ett förfallodatum kommer också att tilldelas varje uppgift genom att addera eller subtrahera förskjutningsdagar från måldatumet, enligt avsnittet "Uppgifter". De aktiva affärsprocesserna kan visas på arbetsytan **Affärsprocesser**

## <a name="employee-self-service"></a>Anställd self-service
När en uppgift tilldelas en medarbetare, kan medarbetaren se denna och hans eller hennes andra tilldelade uppgifter på sidan **Självbetjäning för medarbetare** För varje affärsprocessuppgift som tilldelats honom eller henne, visas namn och beskrivning av uppgiften, anvisningar och namnet på en kontaktperson. Från sidan **Självbetjäning för medarbetare** kan medarbetaren också öppna den associerade sidan i Microsoft Dynamics 365 eller tillhörande webbsida och märka uppgifter som pågår, annullerats eller slutförts.

## <a name="business-process-workspace"></a>Arbetsytan Affärsprocess
Personalansvariga kan visa de aktiva affärsprocesserna från arbetsytan **Affärsprocesser** Arbetsytan visar alla aktiva processer och uppgifter som är kopplade till varandra. Den omfattande uppgiftslistan kan filtreras efter datum. Arbetsytan innehåller även förfallna uppgifter och uppgifter som tilldelats personalansvariga. Personalansvariga kan också uppdatera statusen för alla uppgifter och vid behov tilldela om uppgifter för att låta den övergripande affärsprocessen gå vidare.

## <a name="my-business-processes-workspace"></a>Arbetsytan Mina affärsprocesser
Processägare kan visa aktiva affärsprocesser som tilldelas dem från arbetsytan **Mina affärsprocesser** Arbetsytan visar alla aktiva processer och kopplade uppgifter som användaren äger. Den omfattande uppgiftslistan kan filtreras efter datum. Arbetsytan innehåller även uppgifter som specifikt tilldelats processägaren. Processägaren kan även uppdatera statusen för alla uppgifter, samt tilldela om eventuella uppgifter.

## <a name="navigating-business-processes"></a>Navigerar till affärsprocesser
För att skapa eller kopiera en mall för företagsprocessen, eller för att starta en affärsprocess, navigerar du till affärsprocesser - länkar - Administration av affärsprocesser. Du kan sedan följande åtgärder:

- Välj **Ny** om du vill skapa en ny affärsprocessmall.
- Välj **Kopiera från mall** för att kopiera den valda mallen till en ny.
- Välj **Starta process** för att starta den valda affärsprocessen, tilldela uppgifter och beräkna förfallodatum.

Om du vill visa aktiva processer och tillhörande uppgifter, gå till arbetsytan **Affärsprocesser**

