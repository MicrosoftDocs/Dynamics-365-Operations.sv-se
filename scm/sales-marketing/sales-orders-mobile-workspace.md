---
title: "Mobil arbetsyta för försäljningsorder"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för Försäljningsorder. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst."
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: 1a05c6c12d4b6d98886e418aadcc0bdb2c2fc8ef
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Mobil arbetsyta för försäljningsorder
<a id="sales-orders-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet innehåller information om den mobila arbetsytan för **Försäljningsorder**. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst. 

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.

## Översikt
<a id="overview" class="xliff"></a>
Den mobila arbetsytan **Försäljningsorder** låter dig visa detaljerad information om varje försäljningsorder. Informationen innehåller status för den ordern, kontaktinformation för kunden och kontaktinformation för ordermottagaren. Den mobila arbetsytan för **försäljnigsorder** ger en direkt översikt över försäljningsorder. Du kan visa alla försäljningsorder, visa försäljningsorder per kund, eller visa information om en specifik försäljningsorder. 

Den mobila arbetsytan innehåller två vyer som hjälper dig att analysera försäljningsorder på djupet.

### Visa alla försäljningsorder
<a id="view-all-sales-orders" class="xliff"></a>
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

### Visa order för en kund
<a id="view-orders-for-a-customer" class="xliff"></a>
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

## Förutsättningar
<a id="prerequisites" class="xliff"></a>
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### Kraven om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 uppdatering
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Om Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) har implementerats för din organisation, måste systemadministratören publicera den mobila arbetsytan **Försäljningsorder**. Instruktioner finns i [Publicera en mobil arbetsyta](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Krav om du använder Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare
<a id="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
Om Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav. 

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
<td>Implementera KB 4013633.</td>
<td>Systemadministratör</td>

<td>KB 4013633 är en X++ -uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>Försäljningsorder</strong>. Om du vill implementera KB 4013633 måste systemadministratören göra följande.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Försäljningsorder</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
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
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Visa information om försäljningsorder för en kund med hjälp av den mobila arbetsytan Försäljningsorder
<a id="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace" class="xliff"></a>

1.  På din mobila enhet väljer du arbetsytan **Försäljningsorder**.
2.  Välj **Visa order för en kund**.
3.  Använd konto- eller kundnamninformation för att hitta kunden.
4.  Välj kunden.
5.  Välj **Kontaktinformation** eller **Försäljningsorder**. Om du väljer **Försäljningsorder** visas en lista över försäljningsorder för kunden.
6.  Välj **Försäljningsorder**. Du kan nu visa information om försäljningsorderrader, information om leveranser, kundkontaktinformation och kontaktinformation för ordermottagaren.

