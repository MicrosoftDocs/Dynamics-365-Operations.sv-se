---
title: Utforma ett ER-format för att sidnumrera skapade dokument i Excel
description: Det här ämnet förklarar hur du utformar ett elektroniskt rapporteringsformat (ER) som paginerar ett genererat dokument i Microsoft Excel.
author: kfend
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.form: EROperationDesigner
ms.openlocfilehash: e4a34dffda9e9b95f5d6c7ee382723663817ec6b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285014"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Utforma ett ER-format för att sidnumrera skapade dokument i Excel

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur en användare med rollen Systemadministratör eller Elektronisk rapportering funktionell konsult kan konfigurera ett [ER-format (Elektronisk rapportering)](general-electronic-reporting.md) för att generera utgående dokument i Microsoft Excel och hantera sidnumrering av dokument.

I det här exemplet ändrar du det Microsoft-angivna ER-format som används för att skriva ut kontrollrapporten när Intrastat-deklarationen [genereras](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Med den här rapporten kan du iaktta rapporterade Intrastat-transaktioner. Med dina ändringar kan du hantera sidnumreringen av kontrollrapporter som genereras.

Procedurerna i detta ämne kan slutföras i företaget **DEMF**. Ingen kod behövs. Hämta och spara följande filer innan du börjar.

| beskrivning       | Filnamn |
|-------------------|-----------| 
| Rapportmall 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Rapportmall 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra de här inställningarna innan du börjar använda ER-ramverket för att designa en anpassad version av ett standard-ER-format.

## <a name="import-the-standard-er-format-configuration"></a>Importera standardkonfiguration av ER-format

Följ stegen i [Importera standardkonfiguration för ER-format](er-quick-start2-customize-report.md#ImportERSolution1) för att lägga till ER-standardkonfigurationerna i din nuvarande instans av Dynamics 365 Finance. Importera version **1.9** av formatkonfigurationen för **Intrastat-rapporten**. Basversion 1 av konfigurationen av **Intrastat-modellen** importeras automatiskt från databasen.

## <a name="customize-the-standard-er-format"></a>Anpassa ER-standardformatet

### <a name="create-the-custom-er-format"></a>Skapa det anpassade ER-formatet

I det här scenariot är du representant för Litware, Inc. som för närvarande är valt som aktiv ER-konfigurationsprovider. Du måste skapa en ny ER-formatkonfiguration genom att använda konfigurationen för **Intrastat-rapport** som bas.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Intrastat-modell** och väljer sedan **Intrastat-rapport**. Litware, Inc. kommer att använda version 1.9 av den här ER-formatkonfigurationen som bas för den anpassade versionen.
3. Välj **Skapa konfiguration** om du vill öppna dialogrutan. Du kan använda denna dialogruta för att skapa en ny konfiguration för ett anpassat betalningsformat.
4. I fältgruppen **Ny** väljer du alternativet **Härled från namn: Intrastat-rapport, Microsoft**.
5. I fältet **namn** anger du **Intrastat-rapport Litware**.
6. Välj **Skapa konfiguration** för att skapa det nya formatet.

Version 1.9.1 av **Intrastat-rapport Litware** ER-formatkonfiguration har skapats. Den här versionen har status av **utkast** och kan redigeras. Det aktuella innehållet i det anpassade ER-formatet matchar innehållet i det format som tillhandahålls av Microsoft.

### <a name="make-the-custom-format-runnable"></a>Gör det anpassade formatet som körbart

Nu när den första versionen av det anpassade formatet har skapats och har statusen **utkast** kan du köra formatet i testsyfte. Om du vill köra rapporten måste du bearbeta en leverantörsbetalning genom att använda den betalningsmetod som refererar till det anpassade ER-formatet. Som standard, när du anropar ett ER-format från appen kan endast versioner som har status **slutförd** eller **delad** beaktas. Det här beteendet gör det enklare att använda ER-format som inte innehåller färdiga designer. För att testet ska kunna köras kan du dock tvinga appen att använda den version av ditt ER-format som har statusen **utkast**. På det här sättet kan du justera den aktuella formatversionen om du behöver göra ändringar. Mer information finns i [Tillämplighet](electronic-reporting-destinations.md#applicability).

Om du vill använda utkastversionen av ett ER-format måste du markera ER-format på tydligt sätt.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.
4. Välj **redigera** för att göra den aktuella sidan klar för redigering.
5. I konfigurationsträdet i det vänstra fönstret, välj **Intrastat-rapport Litware**.
6. Ställ in alternativet **Kör utkast** på **Ja** och välj sedan **Spara**.

    ![Alternativet Kör utkast på sidan Konfigurationer.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Ställ in utländska handelsparametrar för att använda det anpassade ER-formatet

Följ dessa steg om du vill konfigurera parametrar för utländsk handel så att du kan använda det anpassade formatet.

1. Gå till **Moms** \> **Inställningar** \> **Utländsk handel** \> **Utländska handelsparametrar**.
2. På sidan **Utländska handelsparametrar** snabbfliken **Elektronisk rapportering** fältet **Mappning av filformat** väljer du **Intrastat report Litware**.
3. I fältet **Mappning av rapportformat**, välj **Intrastat-rapport Litware**.
4. Välj **Spara**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Konfigurera det anpassade formatet för att använda den hämtade rapportmallen

### <a name="review-the-first-downloaded-excel-template"></a>Granska den första hämtade Excel-mallen

1. I Excel-skrivbordsprogrammet, öppna mallfilen **ERIntrastatReportDemo1.xlsx** som du hämtat tidigare.
2. Kontrollera att mallen innehåller namngivna intervall för att skapa rapporthuvud, rapportdetaljer och sidfotsavsnitt i genererade dokument.

    ![Layout för Excel-mall 1 i skrivbordsprogrammet.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Byt ut den aktuella Excel-mallen i det anpassade ER-formatet

Du måste lägga till en ny Excel-mall i det anpassade ER-formatet.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Intrastat-modell** \> **Intrastat-rapport** och välj konfiguration av **Intrastat-rapport Litware**.
3. Välj **Designer**.
4. På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Visa detaljer**.
5. Kontrollera att du har valt rotformatkomponenten **Intrastat: Excel** och sedan i åtgärdsfönstret på fliken **Importera** i gruppen **Importera** väljer du **Uppdatera från Excel**.
6. I dialogrutan **Uppdatera från Excel**, välj **Uppdateringsmall**.
7. I dialogrutan **Öppna**, bläddra till och välj den fil **ERIntrastatReportDemo1.xlsx** som du hämtade tidigare och välj **Öppna**.
8. Välj **OK**.
9. Välj **Spara**.

![Formatstrukturen i ER-formatdesignern efter att den nya Excel-mallen har lagts till.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Ändra databindningen för att visa artikelbeskrivningen i en genererad rapport

1. Välj fliken **Formatdesigner** välj fliken **Mappning**.
2. Expandera **Intrastat** \> **rapportrader** och välj komponenten **Artikelkod**.
3. Välj **Redigera recept**.
4. Ändra den bindningsformeln från `@.CommodityCode` till `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Välj **Spara**.

![Konfigurerad bindning för visning av artikelbeskrivningen i ER-formatdesignern.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Generera en kontrollrapport för EU Intrastat-deklaration

Kontrollera först att du har Intrastat-transaktioner för rapportering på **Intrastat**-sidan.

![Transaktioner på Intrastat-sidan.](./media/er-paginate-excel-reports-transactions1.gif)

Använd sedan det anpassade ER-formatet för att generera kontrollrapporten för Intrastat-deklarationen.

1. Gå till **Moms** \> **Deklarationer** \> **Utländsk handel** \> **Intrastat**.
2. På sidan **Intrastat** i åtgärdsrutan, välj **Utgående** \> **Rapport**.
3. I dialogrutan **Intrastat-rapport**, följ dessa steg för att köra rapporten:

    1. Ställ in fälten **Från datum** och **Till datum** för att inkludera specifika Intrastat-transaktioner i rapporten.
    2. Ange alternativet **Generera fil** som **Nej**.
    3. Ange alternativet **Generera rapport** som **Ja**.
    4. Välj **OK**.

4. Hämta och spara dokumentet som genereras.
5. Öppna dokumentet i Excel och granska det.

    ![Genererat Excel-dokument i skrivbordsprogrammet.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Konfigurera det anpassade formatet till sidnumrerade dokument

### <a name="review-the-second-downloaded-excel-template"></a>Granska den andra hämtade Excel-mallen

1. I Excel, öppna mallfilen **ERIntrastatReportDemo2.xlsx** som du hämtat tidigare.
2. Jämför den här mallen **ERIntrastatReportDemo1.xlsx** och kontrollera att den innehåller flera nya Excel-namn för att skapa och fylla i sidspecifika avsnitt i genererade dokument.

    - Intervallet **ReportPageHeader** läggs till för att skapa sidrubriker.
    - Intervallet **ReportPageFooter** läggs till för att skapa sidfötter.
    - Cellen **ReportPageFooter\_PageLines** är konfigurerad till att visa antalet transaktioner per sida.
    - Cellen **ReportPageFooter\_PageAmount** är konfigurerad till att visa totala antalet transaktioner per sida.
    - Cellen **ReportPageFooter\_PageWeight** är konfigurerad till att visa totala vikten transaktioner per sida.
    - Cellen **ReportPageFooter\_RunningCounterLines** är konfigurerad för att visa transaktionens löpande räknare från början av rapporten till den aktuella sidan.
    - Cellen **ReportPageFooter\_RunningTotalAmount** är konfigurerad för att visa belopp som löper totalt för alla transaktioner från början av rapporten till den aktuella sidan.
    - Cellen **ReportPageFooter\_RunningTotalWeight** är konfigurerad för att visa vikt som löper totalt för alla transaktioner från början av rapporten till den aktuella sidan.

    ![Layout för Excel-mall 2 i skrivbordsprogrammet.](./media/er-paginate-excel-reports-template2a.gif)

    Cellen **CommodityCode** i den här mallen är konfigurerad för att radbryt celltext. Eftersom raden för transaktionsdetaljer är konfigurerad så att den automatiskt passar höjden på en rad måste höjden på hela raden automatiskt ändras när texten i cellen **CommodityCode** cell slås in.

    ![CommodityCode-cell som är konfigurerad för att radbryt celltext.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Upprepa bytet av den aktuella Excel-mallen i det anpassade ER-formatet

1. Följ stegen i avsnittet [Ersätt den nuvarande Excel -mallen i det anpassade ER-formatet](#replace-template) i det här ämnet. I steg 7 markerar du dock filen **ERIntrastatReportDemo2.xlsx**.
2. Välj **Formatdesigner** på sidan, visa **Intrastat**.
3. Namnge formatkomponenter för [intervall](er-fillable-excel.md#range-component) som har lagts till i det redigerbara ER-formatet för att synkronisera strukturen med strukturen för den tillämpade Excel-mallen:

    1. Välj komponenten **intervall** som är associerad med Excel-namnet **ReportPageHeader**.
    2. På fliken **Format** i fältet **Namn** ange **Rapportera sidhuvud**.
    3. Välj komponenten **intervall** som är associerad med Excel-namnet **ReportPageFooter**.
    4. På fliken **Format** i fältet **Namn** ange **Rapportera sidfot**.

4. Välj **Spara**.

![Formatstrukturen i ER-formatdesignern efter att Excel-mallen ersätts.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Ändra formatstrukturen så att dokumentets sidnumrering implementeras

1. På sidan **Formatdesigner**, i formatträdet i det vänstra fönstret, väljer du **Intrastat**-rotkomponenten. 
2. Markera **Lägg till**.
3. I dialogrutan **Lägg till**, välj komponenten [Sidan](er-fillable-excel.md#page-component) i gruppen av komponenter för **Excel**.
4. I dialogrutan **Komponentegenskaper** i fältet **Namn** ange **Rapportsidan**. Välj sedan **OK**.
5. För att använda komponenten **Rapportera sidhuvud** som sidhuvud på varje genererad sida, följ dessa steg:

    1. Välj komponenten **Rapportera sidhuvud** och välj **Klipp ut**.
    2. Välj komponenten **Rapportsidan** och välj **Klistra in**.
    3. Expandera **rapportsidan**.
    4. Om du vill tvinga komponenten **Sida** till [ta hänsyn till](er-fillable-excel.md#page-component-structure) detta område en sidhuvud, välj **Rapportera sidhuvud** och sedan på fliken **Format** i fältet **Replikeringsriktning**, välj **Ingen replikering**.

6. Om du vill sidnumrera ett genererat dokument så att innehållet på rapportrader beaktas gör du så här:

    1. Välj komponenten **Rapportrader** och välj **Klipp ut**.
    2. Välj komponenten **Rapportsidan** och välj **Klistra in**.

7. Gör så här om du vill ta med rapportsfoten efter rapportrader men före den slutliga sidfoten:

    1. Välj komponenten **Rapportsidfot** och välj **Klipp ut**.
    2. Välj komponenten **Rapportsidan** och välj **Klistra in**.

8. För att använda komponenten **Rapportsidfoten** som sidfot på varje genererad sida, följ dessa steg:

    1. Välj komponenten **Rapportsidfot** och välj **Klipp ut**.
    2. Välj komponenten **Rapportsidan** och välj **Klistra in**.
    3. Om du vill tvinga komponenten **Sida** till [ta hänsyn till](er-fillable-excel.md#page-component-structure) detta område en sidfot, välj **Rapportera sidfot** och sedan på fliken **Format** i fältet **Replikeringsriktning**, välj **Ingen replikering**.

![Formatstrukturen i ER-formatdesignern efter dokument sidnumrering genomförs.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Lägga till datakällor när du vill beräkna summor för sidfot

Du måste konfigurera nya datakällor för att beräkna sidsummor, löpande räknare och de löpande totala värdena, och för att visa dem i sidfotsavsnittet. Vi rekommenderar att du använder datakällor för [Datainsamling](er-data-collection-data-sources.md) i detta syfte.

1. Välj fliken **Formatdesigner** välj fliken **Mappning**.
2. Välj **Lägg till rot** igen och gör sedan följande:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Allmänt**, välj **Töm behållare**.
    2. I dialogrutan **Töm behållares datakällegenskaper** i fältet **Namn**, ange **Total**.
    3. Välj **OK**.

3. Välj datakälla **Total**, välj **Lägg till** och följ dessa steg:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Allmänt**, välj **Töm behållare**.
    2. I dialogrutan **Töm behållares datakällegenskaper** i fältet **Namn**, ange **Sidan**.
    3. Välj **OK**.

4. Välj **Lägg till** igen och gör sedan följande:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Allmänt**, välj **Töm behållare**.
    2. I dialogrutan **Töm behållares datakällegenskaper** i fältet **Namn**, ange **Kör**.
    3. Välj **OK**.

5. Välj datakälla **Total.Page**, välj **Lägg till** och följ dessa steg:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
    2. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Belopp**.
    3. Välj **Realtal** i fältet **Artikeltyp**.
    4. Ställ in alternativet **Samla in alla värden** till **Ja**.
    5. Välj **OK**.

6. Välj **Lägg till** igen och gör sedan följande:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
    2. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Vikt**.
    3. Välj **Realtal** i fältet **Artikeltyp**.
    4. Ställ in alternativet **Samla in alla värden** till **Ja**.
    5. Välj **OK**.

7. Välj datakälla **Total.Running**, välj **Lägg till** och följ dessa steg:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
    2. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Belopp**.
    3. Välj **Realtal** i fältet **Artikeltyp**.
    4. Ställ in fältet **Samla in alla värden** till **Ja**.
    5. Välj **OK**.

8. Välj **Lägg till** igen och gör sedan följande:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
    2. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Vikt**.
    3. Välj **Realtal** i fältet **Artikeltyp**.
    4. Ställ in fältet **Samla in alla värden** till **Ja**.
    5. Välj **OK**.

9. Välj **Lägg till** igen och gör sedan följande:

    1. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
    2. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Rader**.
    3. I fältet **Artikeltyp** välj **Heltal**.
    4. Ställ in fältet **Samla in alla värden** till **Ja**.
    5. Välj **OK**.

10. Välj **Spara**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Lägga till datakällor när du vill kontrollera synlighet för sidfot

Om du tänker kontrollera sidfotssynligheten och inte planerar att inkludera sidfoten på den slutgiltiga sidan om den innehåller transaktioner, ska du konfigurera en ny datakälla för att beräkna den räknare som behövs.

1. Välj fliken **Formatdesigner** välj fliken **Mappning**.
2. Välj datakällan **Total.Running** och välj **Lägg till**.
3. I dialogrutan **Lägg till datakälla**, i avsnittet **Funktioner**, välj **Datainsamling**.
4. I dialogrutan **Datainsamling datakällegenskaper** i fältet **Namn**, ange **Lines2**.
5. I fältet **Artikeltyp** välj **Heltal**.
6. Ställ in alternativet **Samla in alla värden** till **Ja**.
7. Välj **OK**.
8. Välj **Spara**.

![Datakällor har lagts till i ER-formatdesignern.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Konfigurera bindande för insamling av totalvärden

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportrader** och välj den kapslade komponenten **Fakturavärde**.
2. Välj **Redigera recept**.
3. Ändra den bindningsformeln från `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` till `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > Förutom att sätta beloppsvärdet i en Excel-cell för varje itererad transaktion, samlar denna in värdet i datasamlingen för datakällan **Total.Page.Amount**.

4. Välj den kapslade komponenten **vikt**.
5. Välj **Redigera recept**.
6. Ändra den bindningsformeln från `@.'$RoundedWeight'` till `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > Förutom att sätta viktvärdet i en Excel-cell för varje itererad transaktion, samlar denna in värdet i datasamlingen **Total.Page.Weight**.

![Konfigurerade bindande för insamling av totala värden i ER-formatdesignern.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Konfigurera bindande för att fylla i sidsfotssummor

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportsidfot**, välj komponenten **intervall** som hänvisar till Excel-cellen **ReportPageFooter\_PageAmount** och gör följande:

    1. I datakällträdet i högra fönstret, välj **Total.Page.Amount.Sum()**.
    2. Välj **bind**.
    3. Välj **Redigera recept**.
    4. Uppdatera formeln till `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Du måste ange argumentet för den här funktionen som **Falsk** för att behålla insamlad data för den aktuella sidan, eftersom denna data krävs för att beräkna mängden löpande totalt, totalt antal rader per sida och löpande räknare för rader.

2. I formatträdet, välj den nästlade komponenten **Intervall** som refererar Excel-cell **ReportPageFooter\_PageWeight** och gör följande:

    1. I datakällträdet i högra fönstret, välj **Total.Page.Weight.Sum()**.
    2. Välj **bind**.
    3. Välj **Redigera recept**.
    4. Uppdatera formeln till `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Konfigurera bindande för att fylla i sida med totalt antal

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportsidfot**, välj komponenten **intervall** som hänvisar till Excel-cellen **ReportPageFooter\_RunningTotalAmount** och gör följande:

    1. I datakällträdet i högra fönstret, välj **Total.Running.Amount.Collect()**.
    2. Välj **bind**.
    3. Välj **Redigera recept**.
    4. Uppdatera formeln till `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > Operanden `Total.Running.Amount.Sum(false)` returnerar det tidigare insamlade beloppet löpande summa. Operanden `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` returnerar det totala beloppet på den aktuella sidan. Du måste ange argumentet för den andra operandens kapslade funktion som **True** för att återställa `Total.Page.Amount` datainsamling så snart detta värde sätts i `Total.Running.Amount` kör total samling. Det angivna argumentet måste börja samla ihop nästa sidsumma från värdet 0 (noll).
    >
    > Funktionen `Total.Running.Amount.Sum(false)` anropas för att ange det löpande totalbeloppet i Excel-cellen **ReportPageFooter\_RunningTotalAmount** på den aktuella sidan.

2. I formatträdet, välj den nästlade komponenten **Intervall** som refererar Excel-cell **ReportPageFooter\_RunningTotalWeight** och gör följande:

    1. I datakällträdet i högra fönstret, välj **Total.Running.Weight.Collect()**.
    2. Välj **bind**.
    3. Välj **Redigera recept**.
    4. Uppdatera formeln till `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Konfigurera bindande för att fylla i sida med sida körräknare

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportsidfot**, välj komponenten **intervall** som hänvisar till Excel-cellen **ReportPageFooter\_RunningCounterLines**:
2. Välj **Redigera recept**.
3. Lägg till formeln `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Den här formeln returnerar antalet insamlade beloppsvärden för hela rapporten. Detta antal är lika med antalet transaktioner som har omräknats vid det aktuella tillfället. Samtidigt samlar formeln det returnerade värdet i inkassosamlingen **Total.Running.Lines**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Konfigurera bindande för att fylla i räknare med sidfot

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportsidfot**, välj komponenten **intervall** som hänvisar till Excel-cellen **ReportPageFooter\_PageLines**:
2. Välj **Redigera recept**.
3. Lägg till formeln `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Denna formel beräknar antalet transaktioner på den aktuella sidan som skillnaden mellan antalet transaktioner som samlades in **Total.Page.Amount.Result** för hela rapporten och antalet transaktioner som har lagrats i detta skede i **Total.Running.Lines.Sum**. Eftersom antalet transaktioner för den aktuella sidan lagras på **Total.Running.Lines** i bindningskomponenten **Intervall** som hänvisar till Excel-cellen **ReportPageFooter\_RunningCounterLines** är antalet transaktioner på den aktuella sidan ännu inte inkluderat. Därför är denna differens lika med antalet transaktioner på den aktuella sidan.

![Konfigurerade bindande för ifyllning av sidfotsräknaren i ER-formatdesignern.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Konfigurera komponentsynlighet

Du kan ändra visningen av sidhuvud och sidfot på en viss sida i ett genererat dokument för att dölja följande element:

- Sidrubriken på den första sidan eftersom rapportrubriken redan innehåller kolumnrubriker
- Sidrubriken på alla sidor där det inte finns några transaktioner som kan inträffa på den sista sidan
- Sidfoten på alla sidor där det inte finns några transaktioner som kan inträffa på den sista sidan

Om du vill ändra synligheten uppdaterar du egenskapen **Aktiverad** för komponenterna **Rapportera sidhuvud** och **Rapportsidfot**.

1. På sidan **Formatdesigner** i formatträdet, visa komponenten **Rapportsidor** och välj den kapslade komponenten **Rapportera sidhuvud** och följ dessa steg.

    1. Markera **Redigera** för fältet **Aktiverad**.
    2. På sidan **Formeldesigner** i fältet **Formel** ange följande uttryck:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. Välj formatet i formatträdet, komponenten **Rapportsidfot** och gör följande:

    1. Markera **Redigera** för fältet **Aktiverad**.
    2. På sidan **Formeldesigner** i fältet **Formel** ange följande uttryck:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > Konstruktion `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` används för att beräkna antalet transaktioner på den aktuella sidan. Konstruktionen `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` används för att lägga till antalet transaktioner på den aktuella sidan i samlingen för att korrekt hantera synligheten för nästa sidfot.
    >
    > Samlingen `Total.Running.Lines` kan inte återanvändas här, eftersom egenskapen **Aktiverad** av en baskomponent bearbetas **efter** bindningarna av kapslade komponenter bearbetas. När egenskapen **Aktiverad** bearbetas ökas redan samlingen `Total.Running.Lines` har redan ökat med antalet transaktioner på den aktuella sidan.

3. Välj **Spara**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Generera en kontrollrapport för EU Intrastat-deklaration (uppdaterad)

1. Kontrollera först att du har 24 Intrastat-transaktioner på **Intrastat**-sidan. Upprepa stegen i avsnittet [Generera en Intrastat-deklarationskontrollrapport](#generate-intrastat-control-report) i den här artikeln om du vill generera och granska kontrollrapporten.

    Alla transaktioner visas på första sidan. Sidsummorna och räknare är lika med rapportsummorna och räknare. Intervallet sidrubriken döljs på den första sidan eftersom rapportrubriken redan innehåller kolumnrubriker. Sidhuvudet och sidfoten är dolda på den andra sidan eftersom den sidan inte innehåller några transaktioner.

    ![Genererat Excel-dokument i skrivbordsprogrammet.](./media/er-paginate-excel-reports-document2.gif)

2. Uppdatera två transaktioner på **Intrastat**-sidan genom att ändra koden **artikelnummer** från **D00006** till **L0010**. Lägg märke till att produktnamnet på den nya varan **Aktivt stereohögtalarpar** är längre än produktnamnet på originalartikeln **Standardhögtalare**. I denna situation tvingars textbrytning i motsvarande cell i det genererade dokumentet. Dokumentnumrering, och sidrelaterad summering och inventering, måste nu uppdateras. Upprepa stegen i avsnittet [Generera en Intrastat-deklarationskontrollrapport](#generate-intrastat-control-report) om du vill generera och granska kontrollrapporten.

    För närvarande visas transaktioner på två sidor och sidsummor och räknare beräknas korrekt. Sidhuvudintervallet är korrekt dolt på första sidan och synligt på den andra sidan. Sidfoten visas på båda sidorna eftersom de innehåller transaktioner.

    ![Uppdaterad genererat Excel-dokument i skrivbordsprogrammet.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>Kan du känna igen när den sista sidan bearbetas av sidformatskomponenten?

**Sidkomponenten** [visar inte](er-fillable-excel.md#page-component-limitations) information om numret på den bearbetade sidan och det totala antalet sidor i ett genererat dokument. Ändå kan du konfigurera ER-[formler](er-formula-language.md) för att känna igen den slutgiltiga sidan. Här är ett exempel:

- Beräkna det totala antalet transaktioner som redan har bearbetats med hjälp av komponenten **Rapportsida**. Du kan göra denna beräkning med hjälp av formeln `COUNT(Total.Page.Amount.Result)`. 
- Beräkna det totala antalet transaktioner som måste bearbetas baserat på den bindande `model.CommodityRecord` som konfigureras för **rapportrad**-komponenten.  Du kan göra denna beräkning med hjälp av formeln `COUNT(model.CommodityRecord)`.
- Jämför två nummer för att känna igen den sista sidan. När båda värdena är lika genereras den sista sidan.

> [!NOTE]
> Vi rekommenderar att du använder detta tillvägagångssätt endast när egenskapen **Aktiverad** för komponenten **Rapportrader** innehåller ingen formel som kan returnera [False](er-formula-supported-data-types-primitive.md#boolean) vid körning för några av de itererade [poster](er-formula-supported-data-types-composite.md#record) för den bundna [Postlistan](er-formula-supported-data-types-composite.md#record-list).

## <a name="additional-resources"></a>Ytterligare resurser

- [Skapa en konfiguration för att generera dokument i Excel-format](er-fillable-excel.md)
- [Använd datakällor för DATAINSAMLING i elektroniska rapporteringsformat (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
