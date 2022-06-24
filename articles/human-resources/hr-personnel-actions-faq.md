---
title: Vanliga frågor och svar om personalåtgärder
description: Det här avsnittet innehåller svar på frågor som du kan ha om din organisation använder personalåtgärder.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8882fd00c68dc3cafcb4ecf1b2fe351a9e7f5741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874319"
---
# <a name="personnel-actions-faq"></a>Vanliga frågor och svar om personalåtgärder


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här avsnittet innehåller svar på frågor som du kan ha om din organisation använder personalåtgärder. Personalåtgärder är ytterligare steg du måste vidta när du utför personalrelaterade uppgifter. 

Exempel på uppgifter som kan kräva personalåtgärder är:
 - När du skapar nya befattningar. 
 - Vid ändringar i befintliga befattningsvärden. 
 - Vid anställning av nya medarbetare. 
 - Vid flytt av medarbetare. 
 - Vid ändringar i medarbetarkompensation. 
 - Vid ändringar i befattningstilldelning. 
 - Vid uppsägning av medarbetare.

> [!NOTE]
> Personalåtgärder finns tillgängliga endast om fälten **Aktivera medarbetaråtgärder** och **Aktivera befattningsåtgärder** har angetts som **Ja** på fliken **Personalåtgärder** på sidan **Delade personalparametrar**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Hur kan jag avgöra om min organisation kräver personalåtgärder?
Personalåtgärder krävs av organisationen om du uppmanas att välja en personalåtgärd när du skapar nya befattningar, ändrar befintliga befattningar, anställer nya arbetare, överför arbetare, ändrar arbetsersättning, ändras befattningstilldelningar, säger upp arbetare eller anger ledighet för arbetare. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Vad är skillnaden mellan en befattningsåtgärd och en arbetaråtgärd?
Det finns två typer av personalåtgärder:

- Åtgärden **Befattning** – En befattningsåtgärd utförs för befintliga befattningar och nya befattningar. Exempelvis kan en befattningsåtgärd krävas om du ändrar ett värde för en befintlig befattning, eller om du skapar en ny säsongsbefattning. 

- Åtgärd för **Medarbetare** – Enmedarbetaråtgärd utförs på befintliga eller nya anställda. En arbetstagaråtgärd krävs till exempel när en ny medarbetare anställs, eller en befintlig medarbetare befordras. 

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Vad innebär status för personalåtgärderna?
Personalåtgärder kan ha följande status:

- **Utkast** – Om arbetsflöde används har åtgärden inte skickats in. Om arbetsflöde inte används har inte åtgärden slutförts.
- **Granskas** – Personalåtgärden har skickats till arbetsflödet, men arbetsflödet har inte slutförts.
- **Godkänd – väntar** – Arbetsflödet har slutförts, men ändringarna bearbetas fortfarande. **Avbröts** – Arbetsflödet avbröts eller också återkallades personalåtgärden. **Avvisades** – Åtgärdsbegäran avslogs av godkännaren.
- **Bearbetningsåtgärd** – Åtgärdsbegäran har godkänts och ändringarna bearbetas.
- **Arbetsflödet slutfört**  – Arbetsflödet har slutförts och ändringarna har bearbetats. **Misslyckades** – Arbetsflödet misslyckades eftersom informationen är inaktuell. Klicka på **Återaktivera** för att visa den senaste informationen och fortsätta.
- **Slutfördes** – Befattningen har skapats eller ändrats, medarbetaren har anställts, bytt befattning eller sagts upp, eller också har kompensationen ändrats. **Fel** – Ett problem har uppstått av någon annan orsak än att informationen är inaktuell. Öppna **meddelandedialogen för personalågärder** för att avgöra felorsaken.
- **Avslogs** – Åtgärdsbegäran avslogs av godkännaren.

## <a name="can-i-delete-a-personnel-action"></a>Kan jag ta bort en personalåtgärd?
Ja, du kan ta bort personalåtgärder som har statusen **Utkast**, **Fel**, **Misslyckades** eller **Avbröts**. Du kan bara ta bort personalåtgärder som har statusen **Slutförd** om du har angett alternativet **Tillåt borttagning av slutförda arbetsåtgärder** som **Ja** på sidan **Delade personalparametrar**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Vad är det snabbaste sättet att kontrollera statusen på en personalåtgärdsbegäran?
Öppna någon av listsidorna för **personalåtgärder** och välj en personalåtgärd.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Vad jag ska göra om personalåtgärdsbegäran misslyckas?
Om en personalåtgärdsbegäran misslyckas följer du dessa steg för att lösa felet och skicka om begäran:

> 1. Klicka på knappen **Feltext** i **Åtgärdsfönstret** om du vill visa meddelandetexten som beskriver problemet.
> 
> 2. Klicka på **Återaktivera** i **Åtgärdsfönstret** om du vill läsa in den senaste informationen och återställa statusen för personalåtgärden till **Utkast**.
> 
> 3. Lös felet och klicka sedan på **Slutför** eller **Skicka in**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Vad händer med en personalåtgärd som använder arbetsflödet, om det sista godkännandet är slutfört?
Om det inte finns några fel, blir personalåtgärden skrivskyddad. (Du kan visa historiken på listsidan **Alla medarbetaråtgärder**, men du kan inte ändra personalåtgärden.) När statusen för en personalåtgärd är **Slutförd** har befattningen eller medarbetarposten redan uppdaterats. Öppna listsidan **Befattningar** eller **Arbetare** om du vill visa de ändringar som görs.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Varför får jag följande felmeddelande när jag anger ett ickenollvärde i fältet Lönesats? "Värdet ligger utanför giltighetsintervallet – det måste vara mellan 0,00 och 0,00"
Du får detta meddelande eftersom fältet **Nivå** på sidan **Jobb** är tomt för det jobb som är kopplat till den valda befattningen.

Du åtgärdar felet genom att följa dessa steg:

> 1. På sidan **Tilldelning av medarbetarbefattningar** klickar du på fältet **Befattning**.  
> 2. Klicka på fältet **Jobb** för att öppna sidan **Jobb**.
> 3. Klicka på **Redigera** i åtgärdsfönstret.
> 4. Klicka på fliken **Kompensation**.
> 5. Välj en nivå i fältet **Nivå**.
> 6. Stäng sidan **Jobb**.
> 7. Stäng sidan **Befattning**.
> 8. Återgå till fliken **Kompensation** på sidan **Medarbetare** och välj **Fast kompensation**.  Välj **Nytt** och ange sedan medarbetarens befattning i fältet **Befattning**.  Ange ett värde i fältet **Plan** och ange sedan medarbetarens kompensation i fältet **Lönesats**.

## <a name="why-cant-i-change-the-effective-date-on-the-header-of-the-worker-action-page"></a>Varför kan jag inte ändra giltighetsdatumet i sidhuvudet på sidan för medarbetaråtgärd?
Du kan inte ändra giltighetsdatum eftersom fältet fylls i med det med logiska datumet för åtgärdstypen.

Exempel:

- Giltighetsdatumet i rubriken för en **Säg upp arbetstagare**-åtgärd är det datum som du angett i fältet **Uppsägningsdatum**.
- Giltighetsdatumet i rubriken för en **Anställ arbetstagare**-åtgärd är det datum som du angett i fältet **Startdatum för anställning**.
- Giltighetsdatumet i rubriken för en **Överför en arbetstagare**-åtgärd är det datum som du angett i fältet **Startdatum för tilldelning**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
