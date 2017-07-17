---
title: "Uppgiftsinspelare och hjälp för kassa"
description: "Det här avsnittet beskriver hur du använder uppgiftsinspelaren i Retail Modern POS och molnbaserad kassa."
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: 41
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 007a7e8a34f3f5a2d0d18eb3955822a8fd8bdd0a
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# Uppgiftsinspelare och hjälp för kassa
<a id="task-recorder-and-help-for-pos" class="xliff"></a>

Det här avsnittet beskriver hur du använder uppgiftsinspelaren i Retail Modern POS och molnbaserad kassa.

Översikt
<a id="overview" class="xliff"></a>
--------

Uppgiftsinspelning i Retail Modern POS eller Cloud POS är en ny lösning som har skapats med fokus på hög tillgänglighet. Det ger ett flexibelt gränssnitt för programprogrammering (API) för utökningsbarhet och sömlös integrering med företagsprocessinspelningar. Dessutom har uppgiftsinspelarintegrering med affärsprocessmodellerarverktyget (BPM) i Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) framhävts. Användare kan därför fortsätta framställa detaljerade affärsprocessdiagram från inspelningar i syfte att analysera och utforma sina program.

## Arkitektur
<a id="architecture" class="xliff"></a>
Uppgiftsinspelningen kan registrera användaråtgärder i klienten med exakt återgivning. Varje kontroll har utrustats för att meddela utförandet av en användaråtgärd till uppgiftsinspelaren. Kontrollen meddelar uppgiftsinspelaren att en händelse har inträffat och vidarebefordrar all relevant information om motsvarande användaråtgärd i realtid. Utifrån denna information kan uppgiftsinspelaren registrera typen av användaråtgärd (till exempel klick, värde eller navigering) och all information som är relaterad till användaråtgärden (t.ex. indata-värde och typ, formulärssammanhang eller postsammanhang). Uppgiftsinspelaren förser informationen med tillräckligt mycket detaljer för att garantera att en uppspelning av inspelningen kan utföra de inspelade åtgärderna precis så som användaren har utfört dem. (Uppspelningsfunktionen har ännu inte implementerats i Retail modern POS eller Cloud POS.)

## Standardkonfiguration
<a id="basic-configuration" class="xliff"></a>
Följ dessa steg om du vill aktivera uppgiftsinspelning för kassan.

1.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparater**.
2.  Klicka på registret för att aktivera uppgiftsinspelningen.
3.  På fliken **Registrera** på snabbfliken **Allmänt**, ange alternativet **"Aktivera uppgiftsinspelning** som **Ja**.
4.  Klicka på **Spara**.
5.  Gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
6.  Markera jobbet **Register (1090)** och klicka sedan på **Kör nu**.

## Skapa en inspelning
<a id="create-a-recording" class="xliff"></a>
Följ dessa steg för att skapa en ny inspelning med hjälp av uppgiftsinspelaren.

1.  Starta Retail Modern POS eller Cloud POS och logga in.
2.  På sidan **Inställningar**, i avsnittet **Uppgiftsinspelare** klickar du på **Öppna uppgiftsinspelaren**. Sidan **Uppgiftsinspelare** visas. Du kan klicka på knappen **Stäng** (**X**) i det övre högra hörnet för att stänga fönstret **Uppgiftsinspelare** innan du påbörjar en ny inspelning. Upprepa steg 2 för att öppna fönstret.
[![Fönstret Uppgiftsinspelare](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3.  Ange ett namn och en beskrivning för inspelningen och klicka sedan på **Starta**. Inspelningssessionen börjar så fort du klickar på **Starta**.

**Obs!** om du klickar på knappen **Stäng** (**X**) i det övre högra hörnet när inspelningen pågår, stängs fönstret **Uppgiftsinspelare**, men inspelningssessionen avslutas inte. Om du vill öppna fönstret Uppgiftsinspelare, klicka då på knappen **Hjälp** (frågetecken) överst på skärmen. 

[![Frågetecken](./media/help.jpg)](./media/help.jpg)

4.  När du klickar på **Starta** växlar Uppgiftsinspelaren till inspelningsläget. Fönstret **Uppgiftsinspelare** visar information och kontroller som är relaterade till inspelningsprocessen.
5.  Utför de åtgärder som du vill utföra i Retail Modern POS- eller Cloud POS-användargränssnittet (UI).
6.  Klicka på **Stopp** för att avsluta inspelningssessionen.

## Hämtningsalternativ
<a id="download-options" class="xliff"></a>
När du avslutar inspelningssessionen visas ett flertal alternativ som gör att du kan hämta din inspelning. 
[![Hämtningsalternativ](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### Spara på datorn
<a id="save-to-this-pc" class="xliff"></a>

Du kan använda inspelningspaketet för att spela upp en uppgiftsguide, bibehålla inspelningen eller redigera kommentarerna i inspelningen. (Denna funktion har ännu inte implementerats i Retail Modern POS eller Cloud POS.)

### Exportera som Word-dokument
<a id="export-as-word-document" class="xliff"></a>

Du kan spara inspelningen som ett Microsoft Word-dokument. Dokumentet innehåller inspelade steg och de skärmdumpar som har registrerats.

### Spara som utvecklingsregistrering
<a id="save-as-developer-recording" class="xliff"></a>

Inspelningens råformatfil kommer att vara till stor nytta för utvecklingsscenarier som exempelvis generering av testkoder. (Den här funktionen är inte implementerad ännu.)

## Inspelningskontroller
<a id="recording-controls" class="xliff"></a>
### [![Inspelningskontroller](./media/controls.jpg)](./media/controls.jpg)
<a id="recording-controlsmediacontrolsjpgmediacontrolsjpg" class="xliff"></a>

### Stopp
<a id="stop" class="xliff"></a>

Klicka på **Stopp** för att avsluta inspelningssessionen. Observera att du inte kan starta om en session när du avslutar den. Se därför till att inspelningen har slutförts innan du avslutar den.

### Pausa 
<a id="pause" class="xliff"></a>

Klicka på **Pausa** för att tillfälligt stoppa (pausa) inspelningssessionen och fortsätta med processen. Steg som du utför efter det att du klickar på **Pausa** spelas inte in.

### Fortsätt
<a id="continue" class="xliff"></a>

Klicka på **Fortsätt** om du vill återuppta inspelningssessionen när du har gjort paus.

### Ta skärmbilder
<a id="capture-screenshots" class="xliff"></a>

Uppgiftsinspelaren kan läsa in skärmdumpar på Modern Retail POS-användargränssnittet när du spelar in en affärsprocess. Uppgiftsinspelaren använder skärmbilderna om du hämtar inspelningen som ett Word-dokument. För att aktivera inspelningsfunktionen för skärmbild, ange alternativet **Fånga skärmbild** som **Ja**. 

#### Sedel
<a id="note" class="xliff"></a>
> Funktionen för att fånga skärmbild stöds inte i Cloud POS.

### Startuppgift och slutuppgift
<a id="start-task-and-end-task" class="xliff"></a>

Du kan ange början och slut för en uppsättning grupperade steg via knapparna **Starta uppgift** och **Avsluta** **uppgift**. Klicka på **Starta uppgift** för att lägga till steget "Starta uppgift" och utföra de steg som ska tas med i gruppen. När du har utfört stegen för gruppen klickar du på **Avsluta uppgift**. Uppgifter hjälper dig att ordna dina procedurer. Uppgifter kan kapslas in i andra uppgifter. På så sätt blir det enklare att organisera mycket långa och komplicerade affärsprocesser.

## Lägga till anteckningar
<a id="adding-annotations" class="xliff"></a>
En anteckning är ytterligare text som du lägger till i ett steg i en inspelning. Du kan exempelvis använda anteckningar för att ge användaren mer kontext eller instruktioner. Du kan lägga till anteckningar före eller efter ett steg. Du kan lägga till en anteckning till ett steg genom att klicka på knappen **Redigera** (pennsymbol) till höger om steget. 

[![Redigeringsknapp för ett steg](./media/annotate.jpg)](./media/annotate.jpg)

### Texter och anteckningar
<a id="texts-and-notes" class="xliff"></a>

Du kan använda fälten **Texter** och **Anteckningar** om du vill lägga till text som ska associeras med ett steg i en uppgiftsguide.
[![Text- och anteckningsfält](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### Text
<a id="text" class="xliff"></a>

Text som du anger i fältet **Text** visas *ovanför* stegtexten i uppgiftsguiden. Den här platsen är lämplig för den text som du vill att användaren ska läsa innan han eller hon slutför ett steg.

#### Anteckningar
<a id="notes" class="xliff"></a>

Text som du anger i fältet **Anteckningar** visas *under* stegtexten i uppgiftsguiden. Användaren måste expandera stegtexten i popup-fönstret för att läsa anteckningen. Den här platsen passar valfritt läsmaterial eller annan information som kan vara användbart för användaren, men som användaren inte behöver för att slutföra åtgärden.

## Hjälp i Retail Modern POS och molnbaserad kassa
<a id="help-in-retail-modern-pos-and-cloud-pos" class="xliff"></a>
Om du vill visa dina egna anpassade uppgiftsinspelningar i hjälpfönstret för Retail Modern POS och Cloud POS så att de kan spelas upp text, så måste du spara dina uppgiftsinspelningar i ditt eget BPM-bibliotek och sedan uppdatera hjälpsystemparametrarna så att de pekar på ditt BPM-bibliotek. Mer information finns i [Ansluta hjälpsystemet](/dynamics365/unified-operations/dev-itpro/get-started/help-connect). Retail Modern POS och Cloud POS Help söker LCS i realtid. Det söker igenom alla BPM-bibliotek som valts i hjälpsystemparametrarna för Microsoft Dynamics 365 for Retail och visar relevanta resultat. För att få åtkomst till menyn **Hjälp** klickar du på knappen **Hjälp** (frågetecken) högst upp på skärmen. Ange sedan ditt processnamn i sökrutan och tryck på sökknappen. 

[![Knappen Hjälp](./media/help.jpg)](./media/help.jpg) 

När du klickar på en uppgiftsguide i sökresultaten kan du antingen se stegen som ett hjälpavsnitt eller exportera stegen till ett Word-dokument. 
#### Sedel
<a id="note" class="xliff"></a>
> Hjälp i Retail Modern POS och molnbaserad kassa visar inte aktivitetsguiderna i enlighet med det formulär du använder eller den åtgärd du utför. Skriv in processnamnet i sökrutan och klicka på **Sök**.


