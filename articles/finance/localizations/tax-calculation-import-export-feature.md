---
title: Beräkningar av import- och exportskatt
description: Det här ämnet innehåller information om import- och exportfunktionen för beräkningstjänsten.
author: Kai-Cloud
ms.date: 10/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690244"
---
# <a name="import-and-export-tax-calculations"></a>Beräkningar av import- och exportskatt

Det här ämnet innehåller information om import- och exportfunktionen för beräkningstjänsten. Med den här funktionen får du en flexibel och effektiv konfigurationserfarenhet.

## <a name="import-and-export-tax-codes"></a>Import- och exportskattekoder

### <a name="export-templates"></a>Exportmallar

1. Logga in på [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. I arbetsytan **Globaliseringsfunktioner** väljer du **Funktioner** och sedan panelen **Skatteberäkning**.
3. Välj en befintlig funktion eller [skapa en ny funktion](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. I rutnätet **Versioner**, välj **Redigera**.
5. På funktionssidan **Momsberäkning** ange [konfigurationsversionen](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Välj **Momskoder** på fliken **Importera**.
7. Välj **Mallen exportera en momskod** om du vill hämta filen **TaxCodesTemplate.zip**. 
8. Avmarkera **TaxCodesTemplate.zip**. Momskodsmallarna komprimeras separat enligt värdet för **Beräkningsursprung**.
9. Avmarkera **Efter nettobelopp.zip** för att få följande kommaavgränsade värden (CSV)-filer:

    - **TaxCode.csv** – Ange momskoderna.
    - **TaxLimit.csv** – Ange momsbegränsningar för varje momskod.
    - **TaxRate.csv** – Ange momssatser för varje momskod.

> [!NOTE]
> Som standard finns poster för momskoden **Exempel** tillgängliga i mallarna. Om momskoden **Exempel** inte tas bort från CSV-filerna, importeras den till funktionen.

### <a name="import-tax-codes"></a>Importera momskoder

Följ dessa steg för att importera momskoden **Exempel** i mallen till funktionen för momsberäkning.

1. I RCS, på funktionssidan **Momsberäkning** på fliken **Momskoder**, välj **Importera**.
2. Välj **Bläddra**, sök efter och markera filen **TaxCode.csv** och välj sedan fältet **Målregister** i **Momskod**. 
3. Välj **OK** för att importera momskoden.
4. Sök och markera filen **TaxRate.csv** och sedan i fältet **Målregister** välj **Momskod**.
5. Välj **OK** för att importera momssats.
6. Sök och markera filen **TaxLimit.csv** och sedan i fältet **Målregister** välj **Momsgräns**.
7. Välj **OK** för att importera momsgräns.

Du kan också importera zip-filen direkt som innehåller alla tre CSV-filer. På det här sättet kan du snabbt och enkelt slutföra importen.

1. I RCS, på funktionssidan **Momsberäkning** på fliken **Momskoder**, välj **Importera**.
2. Välj **Bläddra**, sök efter och markera filen **Efter nettobelopp.zip** och välj **OK**.

### <a name="export-tax-codes"></a>Exportera momskoder

1. I RCS, på funktionssidan **Momsberäkning** på fliken **Momskoder**, välj **Exportera**.

    Knappen **Exportera** är tillgänglig när det finns minst en momskod i rutnätet **momskoder**.

2. Välj **OK** om du vill exportera alla momskoder för funktionen i en zip-fil.

> [!NOTE]
> Använd den exporterade filen som en mall för att importera momskoder till motsvarande funktion.

## <a name="import-and-export-applicability-rules"></a>Importera och exportera tillämplighetsregler

### <a name="export-applicability-rules"></a>Exportera tillämplighetsregler

1. Logga in på [RCS](https://marketing.configure.global.dynamics.com/).
2. I arbetsytan **Globaliseringsfunktioner** väljer du **Funktioner** och sedan panelen **Skatteberäkning**.
3. Välj en befintlig funktion eller [skapa en ny funktion](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. I rutnätet **Versioner**, välj **Redigera**.
5. På funktionssidan **Momsberäkning** ange [konfigurationsversionen](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. På fliken **Tillämplighet för momsgrupp** markerar du raderna i rutnätet **Ställ in tillämplighet för momsgrupp**.
7. Markera knappen **Öppna i knappen Microsoft Office** och välj **Dynamisk tillämplighetsmatris för momstjänst**.

    [![Exportera tillämplighetsregler på Microsoft Excel på funktionssidan för momsberäkning.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Välj **Hämta** om du vill exportera de markerade raderna till ett Microsoft Excel kalkylblad.

### <a name="import-applicability-rules"></a>Importera tillämplighetsregler

Det Excel-kalkylblad som du hämtat innehåller strukturen för rutnätet **Ställ in tillämplighet för momsgrupp**. Du kan lägga till nya regler direkt i kalkylbladet. När du är klar följer du dessa steg för att importera de nya reglerna tillbaka till rutnätet **Ställ in tillämplighet för momsgrupp**.

1. Markera och kopiera de rader som ska importeras i Excel-kalkylbladet.
2. I RCS, på funktionssidan **Momsberäkning** på fliken **Tillämplighet för momsgrupp**, välj **Lägg till** för att infoga en tom post längst ned i rutnätet **Ställ in tillämplighet för momsgrupp**.
3. Välj **Ctrl+V** om du vill klistra in de kopierade raderna i rutnätet.
4. Välj **Spara**.

## <a name="import-feature-demo-data"></a>Importera funktionsdemodata

Följ de här stegen när du vill importera funktionsdemodata.

1. Logga in på [RCS](https://marketing.configure.global.dynamics.com/).
2. I arbetsytan **Globaliseringsfunktioner** väljer du **Funktioner** och sedan panelen **Skatteberäkning**.
3. Välj **Importera** och på sida **Importera funktion från den globala databasen**, välj **Synkronisera**. 
4. I tabellen, välj funktionen **tax-calculation-feature-demo-data** och välj sedan **Importera**.
5. Välj **Visa** om du vill granska momskoder, grupper och tillämplighetsregler som har definierats i den importerade funktionen.
6. I Ekonomi, växla till juridiska personen **DEMF** och gå till **Moms** \> **Inställningar** \> **Momsinställning** \> **Parametrar för momsberäkning**.
7. På fliken **Allmänt** aktiverar du alternativet **Aktivera momsberäkningstjänst**.
8. I fältet **Funktionens konfigurationsnamn**, välj **tax-calculation-feature-demo-data**.
9. Välj en **Kvittningsperiod** och en **Redovisningsbokföringsgrupp** för de nya demomomskoderna och välj sedan **bekräfta**.
10. Välj **Spara**.

> [!NOTE]
> Demofunktionen **tax-calculation-feature-demo-data** baseras på funktionsversionen **40.54.234** och den har utformats för den juridiska personen **DEMF**. Se till att Ekonomi och RCS är uppgraderade till version 10.0.26 eller senare.
