---
title: Ekonomiska dimensioner
description: "Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: e82d53b3f6b4c8d3e2363f26576331e1d03434d9
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Ekonomiska dimensioner
<a id="financial-dimensions" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.

Använd sidan **Ekonomiska dimensioner** om du vill skapa ekonomiska dimensioner som du kan använda som kontosegment för delade kontoplaner. Det finns två typer av ekonomiska dimensioner: anpassade dimensioner och enhetsbaserad dimensioner. Anpassade dimensioner delas av alla juridiska personer, och värdena anges och hanteras av användaren. För enhetsbaserade dimensioner definieras värden på andra ställen i systemet, till exempel kunder och butiker. Vissa enhetsbaserade dimensioner delas av alla juridiska personer och enhetsbaserade dimensioner är företagsspecifka. 

Använd formuläret om du vill tilldela ytterligare egenskaper för varje **Värden för ekonomiska dimensioner** efter att du har skapat ekonomiska dimensioner. 

Du kan använda ekonomiska dimensioner som representerar juridiska personer. Du behöver inte skapa de juridiska personerna i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Ekonomiska dimensioner är inte emellertid avsedda för för juridiska personers drift- eller affärskrav. Internredovisningsfunktionen i Finance and Operations har utformats att endast fokusera på de redovisningsposter som skapas av respektive transaktion. 

Utvärdera dina arbetsprocesser i följande områden för att avgöra, innan du ställer in ekonomiska dimensioner som juridiska personer, om den här inställningen kommer att fungera i din organisation:

- Lager
- Försäljning och inköp mellan ekonomiska dimensioner och juridiska personer
- Mmomsberäkning och rapportering
- Driftsrapportering

Nedan följer några av begränsningarna:

- Du kan bara använda momsfunktioner med juridiska personer, inte med ekonomiska dimensioner.
- Vissa rapporter omfattar inte ekonomiska dimensioner. Därför kan du behöva ändra rapporterna om du vill rapportera per ekonomiska dimension.

## Anpassade dimensioner
<a id="custom-dimensions" class="xliff"></a>

Om du vill skapa en användardefinierad ekonomisk dimension väljer du fältet **Använd värden från** och **&lt; Anpassad dimension &gt;**. Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden. Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck (-). Du kan även ange nummertecken (\#) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång ett dimensionsvärde skapas. Använd ett nummertecken (\#) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav. Det här fältet för formatmask är bara tillgängligt när du väljer **&lt; Anpassad dimension &gt;** i fältet **Använd värden från**.

**Exempel**

Om du vill begränsa dimensionsvärdet till bokstäverna "CC" och tre siffror anger du **CC-\#\#\#** som formatmask.

## Enhetsstödda dimensioner
<a id="entity-backed-dimensions" class="xliff"></a>

Om du vill skapa en enhetsstödd ekonomisk dimension väljer du en systemdefinierad enhet på vilken den ekonomiska dimensionen ska baseras i fältet **Använd värden från**. Värden för ekonomisk dimension skapas utifrån den här entiteten. Om du till exempel vill skapa dimensionsvärden för projekt väljer du **Projekt**. Ett dimensionsvärde skapas sedan för varje projektnamnet. Sidan **värden för ekonomiska dimensioner** visar värdena för entiteten. Om dessa värden är företagsspecifika visar sidan också företaget.

## Dimensionsaktivering
<a id="activating-dimensions" class="xliff"></a>

När du aktiverar en ekonomisk dimension uppdateras registret så att det inkluderar namnet på den ekonomiska dimensionen. Borttagna dimensioner raderas. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension. Men en ekonomisk dimension kan inte utnyttjas någonstans tills den har aktiverats. Du kan t.ex. inte lägga till en ekonomisk dimension till en kontostruktur förrän den ekonomiska dimensionen har aktiverats. När du klickar på **aktivera**, uppdateras alla dimensioner och visar statusändringar. 

## Översättningar
<a id="translations" class="xliff"></a>

På sidan **textöversättning** kan du ange text för den valda ekonomiska dimensionen på olika språk. På sidan **Huvudkontoöversättning** kan du ange text för huvudkontot på olika språk. 

## Juridisk person åsidosätter
<a id="legal-entity-overrides" class="xliff"></a>

Alla dimensioner är inte giltiga för alla juridiska personer. Vissa dimensioner är dessutom endast relevanta för en viss period. I dessa fall kan du använda avsnittet **Juridisk person åsidosätter** för att identifiera vilka företag som dimensionen ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.

## Ta bort ekonomiska dimensioner
<a id="deleting-financial-dimensions" class="xliff"></a>

För att upprätthålla datans referensintegritet kan ekonomiska dimensioner sällan tas bort. Om du försöker ta bort en ekonomisk dimension utvärderas följande kriterier:

- Har den ekonomiska dimensionen använts på bokförda eller ej bokförda transaktioner eller någon typ av dimensionsvärdekombination?
- Är den ekonomiska dimensionen i en aktiv kontostruktur, avancerad regelstruktur, eller ekonomisk dimension angiven?
- Ingår den ekonomiska dimensionen i standardformat för integrering av ekonomisk dimension?
- Har den ekonomiska dimensionen ställts in som standarddimension?

Du kan inte radera den ekonomiska dimensionen om något av villkoren är uppfyllda.

