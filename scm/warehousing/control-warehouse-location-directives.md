---
title: Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv
description: "Denna artikel beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9d0ad4f64ee84da4e90dfa1525ebb5ff9fec4063
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv

[!include[banner](../includes/banner.md)]


Denna artikel beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.

De instruktioner som lagerarbetare tar emot på en mobil enhet bestäms av de arbetsmallar som du anger i Microsoft Dynamics 365 for Operations för att definiera de olika lagerprocesserna och -uppgifterna. Arbetsmallar avgör hur arbetet utförs för varje lager. Genom att koppla en lagerplats direktiv att arbeta mallar, du kan bidra till att garantera att arbetet sker i särskilda fysiska områden i lager.

## <a name="work-templates"></a>Arbetsmallar
**Arbetsmallar** sidan låter dig definiera arbeten som måste utföras i lagret. Typiskt, warehouse arbeten består av ett par åtgärder: en lagerarbetare plockar upp lagersaldot på en plats och sedan lägger de plockade lager ned på en annan plats. 

Arbetsmallar består av ett sidhuvud och tillhörande ledningar. Varje mall för en viss *arbetsorder*. Många arbetsorder som är kopplade till källa dokument, t.ex. inköpsorder eller beställningar. Men andra arbetsordern typer utgör separata lager processer, såsom inventeras. *Arbetet pool-ID *låter dig att organisera arbetet i grupperna. 

Inställningarna i arbetet skärbordets definition kan användas för att avgöra när ett nytt arbete ska skapas. Du kan till exempel ange ett maximalt antal plocka rader och ett maximalt förväntade plocka tid. Om arbetet för en försäljning orderplockningen överskrider något av dessa värden, att arbetet är uppdelat i två delar. 

Arbetet linjerna representerar det fysiska uppgifter som krävs för att bearbeta. För exempelvis ett utgående lager, det kan vara ett arbete för att plocka upp föremål i lagerstället och en annan linje för dessa poster till en mellanlagringsplats. Det kan alltså vara en extra rad för plockning från mellanlagring och en annan linje för att objekten i en lastbil som en del av laddningen. Du kan ställa in ett *direktiv kod *på arbetsmall linjer. Ett direktiv som är kopplad till en plats och därför hjälper till att säkra att lagerarbetet bearbetas på rätt plats i lagret. 

Du kan ställa in en fråga för att kontrollera när en särskild mall används. Du kan till exempel ställa in en begränsning så att en viss mall kan användas för arbete i ett särskilt lager. Alternativt kan du ha flera mallar som används för att skapa arbete för utgående orderhantering, beroende på försäljningen ursprung. Systemet använder fältet **Sekvensnummer** för att avgöra den ordning som de tillgängliga arbetsmallarna värderas i. Därför bör du, om du har en specifik fråga för en specifik arbetsmall, tilldela den ett lågt ordningsnummer. Frågan kommer sedan att utvärderas innan andra, mer allmänna frågor. 

För att stoppa eller pausa en arbetsprocess kan du använda **stopp** på arbetet. I detta fall arbetstagare som utför arbetet inte bli ombedd att utföra nästa rad steg. Gå vidare till nästa steg, att arbetstagaren eller annan arbetstagare måste välja igen. Du kan även ta uppdrag inom ett arbete med en annan *klass-ID *för arbetsmallen.

## <a name="location-directives"></a>Platsdirektiv
Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager. Exempelvis i en försäljningsorder transaktion, en plats direktiv bestämmer var objekten ska plockas, och där plockade artiklar kommer att användas. Plats direktiven består av ett sidhuvud och därtill hörande linjer, och du skapar dem på **plats direktiven** sida. 

På huvudet, varje plats direktiv måste vara associerad med en *arbetsorder typ *som anger typ av lagertransaktionen som direktivet kommer att användas för, såsom beställningar, återfyllnad, eller råmaterial plockning. Den *arbetstyp *anger platsen direktiv kommer att användas för plockning eller arbete, eller för vissa andra lagret process, såsom inventering eller lager status ändras. Du måste också ange en *ort *och ett *lager*. Ett *direktiv kod *som du anger på skärbordet kan användas för att länka placering direktiv till en eller flera arbetsmallar. 

För arbete mallar, du kan sätter upp en fråga att avgöra när en viss plats direktiv används. Du kan till exempel ange att när e-handeln är ursprunget till en försäljningsorder, lager måste plockas upp från ett särskilt område i lagret. Systemet använder fältet **Löpnummer** för att avgöra den ordning som de tillgängliga platsdirektiven värderas i. 

Platsdirektivraderna anger ytterligare begränsningar för tillämpningen av reglerna för platssökning. Du kan ange en minsta kvantitet och en maximal kvantitet att direktivet bör gälla, och du kan ange att direktivet bör vara en viss lagerenhet. Till exempel, om enheten är pallar, poster i pallar kan placeras i en specifik placering. Du kan också ange om kvantiteten kan delas upp över flera platser. Precis som platsdirektivrubriken har varje platsdirektivrad ett serienummer som bestämmer den ordning som raderna värderas i. 

Platsdirektiv har en ytterligare detaljnivå: *platsdirektivåtgärder*. Du kan definiera flera plats direktiv åtgärder för varje linje. Återigen används ett ordningsnummer för att avgöra i vilken ordning åtgärderna bedöms. På den här nivån kan du skapa en fråga för att definiera hur du hittar den bästa platsen i lagerstället. Du kan också använda fördefinierade **inställningar för strategi för**att finna en optimal placering.

### <a name="example-of-the-use-of-location-directives"></a>Exempel på användning av platsen direktiven

I det här exemplet kommer vi att överväga en inköpsorder där placering direktiv måste hitta ledig kapacitet inom ett lager för inventarier som just registrerats vid mottagningsplatsen. Först vill vi försöka hitta ledig kapacitet inom lagret genom att konsolidera med befintliga lagersaldot. Om konsolideringen är inte möjligt, då vill vi att hitta en tom plats. 

För detta scenario, måste vi definiera två plats direktiv åtgärder. Den första åtgärden i sekvensen måste **konsolidera** strategi, och den andra ska använda den **tomma platsen med några inkommande arbete** strategi. Om vi definierar en tredje handlingsplan för att hantera ett överskott scenario två utfall är möjliga när det inte finns något mer kapacitet i lagret: arbete kan skapas även om inga lagerplatser definieras eller arbete processen kan misslyckas. Resultatet bestäms av inställningar på **plats direktiv fel** sida, där du kan bestämma om du vill välja **stopp på plats direktiv fel** alternativ för varje arbetsorder.




