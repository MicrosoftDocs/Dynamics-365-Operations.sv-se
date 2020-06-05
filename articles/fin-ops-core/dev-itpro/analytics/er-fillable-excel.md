---
title: Skapa en konfiguration för att generera dokument i Excel-format
description: Det här avsnittet innehåller information om hur du utformar ett elektroniskt rapporteringsformat (ER) för att fylla i en Excel-mall och sedan generera utgående dokument i Excelformat.
author: NickSelin
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e889b08f10c5d0c95fed7c9e422340706bdd154a
ms.sourcegitcommit: 67ce81c57194afb26a04ae4c0b7509e0efa32afc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "3375823"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a><span data-ttu-id="fcc83-103">Skapa en konfiguration för att generera dokument i Excel-format</span><span class="sxs-lookup"><span data-stu-id="fcc83-103">Design a configuration for generating documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fcc83-104">Du kan utforma en konfiguration för [elektroniskt rapporteringsformat (ER)](general-electronic-reporting.md) som har en ER-[formatkomponent](general-electronic-reporting.md#FormatComponentOutbound) som du kan konfigurera för att generera ett utgående dokument i ett Microsoft Excel-arbetsboksformat.</span><span class="sxs-lookup"><span data-stu-id="fcc83-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) format configuration that has an ER [format component](general-electronic-reporting.md#FormatComponentOutbound) that you can configure to generate an outbound document in a Microsoft Excel workbook format.</span></span> <span data-ttu-id="fcc83-105">Specifika komponenter i ER-format måste användas för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="fcc83-105">Specific ER format components must be used for this purpose.</span></span>

<span data-ttu-id="fcc83-106">Om du vill veta mer om den här funktionen följer du stegen i avsnittet [utforma en konfiguration för generering av rapporter i OpenXML-format](tasks/er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="fcc83-106">To learn more about this feature, follow the steps in the topic, [Design a configuration for generating reports in OPENXML format](tasks/er-design-reports-openxml-2016-11.md).</span></span>

## <a name="add-a-new-er-format"></a><span data-ttu-id="fcc83-107">Lägg till ett nytt ER-format</span><span class="sxs-lookup"><span data-stu-id="fcc83-107">Add a new ER format</span></span>

<span data-ttu-id="fcc83-108">När du lägger till en ny konfiguration för ER-format i syfte att generera ett utgående dokument i ett Excel-format, måste du antingen välja **Excel**-värdet för attributet **Formattyp** för formatet eller lämna attributet **Formattyp** tomt.</span><span class="sxs-lookup"><span data-stu-id="fcc83-108">When you add a new ER format configuration to generate an outbound document in an Excel workbook format, you must either select the **Excel** value for the **Format type** attribute of the format or leave the **Format type** attribute blank.</span></span>

- <span data-ttu-id="fcc83-109">Om du väljer **Excel** kan du konfigurera formatet så att ett utgående dokument endast skapas i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="fcc83-109">If you select **Excel**, you can configure the format to generate an outbound document only in Excel format.</span></span>
- <span data-ttu-id="fcc83-110">Om du lämnar attributet tomt kan du konfigurera formatet så att ett utgående dokument skapas i ett format som stöds av ER-ramverket.</span><span class="sxs-lookup"><span data-stu-id="fcc83-110">If you leave the attribute blank, you can configure the format to generate an outbound document in any format that is supported by the ER framework.</span></span>

<span data-ttu-id="fcc83-111">Om du vill konfigurera ER-formatkomponenten för konfigurationen väljer du **Designer** i åtgärdsfönstret och öppnar ER-formatkomponenten för redigering i ER-åtgärdersdesignern.</span><span class="sxs-lookup"><span data-stu-id="fcc83-111">To configure the ER format component of the configuration, select **Designer** on the Action Pane, and open the ER format component for editing in the ER Operation designer.</span></span>

![Sidan Konfigurationer](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a><span data-ttu-id="fcc83-113">Excel-filkomponent</span><span class="sxs-lookup"><span data-stu-id="fcc83-113">Excel file component</span></span>

### <a name="manual-entry"></a><span data-ttu-id="fcc83-114">Manuell registrering</span><span class="sxs-lookup"><span data-stu-id="fcc83-114">Manual entry</span></span>

<span data-ttu-id="fcc83-115">Du måste lägga till en **Excel\\fil**-komponent i det konfigurerade ER-formatet för att kunna generera ett utgående dokument i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="fcc83-115">You must add an **Excel\\File** component to the configured ER format to generate an outbound document in Excel format.</span></span>

![Excel-\filkomponent](./media/er-excel-format-add-file-component.png)

<span data-ttu-id="fcc83-117">Om du vill ange layouten för det utgående dokumentet bifogar du en Excel-arbetsbok med filnamnstillägget .xlsx till komponenten **Excel\\fil** som mall för utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="fcc83-117">To specify the layout of the outbound document, attach an Excel workbook that has the .xlsx extension to the **Excel\\File** component as the template for outbound documents.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc83-118">När du bifogar en mall manuellt måste du använda en [dokumenttyp](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) som har konfigurerats för detta syfte i [ER-parametrarna](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span><span class="sxs-lookup"><span data-stu-id="fcc83-118">When you manually attach a template, you must use a [document type](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) that has been configured for that purpose in the [ER parameters](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span></span>

![Lägga till en bilaga i Excel\fil-komponenten](./media/er-excel-format-add-file-component2.png)

<span data-ttu-id="fcc83-120">Om du vill ange hur den bifogade mallen ska fyllas i när du kör det konfigurerade ER-formatet måste du lägga till kapslade **Ark-**, **Intervall-** och **Cell-** komponenter i**Excel\\fil**-komponenten.</span><span class="sxs-lookup"><span data-stu-id="fcc83-120">To specify how the attached template will be filled in when you run the configured ER format, you must add nested **Sheet**, **Range**, and **Cell** components to the **Excel\\File** component.</span></span> <span data-ttu-id="fcc83-121">Varje kapslad komponent måste associeras med ett namngivet Excel-objekt.</span><span class="sxs-lookup"><span data-stu-id="fcc83-121">Each nested component must be associated with an Excel named item.</span></span>

### <a name="template-import"></a><span data-ttu-id="fcc83-122">Mallimport</span><span class="sxs-lookup"><span data-stu-id="fcc83-122">Template import</span></span>

<span data-ttu-id="fcc83-123">Du kan välja **Importera från Excel** på fliken **Importera** i åtgärds fönstret för att importera en ny mall till ett tomt ER-format.</span><span class="sxs-lookup"><span data-stu-id="fcc83-123">You can select **Import from Excel** on the **Import** tab of the Action Pane to import a new template into a blank ER format.</span></span> <span data-ttu-id="fcc83-124">I det här exemplet skapas en **Excel\\-fil**komponent automatiskt, och den importerade mallen kopplas till den.</span><span class="sxs-lookup"><span data-stu-id="fcc83-124">In this example, an **Excel\\File** component will be created automatically, and the imported template will be attached to it.</span></span> <span data-ttu-id="fcc83-125">Alla obligatoriska ER-komponenter skapas också automatiskt, baserat på listan med Excel-objekt som upptäcks.</span><span class="sxs-lookup"><span data-stu-id="fcc83-125">All required ER components will also be created automatically, based on the list of Excel named items that are discovered.</span></span>

![Välja Importera från Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> <span data-ttu-id="fcc83-127">Om du vill skapa det valfria **Ark**-elementet i det redigerbara ER-formatet ställer du in alternativet **Skapa formatelement för Excel-ark** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fcc83-127">If you want to create the optional **Sheet** element in the editable ER format, set the **Create Excel Sheet format element** option to **Yes**.</span></span>

## <a name="sheet-component"></a><span data-ttu-id="fcc83-128">Ark-komponent</span><span class="sxs-lookup"><span data-stu-id="fcc83-128">Sheet component</span></span>

<span data-ttu-id="fcc83-129">Komponenten **Ark** anger ett kalkylblad tillhörande den bifogade Excel-arbetsbok som måste fyllas i.</span><span class="sxs-lookup"><span data-stu-id="fcc83-129">The **Sheet** component indicates a worksheet of the attached Excel workbook that must be filled in.</span></span> <span data-ttu-id="fcc83-130">Namnet på kalkylbladet i en Excel-mall definieras i egenskapen **Ark** för den här komponenten.</span><span class="sxs-lookup"><span data-stu-id="fcc83-130">The name of the worksheet in an Excel template is defined in the **Sheet** property of this component.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc83-131">Denna komponent är valfri för Excel-arbetsböcker som innehåller ett enda kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="fcc83-131">This component is optional for Excel workbooks that contain a single worksheet.</span></span>

<span data-ttu-id="fcc83-132">På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **ark**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:</span><span class="sxs-lookup"><span data-stu-id="fcc83-132">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Sheet** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="fcc83-133">Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, infogas lämpligt kalkylblad i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-133">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate worksheet will be put in the generated document.</span></span>
- <span data-ttu-id="fcc83-134">Om ett uttryck för egenskapen **Aktiverad** har konfigurerATS att returnera **False** vid körning kommer det genererade dokumentet inte att innehålla något kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="fcc83-134">If an expression of the **Enabled** property is configured to return **False** at runtime, the generated document won't contain a worksheet.</span></span>

![Exempel på en ark-komponent](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a><span data-ttu-id="fcc83-136">Intervall-komponent</span><span class="sxs-lookup"><span data-stu-id="fcc83-136">Range component</span></span>

<span data-ttu-id="fcc83-137">**Intervall**-komponenten anger ett Excel-intervall som måste kontrolleras av denna ER-komponent.</span><span class="sxs-lookup"><span data-stu-id="fcc83-137">The **Range** component indicates an Excel range that must be controlled by this ER component.</span></span> <span data-ttu-id="fcc83-138">Namnet på intervallet definieras i egenskapen **Excel-intervall** för den här komponenten.</span><span class="sxs-lookup"><span data-stu-id="fcc83-138">The name of the range is defined in the **Excel range** property of this component.</span></span>

<span data-ttu-id="fcc83-139">Egenskapen **Replikeringsriktning** anger om och hur intervallet ska upprepas i ett genererat dokument:</span><span class="sxs-lookup"><span data-stu-id="fcc83-139">The **Replication direction** property specifies whether and how the range will be repeated in a generated document:</span></span>

- <span data-ttu-id="fcc83-140">Om egenskapen **Replikeringsriktning** anges som **Ingen replikering** upprepas inte det aktuella Excel-intervallet i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-140">If the **Replication direction** property is set to **No replication**, the appropriate Excel range won't be repeated in the generated document.</span></span>
- <span data-ttu-id="fcc83-141">Om egenskapen **Replikeringsriktning** anges som **Lodrät** upprepas lämpligt Excel-intervall i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-141">If the **Replication direction** property is set to **Vertical**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="fcc83-142">Varje replikerat intervall placeras under det ursprungliga intervallet i en Excel-mall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-142">Every replicated range is put below the original range in an Excel template.</span></span> <span data-ttu-id="fcc83-143">Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.</span><span class="sxs-lookup"><span data-stu-id="fcc83-143">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>
- <span data-ttu-id="fcc83-144">Om egenskapen **Replikeringsriktning** anges som **Horisontell** upprepas lämpligt Excel-intervall i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-144">If the **Replication direction** property is set to **Horizontal**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="fcc83-145">Varje replikerat intervall placeras till höger om det ursprungliga intervallet i en Excel-mall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-145">Every replicated range is put to the right of the original range in an Excel template.</span></span> <span data-ttu-id="fcc83-146">Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.</span><span class="sxs-lookup"><span data-stu-id="fcc83-146">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>

<span data-ttu-id="fcc83-147">Om du vill veta mer om vågrät replikering följer du stegen i [Använd vågrätt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter](tasks/er-horizontal-1.md).</span><span class="sxs-lookup"><span data-stu-id="fcc83-147">To learn more about horizontal replication, follow the steps in [Use horizontally expandable ranges to dynamically add columns in Excel reports](tasks/er-horizontal-1.md).</span></span>

<span data-ttu-id="fcc83-148">**Intervall**-komponenten kan ha andra kapslade ER-komponenter som används för att ange värden i lämpliga Excel-namngivna intervall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-148">The **Range** component can have other nested ER components that are used to enter values in the appropriate Excel named ranges.</span></span>

- <span data-ttu-id="fcc83-149">Om en komponent i **Text**-gruppen används för att ange värden, anges värdet i ett Excel-intervall som ett textvärde.</span><span class="sxs-lookup"><span data-stu-id="fcc83-149">If any component of the **Text** group is used to enter values, the value is entered in an Excel range as a text value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcc83-150">Använd det här mönstret om du vill formatera angivna värden baserat på de språk som har definierats i programmet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-150">Use this pattern to format entered values based on the locale that is defined in the application.</span></span>

- <span data-ttu-id="fcc83-151">Om en **Cell**-komponent tillhörande gruppen **Excel** används för att ange värden, anges värdet i ett Excel-intervall som värde för den datatyp som definieras av bindningen för den **Cell**-komponenten (t.ex. **Sträng**, **Verklig** eller **Heltal**).</span><span class="sxs-lookup"><span data-stu-id="fcc83-151">If the **Cell** component of the **Excel** group is used to enter values, the value is entered in an Excel range as a value of the data type that is defined by the binding of that **Cell** component (for example, **String**, **Real**, or **Integer**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcc83-152">Använd det här mönstret om du vill göra det möjligt för Excel-programmet att formatera angivna värden baserat på språkinställningen för den lokala dator som öppnar det utgående dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-152">Use this pattern to enable the Excel application to format entered values based on the locale of the local computer that opens the outbound document.</span></span>

<span data-ttu-id="fcc83-153">På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Intervall**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:</span><span class="sxs-lookup"><span data-stu-id="fcc83-153">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Range** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="fcc83-154">Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt intervall i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-154">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate range will be filled in in the generated document.</span></span>
- <span data-ttu-id="fcc83-155">Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall inte representerar hela raderna eller kolumnerna, kommer lämpligt intervall inte att ifyllas i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-155">If an expression of the **Enabled** property is configured to return **False** at runtime, and if this range doesn't represent the entire rows or columns, the appropriate range won't be filled in in the generated document.</span></span>
- <span data-ttu-id="fcc83-156">Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall representerar hela raderna eller kolumnerna, kommer det genererade dokumentet att omfatta dessa rader och kolumner som dolda radera och kolumner.</span><span class="sxs-lookup"><span data-stu-id="fcc83-156">If an expression of the **Enabled** property is configured to return **False** at runtime, and this range represents the entire rows or columns, the generated document will contain those rows and columns as hidden rows and columns.</span></span>

## <a name="cell-component"></a><span data-ttu-id="fcc83-157">Cellkomponent</span><span class="sxs-lookup"><span data-stu-id="fcc83-157">Cell component</span></span>

<span data-ttu-id="fcc83-158">**Cell**-komponenten används för att fylla i Excel-betitlade celler, figurer och bilder.</span><span class="sxs-lookup"><span data-stu-id="fcc83-158">The **Cell** component is used to fill in Excel named cells, shapes, and pictures.</span></span> <span data-ttu-id="fcc83-159">Om du vill ange ett Excel-namngivet objekt som måste fyllas i av en ER-komponent för en **Cell**, måste du ange namnet på objektet i egenskapen **Excel-intervall** för komponenten **Cell**.</span><span class="sxs-lookup"><span data-stu-id="fcc83-159">To indicate an Excel named object that must be filled in by a **Cell** ER component, you must specify the name of that object in the **Excel range** property of the **Cell** component.</span></span>

<span data-ttu-id="fcc83-160">På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Cell**-komponent i syfte att ange om objektet måste ifyllas i ett genererat dokument:</span><span class="sxs-lookup"><span data-stu-id="fcc83-160">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Cell** component to specify whether the object must be filled in in a generated document:</span></span>

- <span data-ttu-id="fcc83-161">Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt objekt i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-161">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate object will be filled in in the generated document.</span></span> <span data-ttu-id="fcc83-162">Bindningen för denna **cell**-komponent anger ett värde som placeras i lämpligt objekt.</span><span class="sxs-lookup"><span data-stu-id="fcc83-162">The binding of this **Cell** component specifies a value that is put in the appropriate object.</span></span>
- <span data-ttu-id="fcc83-163">Om ett uttryck för egenskapen **Aktiverad** konfigureras i syfte att returnera **False** vid körning, kommer lämpligt objekt inte att ifyllas i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-163">If an expression of the **Enabled** property is configured to return **False** at runtime, the appropriate object won't be filled in in the generated document.</span></span>

<span data-ttu-id="fcc83-164">När en **cell**-komponent konfigureras för att ange ett värde i en cell, kan den bindas till en datakälla som returnerar värdet för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**).</span><span class="sxs-lookup"><span data-stu-id="fcc83-164">When a **Cell** component is configured to enter a value in a cell, it can be bound with a data source that returns the value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="fcc83-165">I det här fallet anges värdet i cellen som ett värde av samma datatyp.</span><span class="sxs-lookup"><span data-stu-id="fcc83-165">In this case, the value is entered in the cell as a value of the same data type.</span></span>

<span data-ttu-id="fcc83-166">När en **cell**-komponent konfigureras för att ange ett värde i en Excel-figur kan den bindas till en datakälla som returnerar ett värde för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**).</span><span class="sxs-lookup"><span data-stu-id="fcc83-166">When a **Cell** component is configured to enter a value in an Excel shape, it can be bound with a data source that returns a value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="fcc83-167">I det här fallet anges värdet i Excel-figuren som figurens text.</span><span class="sxs-lookup"><span data-stu-id="fcc83-167">In this case, the value is entered in the Excel shape as the text of that shape.</span></span> <span data-ttu-id="fcc83-168">För värden med datatyper som inte är **strängar** sker konverteringen till text automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fcc83-168">For values of data types that aren't **String**, the conversion to text is done automatically.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc83-169">Du kan konfigurera en **cell**-komponent så att den fyller i en form endast om en formegenskap för text stöds.</span><span class="sxs-lookup"><span data-stu-id="fcc83-169">You can configure a **Cell** component to fill in a shape only in cases where a shape text property is supported.</span></span>

<span data-ttu-id="fcc83-170">När en **Cell**-komponent konfigureras för att ange ett värde i Excel-bild kan den bindas till en datakälla som returnerar ett värde av datatypen **Behållare** som representerar en bild i ett binärt format.</span><span class="sxs-lookup"><span data-stu-id="fcc83-170">When a **Cell** component is configured to enter a value in an Excel picture, it can be bound with a data source that returns a value of the **Container** data type that represents an image in binary format.</span></span> <span data-ttu-id="fcc83-171">I det här fallet anges värdet i Excel-bilden som en bild.</span><span class="sxs-lookup"><span data-stu-id="fcc83-171">In this case, the value is entered in the Excel picture as an image.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc83-172">Alla Excel-bilder och -former betraktas som förankrade med sitt övre vänstra hörn till en viss Excel-cell eller ett visst Excel-intervall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-172">Every Excel picture and shape is considered to be anchored by its upper-left corner to a specific Excel cell or range.</span></span> <span data-ttu-id="fcc83-173">Om du vill replikera en Excel-bild eller -form måste du konfigurera cellen eller intervallet som den är fäst till som en replikerad cell eller ett cellområde.</span><span class="sxs-lookup"><span data-stu-id="fcc83-173">If you want to replicate an Excel picture or shape, you must configure the cell or range that it's anchored to as a replicated cell or range.</span></span>

<span data-ttu-id="fcc83-174">Mer information om hur du bäddar in bilder och former finns i [Bädda in bilder och former i dokument som du skapar med hjälp av ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="fcc83-174">To learn more about how to embed images and shapes, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="page-break-component"></a><span data-ttu-id="fcc83-175">Komponenten PageBreak</span><span class="sxs-lookup"><span data-stu-id="fcc83-175">Page break component</span></span>

<span data-ttu-id="fcc83-176">Komponenten **PageBreak** tvingar Excel att påbörja en ny sida.</span><span class="sxs-lookup"><span data-stu-id="fcc83-176">The **PageBreak** component forces Excel to start a new page.</span></span> <span data-ttu-id="fcc83-177">Den här komponenten behövs inte om du vill använda Excels standardsidindelning, men du bör använda den när du vill att Excel följer ditt ER-format för att strukturera sidindelning.</span><span class="sxs-lookup"><span data-stu-id="fcc83-177">This component isn't required when you want to use Excel's default paging, but you should use it when you want Excel to follow your ER format to structure paging.</span></span>

## <a name="edit-an-added-er-format"></a><span data-ttu-id="fcc83-178">Redigera ett tillagt ER-format</span><span class="sxs-lookup"><span data-stu-id="fcc83-178">Edit an added ER format</span></span>

### <a name="update-a-template"></a><span data-ttu-id="fcc83-179">Uppdatera en mall</span><span class="sxs-lookup"><span data-stu-id="fcc83-179">Update a template</span></span>

<span data-ttu-id="fcc83-180">Du kan välja **Uppdatera från Excel** på fliken **Importera** i åtgärdsfönstret för att importera en uppdaterad mall till ett redigerbart ER-format.</span><span class="sxs-lookup"><span data-stu-id="fcc83-180">You can select **Update from Excel** on the **Import** tab of the Action Pane to import an updated template into an editable ER format.</span></span> <span data-ttu-id="fcc83-181">Under den här processen ersätts en mall för den valda **Excel\\**-filkomponenten med en ny mall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-181">During this process, a template of the selected **Excel\\File** component will be replaced by a new template.</span></span> <span data-ttu-id="fcc83-182">Innehållet i det redigerbara ER-formatet synkroniseras med innehållet i den uppdaterade ER-mallen.</span><span class="sxs-lookup"><span data-stu-id="fcc83-182">The content of the editable ER format will be synced with the content of the updated ER template.</span></span>

- <span data-ttu-id="fcc83-183">En ny komponent för ER-format kommer att skapas automatiskt för alla Excel-namn om komponenten i ER-format inte hittas i det redigerbara formatet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-183">A new ER format component will automatically be created for every Excel name if the ER format component isn't found in the editable format.</span></span>
- <span data-ttu-id="fcc83-184">Alla ER-formatkomponenter tas bort från det redigerbara ER-formatet om det inte finns något korrekt Excel-namn.</span><span class="sxs-lookup"><span data-stu-id="fcc83-184">Every ER format component will be deleted from the editable ER format if the appropriate Excel name isn't found for it.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc83-185">Ange alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** om du vill skapa det valfria elementet **Ark** i det redigerbara ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-185">Set the **Create Excel Sheet format element** option to **Yes** if you want to create the optional **Sheet** element in the editable ER format.</span></span>
>
> <span data-ttu-id="fcc83-186">Om det redigerbara ER-formatet ursprungligen innehöll **ark**-element rekommenderar vi att du ställer in alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** när du importerar en uppdaterad mall.</span><span class="sxs-lookup"><span data-stu-id="fcc83-186">If the editable ER format originally contained **Sheet** elements, we recommend that you set the **Create Excel Sheet format element** option to **Yes** when you import an updated template.</span></span> <span data-ttu-id="fcc83-187">I annat fall kommer alla kapslade element i det ursprungliga **ark**-elementet att skapas från grunden.</span><span class="sxs-lookup"><span data-stu-id="fcc83-187">Otherwise, all nested elements of the original **Sheet** element will be created from scratch.</span></span> <span data-ttu-id="fcc83-188">Därför kommer också alla bindningar för de återskapade formatelementen att gå förlorade i det uppdaterade ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="fcc83-188">Therefore, all bindings of the re-created format elements will be lost in the updated ER format.</span></span>

![Alternativet Skapa formatelement för Excel-ark i dialogrutan Uppdatera från Excel](./media/er-excel-format-update-template.png)

<span data-ttu-id="fcc83-190">Om du vill veta mer om den här funktionen följer du stegen i [Ändra format för elektronisk rapportering genom att återanvända Excel-mallar](modify-electronic-reporting-format-reapply-excel-template.md).</span><span class="sxs-lookup"><span data-stu-id="fcc83-190">To learn more about this feature, follow the steps in [Modify Electronic reporting formats by reapplying Excel templates](modify-electronic-reporting-format-reapply-excel-template.md).</span></span>

## <a name="validate-an-er-format"></a><span data-ttu-id="fcc83-191">Validera ett ER-format</span><span class="sxs-lookup"><span data-stu-id="fcc83-191">Validate an ER format</span></span>

<span data-ttu-id="fcc83-192">När du validerar ett ER-format som kan redigeras görs en konsekvenskontroll för att säkerställa att Excel-namnet finns i den Excel-mall som används för närvarande.</span><span class="sxs-lookup"><span data-stu-id="fcc83-192">When you validate an ER format that can be edited, a consistency check is done to make sure that the Excel name is present in the Excel template that is currently used.</span></span> <span data-ttu-id="fcc83-193">Du får ett meddelande om eventuella inkonsekvenser.</span><span class="sxs-lookup"><span data-stu-id="fcc83-193">You will be notified about any inconsistencies.</span></span> <span data-ttu-id="fcc83-194">För vissa inkonsekvenser kommer alternativet att åtgärda problem automatiskt att erbjudas.</span><span class="sxs-lookup"><span data-stu-id="fcc83-194">For some inconsistencies, the option to automatically fix issues will be offered.</span></span>

![Meddelande om felvalidering](./media/er-excel-format-validate.png)


## <a name="additional-resources"></a><span data-ttu-id="fcc83-196">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fcc83-196">Additional resources</span></span>

[<span data-ttu-id="fcc83-197">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="fcc83-197">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="fcc83-198">Utforma en konfiguration för rapportgenerering i OPENXML-format</span><span class="sxs-lookup"><span data-stu-id="fcc83-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks\er-design-reports-openxml-2016-11.md)

[<span data-ttu-id="fcc83-199">Ändra format för elektronisk rapportering genom att tillämpa mallar från Excel igen</span><span class="sxs-lookup"><span data-stu-id="fcc83-199">Modify Electronic reporting formats by reapplying Excel templates</span></span>](modify-electronic-reporting-format-reapply-excel-template.md)

[<span data-ttu-id="fcc83-200">Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter</span><span class="sxs-lookup"><span data-stu-id="fcc83-200">Use horizontally expandable ranges to dynamically add columns in Excel reports</span></span>](tasks/er-horizontal-1.md)

[<span data-ttu-id="fcc83-201">Bädda in bilder och former i dokument som du skapar med ER</span><span class="sxs-lookup"><span data-stu-id="fcc83-201">Embed images and shapes in documents that you generate by using ER</span></span>](electronic-reporting-embed-images-shapes.md)

[<span data-ttu-id="fcc83-202">Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI</span><span class="sxs-lookup"><span data-stu-id="fcc83-202">Configure Electronic reporting (ER) to pull data into Power BI</span></span>](general-electronic-reporting-report-configuration-get-data-powerbi.md)
