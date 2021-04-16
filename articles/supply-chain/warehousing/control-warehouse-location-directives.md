---
title: Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv
description: Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.
author: perlynne
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91c8df8a111132d75ec02b79912c66e02aef4ea6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831324"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.

De instruktioner som lagerarbetare på en mobil enhet bestäms av arbete mallar som du ställer in i Dynamics 365 Supply Chain Management för att definiera de olika lager och uppgifter. Arbetsmallar avgör hur arbetet utförs för varje lager. Genom att koppla en lagerplats direktiv att arbeta mallar, du kan bidra till att garantera att arbetet sker i särskilda fysiska områden i lager.

## <a name="work-templates"></a>Arbetsmallar

**Arbetsmallar** sidan låter dig definiera arbeten som måste utföras i lagret. Typiskt, warehouse arbeten består av ett par åtgärder: en lagerarbetare plockar upp lagersaldot på en plats och sedan lägger de plockade lager ned på en annan plats. 

Arbetsmallar består av ett sidhuvud och tillhörande ledningar. Varje mall för en viss *arbetsorder*. Många arbetsorder som är kopplade till källa dokument, t.ex. inköpsorder eller beställningar. Men andra arbetsordern typer utgör separata lager processer, såsom inventeras. *Arbetet pool-ID* låter dig att organisera arbetet i grupperna. 

Använd inställningarna i arbetet skärbordets definition för att avgöra när ett nytt arbete ska skapas. Du kan till exempel ange ett maximalt antal plocka rader och ett maximalt förväntade plocka tid. Om arbetet för en försäljning orderplockningen överskrider något av dessa värden, att arbetet är uppdelat i två delar.

Använd knappen **Arbetsuppgiftshuvudet delas** för att definiera när nya arbetsrubriker ska skapas i systemet. Om du till exempel vill skapa ett arbetshuvud för varje _ordernummer_, väljer du **Redigera fråga** i åtgärdsfönstret och lägger sedan till fältet **Ordernummer** till fliken **Sortera** i Frågeredigeraren. Fält som läggs till på fliken **Sortering** är tillgängliga för markering som *grupperingsfält*. Om du vill ange grupperade fält väljer du **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret och markera kryssrutan i kolumnen för varje fält som du vill använda som grupperingsfält **Gruppera efter detta fält**.

Arbetet linjerna representerar det fysiska uppgifter som krävs för att bearbeta. För exempelvis ett utgående lager, det kan vara en rad för att plocka upp föremål i lagerstället och en annan rad för dessa poster till en mellanlagringsplats. Det kan alltså vara en extra rad för plockning från mellanlagring och en annan rad för att objekten i en lastbil som en del av laddningen. Du kan ställa in ett *direktiv kod* på arbetsmall linjer. Ett direktiv som är kopplad till en plats och därför hjälper till att säkra att lagerarbetet bearbetas på rätt plats i lagret.

Du kan ställa in en fråga för att kontrollera när en särskild mall används. Du kan till exempel ställa in en begränsning så att en viss mall kan användas för arbete i ett särskilt lager. Alternativt kan du ha flera mallar som används för att skapa arbete för utgående orderhantering, beroende på försäljningen ursprung. Systemet använder fältet **Sekvensnummer** för att avgöra den ordning som de tillgängliga arbetsmallarna värderas i. Därför bör du, om du har en specifik fråga för en specifik arbetsmall, tilldela den ett lågt ordningsnummer. Frågan kommer sedan att utvärderas innan andra, mer allmänna frågor.

> [!NOTE]
> Om du vill förhindra att ordningen för mallar för arbetsmallar skrivs över automatiskt *sekvensnummer* efter att en mall har tagits bort, aktivera funktionen *Bevara sekvensnummer för arbetsmallen vid borttagning* i [Funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

För att stoppa eller pausa en arbetsprocess kan du använda **stopp** på arbetet. I detta fall arbetstagare som utför arbetet inte bli ombedd att utföra nästa rad steg. Gå vidare till nästa steg, att arbetstagaren eller annan arbetstagare måste välja igen. Du kan även ta uppdrag inom ett arbete med en annan *klass-ID* för arbetsmallen.

## <a name="location-directives"></a>Platsdirektiv

Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager. Exempelvis i en försäljningsorder transaktion, en plats direktiv bestämmer var objekten ska plockas, och där plockade artiklar kommer att användas. Plats direktiven består av ett sidhuvud och därtill hörande linjer, och du skapar dem på **plats direktiven** sida.

På huvudet, varje plats direktiv måste vara associerad med en *arbetsorder typ* som anger typ av lagertransaktionen som direktivet kommer att användas för, såsom beställningar, återfyllnad, eller råmaterial plockning. Den *arbetstyp* anger platsen direktiv kommer att användas för plockning eller arbete, eller för vissa andra lagret process, såsom inventering eller lager status ändras. Du måste också ange en *ort* och ett *lager*. Ett *direktiv kod* som du anger på skärbordet kan användas för att länka placering direktiv till en eller flera arbetsmallar. 

För arbete mallar, du kan sätter upp en fråga att avgöra när en viss plats direktiv används. Du kan till exempel ange att när e-handeln är ursprunget till en försäljningsorder, lager måste plockas upp från ett särskilt område i lagret. Systemet använder fältet **Löpnummer** för att avgöra den ordning som de tillgängliga platsdirektiven värderas i.

Platsdirektivraderna anger ytterligare begränsningar för tillämpningen av reglerna för platssökning. Du kan ange en minsta kvantitet och en maximal kvantitet att direktivet bör gälla, och du kan ange att direktivet bör vara en viss lagerenhet. Till exempel, om enheten är pallar, poster i pallar kan placeras i en specifik placering. Du kan också ange om kvantiteten kan delas upp över flera platser. Precis som platsdirektivrubriken har varje platsdirektivrad ett serienummer som bestämmer den ordning som raderna värderas i.

Platsdirektiv har en ytterligare detaljnivå: *platsdirektivåtgärder*. Du kan definiera flera plats direktiv åtgärder för varje linje. Återigen används ett ordningsnummer för att avgöra i vilken ordning åtgärderna bedöms. På den här nivån kan du skapa en fråga för att definiera hur du hittar den bästa platsen i lagerstället. Du kan också använda fördefinierade **inställningar för strategi för** att finna en optimal placering.

Mer information om hur du skapar och konfigurerar platsdirektiv finns i [skapa ett platsdirektiv](create-location-directive.md).

### <a name="how-location-directives-work"></a>Hur platsdirektiv fungerar

Platsdirektiv bestämmer *var* artiklar ska plockas och *var* de ska placeras. Systemet utvärderar ett platsdirektiv mot varje arbetsrad och väljer sedan en platsbaserad på arbetsradens detaljer. Systemet hittar först alla platsdirektiv som matchar en viss arbetsrad (t.ex. för det korrekta lagerstället och matchar frågan). Därefter utvärderas de direktiv som har hittats sekventiellt.

> [!NOTE]
> Det finns särskilda fall där plockningsplatsen eller artikelns lagerställe har valts på förhand. T.ex. under _inköpsregistrering_, är den första plockningen alltid från den plats där registreringen sker. Ett annat exempel är *inventeringsrörelse efter mall*, där lagerarbetaren väljer plockningsplats, och endast inlagringsplatser hittas genom platsdirektiv.

## <a name="additional-resources"></a>Ytterligare resurser

- Video: [konfiguration för lagerstyrning djupdykning](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Hjälpavsnitt: [Skapa platsdirektiv](create-location-directive.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]