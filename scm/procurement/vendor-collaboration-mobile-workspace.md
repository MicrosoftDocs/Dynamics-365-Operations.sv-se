---
title: "Mobil arbetsyta för leverantörssamarbete för programmet Microsoft Dynamics 365 for Operations"
description: "Med mobil arbetsyta för leverantörssamarbete kan leverantörerna hålla sig uppdaterade i de inköpsorder som har skickats till dem för godkännande och visa information om nya och uppdaterade inköpsorder och kontakter."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e19fee87dae6e5d425f36dac0db4ea89534a8510
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobil arbetsyta för leverantörssamarbete för programmet Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Med mobil arbetsyta för leverantörssamarbete kan leverantörerna hålla sig uppdaterade i de inköpsorder som har skickats till dem för godkännande och visa information om nya och uppdaterade inköpsorder och kontakter.

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
<td>Läs mer om den mobila plattformen Microsoft Dynamics 365 for Operations</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Den mobila plattformen Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Se till att använda en miljö med Microsoft Dynamics 365 for Operations version 1611 och plattformen Microsoft Dynamics for Operations med uppdatering 3 (november 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Mobil enhet med programmet Dynamics 365 for Operations installerat</span></td>
<td><span style="color: #000000">Hämta programmet Dynamics 365 for Operations från din mobilappsbutik.</span></td>
</tr>
<tr class="even">
<td>Snabbkorrigering KB 4013633</td>
<td>Installera snabbkorrigeringen om du vill aktivera de arbetsytor som finns i Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Snabbkorrigering KB 3216943</span> </span></td>
<td>Installera snabbkorrigering om du vill aktivera Mobil arbetsyta för leverantörssamarbete.</td>
</tr>
<tr class="even">
<td>Leverantörsanvändaren måste har tillgång till leverantörswebbgränssnittet i Dynamics 365 for Operations och ställa in en leverantörssamarbetesanvändare.</td>
<td>Följ instruktionerna i följande avsnitt för att ställa in och arbeta med leverantörswebbgränssnitt.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Använd leverantörssamarbete för att arbeta med externa leverantörer</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Hantera användare av leverantörssamarbete</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Skapa och underhåll leverantörssamarbete</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Använd leverantörssamarbete för att arbeta med kunder i Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Översikt
Mobil arbetsyta för leverantörssamarbete sparar information om nya inköpsorder så att de kan visa och svara på inköpsorder i webbklienten för Dynamics 365 for Operations. 

**Obs!:** Den mobila arbetsytan kan användas som ett tillägg till leverantörswebbgränssnittet, men ingen ersättning. 

Med mobil arbetsyta för leverantörssamarbete kan leverantörerna visa nya inköpsorder som har skickats för godkännande. Den visar inköpsorderinformation som till exempel produkter, kvantitet och begärt leveransdatum. Prisuppgifter finns tillgängliga, beroende på konfigurationen för varje leverantör. 

När en användare loggar in som en leverantör, visas vilka inköpsorder som har har svarat eller vilken inköpsorder som fortfarande väntar på kundåtgärd. Leverantören kan ha föreslås ett annat leveransdatum som inte ännu har kommits överens med kunden så att inköpsordern väntar på kundåtgärden. Dessutom vill leverantören se en lista över inköpsorder som har bekräftats men ännu inte levererats. 

För att svara på en inköpsorder måste säljaren använda webbgränssnittet för leverantörssamverkan som finns i webbklienten Dynamics 365 for Operations. Det här är också där som leverantören kommer att få mer information om beställningen, till exempel dokumentfiler, leveransadress per rad och avgifter som är kopplade till leverantören. 

Med en särskild säkerhetsroll kan leverantören se vilka kontaktpersoner som är registrerade för ett leverantörskonto. Med samma säkerhetsroll kan leverantören visa status för alla användarförfrågningar som har skickats in. 

Skapa nya kontakter och skicka nya användarförfrågningar måste göras i leverantörsamarbetesgränssnitt som finns tillgängligt i webbklienten Dynamics 365 for Operations. 

Med mobil arbetsyta kan leverantören:

-   Visa nya inköpsorder som skickats till leverantören.
-   Visa inköpsorder som leverantören har svarat på och som väntar på kundåtgärd.
-   Visa inköpsorder som har statusen bekräftat och inte har inlevererats helt.
-   Visa kontaktpersoninformation som har registrerats för leverantörskontot (kräver ytterligare en säkerhetsroll).
-   Visa information och följ statusen för en användarförfrågan som skickats av leverantören (kräver ytterligare en säkerhetsroll).

## <a name="get-started"></a>Kom igång
Komma igång med din mobila enhet:

1.  Hämta och installera appen Microsoft Dynamics 365 for Operations från din mobilappsbutik.
2.  Starta appen på din enhet.
3.  Ange din webbadress för Dynamics 365.
4.  Ange ett företag att logga in på. Ange till exempel **USMF**.
5.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 for Operations-konto.

När du loggar in i appen syns inga arbetsytor. Om du vill visa arbetsytor i din mobilapp måste du först publicera önskade arbetsytor i appen Dynamics 365 for Operations app. Du behöver systemadministrationsbehörighet för att publicera på arbetsytan.

1.  Starta Dynamics 365 for Operations.
2.  Navigera till **Systemadministration** &gt; **Inställningar** &gt; **systemparametrar**.
3.  Välj **Hantera mobilapp**.
4.  Markera arbetsytan **Leverantörssamarbete** för att publicera i den mobila plattformen.
5.  Välj **Publicera arbetsytan**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.
7.  Välj **Faktureringsarbetsyta för leverantörssamarbeten** Du kommer till nästa sida.

    [![mobilapp-för-leverantörssamarbetes](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kontakter
Sidan **kontakter** låter dig visa alla kontakter som har ställts in för leverantörskontot. Den visar kontaktpersonens namn och primära e-postadress och användaralias, om sådana finns. Den visar också om kontaktpersonens användarkonto är aktivt. När du väljer en kontakt finns kontaktinformation, till exempel vilka juridiska personer som personen är kontakt för och kontaktinformation som till exempel telefonnummer eller någon annan e-postadress.

## <a name="user-requests"></a>Användarförfrågningar
Sidan **användarfrågor** låter dig se alla användarförfrågningar som du har skickat in via leverantörswebbgränssnittet och följa status. När du väljer en användarförfrågan kan du se vad som förfrågades, lägga till eller inaktivera en användare, ändra säkerhetsinställningar och se vilka säkerhetsroller som krävdes för användaren.

## <a name="purchase-orders-ready-for-review"></a>Inköpsorder redo för granskning
Sidan **inköpsorder som är redo för granskning** låter dig se alla inköpsorder som har skickats av kunden och har inte besvarats. Du kan visa utvald information om ordern, till exempel vilka produkter som har begärts och när du kan leverera. Prisuppgifter finns bara om det har konfigurerats för leverantören. Du kan se om inköpsordern har anteckningar och bifogade filer. För att öppna bifogade filer måste du använda leverantörssamarbete i webbklienten. Välj **inköpsorderrad** för att visa alla rader med information. Observera att för varje rad visar en indikator om det finns anteckningar och bilagor, eller om det finns en leveransadress som är en annan än vad som anges i rubriken. Om du vill svara på inköpsordern måste du använda webbklienten för leverantörssamarbete.

## <a name="awaiting-customer-action"></a>Väntar på kundåtgärd
Sidan **Inväntar kundåtgärd** låter dig söka efter inköpsorder som du eller någon i företaget som har åtkomst till leverantörssamarbete har svarat på. Inköpsorder visas bara i listan om kunden måste du göra något av följande åtgärder på inköpsordern.

-   Om inköpsordern har avvisats skulle kunden antingen behöva uppdatera den skickade ordern och skicka igen, eller avbryta ordern och skicka igen. När inköpsordern har skickats igen, försvinner den från sidan **Inväntar kundåtgärd**.
-   Om inköpsordern togs emot med ändringar skulle kunden behöva uppdatera den ursprungliga ordern och skicka om för granskning, eller uppdatera enligt ändringarna och bekräfta det omedelbart. I båda fall kommer inköpsordern att försvinna från sidan **Inväntar kundåtgärd**.
-   Om inköpsordern som har godkänts och visas på sidan **Inväntar kundåtgärd** beror det på att inköpsordern inte bekräftades automatiskt när mottagande gjordes. Den väntar på att en inköpsagent ska ändra ordern till Bekräftad. Vanligtvis skulle inköpsordern betraktas som ett avtal mellan kund och leverantör så snart som leverantören accepterar ordern. Flytta inköpsordern till statusen bekräftat blir en formalitet.

Genom att välja inköpsordern, visas ytterligare information om svaret. Du kan se raddetaljer och svar för varje rad. Radstatus visar i vilket av följande svar som har getts.

-   Godkänt
-   Avvisat
-   Godkänd med ändringar
-   Ersatt/ersättning
-   Dela upp i schema/schemarad

Observera att en indikator visar **sända**= Ja/Nej, som används för att ange att raderna inte kommer att levereras. Detta kan bero på att raden avslogs eller ersätts där de ursprungliga raderna inte förväntas levereras eller en rad som har delats upp i flera schemarader och den ursprungliga raden inte förväntas levereras enligt vad som begärts i den inlevererade ordern. Eventuella ändringar i orderradsvaret visas förutom överförda anteckningar och bifogade filer, som du kan se genom att använda webbgränssnittet för leverantörssamarbete.

## <a name="open-confirmed-orders"></a>Öppna bekräftade order
När inköpsordern har bekräftats av kunden, vilket betyder att inköpsordern ändras till statusen bekräftat visas den i den öppna bekräftade ordern. Den ligger i listan tills den registreras som mottagen av kunden.





