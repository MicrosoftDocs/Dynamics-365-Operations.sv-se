---
title: Vanliga frågor och svar om personalåtgärder
description: Det här avsnittet innehåller svar på frågor som du kan ha om din organisation använder personalåtgärder. Personalåtgärder är ytterligare steg du måste vidta när du utför personalrelaterade uppgifter.
author: andreabichsel
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 43c727fa8e0508adf66109efd84a66cb31df7ea3
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115424"
---
# <a name="personnel-actions-faq"></a>Vanliga frågor och svar om personalåtgärder

Det här avsnittet innehåller svar på frågor som du kan ha om din organisation använder personalåtgärder. Personalåtgärder är ytterligare steg du måste vidta när du utför personalrelaterade uppgifter. Exempel på uppgifter som kan kräva personalåtgärder är när du skapar nya befattningar, ändrar befintliga befattningsvärden, anställer nya arbetstagare, överför arbetstagare, ändrar arbetstagares kompensation, ändrar befattningstilldelningar eller säger upp arbetstagare.

**Obs:** Personalåtgärder finns tillgängliga endast om fälten **Aktivera arbetaråtgärder** och **Aktivera positionsåtgärder** har angetts som **Ja** på fliken **Personalåtgärder** på sidan **Personalparametrar**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Hur kan jag avgöra om min organisation kräver personalåtgärder?
Personalåtgärder krävs av organisationen om du uppmanas att välja en personalåtgärd när du skapar nya befattningar, ändrar befintliga befattningar, anställer nya arbetare, överför arbetare, ändrar arbetsersättning, ändras befattningstilldelningar, säger upp arbetare eller anger ledighet för arbetare. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Vad är skillnaden mellan en befattningsåtgärd och en arbetaråtgärd?
Det finns två typer av personalåtgärder:

- Befattningsåtgärd – En befattningsåtgärd utförs för befintliga befattningar och nya befattningar. Exempelvis kan en befattningsåtgärd krävas om du ändrar ett värde för en befintlig befattning, eller om du skapar en ny säsongsbefattning. För detaljerad information om hur du använder befattningsåtgärder, se Nyckeluppgifter: Befintliga arbetarbefattningar eller Nyckeluppgifter: Nya arbetarbefattningar.

- Arbetaråtgärd – En arbetaråtgärd utförs för befintliga medarbetare eller nya medarbetare. En arbetstagaråtgärd krävs till exempel när en ny medarbetare anställs, eller en befintlig medarbetare befordras. Detaljerad information om hur du använder arbetaråtgärder finns i Tilldela personalåtgärder till arbetstagare.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Vad innebär status för personalåtgärderna?
Personalåtgärder kan ha följande status:

- **Utkast** – Om arbetsflöde används har inte åtgärden skickats in. Om arbetsflöde inte används har inte åtgärden slutförts.
- **Granskas** – Personalåtgärden har skickats till arbetsflödet, men arbetsflödet har inte slutförts.
- **Godkänd – väntar** – Arbetsflödet har slutförts, men ändringarna bearbetas fortfarande. Avbröts – Arbetsflödet avbröts eller också återkallades personalåtgärden. Avvisades – Åtgärdsbegäran avslogs av godkännaren.
- **Bearbetningsåtgärd** – Åtgärdsbegäran har godkänts och ändringarna bearbetas.
- **Arbetsflödet slutfört**  – Arbetsflödet har slutförts och ändringarna har bearbetats. Misslyckades – Arbetsflödet misslyckades eftersom informationen är inaktuell. Klicka på Återaktivera för att visa den senaste informationen och fortsätta.
- **Slutfördes** – Befattningen har skapats eller ändrats, medarbetaren har anställts, bytt befattning eller sagts upp, eller också har kompensationen ändrats. Fel – Ett problem har uppstått av någon annan orsak än att informationen är inaktuell. Öppna meddelandeloggen för personalåtgärder om du vill fastställa orsaken till felet.
- **Avslogs** – Åtgärdsbegäran avslogs av godkännaren.

## <a name="can-i-delete-a-personnel-action"></a>Kan jag ta bort en personalåtgärd?
Ja, du kan ta bort personalåtgärder som har statusen **Utkast**, **Fel**, **Misslyckades** eller **Avbröts**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Vad är det snabbaste sättet att kontrollera statusen på en personalåtgärdsbegäran?
Öppna någon av listsidorna för personalåtgärder och välj en personalåtgärd.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Vad jag ska göra om personalåtgärdsbegäran misslyckas?
Om en personalåtgärdsbegäran misslyckas följer du dessa steg för att lösa felet och skicka om begäran:

> 1. Klicka på knappen **Feltext** i **Åtgärdsfönstret** om du vill visa meddelandetexten som beskriver problemet.
> 
> 2. Klicka på **Återaktivera** i **Åtgärdsfönstret** om du vill läsa in den senaste informationen och återställa statusen för personalåtgärden till **Utkast**.
> 
> 3. Lös felet och klicka sedan på **Slutför** eller **Skicka in**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Vad händer med en personalåtgärd som använder arbetsflödet, om det sista godkännandet är slutfört?
Om det inte finns några fel, blir personalåtgärden skrivskyddad. (Du kan visa historiken i listsidan **Alla arbetaråtgärder**, men du kan inte ändra personalåtgärden.) När statusen för en personalåtgärd är **Slutförd** har befattningen eller arbetarposten redan uppdaterats. Öppna listsidan **Befattningar** eller **Arbetare** om du vill visa de ändringar som görs.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Varför får jag följande felmeddelande när jag anger ett ickenollvärde i fältet Lönesats? "Värdet ligger utanför giltighetsområdet – det måste vara mellan 0,00 och 0,00"
Du får detta meddelande eftersom fältet Nivå i jobbformuläret är tomt för det jobb som är kopplat till den valda befattningen.

Du åtgärdar felet genom att följa dessa steg:

> 1. Klicka på fältet Befattning i tilldelningsformuläret för arbetstagarbefattningen.  
> 2. Klicka på fältvärdet Jobb för att öppna sidan Jobb.
> 3. Klicka på Redigera i åtgärdsfönstret.
> 4. Klicka på fliken Kompensation.
> 5. Välj en nivå i fältet Nivå.
> 6. Stäng sidan Jobb.
> 7. Stäng sidan Befattning.
> 8. Gå tillbaka till fliken Kompensation på sidan Arbetare och välj Fast kompensation.  Välj Nytt och ange medarbetarens befattning i fältet befattning.  Ange ett värde i fältet Plan, och ange sedan medarbetarens kompensation i fältet Lönesats.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>Varför kan jag inte ändra giltighetsdatumet i huvudet på formuläret för arbetstagaråtgärd?
Du kan inte ändra giltighetsdatum eftersom fältet fylls i med det logiska datumet för åtgärdstypen.

Exempel:

- Giltighetsdatumet i rubriken för en **Säg upp arbetstagare**-åtgärd är det datum som du angett i fältet **Uppsägningsdatum**.
- Giltighetsdatumet i rubriken för en **Anställ arbetstagare**-åtgärd är det datum som du angett i fältet **Startdatum för anställning**.
- Giltighetsdatumet i rubriken för en **Överför en arbetstagare**-åtgärd är det datum som du angett i fältet **Startdatum för tilldelning**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]