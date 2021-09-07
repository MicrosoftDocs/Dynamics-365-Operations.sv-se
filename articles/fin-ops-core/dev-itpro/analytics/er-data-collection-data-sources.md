---
title: Använd datakällor för DATAINSAMLING i elektroniska rapporteringsformat
description: Detta ämne beskriver hur du använder datakällor för DATAINSAMLING i elektroniska rapporteringsformat (ER).
author: NickSelin
ms.date: 08/23/2021
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
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: f001734baf9aee59f0a61d21ca5a99af0c55b56f
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413618"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Använd datakällor för DATAINSAMLING i elektroniska rapporteringsformat

[!include [banner](../includes/banner.md)]

Du kan använda Operations designer för ramverket för [Elektronisk rapportering (ER)](general-electronic-reporting.md) för att konfigurera komponenten [formatera komponenten](general-electronic-reporting.md#FormatComponentOutbound) för en ER-lösning som används för att generera utgående dokument i andra format. Den hierarkiska strukturen för den konfigurerade formatkomponenten består av formatelement av olika typer. Dessa formatelement används för att fylla genererade dokument med den information som krävs vid körning. När du kör ett ER-format körs formatelementen som standard i samma ordning som de presenteras i formathierarkin: en i taget, uppifrån och ned.

När ER kör ett formatelement som innehåller en bindning körs formeln för denna bindning, och formatelementet tillför värdet till ett genererat dokument. Bindningen kan exempelvis överföra värdet från ett [datamodellfält](general-electronic-reporting.md#data-model-and-model-mapping-components) till ett formatelement. Du kan konfigurera en datakälla för DATAINSAMLING om du vill samla in värden från datamodellfält vid körning, summera värden och fylla ett genererat dokument med de insamlade värdena. Om du vill använda denna metod ändrar du den ursprungliga bindningen så att den konfigurerade datakällan för DATAINSAMLING används för att överföra värdet i ett datamodellfält till ett formatelement. Genom att ange värden via datakällan för DATAINSAMLING kan du samla in information som krävs för vidare användning.

När du konfigurerar en datakälla för DATASAMLING anger du en värdetyp som ska hanteras i datakällan. Följande [datatyper](er-formula-supported-data-types-primitive.md) stöds för närvarande för insamling av värden:

- Booleskt
- Datum
- DatumTid
- GUID
- Int64
- Heltal
- Realtal
- Sträng
- Tid

Du kan använda metoden `Collect(Value)` för en datakälla för DATAINSAMLING om du vill föra över ett värde till en datakälla för insamling. I denna metod är argumentet `Value` antingen en konstant eller en giltig sökväg för ett datakällfält av relevant datatyp.

Använd egenskapen `Result` för en datakälla för DATAINSAMLING för att komma åt listan över insamlade värden. Denna egenskap returnerar en [postlista](er-formula-supported-data-types-composite.md#record-list). Postlistans poster innehåller det `Value`-fält som du kan använda för att komma åt insamlade värden.

Datakällan för DATAINSAMLING samlar som standard endast in unika värden.

Om du vill samla in alla värden anger du fältet **Samla in alla värden** för den konfigurerade datakällan för DATAINSAMLING som **Ja**. När fältet **Samla in alla värden** anges som **Ja** blir den parameteriserade egenskapen `Sum(Flag)` tillgänglig. Du kan använda denna egenskap för att få totalsumman av alla för tillfället insamlade värden. I den här egenskapen är argumentet `Flag` ett [booleskt](er-formula-supported-data-types-primitive.md#boolean) värde som används för att ange om det totala värdet måste återställas.

- När värdet **Falskt** anges fortsätter summeringen från det tidigare insamlade beloppet.
- När värdet **Sant** anges startas en ny summering.

Följande datatyper stöds för närvarande för summering:

- Int64
- Heltal
- Realtal

Om du vill veta mer om den här funktionen fyller du i det exempel som följer.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Exempel: Konfigurera ett ER-format som ska räkna och summera genom att använda en datakälla för DATAINSAMLING

I det här exemplet visas hur en användare med rollen Systemadministratör eller Funktionskonsult för elektronisk rapportering kan konfigurera ett ER-format som har en datakälla för DATAINSAMLING som används för att beräkna löpande summor och samla in summerade värden.

Procedurerna i detta exempel kan slutföras i USMF-företaget USMF i Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Överför och använd den angivna ER-lösningen

1. [Importera ER-exempelkonfigurationer](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Aktivera en konfigurationsprovider](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Granska den importerade modellmappningen](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Granska det importerade formatet](er-defer-sequence-element.md#review-the-imported-format).
5. [Kör det importerade formatet](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Kör formatet för den angivna ER-lösningen

1. Välj **Formatdesigner** på sidan **Kör**.
2. I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.
3. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämtade fil som innehåller resultaten av den ursprungliga formatkörningen](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Ändra formatet på ER-lösningen för beräkning av löpande momssummor

Om transaktionsvolymen är mycket större än volymen i det aktuella exemplet kan den erforderliga summeringstiden öka och orsaka prestandaproblem. Genom att ändra formatets inställningar kan du förhindra dessa prestandaproblem. Eftersom du får tillgång till momsvärden för att inkludera dessa i den genererade rapporten kan du återanvända denna information för att summera momsvärden.

1. På sidan **Formatdesigner** på fliken **Mappning** väljer du **Lägg till rot**.
2. I dialogrutan **Lägg till datakälla** väljer du **Funktioner** \> **Datasamling**.
3. I dialogrutan **Egenskaper för datakällan "Datainsamling"** följer du dessa steg:

    1. I fältet **Namn** anger du **CollectedTaxValues**.
    2. Välj **Realtal** i fältet **Artikeltyp**.
    3. I fältet **Samla alla värden** väljer du **Ja**.
    4. Välj **OK**.

4. Markera det numeriska elementet **Rapport\\Rader\\Post\\Momsbelopp**.

    > [!NOTE]
    > För närvarande konfigureras bindningen `@.Value` för detta element. Därför måste ett genererat dokument fyllas med momsvärden från fältet `model.Data.List.Value`.

5. Välj **Redigera recept**.
6. På sidan **Formeldesigner** följer du dessa steg:

    1. I fältet **Formel** ersätter du `@.Value` med `CollectedTaxValues.Collect(@.Value)`.
    2. Spara ändringarna och stäng sidan.

    > [!NOTE]
    > Den nya bindningen kommer att föra över samma momsvärden till ett genererat dokument. Dessa värden samlas dock även in i datakällan **CollectedTaxValues**.

7. Välj det numeriska formatelementet **Rapport\\Rader\\Post\\RunningTotal**.
8. Välj **Redigera recept**.
9. På sidan **Formeldesigner** följer du dessa steg:

    1. I fältet **Formel** anger du `CollectedTaxValues.Sum(false)`.
    2. Spara ändringarna och stäng sidan.

    > [!NOTE]
    > Den nya bindningen kommer att skicka (till ett genererat dokument) det totala beloppet av momsvärden som redan har angetts.

    ![Numeriska element som har uppdaterade bindningar på sidan Formatdesigner](./media/er-data-collection-data-sources-02.png)

10. Välj **spara** och välj sedan **kör**.
11. I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.
12. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämtade fil som innehåller resultaten av den modifierade formatkörningen](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Ändra formatet för att utvärdera listan över insamlade momsvärden

1. På sidan **Formatdesigner**, på fliken **Format**, väljer du det numeriska formatelementet **Rapport\\Rader\\Post\\RunningTotal** och följer sedan följande steg:

    1. I fältet **Numerisk typ** ändrar du värdet från **Realtal** till **Heltal**.
    2. I fältet **Numeriskt format** ändrar du värdet från **F2** till **F0**.

3. På fliken **Mappning** väljer du **Redigera formel**.
4. På sidan **Formeldesigner** följer du dessa steg:

    1. I fältet **Formel** anger du `COUNT(CollectedTaxValues.Result)`.
    2. Spara ändringarna och stäng sidan.

    > [!NOTE]
    > Den nya bindningen kommer att föra över antalet poster i listan där momsvärdena samlas in till ett genererat dokument.

5. Välj **spara** och välj sedan **kör**.
6. I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.
7. Hämta och granska filen som webbläsaren erbjuder.

    ![Hämtade fil som innehåller resultaten av en annan modifierad formatkörning](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Om jag måste beräkna löpande summor och samla in data, vad är skillnaden mellan att använda en datakälla för DATASAMLING och att använda de inbyggda funktionerna för DATAINSAMLING?

Både en datakälla för DATAINSAMLING och de inbyggda funktionerna för [DATAINSAMLING](er-functions-category-data-collection.md) kan användas för datasamling, summering och inventering baserat på information som överförs till ett genererat utgående dokument. När du försöker avgöra vilken teknik som ska användas måste du dock ta hänsyn till följande:

| Datakälla | Inbyggda funktioner |
|-------------| ------------------ |
| Endast värden samlas in. | <p>Namngivna värden samlas in. Därför kan summor beräknas för separata grupper av värden.</p><p>Grupper kan dessutom extraheras som en lista.</p><p>Textvärden kan också samlas in.</p> |
| Unika värden samlas in automatiskt. | Ytterligare inställningar krävs för att hämta en lista med unika värden från de insamlade värdena. |
| Prestandan beror på volymen av insamlade värden. | Rent praktiskt beror prestandan inte på volymen av insamlade värden. |
| Denna metod fungerar för alla typer av utgående dokument. | Denna metod fungerar bara för text- och XML-dokument. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera format för inventering och summering](./tasks/er-format-counting-summing-1.md)
- [Skjuta upp körningen av sekvenselement i ER-format](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
