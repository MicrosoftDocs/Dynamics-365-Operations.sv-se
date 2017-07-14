---
title: "Mobil arbetsyta för fakturagodkännanden"
description: "Det här avsnittet innehåller information om den mobila arbetsytan för fakturagodkännanden. Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud."
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 70f3e0fe53fc0b1daa471a7022f5659d09caa867
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# Mobil arbetsyta för fakturagodkännanden
<a id="invoice-approvals-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Detta avsnitt tillhandahåller innehåller information om den mobila arbetsytan för **fakturagodkännanden**. Denna arbetsyta tillhandahåller en lista med fakturor som har tilldelats till dig via arbetsflödet för leverantörsfakturahuvud. 

Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.

## Översikt
<a id="overview" class="xliff"></a>

Den mobila arbetsytan **Faktureringsgodkännanden** låter ansvariga och chefer inom leverantörsreskontra visa fakturor som har tilldelats till dem som ett led i arbetsflödet för leverantörsfakturahuvud. Du kan visa faktureringsinformationen - och till och med rad- och distributionsinformationen - för att hjälpa dig att fatta välinformerade godkännandebeslut. Från arbetsytan kan vidta du åtgärder för att flytta faktura genom arbetsflödesprocessen. 

## Förutsättningar
<a id="prerequisites" class="xliff"></a>

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
<td>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (uppdatering juli 2017) måste vara implementerad i din organisation.</td>
<td>Systemadministratör</td>
<td>Se <a href="../deployment/deploy-demo-environment.md">Distribuera en demonstrationsmiljö</a>.
</td>
</tr>
<tr class="even">
<td>Den mobila arbetsytan <strong>Fakturagodkännanden</strong> måste publiceras.</td>
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
2.  Ange din webbadress för Microsoft Dynamics 365.
3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
4.  När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    [![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Godkänn fakturor genom att använda den mobila arbetsytan för fakturagodkännanden
<a id="approve-invoices-by-using-the-invoice-approvals-mobile-workspace" class="xliff"></a>
1.  På din mobila enhet väljer du arbetsytan **Fakturagodkännanden**.
2.  Välj den faktura som har tilldelats dig av arbetsflödet för leverantörsfakturahuvud.
3.  På sidan **Fakturainformation** granskar du informationen i fakturahuvudet, till exempel leverantör och datum.
4.  Markera en rad på fakturan för att visa mer detaljerad information om den i vyn **Information om fakturarader**.
5.  I vyn **Information om fakturarader** väljer du **Fördelningar** för att visa radfördelningarna. Här kan du visa redovisningen för fakturaraden. Den information som visas inkluderar ekonomiska dimensioner och huvudkontot.
6.  På sidan **Fakturainformation** väljer du **Fördelningar** för att visa alla fördelningar. Här kan du visa redovisningen för hela fakturan. Den information som visas inkluderar ekonomiska dimensioner och huvudkonton. 
7.  Välj **Bilagor** för att visa noteringar eller filer som är kopplade till fakturan.
8.  På sidan **Fakturainformation** väljer du lämplig arbetsflödesåtgärd för att slutföra din granskningsprocess.
9.  Välj **Klar**.
