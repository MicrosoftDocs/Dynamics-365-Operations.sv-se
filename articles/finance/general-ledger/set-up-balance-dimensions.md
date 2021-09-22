---
title: Hur konfigurerar jag balanserande ekonomiska dimensioner?
description: I det här ämnet beskrivs alternativen för inställning och användning av funktionen Balanserande ekonomisk dimension.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: 188c15c4cb0c295a9fcbb08273ddb391fbc29e24
ms.sourcegitcommit: b4c78655f2ab4b0e7ead96dfb9cf087a18014253
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2021
ms.locfileid: "7468950"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Hur konfigurerar jag balanserande ekonomiska dimensioner?

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs alternativen för inställning och användning av funktionen Balanserande ekonomisk dimension.

## <a name="symptom"></a>Symptom

Det finns två alternativ för inställning av balanserade ekonomiska dimensioner. Det första alternativet är att använda fältet **Balanserande ekonomisk dimension** på konfigurationssidan **Redovisning** (**Redovisning \> Redovisningsinställningar \> Redovisning**). Det andra alternativet är att använda fältet **Kräv att dimensioner ska balanseras** på sidan **Ekonomiska dimensioner** (**Redovisning > Kontoplan \> Dimensioner \> Ekonomiska dimensioner**). I det här ämnet beskrivs skillnaden mellan dessa två alternativ.

## <a name="resolution"></a>Lösning

Organisationer använder vanligtvis balanserande dimensioner för att generera en balansräkning som är i balans med den ekonomiska dimensionsnivån. Om du aktiverar någon av dessa funktioner balanseras inte bokförda och obalanserade dimensioner. Du måste först registrera justeringsposter manuellt om du vill få balansräkningen i balans innan du aktiverar någon av de här funktionen.

De två alternativen är ömsesidigt uteslutande. Alternativet som används i din organisation bör baseras på företagets krav. Vi hör ofta om kunder som definierar den balanserande dimensionen i både redovisningsinställningarna och den ekonomiska dimensionsinställningen och sedan slutför en del av eller alla de ytterligare inställningar som krävs. De kan dock fortfarande inte bokföra på grund av en obalans på den ekonomiska dimensionsnivån.

I de följande avsnitten beskrivs de två alternativen och information om hur du ställer in dem.

### <a name="ledger--balancing-financial-dimension"></a>Redovisning - balanserande ekonomisk dimension

Den balanserande dimensionen på inställningssidan **Redovisning** används för att aktivera internredovisning. Följ stegen för att aktivera funktionen.

1. Bestäm vilken ekonomisk dimension som ska vara den balanserande dimensionen.

    - Med denna funktion kan du endast välja en ekonomisk dimension som balanserande dimension.
    - Välj ännu inte dimensionen på inställningssidan **Redovisning**.
    - Se till att balansräkningen redan är balanserad för den valda ekonomiska dimensionen.

2. Uppdatera kontostrukturen för den balanserande ekonomiska dimensionen.

    - Den balanserande ekonomiska dimensionen måste inkluderas i alla kontostrukturer som tilldelas redovisningen.
    - Den ekonomiska dimensionen får inte tillåta tomma i kontostrukturen. Denna begränsning garanterar att varje redovisningspost som bokförs i redovisningen innehåller ett värde för ekonomisk dimension. En tom dimension är inte giltig när balanserande dimensioner används.

3. På sidan **Konton för automatiska transaktioner** (**Redovisning \> Bokföringsinställningar \> Konton för automatiska transaktioner**), definiera internredovisningens huvudkonton för debet och kredit.
4. På inställningssidan **Redovisning** (**Redovisning \> Redovisningsinställningar \> Redovisning**), i fältet **Balanserande ekonomisk dimension** väljer du en ekonomisk dimension att använda för balansering.

Om den valda ekonomiska dimensionen inte balanseras när transaktioner registreras och bokförs, läggs de debet- eller kreditposter automatiskt till som krävs för att balansera redovisningsposten under bokföringen. Debet- och kreditredovisningskontona för internredovisningstransaktionen visas på den bokförda verifikationen i redovisningen. De kommer dock inte att visas på journalerna eller källdokumenten som redovisningsposterna har bokförts för.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Ekonomiska dimensioner – kräv att dimensionen balanseras

Även om den balanserande dimensionen på sidan **Ekonomiska dimensioner** normalt används av företag inom den offentliga sektorn, är funktionerna inte kopplade till någon konfigurationsnyckel för offentlig sektor. Eftersom det inte finns några begränsningar i systemet kan du använda den här funktionen även om din organisation inte är en enhet i den offentliga sektorn.

Denna funktion används normalt inom den offentliga sektorns kundbas eftersom den kräver att bokföringsdefinitioner används för att automatiskt balansera varje transaktion. Den använder inte debet- och kreditkonton som har definierats på sidan **Konton för automatiska transaktioner** för att automatiskt balansera redovisningsposterna. Om en redovisningspost inte balanseras på dimensionsnivå efter att bokföringsdefinitionerna har tillämpats, bokförs transaktionen inte, även om de interna debet- och kreditkontona har definierats.

Vi hör ofta om kunder som definierar den balanserande dimensionen i både redovisningsinställningarna och den ekonomiska dimensionsinställningen. I det här fallet använder systemet funktionen för ekonomiska dimensioner. Inställningen för balanserande dimensioner på den ekonomiska dimensionens nivå har prioritet vid bokföring. Bokföringen misslyckas om bokföringsdefinitionen inte skapar någon balanserad redovisningspost på ekonomisk dimensionsnivå.

Följ dessa steg för att aktivera användningen av en balanserande dimension på den ekonomiska dimensionsnivån.

1. Bestäm vilka ekonomiska dimensioner som ska vara de balanserande dimensionerna.

    - Du kan ställa in mer än en ekonomisk dimension som en balanserande dimension.
    - Ställ ännu inte in de ekonomiska dimensioner som måste balansera en transaktion på sidan **Ekonomiska dimensioner**.

2. Definiera bokföringsdefinitionerna för respektive typ av journal- eller källdokument som används av din organisation. Bokföringsdefinitioner använder redovisningskontona från en ej bokförd journal eller källdokument som "matchningskriterier". Bokföringsdefinitionen returnerar sedan de "genererade poster" som blir redovisningsposten. Om bokföringsdefinitionen är korrekt inställd inkluderar den genererade posten matchningskriteriets redovisningskonton samt ytterligare konton för att balansera redovisningsposten på dimensionsnivå. Mer information finns i [Bokföringsdefinitioner](posting-definitions.md). 
   
   Bokföringsdefinitioner stöds inte på alla typer av transaktioner. Bokföringsdefinitioner kan till exempel inte definieras för transaktioner som anges i den allmänna journalen eller journalen för anläggningstillgångar. Om en bokföringsdefinition inte kan definieras för en journal eller ett källdokument måste transaktionen balanseras manuellt med värdet för den ekonomiska dimensionen. Om till exempel en allmän journalpost görs och dimensionen Avdelning är den balanserande dimensionen, måste du se till att varje avdelnings värde är i balans.  Om dimensionen inte är balanserad för varje avdelningsvärde bokförs inte verifikationen förrän obalansen korrigeras genom att manuellt lägga till en intern debet eller kredit till verifikationen. 

    > [!IMPORTANT]
    > Om för många transaktioner måste balanseras manuellt bör du **inte** använda funktionen för balanserande dimension på sidan **Ekonomiska dimensioner**. I stället använder du funktionen för balanserande dimension på inställningssidan **Redovisning**.

3. När bokföringsdefinitioner har definierats kan de ekonomiska dimensionerna markeras som obligatoriska för balansering.

När du anger och bokför transaktioner anropas bokföringsdefinitionerna under bokföringen för att bestämma redovisningsposterna. Om de ekonomiska dimensionerna är balanserade sker validering efter att redovisningsposterna har fastställts. Om de ekonomiska dimensionerna inte är balanserade bokförs transaktionen inte och du får ett meddelande om att debet inte är lika med krediterna för en viss dimension.
