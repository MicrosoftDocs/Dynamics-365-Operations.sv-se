---
title: "Mobil arbetsyta för fakturagodkännanden"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för fakturagodkännanden. Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud."
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6c95c2779d996f489679c8dda4cda462ba0a05ac
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="invoice-approvals-mobile-workspace"></a>Mobil arbetsyta för fakturagodkännanden

[!include[banner](../includes/banner.md)]

Detta avsnitt tillhandahåller innehåller information om den mobila arbetsytan för **fakturagodkännanden**. Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud. 

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>Översikt

Den mobila arbetsytan **Faktureringsgodkännanden** låter ansvariga och chefer inom leverantörsreskontra visa fakturor som har tilldelats till dem som ett led i arbetsflödet för leverantörsfakturahuvud. Du kan visa faktureringsinformationen - och till och med rad- och distributionsinformationen - för att hjälpa dig att fatta välinformerade godkännandebeslut. Från arbetsytan kan vidta du åtgärder för att flytta faktura genom arbetsflödesprocessen. 

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara uppfyllda innan du kan använda den här mobila arbetsytan.

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
<td>Microsoft Dynamics 365 for Finance and Operations måste användas inom din organisation.</td>
<td>Systemadministratör</td>
<td>Se <a href="../deployment/deploy-demo-environment.md">Distribuera en demonstrationsmiljö</a>.
</td>
</tr>
<tr class="even">
<td>Den mobila arbetsytan <strong>Fakturagodkännanden</strong> måste publiceras.</td>
<td>Systemadministratör</td>
<td>Se <a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Hämta och installera mobilappen Dynamics 365 for Unified Operations:

-   [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
-   [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1.  Starta appen i din mobila enhet.
2.  Ange din webbadress för Microsoft Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Godkänn fakturor genom att använda den mobila arbetsytan för fakturagodkännanden
1.  På din mobila enhet väljer du arbetsytan **Fakturagodkännanden**.
2.  Välj den faktura som har tilldelats dig av arbetsflödet för leverantörsfakturahuvud.
3.  På sidan **Fakturainformation** granskar du informationen i fakturahuvudet, till exempel leverantör och datum.
4.  Markera en rad på fakturan för att visa mer detaljerad information om den i vyn **Information om fakturarader**.
5.  I vyn **Information om fakturarader** väljer du **Fördelningar** för att visa radfördelningarna. Här kan du visa redovisningen för fakturaraden. Den information som visas inkluderar ekonomiska dimensioner och huvudkontot.
6.  På sidan **Fakturainformation** väljer du **Fördelningar** för att visa alla fördelningar. Här kan du visa redovisningen för hela fakturan. Den information som visas inkluderar ekonomiska dimensioner och huvudkonton. 
7.  Välj **Bilagor** för att visa noteringar eller filer som är kopplade till fakturan.
8.  På sidan **Fakturainformation** väljer du lämplig arbetsflödesåtgärd för att slutföra din granskningsprocess.
9.  Välj **Klar**.

