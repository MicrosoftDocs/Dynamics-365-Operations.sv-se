---
title: Mobil arbetsyta för försäljningsorder
description: Denna artikel innehåller information om den mobila arbetsytan för Försäljningsorder. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst.
author: Henrikan
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 38971f2a5f3f3d2692de0e52365e2215170101cc
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103193"
---
# <a name="sales-orders-mobile-workspace"></a>Mobil arbetsyta för försäljningsorder

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Denna artikel innehåller information om den mobila arbetsytan för **Försäljningsorder**. Arbetsytan hjälper dig att hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst. 

Denna mobila arbetsyta är avsedd att användas med mobilappen Ekonomi och drift (Dynamics 365).

## <a name="overview"></a>Översikt
Den mobila arbetsytan **Försäljningsorder** låter dig visa detaljerad information om varje försäljningsorder. Informationen innehåller status för den ordern, kontaktinformation för kunden och kontaktinformation för ordermottagaren. Den mobila arbetsytan för **försäljnigsorder** ger en direkt översikt över försäljningsorder. Du kan visa alla försäljningsorder, visa försäljningsorder per kund, eller visa information om en specifik försäljningsorder. 

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
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Förutsättningar om du använder Supply Chain Management 
Om Supply Chain Management används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Försäljningsorder**. Instruktioner finns i [Publicera en mobil arbetsyta](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Förutsättningar om du använder Dynamics 365 for Operations version 1611 med plattformsuppdateringen 3 eller senare
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
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigeringar för metadata från Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Försäljningsorder</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen
Ladda ner och installera mobilappen för Ekonomi och drift (Dynamics 365):

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

[![Dra nedåt för att uppdatera.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Visa information om försäljningsorder för en kund med hjälp av den mobila arbetsytan Försäljningsorder

1.  På din mobila enhet väljer du arbetsytan **Försäljningsorder**.
2.  Välj **Visa order för en kund**.
3.  Använd konto- eller kundnamninformation för att hitta kunden.
4.  Välj kunden.
5.  Välj **Kontaktinformation** eller **Försäljningsorder**. Om du väljer **Försäljningsorder** visas en lista över försäljningsorder för kunden.
6.  Välj **Försäljningsorder**. Du kan nu visa information om försäljningsorderrader, information om leveranser, kundkontaktinformation och kontaktinformation för ordermottagaren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

