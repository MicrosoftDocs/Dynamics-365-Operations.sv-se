---
title: "Parametrar för utläggshantering"
description: "Följande parametrar styr beteendet i utgiftshanteringen."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8ca9e80d6d2b87fcdd10ebb9d32bd0a2b2d15614
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-parameters"></a>Parametrar för utläggshantering
-----------------------------

Följande parametrar styr det allmänna beteendet i utgiftshanteringen.

### <a name="general"></a>Allmänt

| **Fält**                                                | **Beskrivning**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Standardtariff för milersättning**                             | Ange vilken tariff för milersättning. Satsen ska multipliceras med den körsträcka som angetts för att beräkna beloppet återbetalas för reseutgifter utgiften.                       |
|**Privata utgifter betalas av**                             | Välj vem som är ansvarig för att betala alla kreditkortstransaktionsbelopp som kategoriseras som personliga.                                                                                                     |
|**Visa hela utgiftsrapporten vid vidaresökning bakåt**               | Välj detta alternativ om du vill visa alla utgifter för en utgiftsrapport när du visar informationen i det ursprungliga dokumentet för en viss verifikation som skapades när utgiftsrapporten bokförs.              |
|**Förauktorisering för resa är obligatoriskt**                 | Välj detta alternativ om du vill att en reserekvisition överlämnas och godkänns innan en medarbetare kan skicka en utgiftsrapport.                                                                    |
|**Tillåt redigering av fördelningar före bokföring**            | Välj om distribution av en utgiftsrapport kan ändras före bokföring.                                                                                                                 |
|**Utvärdera policyer för utläggshantering**                     | Välj när utgifter utvärderas för att avgöra om en utgiftspolicy har överträtts. Utgifter kan kontrolleras för brott när utgiftsposten anges och sparas eller när utgifterna har skickats för godkännande. Policyregler för kvitton som krävs kontrolleras när utgiftsraden har sparats.                   |
|**Tillåt koncerninterna utgiftsrader**                         | Välj om du vill tillåta inmatning av utgifter för andra juridiska personer i en utgiftsrapport.                                                                                                          |
|**Tillåt redigering av valutakursen för kreditkortsutgifter** | Välj detta alternativ om du vill tillåta användaren att redigera växelkursen för importerade kreditkortutgifter.                                                                        |
|**Flera hierarkinivåfält att visa**                  | Välj vilket godkännarfält som visas när tilldelningstypen för utgiftsrapportarbetsflödet anges till hierarki och alternativet hierarki är konfigurerat att använda godkännandehierarki på flera nivåer för utgift. När godkännandehierarkin på flera nivåer används för arbetsflöde visas och redigeras de markerade fälten i utgiftsrapporten. |
|**Ange medarbetarens kreditkortsnummer (uppdatering juli 2017)**     | Välj om ett 15 eller 16 teckens nummer anges och sparas i fältet **kort-ID** på sidan **kreditkort** för en medarbetare.                                                                          |

### <a name="financial"></a>Ekonomi

| **Fält**                                                            | **Beskrivning**     |
|----------------------------------------------------------------------|------------------------------------|
|**Namn på dagboksjournal i redovisning**                                         | Välj vilket namn på redovisningsjournal som godkända utgiftsrapporter ska bokföras i.            |
|**Aktivera momsåterbetalning från utgifter**                                  | Välj detta alternativ om du vill aktivera momsåterbetalning för berättigade utgifter. Det här alternativet kan inte aktiveras om amerikansk moms och använda skatteregler har aktiverats.      |
|**Bokför förskott omedelbart**                                     | Välj det här alternativet om du vill bokföra ett godkänt förskott när processen att betala och överföra har slutförts. Om alternativet inte är markerat genererat processen Betala och överför en ej bokförd redovisningsjournal. |
|**Korrekt redovisningsdatum under bokföring**                             | Välj detta alternativ om du vill uppdatera redovisningsdatumet när utgifter bokförs om den aktuella perioden är spärrad eller stängd. Redovisningsdatumet anges till nästa öppna period.   |
|**Tillåt gruppering av transaktioner baserade på motkonto angivet i betalningsmetoden**      | Välj detta alternativ om du vill summera utgiftstransaktioner för utgiftsrapporter som baseras på motkontot enligt betalningsmetoden för utgifterna.   
|**Inklusive skatt**                                                   | Välj det här alternativet för att inkludera moms i utgiftsbeloppet som standard.             |
|**Frisläpp inteckningar vid stängning av reserekvisitioner**            | Välj detta alternativ för att frisläppa intecknade medel när en godkänd reserekvisition stängs.                                                                                   |
|**Tillåt att reserekvisition skickas vid budgetöverskridningar för budgetregister och projektbudget** | Välj detta alternativ om du vill tillåta att medarbetare skickar reserekvisitioner för godkännande som antingen överstiger tillåten budget som har angetts i budgetregistret eller tillåten budget för ett projekt.            |
|**Tillåt att utgiftsrapport skickas vid budgetöverskridningar för budgetregister och projektbudget**    | Välj detta alternativ om du vill tillåta att medarbetare skickar utgiftsrapporter för godkännande som antingen överstiger tillåten budget som har angetts i budgetregistret eller tillåten budget för ett projekt.                |
|**Tillåt godkännande av utgiftsrapport vid budgetöverskridningar endast för budgetregister**                | Välj detta alternativ om du vill tillåta godkännare att godkänna utgiftsrapporter som överskrider den tillåtna budget som anges i budgetregistret.                                                                       |

### <a name="per-diem"></a>Traktamente

| **Fält**                             | **Beskrivning**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Lägsta antal timmar för dagtraktamente**           | Ange lägsta standardantal timmar som en medarbetare måste arbeta per dag för att vara berättigad till traktamente för reserelaterade utgifter.  Detta värde används endast som ett standardvärde för fältet för lägsta antal timmar på traktamenteprisnivåer.                                                                                      |
|**Måltidsprocent**                          | Ange en standardprocentsats för traktamentet för måltider som används på den första och sista dagen i den reserelaterade utgiften när fältet **beräkna måltidsavdrag genom** anges till antingen **Måltidstyp per dag** eller **Antal måltider per dag**. Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag. Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet. Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00. |
|**Hotellprocent**                        | Ange en standardprocentsats för traktamentet för hotell som används på de första och sista dagarna för den reserelaterade utgiften. Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag. Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet. Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00.                                              |
|**Annan procent**                        | Ange en standardprocentsats för traktamentet för diverse utgifter som används på de första och sista dagarna för den reserelaterade utgiften. Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag. Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet. Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00.                                                                                                     |
|**Reducering (procentandel) för frukost** | Ange beloppet som dagtraktamentet minskar för frukost. Om medarbetaren till exempel får gratis frukost kan du välja att sänka beloppet för dagtraktamentet med 10 procent.                               |
|**Reducering (procentandel) för lunch**    | Ange beloppet som dagtraktamentet minskar för lunch. Om medarbetaren till exempel får gratis lunch kan du välja att sänka beloppet för dagtraktamentet med 15 procent.                                       |
|**Reducering (procentandel) för middag**   | Ange beloppet som dagtraktamentet minskar för middag. Om medarbetaren till exempel får gratis middag kan du välja att sänka beloppet för dagtraktamentet med 25 procent.                                     |
|**Beräkna måltidsreducering med**         | Välj hur systemet beräknar reducering av traktamente genom att välja om reduceringen baseras på måltidstyp per resa eller per dag, eller om den reduceras baserat på antalet måltider som tillåts per dag.|
|**Avrundning av dagtraktamente**                  | Välj den typ av avrundning som ska användas för dagtraktamentsutgifter. Om du väljer normal avrundning avrundas traktamenteutgifter som har ett belopp på 0,50 upp till 1,00 och traktamentesutgifter som har ett belopp som är mindre än 0,50 avrundas nedåt till 0,00.                                                                                              |
|**Basera beräkning av dagtraktamente på**         | Anger om beloppet för dagtraktamenten baseras på en kalenderdag eller en 24-timmars period.       |

### <a name="fax-cover-pages"></a>Faxförsättssida

| **Fält**                      | **Beskrivning**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Instruktioner**                   | Ange instruktionerna som anställda måste följa när de skapar en försättssida för ett faxmeddelande som används för att skicka kvitton relaterade till en utgiftsrapport. Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk. |
|**Användar-ID (streckkodsinformation)** | Välj det här alternativet om du vill lagra en arbetares unika identifierare i streckkoden som används på faxets försättssida.                 |
|**Streckkod**                      | Välj streckkoden som används på försättssidan av faxet. Streckkoder 39 och 128 stöds med utgiftshantering.               |

### <a name="anti-corruption"></a>Antikorruption

| **Fält**                             | **Beskrivning**      |
|---------------------------------------|------------------------------------------------------------------------|
|**Visa antikorruptionsattestering**   | Välj detta alternativ om du vill visa antikorruptionstexten när du skapar en ny utgiftsrapport. Särskilda kostnadskategorier kan aktiveras som kräver att antikorruptionsattestering väljs i utgiftsrapporten. Exempelvis kan en gåvokategori relaterad till officiella offentliga utgifter kräva att medarbetare bekräftar att utgiften uppfyller företagets policy relaterat till statliga tjänstemän. |
|**Antikorruptionsmeddelande till insändare** | Ange den text som ska visas för medarbetaren när du skapar en ny utgiftsrapport. Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk.         |
|**Antikorruptionsmeddelande till godkännare**  | Ange den text som ska visas för godkännaren när du skapar en ny utgiftsrapport. Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk.        |

