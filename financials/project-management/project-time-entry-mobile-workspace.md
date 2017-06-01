---
title: "Mobil arbetsyta för projekttidangivelse för appen Dynamics 365 for Operations"
description: "Det här avsnittet innehåller information om Mobil arbetsyta för projekttidangivelse. Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet."
author: annbe
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9c592c301908898915164e9236850759b73543fe
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Mobil arbetsyta för projekttidangivelse

[!include[banner](../includes/banner.md)]



Det här avsnittet innehåller information om den mobila arbetsytan för projekttidangivelse för mobilappen Microsoft Dynamics 365 for Operations. Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Översikt över Mobil arbetsyta för projekttidangivelse
---------------------------------------------------

Som ett led i sitt dagliga arbete är projektresurser ofta på plats eller på resande fot. Arbetsytan för **projekttidangivelse** låter användarna mata in sin fakturerbara tid eller ej fakturerbara tid mot ett projekt på den mobila enheten efter eget val. Därför registrerar projektresurser tidangivelse när som helst och var som helst. De kan också visa tidangivelse som redan har registrerats. 

Närmare bestämt erbjuder mobila arbetsytan för **Projekttidsangivelse** följande funktioner:

-   Ange antalet timmar som du ägnar till en specifik uppgift för alla valda datum.
-   Sök efter projektnamn eller kund och hitta projektet du vill registrera tid för.
-   Ange kategori och aktivitet under den tid som du ägnar.
-   Ange hur mycket tid som är fakturerbar tid eller ej fakturerbart för projektet.
-   Ange eventuella interna eller externa kommentarer.

Om du vill implementera den mobila arbetsytan för **Projekttidsangivelse**, se följande delar i det här avsnittet.

## <a name="prerequisites"></a>Förutsättningar
Innan du kan implementera **Mobil arbetsyta för projekttidsangivelse** ska du se till att systemadministratören har slutfört följande förutsättningar.

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
<td>Om du inte redan använder Dynamics 365 for Operations i din organisation kan systemadministratören se <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Distribuera en demomiljö för Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4018050 måste genomföras.</td>
<td>Systemadministratör</td>
<td>KB 4018050 är X ++ uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>projekttidangivelse</strong>. Om du vill implementera KB 4018050 måste systemadministratören göra följande.
<ol>
<li>Hämta KB 4018050 från Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket</a> som innehåller modellerna <strong>ApplicationSuite</strong> och <strong>ProjectMobile</strong> och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Koppla det driftfärdiga paketet</a> till Dynamics 365 for Operations-systemet.</li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>Mobil arbetsyta för projekttidangivelse</strong> måste publiceras i mobilappen för Dynamics 365 for Operations.</td>
<td>Systemadministratör</td>
<td><ol>
<li>Starta Dynamics 365 for Operations i din webbläsare.</li>
<li>På sidan <strong>systemparametrar</strong> på fliken <strong>Hantera mobila arbetsområden</strong> väljer du arbetsytan <strong>projekttidangivelse</strong>.</li>
<li>Klicka på <strong>Publicera mobil arbetsyta</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Hämta och installera mobilappen Dynamics 365 for Operation.
Hämta och installera mobilappen Dynamics 365 for Operation från din mobilappsbutik.

-   För Android - [Dynamics 365 for Operations i Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   För iPhone: [Dynamics 365 for Operations iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Logga in på mobilappen Dynamics 365 for Operations
1.  Starta appen i din mobila enhet.
2.  Ange URL för Dynamics 365 for Operations
3.  Ange ett företag att logga in på. Ange till exempel **USMF**.
4.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter.
5.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Ange tid genom att använda mobila arbetsytan för projekttidangivelse
1.  På din mobila enhet väljer du arbetsytan **projekttidangivelse**.
2.  Välj **tidangivelse**. Du kan se kalenderdatum under den aktuella veckan.
3.  Välj för ett valt datum **åtgärder** &gt; **ny post**.
4.  Ange antalet timmar att registrera.
5.  Välj nästa projekt för nästa tidsangivelse. Du kan se en lista över de projekt som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Om projektet inte finns i listan väljer du **Sök** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter namn eller gå till sök efter projektnamn eller kund.
7.  Markera en kategori. Du kan se en lista över de kategorier som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Om kategorin inte finns i listan väljer du **Sök** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter kategori eller växla om du vill söka efter kategorinamnet.
9.  Välj en aktivitet. Du kan se en lista över de aktiviteter som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information bör utvecklare finns [Den mobila plattformen för Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Om aktiviteten inte finns i listan väljer du **Sök** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter aktivitetsnummer eller växla till att söka efter funktion.
11. Välj radegenskapen.
12. Tillval: Ange eventuella interna och externa kommentarer.
13. Välj **Klar**.






