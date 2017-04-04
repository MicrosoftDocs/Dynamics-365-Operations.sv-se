---
title: "Leverantören mobila samarbetsyta för Microsoft Dynamics 365 för operationer app"
description: "Med mobil arbetsytan leverantör samarbete kan leverantörerna hålla sig uppdaterade i de inköpsorder som har skickats till dem för godkännande och visa information om nya och uppdaterade inköpsorder och kontakter."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Leverantören mobila samarbetsyta för Microsoft Dynamics 365 för operationer app

Med mobil arbetsytan leverantör samarbete kan leverantörerna hålla sig uppdaterade i de inköpsorder som har skickats till dem för godkännande och visa information om nya och uppdaterade inköpsorder och kontakter.

<a name="prerequisites"></a>Förutsättningar
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Läs mer om Microsoft Dynamics 365 för operationer</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 för operationer</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 för operationer</td>
<td>Försäkra dig om att du använder en miljö med Microsoft Dynamics 365 för operationer version 1611 och uppdatera Microsoft Dynamics för operationer 3 (November 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Mobil enhet med Dynamics 365 för operationer program installerat</span></td>
<td><span style="color: #000000;">Hämta mobiltelefonprogrammet lagringsplatsen Dynamics 365 för operationer app.</span></td>
</tr>
<tr class="even">
<td>Snabbkorrigering KB 3215650</td>
<td>Installera snabbkorrigering om du vill aktivera arbetsytor som finns i Dynamics 365 för operationer.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">Snabbkorrigering KB 3216943</span> </span></td>
<td>Installera snabbkorrigering om du vill aktivera samarbete leverantör mobil arbetsytan.</td>
</tr>
<tr class="even">
<td>Leverantör-användaren måste har tillgång till webbgränssnittet leverantör samarbete i Dynamics 365 för operationer och ställer du leverantören samarbete.</td>
<td>Följ instruktionerna i följande avsnitt för att ställa in och arbeta med leverantören samarbete webbgränssnittet.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Använd leverantör samarbete arbeta med externa leverantörer</a></li>
<li><a href="manage-vendor-collaboration-users.md">Hantera leverantörssamarbetesanvändare</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Skapa och underhåll leverantörssamarbeten</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Använd leverantör samarbete för att arbeta med kunder i Dynamics 365 för operationer</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Översikt
Leverantören samarbete mobil arbetsytan sparas information om nya inköpsorder så att de kan visa och svara på inköpsorder i Dynamics 365 för operationer webbklienten leverantörer.  

**Anmärkning:** mobil arbetsytan kan användas som ett tillägg till leverantörens webbgränssnittet samarbete, men ersätter inte.  

Med leverantören samarbete mobil arbetsytan kan visa leverantörerna nya inköpsorder som har skickats för godkännande. Inköpsorderinformation, till exempel produkter, kvantitet och begärt leveransdatum visas. Prisuppgifter finns tillgängliga, beroende på konfigurationen för varje leverantör.  

När en användare loggar in som en leverantör, visas vilka inköpsorder har har svarat eller vilken inköpsorder väntar fortfarande kunden åtgärd. Leverantören kan ha föreslås ett annat leveransdatum som inte ännu har kommit överens med kunden så att kunden åtgärden väntar på inköpsordern. Dessutom visas en lista över inköpsorder som har bekräftats men ännu inte levererats leverantören.  

Leverantören måste använda webbgränssnittet för leverantören samarbete i Dynamics 365 för webbklienten operationer är för att besvara en inköpsorder. Du kan även där leverantören får mer information om ordern, till exempel bifogade dokumentfiler, leveransadress per rad och kostnader som är kopplade till leverantören.  

Leverantören kan visa vilka personer som har registrerats för ett leverantörskonto kontakt med en särskild säkerhetsroll. Leverantören kan visa status för varje användarbegäran som har skickats med samma säkerhetsroll.  

Skapa nya kontakter och skickar begäranden om nya användare måste du göra i gränssnittet leverantör samarbete i Dynamics 365 för operationer webbklienten.  

Med mobil arbetsytan kan leverantören:

-   Visa nya inköpsorder som skickas till leverantören.
-   Visa inköpsorder att leverantören har svarat på och väntar på kund-åtgärd.
-   Visa inköpsorder som har statusen bekräftat och inte har inlevererats helt.
-   Visa information för kontaktperson som har registrerats för leverantörskontot (kräver ytterligare en säkerhetsroll).
-   Visa information och följ statusen för en begäran skickats av leverantören (kräver ytterligare en säkerhetsroll).

## <a name="get-started"></a>Kom igång
Komma igång med din mobila enhet:

1.  Hämta och installera Microsoft Dynamics 365 for app operationer på din mobiltelefonprogrammet butik.
2.  Starta programmet för enheten.
3.  Ange en Webbadress för Dynamics 365.
4.  Ange att logga in på företaget. Till exempel anger **USMF**.
5.  Första gången du loggar in, uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 för operationer. 

När du loggar in i appen syns inga arbetsytor. Om du vill visa arbetsytor på din mobiltelefonprogrammet måste du publicera önskade arbetsytor till Dynamics 365 for app operationer. Du behöver system administration behörighet att publicera på arbetsytan.

1.  Starta Dynamics 365 för operationer.
2.  Gå till **systemadministration**&gt;**inställningar**&gt;**systemparametrar**.
3.  Välj **hantera mobiltelefonprogrammet**.
4.  Markera arbetsytan **leverantör samarbete** publiceras mobil plattform.
5.  Välj **publicera arbetsytan**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.
7.  Välj den **leverantör samarbete** arbetsytan. Du kommer till nästa sida.

[![leverantör-samarbete mobile-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kontakter
Den **kontakter** på sidan kan du visa alla kontakter som har ställts för leverantörskontot. Visas kontaktpersonens namn och primär e-användaralias, om sådana finns. Det visar också om kontaktpersonens användarkonto är aktiv. När du väljer en kontakt finns kontaktinformation, till exempel vilka juridiska personer som personen är en kontakt för och kontaktinformation, till exempel telefonnummer eller någon annan e-postadress.

## <a name="user-requests"></a>Användarförfrågningar
Den **användarfrågor** sidan kan du se alla användare begär att du har skickat via webbgränssnittet leverantör samarbete och följa status. När du väljer en begäran om kan du se vad som förväntades, lägga till eller inaktivera en användare, ändra säkerhetsinställningar och se vilka säkerhetsroller som krävdes för användaren.

## <a name="purchase-orders-ready-for-review"></a>Inköpsorder som är klara för granskning
Den **inköpsorder som är klara för granskning** sidan kan du se alla inköpsorder som har skickats av kunden och har inte besvarats. Du kan visa utvald information om ordern, till exempel vilka produkter som har begärts och när du kan leverera. Prisuppgifter finns bara om det har konfigurerats för leverantören.  

Du kan se om inköpsordern har anteckningar och bifogade filer. Öppna bifogade filer måste du använda leverantörens samarbete i webbklienten. Välj **inköpsorderrad** att visa alla rader med information. Observera att för varje rad en indikator visas om det finns anteckningar och bilagor, eller om det finns en leveransadress än vad som anges i huvudet.  

Om du vill svara på inköpsordern måste du använda webbklienten samarbete för leverantören.

## <a name="awaiting-customer-action"></a>Väntar på kundåtgärd
Den **väntar på kund åtgärden** sidan kan du söka efter inköpsorder som du eller någon i företaget som har åtkomst till leverantören samarbete har svarat. Inköpsorder visas bara i listan om kunden måste du göra något av följande på inköpsordern.

-   Om inköpsordern har avvisats skulle kunden antingen behöver uppdatera skickade ordern och skicka igen, eller Avbryt ordern och skicka. När inköpsordern har skickats igen, försvinner den från de **väntar på kund åtgärden** sida.
-   Om inköpsordern togs emot med ändringar får skulle kunden behöva uppdatera den ursprungliga ordern och skicka för granskning, eller uppdateras enligt ändringarna och bekräfta det omedelbart. I båda fallen inköpsordern tas bort från den **väntar på kund åtgärden** sida.
-   Om inköpsordern som har godkänts och visas i de **väntar på kund åtgärden** sidan beror det på inköpsordern inte bekräftades automatiskt när mottagande gjordes. Väntar på en Inköpsagent ändra ordern till Bekräftat. Vanligtvis skulle inköpsordern betraktas som ett avtal mellan kund och leverantör som leverantören accepterar sorteringsordningen. Flytta inköpsordern till statusen bekräftat blir en formalitet.

Genom att välja inköpsordern, visas ytterligare information om svaret. Du kan se raddetaljer och svar för varje rad. Raden status visas i vilken av följande svar har fått.

-   Godkänt
-   Avvisat
-   Godkänd med ändringar
-   Ersätta/ersättning
-   Dela upp i schemat/kontouppställningens rad

Observera att en indikator som anger **sända**= Ja/Nej, som används för att ange att raderna inte levereras. Detta kan bero på att raden avslogs eller ersätta där de ursprungliga raderna förväntas inte levereras eller en rad som har delats upp i flera rader för leverantörsbetalningsplan och den ursprungliga raden inte antas enligt förfrågan i den inlevererade ordern levereras.  

Eventuella ändringar i ordern rad svaret visas förutom överförda anteckningar och bifogade filer, som du kan visa genom att använda webbgränssnittet för leverantören samarbete.

## <a name="open-confirmed-orders"></a>Öppna bekräftade order
När inköpsordern har bekräftats av kunden, ändras vilket betyder att inköpsordern till statusen bekräftat visas i den öppna ordern bekräftad. Det ligger i listan tills registreras som kunden har mottagit.


