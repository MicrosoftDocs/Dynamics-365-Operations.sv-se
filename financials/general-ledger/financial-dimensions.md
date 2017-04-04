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
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Ekonomiska dimensioner

Den här artikeln beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.

Använd sidan Ekonomiska dimensioner om du vill skapa ekonomiska dimensioner som du kan använda som kontosegment för delade kontoplaner. Det finns två typer av ekonomiska dimensioner, anpassade dimensioner och enhetsbaserad dimensioner. Anpassade dimensioner delas av alla juridiska personer, och värdena anges och hanteras av användaren. Enhetsbaserade dimensioner är dimensioner vars värden definieras på andra ställen i systemet, till exempel kunder och butiker. Vissa enhetsbaserade dimensioner delas av alla juridiska personer och enhetsbaserade dimensioner är företagsspecifka. 

Använd formuläret  om du vill tilldela ytterligare egenskaper för varje ekonomisk dimension efter att du har skapat ekonomiska dimensioner. 

Men representerar juridiska personer utan att de juridiska personerna i Microsoft Dynamics 365 för operationer kan du använda ekonomiska dimensioner, ekonomiska dimensioner inte är utformat för att möta drifts- eller affärsbehov rättssubjekt. Enhetsintern redovisning-funktionerna i Microsoft Dynamics 365 för operationer är avsett att uppfylla de redovisningsposter som skapas av varje transaktion. 

Utvärdera dina arbetsprocesser i följande områden för att avgöra, innan du ställer in ekonomiska dimensioner som juridiska personer, om den här inställningen kommer att fungera i din organisation:

-   Lager
-   Försäljning och inköp mellan ekonomiska dimensioner och juridiska personer
-   Mmomsberäkning och rapportering
-   Driftsrapportering

Följande är exempel på begränsningar:

-   Du kan bara använda momsfunktioner med juridiska personer, inte med ekonomiska dimensioner.
-   En del rapporter inkluderar inte ekonomiska dimensioner, så du kan inte alltid rapportera per ekonomisk dimension, om inte dessa rapporter ändras.

**Custom dimensions** 

Om du vill skapa en användardefinierad ekonomisk dimension i fältet Använd värden från fältet &lt;dimension anpassade&gt;. Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden. Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck. Du kan även ange nummertecken (\#) och et-tecken (&) som platshållare för bokstäver och siffror som ändras varje gång ett dimensionsvärde. Använd ett nummertecken (\#) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav. 

**Exempel** 

Om du vill begränsa dimensionsvärdet på brev kopia och tre talen du anger CC -\#\#\# som Formatmask. Detta fält är tillgängligt om du markerar &lt;dimension anpassade &gt;i fältet Använd värden från fältet. 

**Dimensioner för enheten säkerhetskopior** 

Skapa ekonomiska enhetsdimensionen lagras, i fältet Använd värden från fältet välja en systemdefinierad enhet ska ekonomisk dimension baseras på. Värden för ekonomisk dimension skapas utifrån det här valet. Om du till exempel vill skapa dimensionsvärden för projekt väljer du Projekt. Ett dimensionsvärde skapas för varje projektnamnet. Sidan Dimensionsvärde visar värdena för enheten och om de innehåller företagsspecifika, företag för värdet. 

**Aktivera dimensioner** 

Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas någonstans förrän den har aktiverats. Du kan t.ex. inte lägga till en ekonomisk dimension till en kontostruktur förrän den ekonomiska dimensionen har aktiverats. Att klicka på aktivera kommer att uppdateras alla dimensioner med statusändringar. 

**Translations** 

Sidan översättning Text kan du ange text som ska visas på olika språk för den valda ekonomiska dimensionen. Sidan Huvudkontoöversättning är där du kan ange text som ska visas på olika språk för huvudkontot. 

**Legal entity overrides** 

Inte alla dimensioner som är giltiga för alla juridiska personer och vissa kanske bara relevanta för en viss tidsperiod. I det här scenariot kan åsidosättandet av juridisk person användas för att identifiera vilka företag som dimensionen ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.




