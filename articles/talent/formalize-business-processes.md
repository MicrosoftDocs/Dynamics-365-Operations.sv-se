---
title: "Formalisera affärsprocesser"
description: "Funktionen affärsprocess låter dig skapa affärsprocessmallar för processer som behöver slutföras inom organisationen."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1b50a97f5e2fc94255ff71702faf91ab36e68eb4
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="formalize-business-processes"></a>Formalisera affärsprocesser
Funktionen affärsprocess låter dig skapa affärsprocessmallar för processer som behöver slutföras inom organisationen. Företaget kan exempelvis göra en personalgranskning per år. En mall kan skapas för att spåra alla uppgifter som granskningen omfattar för att garantera att alla uppgifter görs varje gång som processen har slutförts och om så krävs för att säkerställa att uppgifterna utförs i rätt ordning. Mallar kan återanvändas för återkommande processer eller kopieras om du vill använda dem som utgångspunkt för att skapa nya.

När du har skapat en mall kan en process startas och spåras i arbetsytan Affärsprocess.  När en affärsprocess startas kommer uppgifterna tilldelas till rätt personer och innehålla ett förfallodatum. Vi täcker dessa komponenter i detalj nedan.

## <a name="business-process-template"></a>Affärsprocessmall
En affärsprocessmall visar en grupp med aktiviteter som utgör en affärsprocess. Personalchefer och medhjälpare kan skapa affärsprocesser som standard.  Detta kan dock ändras i säkerhetskonfigurationen genom att redigera Underhåll allmänna affärsprocesser.

En processägare kan definieras för varje process. Processägaren kommer att ha insyn i alla uppgifter för processen kan tilldela om uppgifter eller ändra förfallodatum.  T.ex. personalchefen kan till skapa en affärsprocessmall för en förmånsgranskning.  Chefen över kompensationer och förmåner kan anges som processägare så att han eller hon kan få inblick i de uppgifter som måste slutföras som en del av granskningen.  En processägare kan inte skapa eller ta bort aktiva affärsprocesser eller affärsprocessmallar.

## <a name="task"></a>Uppgift
En affärsprocess består ofta av flera uppgifter. Vissa uppgifter kan slutföras i Dynamics 365 for Talent, såsom att granska interna kurserbjudanden. I detta fall markeras ett menyalternativ i fältet Uppgiftslänk. Andra uppgifter kan omfatta granska eller komplettera formulär på en webbplats. Genom att markerar URL:en i fältet Uppgiftslänk kan webbadressen anges. Du kan ange URL:er för både externa och interna webbplatser i det här fältet. Du kan också skapa uppgifter för aktiviteter som du slutför manuellt, till exempel granska tillgänglighet av alla strukturer. I detta fall krävs inte en uppgiftslänk. Denna flexibilitet låter dig spåra flera typer av uppgifter i en omfattande process.

Uppgifter kan tilldelas till en särskild arbetare eller till en befattning. Exempelvis ska en chef över kompensationer och förmåner alltid vara den person som utför en granskning av försäkringspremier.   När du skapar denna uppgift, välj befattning för tilldelningstypen och välj sedan chef över kompensationer och förmåner från listan. När processen startar tilldelas uppgiften till den anställde som har befattningen chef över kompensationer och förmåner. Du kan också tilldela en uppgift till en särskild arbetare genom att välja arbetare i fältet Tilldelningstyp och sedan välja rätt person.

Uppgiftens förfallodatum datum beror på måldatumet som anges i början av processen. Vissa uppgifter måste slutföras före måldatumet och vissa kan slutföras efter måldatumet.  När du definierar en uppgift anger du ett förfallodatum som är i relation till datumet i fältet Förfallodatum förskjutet från måldatum. Anta till exempel att chefen över kompensationer och förmåner måste utföra en granskning av försäkringspremier 10 dagar innan personalgranskningen är klar. Den skapade uppgiften kommer att ha ett förfallodatum i relation till måldatumet på -10. Om processen har startat 13 maj kommer uppgiften därför att förfalla 3 maj. Obs! Förfallodatum kan också justeras när processen startas.

Komplicerade uppgifter kanske kräver flera steg eller kräver att personen som utför uppgifter tillhandahåller ytterligare information. Du kan lägga till instruktioner till uppgiften och inkluderar RTF även för anvisningarna. Instruktionerna kan ge ytterligare information om hur du slutför uppgiften till den person som har tilldelats för att slutföra den.

## <a name="starting-a-process"></a>Starta en process
En process kan startas inom en affärsprocessmall genom att välja Starta process.  När en process startas skapas uppgifter för valda arbetare och/eller befattningar som definierats i de uppgifter som ingår i affärsprocessmallen. Ett förfallodatum kommer också att tilldelas varje uppgift genom att addera eller subtrahera förskjutningsdagar från måldatumet (se information om förskjutningsdagar under uppgiftsavsnittet). De aktiva affärsprocesserna kan visas på arbetsytan Affärsprocesser. 

## <a name="employee-self-service"></a>Anställd self-service
När en uppgift tilldelas en medarbetare, kan deras tilldelade uppgifter visas på sidan Självbetjäning för medarbetare. Medarbetare som har en affärsprocessuppgift tilldelad kan se uppgiften, dess beskrivning, anvisningar för att slutföra den och namnet på en kontaktperson och de kan öppna motsvarande Dynamics 365-sida eller webbsida från sidan Självbetjäning för medarbetare. Uppgifter kan markeras som pågår, annullerad eller slutförd.

## <a name="business-process-workspace"></a>Arbetsytan Affärsprocess
Personalansvariga kan visa de aktiva affärsprocesserna från arbetsytan Affärsprocesser. Arbetsytan visar alla aktiva processer och uppgifter som är kopplade till varandra. Den omfattande uppgiftslistan kan filtreras efter datum. Sidan innehåller även förfallna uppgifter och uppgifter som tilldelats personalansvariga. De kan också uppdatera statusen för alla uppgifter och vid behov tilldela om uppgifter för att låta den övergripande affärsprocessen gå vidare.

## <a name="my-business-processes-workspace"></a>Arbetsytan Mina affärsprocesser
Processägare kan visa aktiva affärsprocesser som tilldelas dem från arbetsytan Mina affärsprocesser. Arbetsytan visar alla aktiva processer och kopplade uppgifter som den användaren äger.  Den omfattande uppgiftslistan kan filtreras efter datum. Sidan innehåller även uppgifter som specifikt har tilldelats processägare. Processägaren kan även uppdatera statusen för alla uppgifter, samt tilldela om eventuella uppgifter.

## <a name="navigating-business-processes"></a>Navigerar till affärsprocesser
1. För att lägga till en affärsprocessmall, navigera till Affärsprocesser - Länkar - Administration av affärsprocesser.
   - a.   Ny kommer att skapa en ny mall.
   - b.   Kopiera från mall kopierar den valda mallen till en ny.
   - c.   Starta processen kommer starta den valda affärsprocessen, tilldela uppgifter och beräkna förfallodatum.  
2. Om du vill visa aktiva processer och tillhörande uppgifter, gå till arbetsytan Affärsprocesser.

