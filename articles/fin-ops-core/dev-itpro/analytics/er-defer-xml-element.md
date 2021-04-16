---
title: Skjut upp körningen av XML-element i ER-format
description: I det här avsnittet beskrivs hur du uppskjuta körningen av ett XML-element i ett format för elektronisk rapportering (ER).
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 84c8c782b917850267c34696f3b2afa607118d84
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753634"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Skjut upp körningen av XML-element i ER-format

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Du kan använda Operations designer för ramverket [Elektronisk rapportering (ER)](general-electronic-reporting.md) för att [konfigurera](./tasks/er-format-configuration-2016-11.md) [formatkomponenten](general-electronic-reporting.md#FormatComponentOutbound) av en ER-lösning som används för att generera utgående dokument i ett XML-format. Den hierarkiska strukturen för den konfigurerade formatkomponenten består av formatelement av olika typer. Dessa formatelement används för att fylla genererade dokument med den information som krävs vid körning. När du kör ett ER-format körs formatelementen som standard i samma ordning som de presenteras i formathierarkin: en i taget, uppifrån och ned. Vid designtillfället kan du dock ändra körningsordningen för alla XML-element i den konfigurerade formatkomponenten.

Genom att aktivera alternativet <a name="DeferredXmlElementExecution"></a>**Uppskjuten körning** körning för ett XML-element i det konfigurerade formatet kan du skjuta upp körningen av det elementet. I det här fallet körs inte elementet förrän alla andra element i dess överordnade har körts.

Om du vill veta mer om den här funktionen fyller du i exemplet i det här avsnittet.

## <a name="limitations"></a>Begränsningar

**Alternativet för uppskjuten** körning stöds bara för XML-element som är konfigurerade för ett ER-format som används för att generera **utgående** dokument i XML-format.

Alternativet **uppskjuten körning** stöds bara för XML-element som bara finns i ett annat XML-element. Därför gäller det inte XML-element som finns i andra typer av formatelement (t.ex. i ett **XML-sekvens**-element).

Alternativet **uppskjuten körning** stöds inte för XML-element som finns i formatelement **vanliga\\fil** när alternativet **dela fil** anges till **ja**. För mer information om hur du delar upp XML-filer, se [Dela upp genererade XML-filer utifrån filstorlek och innehållskvantitet](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Exempel: Skjut upp körningen av XML-element i ER-format

Följande steg förklarar hur en användare i systemadministratören eller funktionell konsult för elektronisk rapportering [roll](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) kan konfigurera ett ER-format som innehåller ett XML-element där exekveringsordningen skiljer sig från ordningen i formathierarkin.

Dessa steg kan utföras i **USMF**-nivå i Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Förutsättningar

För att slutföra detta exempel måste du ha åtkomst till **USMF** företag i ekonomi för en av följande roller:

- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Om du inte redan har fyllt i exemplet i [avsnittet om körning av serieelement i ER](er-defer-sequence-element.md#Example)-format hämtar du följande [konfigurationer](general-electronic-reporting.md#Configuration) för exempel på ER-lösningen.

| Beskrivning av innehåll            | Filnamn |
|--------------------------------|-----------|
| Exempel på konfiguration av ER-datamodell.    | [Modell för att lära dig uppskjutna element.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Konfiguration och ER-modellmappning | [Mappning för att lära dig uppskjutna element.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Innan du börjar måste du också hämta och spara följande konfiguration av exempel ER-lösningen till din lokala dator.

| Beskrivning av innehåll     | Filnamn |
|-------------------------|-----------|
| Konfiguration för ER-fomat | [Format för att lära dig uppskjutna XML-element.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="import-the-sample-er-configurations"></a>Importera ER-exempelkonfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. På sidan **konfigurationer**, om konfigurationen **Modell för att lära dig uppskjuten** inte är tillgänglig i konfigurationsträdet på sidan konfigurationer kan du importera konfigurationen för data modellen ER-datamodell:

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **bläddra**, hitta och välj **Modell för att lära dig uppskjutna element.1.xml** och välj sedan **OK**.

4. På sidan konfigurationer **Kartlägga för att lära dig uppskjutna element** är inte tillgänglig i konfigurationsträdet, importera ER-modellens mappningskonfiguration:

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **bläddra**, hitta och välj **Mapping för att lära dig uppskjutna element.1.1.xml** och välj sedan **OK**.

5. Importera ER-formatkonfiguration:

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **bläddra**, hitta och välj **Format för att lära dig uppskjutna XML-element.1.1.xml** och välj sedan **OK**.

6. I konfigurationsträdet expanderar **Modell för att se uppskjutna element**.
7. Granska listan över importerade ER-konfigurationer i konfigurationsträdet.

    ![Importerade ER-konfigurationer på sidan konfigurationer](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Aktivera en konfigurationsprovider

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** kontrollerar du att [konfigurationsprovidern](general-electronic-reporting.md#Provider) för Litware, Inc. (`http://www.litware.com`) exempelföretageet är listat och att det är markerat som aktivt. Om denna konfigurationsprovider inte finns med i listan, eller om den inte är markerad som aktiv, följer du [Skapa en konfigurationsleverantör och markera den som aktiv](./tasks/er-configuration-provider-mark-it-active-2016-11.md) markerar den som ett aktivt ämne.

    ![Litware, Inc. exempelföretag på sidan lokaliseringskonfiguration](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Granska den importerade modellmappningen

Granska inställningarna för komponenten ER-modellmappning komponenten är konfigurerad för att få åtkomst till momstransaktioner och visa tillgängliga data på begäran.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Modell för att lära dig uppskjutna element**.
4. Välj konfigurationen av **Mappning för att lära dig uppskjutna element**.
5. Välj **designer** om du vill öppna listan över mappningar.
6. Välj **Designer** för att granska mappningsinformationen.
7. Välj **Visa detaljer**.
8. Granska de datakällor som är konfigurerade att få åtkomst till momstransaktioner:

    - Datakällor **Transaktion** typen *registerpost* är konfigurerad för att få åtkomst till poster i programregistret **TaxTrans**.
    - Datakällan **Verifikationer** av typen *beräknade fältet* typen är konfigurerad för att returnera de obligatoriska kupongkoderna (**INV-10000349** och **INV-10000350**) som en lista av poster.
    - Datakällan **filtrerade** av typen *beräknade fält* är konfigureras för att välja, från datakällan **Transaktioner** endast momstransaktioner för de verifikationer som krävs.
    - Fältet **\$TaxAmount** av typen *beräknade typen* läggs till datakällan **filtrerade** för att visa det momsvärde som har motsatt tecken.
    - Datakällan **Grupperade** typ *Gruppera efter* är konfigurerad för att gruppera filtrerade momstransaktioner för den filtrerade **datakällan**.
    - Sammansättningsfältet **TotalSum** för datakällan **Gruppera** konfigurerad för att sammanfatta värden på fälten **\$TaxAmount** datakällan **filtrerade** datakälla för alla filtrerade skattetransaktioner för den datakällan.

        ![TotalSum aggregeringsfält på sidan redigera 'GroupBy'-parametrar](./media/ER-DeferredXml-GroupByParameters.png)

9. Granska hur de konfigurerade datakällorna är bundna till datamodellen och hur de visar öppna data så att de blir tillgängliga i ett ER-format:

    - Den **filtrerade** datakällan är bunden fältet **Data.List** i datamodellen.
    - Fältet **\$TaxAmount** för datakällan **filtrerade** är bunden fältet **Data.List.Value** i datamodellen.
    - Fältet **TotalSum** för datakällan **Gruppera** är bunden fältet **Data.Summary.Total** av datamodellen.

    ![Modellmappningsdesigner](./media/ER-DeferredXml-ModelMapping.png)

10. Stäng sidan **Modellmappningsdesigner** och **Modellmappning**.

### <a name="review-the-imported-format"></a>Granska det importerade formatet

1. Sidan **konfigurationen** i konfigurationsträdet, välj konfigurationer **Formatera för att lära dig uppskjutna XML-element**.
2. Välj **Designer** för att granska formatinformationen.
3. Välj **Visa detaljer**.
4. Granska inställningarna för komponenter i ER-format som har konfigurerats för att generera ett utgående dokument i XML-format som innehåller information om momstransaktionerna:

    - XML-elementet **rapport\\meddelande** XML element är konfigurerad för att fylla det utgående dokumentet med en enda nod som innehåller de kapslade XML-elementen (**rubrik**, **post** och **sammanfattning**).
    - **Rapport\\Meddelande\\Rubrik** XML-elementet sekvensformat är konfigurerat för att fylla det utgående dokumentet med en enda rubriknod som visar datum och tid när behandlingen startar.
    - **Rapport \\Meddelande\\Post** XML-element är konfigurerat för att fylla det utgående dokumentet med en enda postnod som visar detaljerna för enskilda skattetransaktioner.
    - **Rapport\\Meddelande\\Sammanfattning** XML-element är konfigurerat för att fylla det utgående dokumentet med en enda sammanfattningsnod som inkluderar summan av skattvärdena från de behandlade skattetransaktionerna.

    ![XLM-element för meddelande och kapslade XML-element på sidan formatera designer](./media/ER-DeferredXml-Format.png)

5. På fliken **Mappning** granska följande information:

    - Element **Rapport\\Meddelande\\Rubrik** behöver inte vara bundet till en källa för att generera en enda nod i ett utgående dokument.
    - Attributet **ExecutionDateTime** genereras datum och tid (inklusive millisekunder) när rubriknoden läggs till.
    - Elementet **Rapport\\Meddelande\\Post** är bundet listan **model.Data.List** för att generera en enda postnod för varje post från den bundna listan.
    - Attributet **TaxAmount** är bundet till **model.Data.List.Value** (som visas som **\@.Value** i vyn relativ sökväg) för att generera skattevärde för den aktuella momstransaktionen.
    - Attributet **RunningTotal** är en platshållare för det totala skattevärdet. För närvarande har det här attributet inga utdata, eftersom varken bindning eller standardvärde har konfigurerats.
    - Attributet **ExecutionDateTime** genereras datum och tid (inklusive millisekunder) när den aktuella transaktionen bearbetas i den här rapporten.
    - Element **Rapport\\Meddelande\\Sammanfattning** behöver inte vara bundet till en datakälla för att generera en enda nod i ett utgående dokument.
    - Attributet **TotalTaxAmount** är bundet till **model.Data.Summary.Total** för att generera summan av momsvärden för de bearbetade skattetransaktionerna.
    - Attributet **ExecutionDateTime** genereras datum och tid (inklusive millisekunder) när sammanfattningsnoden läggs till.

    ![Fliken Mappning på sidan Formatdesigner](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Kör det importerade formatet

1. Välj **Formatdesigner** på sidan **Kör**.
2. Hämta filen som webbläsaren erbjuder och öppna den för granskning.

    ![Hämta fil](./media/ER-DeferredXml-Run.png)

Observera att sammanfattningsnoden visar summan av momsvärden för de bearbetade transaktionerna. Eftersom formatet konfigureras för att använda **model.Data.Summary.Total** bindning om du vill returnera den här summan beräknas summan genom att den **TotalSum** aggregering av datakällan **Grupperad** av typen *GroupBy* som använder modellmappningen. För att beräkna denna modellmappning itererar modellmappningen över alla transaktioner som har valts i datakällan **filtrerade**. Genom att jämföra körningstiderna för sammanfattningsnoden och den sista postnoden kan du bestämma att beräkningen av summan tog 12 millisekunder (ms). Genom att jämföra körningstiderna för första och sista postnoderna kan du bestämma att genereringen av alla postnoder tog 9 ms. Därför krävdes totalt 21 ms.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Ändra formatet så att beräkningen baseras på genererade utdata

Om transaktionsvolymen är mycket större än volymen i det aktuella exemplet kan beräkningstiden öka och orsaka prestandaproblem. Genom att ändra formatets inställningar kan du förhindra dessa prestandaproblem. Eftersom du får tillgång till momsvärden för att inkludera dem i den genererade rapporten kan du återanvända den här informationen för att beräkna momsvärden. Mer information finns i [konfigurera format för inventering och summering](./tasks/er-format-counting-summing-1.md).

1. På sidan **Formatdesigner** på fliken **Format** välj filelementet **Rapport** i formatträdet.
2. Ställ in alternativet **Samla in utdatadetaljer** till **Ja**. Du kan nu konfigurera det här formatet genom att använda innehållet i en genererad rapport som en datakälla som du öppnar genom att använda de fördefinierade ER-funktionerna i kategorin [datainsamling](er-functions-category-data-collection.md).
3. På fliken **Mappning** välj XML-elementet **Rapport\\Meddelande\\Post** XML element.
4. Konfigurera uttrycket **Insamlat datanyckelnamn** som `WsColumn`.
5. Konfigurera uttrycket **Insamlat datanyckelvärde** som `WsRow`.

    ![Post XML-element på sidan formatdesigner](./media/ER-DeferredXml-Format3.png)

6. Välj attributet **Rapport\\Meddelande\\Post\\TaxAmount**.
7. Konfigurera uttrycket **Insamlat datanyckelnamn** som `SummingAmountKey`.

    ![Attributet TaxAmount på sidan formatdesigner](./media/ER-DeferredXml-Format4.png)

    Du kan fundera på att ange att ett virtuellt kalkylblad ska uppfyllas, där värdet i cell A1 läggs till med värdet för momsbeloppet från alla bearbetade momstransaktioner.

8. Markera attributet **rapport\\meddelande\\posten\\RunningTotal** och välj **redigera formel**.
9. Konfigurera uttrycket `SUMIF(SummingAmountKey, WsColumn, WsRow)` med hjälp av den inbyggda [SUMIF](er-functions-datacollection-sumif.md) ER-funktionen och välj sedan **Spara**.

    ![SUMIF-uttryck](./media/ER-DeferredXml-FormulaDesigner.png)

10. Stäng sidan **Formeldesigner**.
11. Välj **spara** och välj sedan **kör**.
12. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämta fil](./media/ER-DeferredXml-Run1.png)

    Den sista postnoden innehåller den löpande summan av momsvärden som beräknas för alla bearbetade transaktioner genom att använda den genererade utmatningen som en datakälla. Den här datakällan startar från rapportens början och fortsätter genom den senaste momstransaktionen. Sammanfattningsnoden innehåller summan av alla momsvärden för alla bearbetade transaktioner som beräknas i modellmappningen med hjälp av datakällan för typen *GroupBy*. Observera att dessa värden är lika. Därför kan du använda den utmatnings summeringen i stället **GroupBy**. Genom att jämföra körningstiderna för första postnoden och sammanfattningsnoden kan du bestämma att genereringen av postnoder och sammanfattningsnoder tog 11 ms. Därför är det ändrade formatet ungefär två gånger snabbare än det ursprungliga formatet när det gäller genereringen av postnoder och summering av momsvärden.

13. Markera attributet **rapport\\meddelande\\sammanfattning\\TotalTaxAmount** och välj **redigera formel**.
14. Ange `SUMIF(SummingAmountKey, WsColumn, WsRow)`uttrycket i stället för det befintliga uttrycket.
15. Välj **spara** och välj sedan **kör**.
16. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämta fil](./media/ER-DeferredXml-Run2.png)

    Observera att den totala momsvärden som körs på den sista raden i sista postnoden nu är lika med sammanfattningsnoden.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Placera värden för utflöde baserad summering i rapporthuvudet

Om du till exempel vill visa summan av momsvärden i rapportens rubrik kan du ändra formatet.

1. På sidan **Formatdesigner** på fliken **Format**, välj XML-element **Rapport\\Meddelande\\Sammanfattning**.
2. Välj **Flytta upp**.
3. Välj **spara** och välj sedan **kör**.
4. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämta fil](./media/ER-DeferredXml-Run3.png)

    Observera att summan av momsvärden på sammanfattningsnod nu är lika med 0 (noll), eftersom summan nu beräknas baserat på den genererade utleveransen. När den första postnoden genereras, innehåller den genererade utflödet inte ännu postnoder som har transaktionsdetaljer. Du kan konfigurera det här formatet för att skjuta upp körningen element **Rapport\\Meddelande\\Sammanfattning** tills sekvenselement **Rapport\\Meddelande\\Post** har körts för alla momstransaktioner.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Skjut upp körningen av sammanfattning XML-element så att den beräknade summan används

1. På sidan **Formatdesigner** på fliken **Format**, välj XML-element **Rapport\\Meddelande\\Sammanfattning**.
2. Ge alternativet **uppskjuten körning** värdet **Ja**.

    ![Alternativet uppskjuten körning av sammanfattning XML-element på sidan formatdesigner](./media/ER-DeferredXml-Format5.png)

3. Välj **spara** och välj sedan **kör**.
4. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämta fil](./media/ER-DeferredXml-Run4.png)

    Sekvenselementet **Rapport\\Meddelande\\Sammanfattning** körs nu bara efter alla andra objekt som är kapslade under dess överordnade element **Rapport\\Meddelande** har körts. Därför körs det efter att elementet **Rapport\\Meddelande\\Post** har elementet har körts för alla skattetransaktioner i **model.Data.List**. Körningstiderna för de första och sista postnoderna, och för huvud- och sammanfattningsnoderna, avslöjar detta faktum.

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera format för inventering och summering](./tasks/er-format-counting-summing-1.md)
- [Spåringskörning av ER-format för att hjälpa dig att felsöka prestandaproblem.](trace-execution-er-troubleshoot-perf.md)
- [Skjut upp körningen av serie element i ER-format](er-defer-sequence-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]