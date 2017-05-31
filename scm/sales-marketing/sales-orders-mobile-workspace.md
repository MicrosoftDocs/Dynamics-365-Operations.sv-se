---
title: "Mobil arbetsyta för försäljningsorder"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för försäljningsorder som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11898146a13756a6bb22a769e37e8773484e0d04
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Mobil arbetsyta för försäljningsorder

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om den mobila arbetsytan för försäljningsorder som är tillgänglig för mobilappen Microsoft Dynamics 365 for Operations. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Översikt över Mobil arbetsyta för försäljningsorder
---------------------------------------------

Den **Mobila arbetsytan** för försäljningsorder ger åtkomst till Microsoft Dynamics 365 for Operations och du kan visa detaljerad information om varje försäljningsorder. Informationen innehåller status för den ordern, kontaktinformation för kunden och kontaktinformation för ordermottagaren. Den mobila arbetsytan för **försäljnigsorder** ger en direkt översikt över försäljningsorder. Du kan visa alla försäljningsorder, visa försäljningsorder per kund, eller visa information om en specifik försäljningsorder. 

Den mobila arbetsytan innehåller två vyer som hjälper dig att analysera försäljningsorder på djupet.

### <a name="view-all-sales-orders"></a>Visa alla försäljningsorder

Den här vyn visar en lista över alla försäljningsorder.

-   Använd ett av följande filter för att välja de försäljningsorder som du vill visa:
    -   Sök efter försäljningsorder
    -   Sök efter kundkonto
    -   Sök efter kundnamn
    -   Sök efter status
    -   Sök efter frisläppningsstatus
    -   Sök efter skapat datum och klockslag
    
-   När du valt en försäljningsorder kan visa du uppgifter om särskilda order. Du kann särskilt visa följande information:
    -   Information om kundens namn och adress
    -   Olika datum för försäljningsordern, till exempel det begärda leveransdatumet och det bekräftade leveransdatumet
    -   Kontaktinformation för ordermottagaren
    -   Kundens kontaktinformation
    -   Orderrader
    -   Leveranser som visar hur och när en försäljningsorder har levererats

### <a name="view-orders-for-a-customer"></a>Visa order för en kund

Denna vy listar försäljningsorder per kund.

-   Använd något av följande filter för att visa order för en kund:
    -   Sök efter namn
    -   Sök efter konto

-   När du har valt en kund kan du visa följande information:
    -   Kundens namn och grupp
    -   Kundens kontaktinformation
    -   Försäljningsorder för kunden och information om dessa försäljningsorder:
        -   Information om kundens namn och adress
        -   Olika datum för försäljningsorder
        -   Kontaktinformation för ordermottagaren
        -   Kundens kontaktinformation
        -   Orderrader
        -   Leveranser som visar hur och när en försäljningsorder har levererats

## <a name="prerequisites"></a>Förutsättningar
Innan du kan använda mobil arbetsyta för **Försäljningsorder** ska du se till att systemadministratören har följande förutsättningar på plats.

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
<td>Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare måste genomföras.</td>
<td>Systemadministratör</td>
<td>Om du inte redan använder Dynamics 365 for Operations i din organisation kan systemadministratören se <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment/">Distribuera en demomiljö för Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4013633 måste genomföras.</td>
<td>Systemadministratör</td>
<td>KB 4013633 (X++ uppdatering eller snabbkorrigering av metadata) innehåller fyra mobila arbetsytor för hantering av leveranskedjan. Om du vill implementera KB 4013633 måste systemadministratören göra följande:
<ol>
<li>Hämta KB 4013633 från Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Koppla det driftfärdiga paketet</a> till Dynamics 365 for Operations-systemet.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobil arbetsyta för <strong>försäljningsorder</strong> måste publiceras i mobilappen för Dynamics 365 for Operations.</td>
<td>Systemadministratör</td>
<td><ol>
<li>Starta Dynamics 365 for Operations i din webbläsare.</li>
<li>På sidan <strong>systemparametrar</strong> anger du <strong>Hantera mobila arbetsområden</strong>.</li>
<li>Välj arbetsytan <strong>försäljningsorder</strong>.</li>
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

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Visa information om försäljningsorder för en kund med den mobila arbetsytan
1.  På din mobila enhet väljer du arbetsytan **Försäljningsorder**.
2.  Välj **Visa order för en kund**.
3.  Använd konto- eller kundnamninformation för att hitta kunden.
4.  Välj kunden.
5.  Välj **Kontaktinformation** eller **Försäljningsorder**. Om du väljer **Försäljningsorder** visas en lista över försäljningsorder för kunden.
6.  Välj **Försäljningsorder**. Du kan nu visa information om försäljningsorderrader, information om leveranser, kundkontaktinformation och kontaktinformation för ordermottagaren.





