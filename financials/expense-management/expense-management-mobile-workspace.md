---
title: "Mobil arbetsyta för utgiftshantering"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för utgiftshantering som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Den här arbetsytan låter användarna hämta och skicka ett kvitto så att de kan bifogas till en utgiftsrapport senare. Den mobila arbetsytan låter även användare snabbt skapa en utgiftsrad med en kopplad inleverans."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 8bc47c5b170fd7dd8f6288682aad6eae1d2dc09a
ms.openlocfilehash: 9d3b7a4d5184c3c4958f4298f1d3dd4de0cd06d6
ms.contentlocale: sv-se
ms.lasthandoff: 04/26/2017


---

# <a name="expense-management-mobile-workspace"></a>Mobil arbetsyta för utgiftshantering

[!include[banner](../includes/banner.md)]

"[!include[banner](../includes/banner.md)]"


Det här avsnittet innehåller information om den mobila arbetsytan för utgiftshantering som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Den här arbetsytan låter användarna hämta och skicka ett kvitto så att de kan bifogas till en utgiftsrapport senare. Den mobila arbetsytan låter även användare snabbt skapa en utgiftsrad med en kopplad inleverans.

<a name="overview-of-the-expense-management-mobile-workspace"></a>Översikt över Mobil arbetsyta för utgiftshantering
---------------------------------------------------

Många organisationer kräver att en kopia av ett kvitto ska kopplas till en reserelaterad eller affärsrelaterad utgiftsrapport som medarbetaren skickar till dig. Den mobila arbetsytan **utgiftshantering** låter användare snabbt skapa nya utgiftsrader med ett bifogad foto på ett kvitto på den mobila enheten efter eget val. Användare kan även fånga en bild av en inleverans och sedan koppla den till en utgiftsrapport. Den mobila arbetsytan **utgiftshantering** används för att:

-   Ta en bild av en inleverans och överföra den till Microsoft Dynamics 365 for Operations. En användare kan sedan bifoga den bilden i en utgiftsrapport senare.
-   Överför en fil som ett insamlat kvitto. En användare kan sedan bifoga den filen i en utgiftsrapport senare.
-   Skapa en ny utgiftsrad med en kopplad inleverans. En användare kan sedan lägga till artikeln i en utgiftsrapport senare och skicka det för godkännande och återbetalning.

De andra delarna i det här avsnittet innehåller information om hur du implementerar och använder den mobila arbetsytan **utgiftshantering**.

## <a name="prerequisites"></a>Förutsättningar
Innan du kan implementera **Mobil arbetsyta för utgiftshantering** ska du se till att systemadministratören har slutfört följande förutsättningar.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Roll</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare måste genomföras.</td>
<td>Systemadministratör</td>
<td>Om du inte redan använder Dynamics 365 for Operations i din organisation kan systemadministratören se <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Distribuera en demomiljö för Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4019015 måste genomföras.</td>
<td>Systemadministratör</td>
<td>KB 4019015 (X++ uppdatering eller snabbkorrigering av metadata) innehåller fyra mobila arbetsytor för hantering av leveranskedjan. Om du vill implementera KB 4019015 måste systemadministratören göra följande:
<ol>
<li>Hämta KB 4019015 från Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Snabbkorrigering av metadata</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Skapa ett driftfärdigt paket</a> som innehåller modellerna <strong>ApplicationSuite</strong> och modellen <strong>ExpenseMobile</strong> och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Koppla det driftfärdiga paketet</a> till Dynamics 365 for Operations-systemet.</li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Mobil arbetsyta för utgiftshantering</strong> måste publiceras i mobilappen för Dynamics 365 for Operations.</td>
<td>Systemadministratör</td>
<td><ol>
<li>Starta Dynamics 365 for Operations i din webbläsare.</li>
<li>På sidan <strong>systemparametrar</strong> anger du <strong>Hantera mobila arbetsområden</strong>.</li>
<li>Välj <strong>Mobil arbetsyta för utgiftshantering</strong></li>
<li>Klicka på <strong>Publicera mobil arbetsyta</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Hämta och installera mobilappen Dynamics 365 for Operation.
Hämta och installera mobilappen Dynamics 365 for Operation från din mobilappsbutik.

-   För Android - [Dynamics 365 for Operations i Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   För iPhone: [Dynamics 365 for Operations iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)
-   För Windows phone (Universal Windows-plattform \[UWP\]): kommer snart!

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Logga in på mobilappen Dynamics 365 for Operations
1.  Starta appen i din mobila enhet.
2.  Ange URL för Dynamics 365 for Operations
3.  Ange ett företag att logga in på. Ange till exempel **USMF**.
4.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter.
5.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor. [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Skapa en inleverans med hjälp av mobil arbetsyta för utgiftshantering
1.  På din mobila enhet väljer du arbetsytan **Utgiftshantering**.
2.  Välj **Samla in kvitto**.
3.  Välj **ta foto** eller **Välj bild**.
4.  Om du har valt **ta foto**, gör du följande:
    1.  Du förflyttas till kameran på din mobila enhet så att du kan ta ett foto på kvittot. När du är klar med en bild klickar du på **OK** för att acceptera fotot.
    2.  Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

     Eller om du har valt **Välj bild**, gör du följande:
    1.  Välj en bild i listan.
    2.  Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

5.  Välj **Klar**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Snabb utgiftspost med mobil arbetsyta för utgiftshantering
1.  På din mobila enhet väljer du arbetsytan **Utgiftshantering**.
2.  Välj **snabb utgiftspost**.
3.  Välj kategori för utgiften. Du kan se en lista över de utgiftskategorier som laddas i ditt program för användning offline. Upp till 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Om kategorin inte finns i listan väljer du **Sök** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter kostnadskategori eller växla om du vill söka efter utgiftstyp.
4.  Ange transaktionsdatum för utgiften.
5.  Valfritt: Ange handlare för utgiften.
6.  Ange belopp för utgiften.
7.  Välj valutakod för utgiften. Du kan se en lista över de valutakoder som laddas i ditt program för användning offline. Upp till 400 valutor laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/). Om valutan inte finns i listan väljer du **Sök** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter valuta eller växla om du vill söka efter namnet.
8.  Välj **ta foto** eller **Välj bild**.
9.  Om du valde **Ta foto** förflyttas du till kameran på din mobila enhet så att du kan ta ett foto på kvittot. När du är klar med en bild klickar du på **OK** för att acceptera fotot.  eller om du har valt **Välj bild**, markerar du en bild i listan.
10. Välj **Klar**.






