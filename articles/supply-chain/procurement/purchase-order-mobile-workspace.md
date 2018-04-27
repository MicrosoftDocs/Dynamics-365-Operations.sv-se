---
title: "Mobil arbetsyta för inköpsordergodkännande"
description: "Det här avsnittet innehåller information om den mobila arbetsytan Godkännande av inköpsorder där du kan visa inköpsorder och reagera på dem genom att utföra åtgärder. Du kan exempelvis godkänna eller avvisa en inköpsorder."
author: mkirknel
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2f495fa3507fd54499e29b4c09f504dd037c0a6c
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="purchase-order-approval-mobile-workspace"></a>Mobil arbetsyta för inköpsordergodkännande

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

Detta avsnitt innehåller information om den mobila arbetsytan **Godkännande av inköpsorder**. På den här arbetsytan kan du visa inköpsorder och reagera på dem genom att utföra åtgärder. Du kan exempelvis godkänna eller avvisa en inköpsorder.
 
## <a name="overview"></a>Översikt 
Inköpsorder som kräver godkännande genomgår en arbetsflöde för godkännande. Arbetsflödet kan innehålla olika steg som kräver att en eller fler personer utför åtgärder. Exempelvis kanske en person behöva slutföra en aktivitet eller godkänna inköpsordern. 

Med hjälp av den mobila arbetsytan **Godkännande av inköpsorder** kan du lätt visa och svara på inköpsorder från din mobila enhet. På den här arbetsytan kan du utföra samma arbetsflödesåtgärder som du kan utföra från webbklienten Microsoft Dynamics 365 for Finance and Operations.

## <a name="prerequisites"></a>Krav
Förutsättningarna varierar beroende på vilken version av Finance and Operations som har distribuerats inom organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Förutsättningar om du använder Microsoft Dynamics 365 for Finance and Operations. 
Om Microsoft Dynamics 365 for Finance and Operations används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Godkännande av inköpsorder**. Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Implementera KB 4017918.</td>
<td>Systemadministratör</td>
<td>KB 4017918 är en X++-uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>. Om du vill implementera KB 4017918 måste systemadministratören göra följande.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Publicera den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen
Hämta och installera mobilappen Microsoft Dynamics 365 for Unified Operations:

- [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
- [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1. Starta appen i din mobila enhet.
2. Ange din webbadress för Microsoft Dynamics 365.
3. Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4. När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

![Arbetsytan Godkännande av inköpsorder i listan över tillgängliga arbetsytor](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Visa order som har tilldelats dig
1. På din mobila enhet väljer du arbetsytan **Godkännande av inköpsorder**.
2. Välj **Order tilldelad till mig** om du vill visa alla inköpsorder som du har blivit ombedd att vidta åtgärder för i arbetsflödet Godkännande av inköpsorder.
3. Välj en order. På sidan **Orderinformation** visas informationen i orderrubriken och raderna. Du kan också finna riktlinjer för arbetsflödesuppgiften.
4. Välj **Redovisningsfördelningar** för att öppna sidan **Redovisningsfördelning, huvud**.
5. Gå tillbaka till sidan **Orderinformation** och markera en rad. Du kan även utforska radspecifika redovisningsfördelningar från raden Orderinformation.

## <a name="complete-an-action-on-the-purchase-order"></a>Utföra en åtgärd på inköpsordern
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

