---
title: Ekonomiska dimensioner
description: "Den här artikeln beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5ee2d132f0b23ceec2a79ee6b0ee33862d6a0518
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="financial-dimensions"></a>Ekonomiska dimensioner

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.

Använd sidan Ekonomiska dimensioner om du vill skapa ekonomiska dimensioner som du kan använda som kontosegment för delade kontoplaner. Det finns två typer av ekonomiska dimensioner, anpassade dimensioner och enhetsbaserad dimensioner. Anpassade dimensioner delas av alla juridiska personer, och värdena anges och hanteras av användaren. Enhetsbaserade dimensioner är dimensioner vars värden definieras på andra ställen i systemet, till exempel kunder och butiker. Vissa enhetsbaserade dimensioner delas av alla juridiska personer och enhetsbaserade dimensioner är företagsspecifka. 

Använd formuläret  om du vill tilldela ytterligare egenskaper för varje ekonomisk dimension efter att du har skapat ekonomiska dimensioner. 

Även om du kan använda ekonomiska dimensioner för att representera juridiska personer utan att skapa juridiska personer i Microsoft Dynamics 365 for Operations, är ekonomiska dimensioner inte utformade för att tillgodose juridiska personers verksamhetsbehov. Internredovisningsfunktionen i Microsoft Dynamics 365 for Operations har utformats att endast fokusera på de redovisningsposter som skapas av respektive transaktion. 

Utvärdera dina arbetsprocesser i följande områden för att avgöra, innan du ställer in ekonomiska dimensioner som juridiska personer, om den här inställningen kommer att fungera i din organisation:

-   Lager
-   Försäljning och inköp mellan ekonomiska dimensioner och juridiska personer
-   Mmomsberäkning och rapportering
-   Driftsrapportering

Följande är exempel på begränsningar:

-   Du kan bara använda momsfunktioner med juridiska personer, inte med ekonomiska dimensioner.
-   En del rapporter inkluderar inte ekonomiska dimensioner, så du kan inte alltid rapportera per ekonomisk dimension, om inte dessa rapporter ändras.

**Anpassade dimensioner** 

Om du vill skapa en användardefinierad ekonomisk dimension väljer du &lt; Anpassad dimension &gt; i fältet Använd värden från. Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden. Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck. Du kan även ange nummertecken (\#) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång ett dimensionsvärde skapas. Använd ett nummertecken (\#) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav. 

**Exempel** 

Om du vill begränsa dimensionsvärdet till bokstäverna CC och tre siffror anger du CC-\#\#\# som formatmask. Det här fältet är bara tillgängligt när du väljer &lt; Anpassad dimension &gt; i fältet Använd värden från. 

**Enhetsstödda dimensioner** 

Om du vill skapa en enhetsstödd ekonomisk dimension väljer du en systemdefinierad enhet på vilken den ekonomiska dimensionen ska baseras i fältet Använd värden från. Värden för ekonomisk dimension skapas utifrån det här valet. Om du till exempel vill skapa dimensionsvärden för projekt väljer du Projekt. Ett dimensionsvärde skapas för varje projektnamnet. Sidan Dimensionsvärde visar värdena för enheten och om de innehåller företagsspecifika, företag för värdet. 

**Dimensionsaktivering** 

Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas någonstans förrän den har aktiverats. Du kan t.ex. inte lägga till en ekonomisk dimension till en kontostruktur förrän den ekonomiska dimensionen har aktiverats. Att klicka på aktivera kommer att uppdateras alla dimensioner med statusändringar. 

**Översättningar** 

Sidan för Textöversättningar låter dig ange text som ska visas på olika språk för den valda ekonomiska dimensionen. Sidan Huvudkontoöversättning är där du kan ange text som ska visas på olika språk för huvudkontot. 

**Åsidosättande av juridisk person** 

Alla dimensioner är inte giltiga för alla juridiska personer, och några kanske bara är relevanta under en viss tidsperiod. I det här scenariot kan åsidosättandet av juridisk person användas för att identifiera vilka företag som dimensionen ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.






