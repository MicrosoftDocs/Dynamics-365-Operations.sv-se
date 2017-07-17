---
title: "Mobil arbetsyta för leverantörssamarbete"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för leverantörssamarbete. Den här arbetsytan hjälper till att hålla dina leverantörer uppdaterade om de inköpsorder som har skickats till dem för godkännande. De kan också visa information om nya och uppdaterade inköpsorder och kontakter."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 20e4c77bc47bffc3474559e3b9933b87e947e178
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Mobil arbetsyta för leverantörssamarbete
<a id="vendor-collaboration-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet innehåller information om den mobila arbetsytan för **Leverantörssamarbete**. Den här arbetsytan hjälper till att hålla dina leverantörer uppdaterade om de inköpsorder som har skickats till dem för godkännande. De kan också visa information om nya och uppdaterade inköpsorder och kontakter.

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.

## Översikt
<a id="overview" class="xliff"></a> 
Den mobila arbetsytan **Leverantörssamarbete** håller leverantörer informerade om nya inköpsorder, så att de kan visa och svara på dem i webbklienten för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. 

>[!NOTE]
> Den mobila arbetsytan ska användas som ett tillägg till webbgränssnittet för leverantörssamarbete, inte som en ersättning för det. 

Dina leverantörer kan använda den mobila arbetsytan **Leverantörssamarbete** för att visa nya inköpsorder som har skickats till dem för godkännande. Den visar information om inköpsorder såsom produkter, kvantiteter och begärda leveransdatum. Även prisuppgifter finns tillgängliga, beroende på konfigurationen för varje leverantör. 

En användare som loggar in som en leverantör ser vilka inköpsorder som har besvarats och vilka inköpsorder som fortfarande väntar på kundåtgärd. En inköpsorder kan exempelvis vänta på en kundåtgärd eftersom leverantören föreslog ett annat leveransdatum, men kunden har ännu inte accepterat det datumet. Dessutom kan leverantören se en lista över inköpsorder som har bekräftats men som ännu inte har levererats. 

För att svara på en inköpsorder måste leverantören använda webbgränssnittet för leverantörssamarbete som finns i webbklienten. Där kan leverantören även få mer information om beställningen såsom dokumentbilagor, leveransadress per rad och avgifter som är kopplade till leverantören. 

Leverantörer med en särskild säkerhetsroll kan se vilka kontaktpersoner som är registrerade för ett leverantörskonto. Med samma säkerhetsroll kan leverantören visa statusen för alla användarförfrågningar som har skickats in. 

Webbgränssnittet för leverantörssamarbete i webbklienten måste användas för att skapa nya kontakter och skicka begäranden om nya användare. 

Med hjälp av den mobila arbetsytan **Leverantörssamarbete** kan en leverantör utföra följande uppgifter:

-   Visa nya inköpsorder som har skickats till leverantören.
-   Visa inköpsorder som leverantören har svarat på och som väntar på kundåtgärd.
-   Visa inköpsorder som har bekräftats, men som ännu inte har mottagits till fullo.
-   Visa uppgifter om kontaktpersonen som är registrerad för leverantörskontot. (Den här uppgiften kräver ytterligare en säkerhetsroll.)
-   Visa information om en användarförfrågan som skickades av leverantören och följa statusen på densamma. (Den här uppgiften kräver ytterligare en säkerhetsroll.)

## Förutsättningar
<a id="prerequisites" class="xliff"></a>
Förutsättningarna varierar beroende på vilken version av Microsoft Dynamics 365 som har distribuerats inom organisationen.

### Kraven om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 uppdatering
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Om Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) har implementerats för din organisation måste systemadministratören publicera den mobila arbetsytan **Leverantörssamarbete**. Instruktioner finns i [Publicera en mobil arbetsyta](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
Om Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav. 

<table>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Roll</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>KB 3216943 måste implementeras om du använder plattformsuppdatering 3.</td>
<td>Systemadministratör</td>
<td>KB 3216943 är en binär uppdatering som krävs om du använder plattformsuppdatering 3. Om du vill implementera denna KB måste systemadministratören göra följande:
<ol>
<li>Hämta KB 3216943 från Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Installera den binära uppdateringen som levereras som ett distribuerbart paket. Information om hur du installerar ett distribuerbart paket hittar du under <a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>KB 4013633 måste genomföras.</td>
<td>Systemadministratör</td>
<td>KB 4013633 är en X++ -uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>lagerbehållning</strong>. Om du vill implementera KB 4013633 måste systemadministratören göra följande.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigeringen för metadata från LCS</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li><li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>
</ol></td>
</tr>
<tr class="odd">
<td>Den mobila arbetsytan <strong>Leverantörssamarbete</strong> måste publiceras.</td><td>Systemadministratör</td>
<td>Se <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
</tr>
<tr class="even">
<td>Leverantörsanvändaren måste har tillgång till webbgränssnittet för leverantörssamarbete webbklienten och måste ställa in en leverantörssamarbetesanvändare.</td><td>Inköpsansvariga och systemadministratör</td>
<td>Följ instruktionerna i följande avsnitt för att ställa in och arbeta med webbgränssnittet för leverantörssamarbete.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Använd leverantörssamarbete för att arbeta med externa leverantörer</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Hantera användare av leverantörssamarbete</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Skapa och underhåll leverantörssamarbete</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Använd leverantörssamarbetet för att arbeta med kunder i Finance and Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## Hämta och installera mobilappen
<a id="download-and-install-the-mobile-app" class="xliff"></a>

Hämta och installera mobilappen Dynamics 365 for Unified Operations:

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## Logga in på mobilappen
<a id="sign-in-to-the-mobile-app" class="xliff"></a>
1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Microsoft Dynamics 365.
4.  Första gången du loggar in uppmanas du att ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
5.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Använda den mobila arbetsytan för leverantörssamarbete
<a id="use-the-vendor-collaboration-mobile-workspace" class="xliff"></a>
När du väljer den mobila arbetsytan **Leverantörssamarbete** visas följande alternativ:

![Mobil arbetsyta för leverantörssamarbete](./media/vendor-collaboration-mobile-app.png)

Arbetsytan **Leverantörssamarbete** omfattar följande sidor:

### Kontakter
<a id="contacts" class="xliff"></a>
Sidan **kontakter** låter dig visa alla kontakter som har ställts in för leverantörskontot. Den visar kontaktpersonens namn, primär e-postadress och användaralias, om kontaktpersonen har ett alias. Sidan visar också om kontaktpersonens användarkonto är aktivt. När du väljer en kontakt visas kontaktinformation såsom juridiska personer som personen är kontaktperson för. Du kan också visa kontaktinformation, till exempel ett telefonnummer eller en alternativ e-postadress.

### Användarförfrågningar
<a id="user-requests" class="xliff"></a>
Sidan **Användarförfrågningar** låter dig se alla användarförfrågningar som du har skickat in via webbgränssnittet för leverantörssamarbete. Du kan också visa status för dessa förfrågningar. När du väljer en användarförfrågan kan du se vad som förfrågades, lägga till eller inaktivera en användare, ändra säkerhetsinställningar och se vilka säkerhetsroller som krävdes för användaren.

### Inköpsorder redo för granskning
<a id="purchase-orders-ready-for-review" class="xliff"></a>
Sidan **Inköpsorder klara för granskning** låter dig se alla inköpsorder som har skickats av kunden, men som inte har besvarats ännu. Du kan visa utvald information om ordern, till exempel vilka produkter som har begärts och när de produkterna ska levereras. Även prisuppgifter finns tillgängliga, beroende på konfigurationen av leverantören.

Du kan se om inköpsordern har anteckningar och bifogade filer. För att öppna anteckningar och bifogade filer måste du dock använda webbgränssnittet för leverantörssamarbete i webbklienten. Välj **Inköpsorderrad** för att visa alla rader tillsammans med information om dem. För varje rad visar en indikator om det finns anteckningar eller bilagor, eller om leveransadressen är en annan än den som anges i rubriken.

Om du vill svara på inköpsordern måste du använda webbgränssnittet för leverantörssamarbete i webbklienten.

### Väntar på kundåtgärd
<a id="awaiting-customer-action" class="xliff"></a>
Sidan **Inväntar kundåtgärd** låter dig söka efter inköpsorder som du, eller någon annan på företaget som har åtkomst till leverantörssamarbete, har svarat på. Inköpsorder visas bara i listan om kunden måste du vidta någon av följande åtgärder på inköpsordern:

-   Om inköpsordern har avvisats måste kunden antingen uppdatera eller avbryta den ursprungliga ordern och sedan skicka den igen. När inköpsordern har skickats igen försvinner den från sidan **Inväntar kundåtgärd**.
-   Om inköpsordern accepterades med ändringar måste kunden antingen uppdatera den ursprungliga ordern och sedan skicka den igen för granskning eller uppdatera ordern enligt ändringarna och sedan bekräfta det omedelbart. I båda fallen kommer inköpsordern att försvinna från sidan **Inväntar kundåtgärd**.
-   Om inköpsordern som accepterades fortfarande visas på sidan **Inväntar kundåtgärd** beror det på att inköpsordern inte bekräftades automatiskt när den accepterades. Den väntar nu på att en inköpsagent ska ändra orderstatusen till **Bekräftad**. Vanligtvis brukar inköpsordern betraktas som ett avtal mellan kunden och leverantören så snart leverantören accepterar ordern. Det innebär att uppdateringen till statusen **Bekräftad** vanligtvis bara är en formalitet.

När du väljer en inköpsorder visas ytterligare information om svaret. Du kan se raddetaljer och svar för varje rad. Radstatusen visar vilket av följande svar som har getts:

-   Godkänd
-   Avvisad
-   Godkänd med ändringar
-   Ersatt/ersättning
-   Dela upp i schema/schemarad

Observera att fältet **Levereras** ställs in på antingen **Ja** eller **Nej** för att ange om raderna ska levereras. En rad kan inte levereras på grund av följande skäl:

- Raden har avvisats.
- En ersättning gjordes och den ursprungliga raden förväntades inte levereras enligt förfrågan i den mottagna ordern.
- Raden är uppdelad i flera rader för tidsplaner och den ursprungliga raden förväntas inte levereras enligt förfrågan i den mottagna ordern.

All ändringar som har gjorts av responsen på orderraden visas. Dock visas inte överförda anteckningar och bifogade filer. För att visa anteckningar och bifogade filer måste du använda webbgränssnittet för leverantörssamarbete i webbklienten.

### Öppna bekräftade order
<a id="open-confirmed-orders" class="xliff"></a>
När inköpsordern har bekräftats av kunden (dvs. när statusen för inköpsordern har ändrats till **Bekräftad**) visas den i den öppna bekräftade ordern. Den finns kvar i listan tills den registreras som mottagen av kunden.

