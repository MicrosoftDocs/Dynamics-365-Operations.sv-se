---
title: Arbeta med förinställda stilar
description: I det här avsnittet beskrivs hur du arbetar med förinställda stilar i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1bd8f6e31afa300c5e7687a657ae2807995af8d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006320"
---
# <a name="work-with-style-presets"></a>Arbeta med förinställda stilar

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du arbetar med förinställda stilar i Microsoft Dynamics 365 Commerce webbplatsskapare.

## <a name="overview"></a>Översikt

En format för inställning är en lagrad uppsättning av alla redigeringsbara formatmallar i en webbplatstema. Du kan använda den för att omedelbart ändra utseendet på en webbplats från webbplatsskaparen. Förinställningar av stil låter Commerce webbplatsskapare snabbt ändra, förhandsgranska och aktivera en uppsättning av stilvärden på sin webbplats utan att behöva använda sammanhängande formatmallar (CSS) eller distribuera teman. Teckensnittsstilar, knappformat och webbplatsfärger är typiska exempel på formatvariabler som kan hanteras via format för inställningar.

Den uppsättning med formatvariabler som är tillgänglig på en plats bestäms av tema- och modulbiblioteket som distribueras till platsens innehavare. I Dynamics 365 Commerce Online Software Development Kit (SDK) kan utvecklare använda så många (eller så få), redigeringsbara formatmallar som de behöver för ett visst tema. Genom att aktivera fler formatvariabler kan en affärsutvecklare lägga till färdiga alternativ om webbplatsformat i händerna på webbplatsskaparna. Därför kan icke-utvecklare uppdatera och förhandsgranska webbplatsformat med hjälp av verktygen. Funktionen är också användbar i alla scenarier där direkta ändringar av teman eller CSS orsakar onödiga omkostnader.

Teman där de formatbaserade variablerna för redigering är aktiverade kräver ett standard inställningsformat. De kan också inkludera fler förinställda alternativ som en del av ett distribuerat temapaket. Ett tema kan till exempel distribueras med en enda standardinställning av typen "modern ljus". Alternativt kan det innefatta ytterligare alternativ för inställning av formatmallar förutom standardinställningen, till exempel "modernt mörker", "vintage ljus" eller "vintage mörk". Dessa inbyggda förinställda teman skapas av utvecklare och kan användas som utgångspunkter för nya webbplatsdesigner.

I webbplatsskaparen kan författare välja bland ett temas inbyggda förinställningar, eller så kan de skapa egna format för inställningar och anpassningar genom att använda de aktiverade variablerna. Ett inställningsformat kan förhandsgranskas i webbplatsskaparen innan det aktiveras på den aktiva webbplatsen. När en författares formatändringar har granskats, kan inställningsformat anges till "aktiv" för den aktiva webbplatsen.

## <a name="preview-a-style-preset"></a>Förhandsgranska ett inställningsformat

Om du vill förhandsgranska ett inställningsformat i webbplatsskaparen följer du stegen nedan.

1. I vänster navigeringsfönster för din webbplats, gå till **Webbplatsinställningar \> Design**.
1. På fliken **förinställda stilar** längst upp i designredigeraren, i listan **Tillgängliga förinställningar** välj en förinställning och välj sedan **Vy** för att gå till förinställningsredigeraren.

    Om det för närvarande inte finns några förinställningar i listan **Tillgängliga förinställningar**, se [Skapa ett anpassat förinställningsformat](#create-a-custom-style-preset) för information om hur du skapar ett anpassat förinställningsformat.

    > [!NOTE]
    > För inställningar som ingick i temat indikeras med en **inbyggd** skylt. Dessa inbyggda förinställningar är skrivskyddade. Om du vill kopiera en inbyggd för inställning som en ny anpassningsbar för inställning väljer du ellipsknappen (**...**) för inställningen och väljer **Spara som**.

1. Klicka på **förhandsversion** i kommandofältet.
1. Välj en URL från din webbplats som du vill använda för att förhandsgranska formatmallen för inställningar och välj sedan **OK**.
1. Välj den leverantörsspecifika och språkspecifika URL-varianten som ska förhandsgranskas genom att välja variantens namn. Ett nytt fönster för förhandsgranskningswebbläsaren öppnas, där valt inställningsformat används på den angivna sidan.

> [!NOTE]
> URL:en för förhandsgranskning är beständig och autentiserad. Därför kan du kopiera, klistra in och skicka den till andra autentiserade medarbetare för granskning innan du ställer in den på "aktiv" på din aktiva webbplats. URL:en för förhandsgranskning är också användbar när du vill kontrollera stilar på olika enheter, i olika webbläsare och på olika skärmar.

> [!TIP]
> När du redigerar ett inställningsformat kan det vara bra att låta förhandsgranskningsfönstret vara öppet i ett separat webbläsarfönster, så att du snabbt kan validera dina ändringar. När du har sparat ändringarna i en förinställning uppdaterar du det öppna fönstret för förhandsgranskning av webbläsare för att validera användarupplevelsen.

## <a name="create-a-custom-style-preset"></a>Skapa ett anpassat inställningsformat

Om du vill skapa ett anpassat inställningsformat i webbplatsskaparen följer du stegen nedan.

1. I vänster navigeringsfönster för din webbplats, gå till **Webbplatsinställningar \> Design**.
1. På fliken **förinställda stilar** längst upp på designredigeraren, i kommandofältet väljer du **Ny förinställning**.
1. Ange ett namn på och en beskrivning för den nya förinställningen och välj sedan **Spara**. En ny anpassningsbar förinställning skapas som använder temats standardvärden som utgångspunkt.

> [!NOTE]
> Du kan också skapa en ny anpassad inställningsformat från en befintlig för inställning genom att markera ellipsknappen (**...**) för inställningen och sedan välja **Spara som**. Du kan också välja **Spara som** i kommandofältet i för inställningsredigeraren.

## <a name="modify-global-and-module-type-style-values"></a>Ändra globala format och värden för modultypformat

Vissa av temats formatvariabler delas mellan olika modultyper. Dessa formatvariabler kallas för *globala* formatvariabler. Exempel på detta är primära webbplatsfärger, standardstilar för teckensnitt och knappformat. Genom att ställa in globala variabler kan du ändra utseendet på många olika typer av moduler.

Vissa formatvärden kan vara unika för en modultyp, eller också måste ett globalt standardvärde åsidosättas. Om en webbplats tema har implementerat variabler för modultypen kan webbplatsskaparen anpassa formatet för en modultyp oberoende av de globala inställningarna. En modultyps variabler kan antingen utöka eller åsidosätta variabler i det globala formatet i ett tema.

> [!NOTE]
> Hierarkin med formatvärden på en webbplats fungerar på följande sätt. Formatvärden som visas längre fram till höger åsidosätter formatvärden till vänster om dem.
>
> Standardvärden för tema \< Globala formatvärden \< Formatvärden av modultyp \< CSS-åsidosättning

Gör så här om du vill ändra globala formatvärden eller modultyp i webbplatsskaparen.

1. I vänster navigeringsfönster för din webbplats, gå till **Webbplatsinställningar \> Design**.
1. På fliken **formatinställningar** längst upp i designredigeraren väljer du **Visa** för att gå med alla inställningsformat till förinställningsredigeraren.
1. Välj **Förhandsgranska** och följ sedan URL-urvalet för att öppna en förhandsgranskning i helskärm av din förinställning. Lämna det här fönstret för förhandsgranskning öppet.
1. I förinställningsredigeraren, välj **Redigera** uppe till höger.
1. Använd formatvariabelkontrollerna i redigeraren för att ändra vissa globala formatvärden.
1. Längst upp i redigeraren, på fliken **Moduler** till höger om fliken **Global** välj en modultyp som måste formateras.
1. Använd formatkontrollerna för att ändra vissa värden för modultypen.
1. När du är redo att förhandsgranska ändringarna väljer du **Spara** i kommandofältet.
1. Gå tillbaka till det öppna fönstret för förhandsgranskning och uppdatera det. Förhandsgranskningen i hela webbläsaren är användbar när du vill kontrollera ändringar av format i olika visningars brytpunkter, i olika webbläsare och på olika datorplattformar.
1. När alla ändringar har slutförts och validerats väljer du **Slutför redigering** längst upp till höger i redigeraren.

> [!NOTE]
> Om du redigerar den formatinställning som är aktiv på din webbplats visas ett blått **aktivt** märke i redigeraren. Det här aktivitetsfältet anger att förinställningen är aktiv på webbplatsen. Om du ändrar den aktiva för inställningen väljer du **publicera** om du vill skicka ändringarna till din aktiva webbplats.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Aktivera en ny formatinställning som är aktiv på din aktiva webbplats

Om du vill ställa in en formatinställning som ny aktiv för inställning på webbplatsen följer du stegen nedan.

- Välj knappen **Ange som aktiv** på något av följande ställen:

    - Kommandofältet i redigeraren för formatinställning
    - Ellipsknappen (**...**) för alla tillgängliga för inställningar i huvudvyn på fliken **formatinställningar** på **webbplatsinställningar \> design**

De förinställda värdena för för inställningen görs aktiva på din offentliga webbplats.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en logotyp](add-logo.md)

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägga till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)
