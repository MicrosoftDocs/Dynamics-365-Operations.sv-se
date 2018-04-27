---
title: "Mobil arbetsyta för projekttidangivelse"
description: "Det här avsnittet innehåller information om Mobil arbetsyta för projekttidangivelse. Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9bf79af6eea6f899158fc3c8d523587cb11c90ad
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="project-time-entry-mobile-workspace"></a>Mobil arbetsyta för projekttidangivelse

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet innehåller information om den mobila arbetsytan **Projekttidsangivelse**. Den här arbetsytan låter användarna ange och spara tid för ett projekt genom att använda sin mobilenhet.

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations. 

## <a name="overview"></a>Översikt
Som ett led i sitt dagliga arbete är projektresurser ofta på plats eller på resande fot. Arbetsytan för **projekttidangivelse** låter användarna mata in sin fakturerbara tid eller ej fakturerbara tid mot ett projekt på den mobila enheten efter eget val. Därför registrerar projektresurser tidangivelse när som helst och var som helst. De kan också visa tidangivelse som redan har registrerats. 

I den mobila arbetsytan **Projekttidsangivelse** kan användarna utföra följande uppgifter:

-   Ange antalet timmar som du ägnar till en specifik uppgift för alla valda datum.
-   Sök efter projektnamn eller kund och hitta projektet du vill registrera tid för.
-   Ange kategori och aktivitet under den tid som du ägnar.
-   Ange hur mycket tid som är fakturerbar tid eller ej fakturerbart för projektet.
-   Ange eventuella interna eller externa kommentarer.

## <a name="prerequisites"></a>Förutsättningar
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Förutsättningar om du använder Microsoft Dynamics 365 for Finance and Operations.
Om Microsoft Dynamics 365 for Finance and Operations används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Projekttidsangivelse**. Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare
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

<td>Implementera KB 4018050.</td>
<td>Systemadministratör</td>
<td>KB 4018050 är X ++ uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>projekttidangivelse</strong>. Om du vill implementera KB 4018050 måste systemadministratören göra följande.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket</a> som innehåller modellerna <strong>ApplicationSuite</strong> och <strong>ProjectMobile</strong> och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Projekttidsangivelse</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Hämta och installera mobilappen Dynamics 365 for Unified Operations:

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen
1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Ange tid genom att använda mobila arbetsytan för projekttidangivelse
1.  På din mobila enhet väljer du arbetsytan **projekttidangivelse**.
2.  Välj **tidangivelse**. Du kan se kalenderdatum för den aktuella veckan.
3.  Välj för ett valt datum **åtgärder** &gt; **ny post**.
4.  Ange antalet timmar att registrera.
5.  Välj nästa projekt för nästa tidsangivelse. En lista visar de projekt som laddas in i din app för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Om projektet inte finns i listan, välj **Sök**. Sök efter namn eller gå till sök efter projektnamn eller kund.
7.  Markera en kategori. En lista visar de kategorier som laddas in i din app för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Om kategorin inte finns i listan, välj **Sök**. Sök efter kategori eller växla om du vill söka efter kategorinamnet.
9.  Välj en aktivitet. En lista visar de aktiviteter som laddas in i din app för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. För information, se [Mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Om aktiviteten inte finns i listan, välj **Sök**. Sök efter aktivitetsnummer eller växla till att söka efter funktion.

11. Välj radegenskapen.
12. Tillval: Ange eventuella interna och externa kommentarer.
13. Välj **Klar**.

