---
title: "Mobil arbetsyta för inköpsordergodkännande"
description: "Det här avsnittet innehåller information om den mobila arbetsytan Godkännande av inköpsorder där du kan visa inköpsorder och reagera på dem genom att utföra åtgärder. Du kan exempelvis godkänna eller avvisa en inköpsorder."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: a2ab719b971c325be184d1d950f6c03815e4cea2
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# Mobil arbetsyta för inköpsordergodkännande
<a id="purchase-order-approval-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Detta avsnitt innehåller information om den mobila arbetsytan **Godkännande av inköpsorder**. På den här arbetsytan kan du visa inköpsorder och reagera på dem genom att utföra åtgärder. Du kan exempelvis godkänna eller avvisa en inköpsorder.
 
## Översikt
<a id="overview" class="xliff"></a> 
Inköpsorder som kräver godkännande genomgår en arbetsflöde för godkännande. Arbetsflödet kan innehålla olika steg som kräver att en eller fler personer utför åtgärder. Exempelvis kanske en person behöva slutföra en aktivitet eller godkänna inköpsordern. 

Med hjälp av den mobila arbetsytan **Godkännande av inköpsorder** kan du lätt visa och svara på inköpsorder från din mobila enhet. På den här arbetsytan kan du utföra samma arbetsflödesåtgärder som du kan utföra från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, web client.

## Förutsättningar
<a id="prerequisites" class="xliff"></a>
Förutsättningarna varierar beroende på vilken version av Finance and Operations som har distribuerats inom organisationen.

### Kraven om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 uppdatering
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Om Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juliuppdateringen 2017) har implementerats för din organisation måste systemadministratören publicera den mobila arbetsytan **Godkännande av inköpsorder**. Instruktioner finns i [Publicera en mobil arbetsyta](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

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
<td>Implementera KB 4017918.</td>
<td>Systemadministratör</td>
<td>KB 4017918 är en X++-uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>. Om du vill implementera KB 4017918 måste systemadministratören göra följande.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Snabbkorrigering av metadata</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Tillämpa ett distribuerbart paket</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## Hämta och installera mobilappen
<a id="download-and-install-the-mobile-app" class="xliff"></a>
Hämta och installera mobilappen Microsoft Dynamics 365 for Unified Operations:

- [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
- [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## Logga in på mobilappen
<a id="sign-in-to-the-mobile-app" class="xliff"></a>

1. Starta appen i din mobila enhet.
2. Ange din webbadress för Microsoft Dynamics 365.
3. Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4. När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

![Arbetsytan Godkännande av inköpsorder i listan över tillgängliga arbetsytor](./media/po-workspaces.png)

## Visa order som har tilldelats dig
<a id="view-orders-that-are-assigned-to-you" class="xliff"></a>
1. På din mobila enhet väljer du arbetsytan **Godkännande av inköpsorder**.
2. Välj **Order tilldelad till mig** om du vill visa alla inköpsorder som du har blivit ombedd att vidta åtgärder för i arbetsflödet Godkännande av inköpsorder.
3. Välj en order. På sidan **Orderinformation** visas informationen i orderrubriken och raderna. Du kan också finna riktlinjer för arbetsflödesuppgiften.
4. Välj **Redovisningsfördelningar** för att öppna sidan **Redovisningsfördelning, huvud**.
5. Gå tillbaka till sidan **Orderinformation** och markera en rad. Du kan även utforska radspecifika redovisningsfördelningar från raden Orderinformation.

## Utföra en åtgärd på inköpsordern
<a id="complete-an-action-on-the-purchase-order" class="xliff"></a>
När du har visat den inköpsorder som har tilldelats dig och läst instruktionerna om arbetsflödet bör du vara redo att vidta åtgärder.

1. På din mobila enhet väljer du arbetsytan **Godkännande av inköpsorder**.
2. Välj **Order tilldelad till mig** om du vill visa alla inköpsorder som du har blivit ombedd att vidta åtgärder för i arbetsflödet Godkännande av inköpsorder.
3. Markera en order och visa informationssidan.
4. Välj **Åtgärder** om du vill visa tillgängliga åtgärder. Vilka åtgärder som är tillgängliga beror på vilken uppgift som har tilldelats dig.

    | Aktivitetsåtgärd    | Godkännandeåtgärd  |
    |----------------|------------------|
    | Komplett       | Godkänn          |
    | Retur         | Avvisa           |
    | Begär ändring | Begär ändring   |
    | Delegera       | Delegera         |

5. Välj lämplig åtgärd.
6. Skriv en kommentar på sidan **Slutför uppgift**. Observera att om du väljer åtgärden **Delegera** måste du välja den användare du vill delegera uppgiften till.
7. Välj **Klar**. När du uppdaterar din arbetsyta kommer inköpsordern inte längre att finnas i listan. 
