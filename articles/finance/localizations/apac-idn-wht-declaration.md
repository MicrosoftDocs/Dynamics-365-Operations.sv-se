---
title: Källskatterapport för Indonesien
description: I det här avsnittet beskrivs hur du konfigurerar och genererar rapport för källskattedeklaration för Indonesien.
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6cf2f9240ea747054578c52343af34b15c250f38
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/21/2021
ms.locfileid: "7943666"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Källskatterapport för Indonesien (ID-00005)

[!include [banner](../includes/banner.md)]

Det här ämnet förklarar hur man ställer in och genererar PPH-källskattefilen som juridiska personer i Indonesien använder för att rapportera källskattetransaktioner i e-Bupot-appen.

Den indonesiska skattemyndigheten (DGT) fastställer att skattepliktiga företagare (PKP) som är registrerade hos KPP Pratama som skatteinnehållare/uppbärare av inkomstskatt (PPh) artikel 23 och/eller artikel 26 ska elektroniskt rapportera inkomstdeklaration artikel 23 och 26 genom att använda e-Bupot-appen. 

- **Artikel 23** – Rapporten innehåller alla källtransaktioner från leverantörer där lands-/regionkoden för den primära adressen är koden för Indonesien.
- **Artikel 26** – Rapporten innehåller alla källtransaktioner från leverantörer där lands-/regionkoden för den primära adressen som inte är koden för Indonesien.

## <a name="prerequisites"></a>Förutsättningar

- Den primära adressen för den juridiska personen måste dock finnas i Indonesien.
- I arbetsytan **funktionshantering** måste funktionen **Global källskatt** aktiveras. Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>Hämta konfigurationer för elektronisk rapportering

Genereringen av en importfil baseras på konfigurationen elektronisk rapportering (ER). Mer information om möjligheterna med och koncepten med konfigurerbara rapporter finns i [Elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Information om hur du testar produktion och användares godkännande (UAT), följ instruktionerna i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Om du vill generera importfilen överför du följande konfigurationer från databasen:

- **Tax declaration model.version.93.xml** eller senare version
- **Tax declaration model mapping.version.93.153.xml** eller senare version
- **WHT PPh schema import (ID).version.93.14** eller en senare version

## <a name="set-up-general-ledger-parameters"></a>Ställ in redovisningsparametrar

1. Gå till **Moms** \> **Inställningar** \> **Redovisningsparametrar**.
2. På fliken **källskatt** i fältet **WHT mappning av deklarationsformat**, välj **WHT PPh-schemaimport (ID)**. 
3. Gå till **Moms** \> **Inställningar** \> **Källskatt** \> **Typer av källskatteintäkter** för att ange **Kode Bukti Potong** intäktstyp för källskatt och sedan tilldela koderna till de relaterade kategorierna för källskatt. Koderna behövs för att generera integrationsfilen genom att använda programmet e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Generera källimportfilen

Processen för att förbereda och genererar e-Bupot-filen för en viss period baseras på källskattetransaktionerna som bokförs under kvittnings- och redovisningsjobbet.

Följ dessa steg för att skapa filen.

1. Gå till **Moms** \> **Deklarationer** \> **Källskatt** \> **PPH importfil e-bupot 23 och 26**.
2. Välj "från"-datum och "till"-datum för rapporten och välj sedan avräkningsperioden.
3. Ange transaktionsdatum och klicka sedan på **OK**.
4. Välj språk. Alla rapporter översätts till amerikansk engelska (**en-us**) och indonesiska (**id**).
5. Välj affärstyp och ange sedan check- och dokumentnummer. 
6. Kontrollera om rapporten har signerats av chefen. Denna information redovisas i filen. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
