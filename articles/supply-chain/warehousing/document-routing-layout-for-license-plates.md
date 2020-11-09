---
title: Layout för dokumentflöde för ID-nummeretiketter
description: I det här avsnittet beskrivs hur du använder formateringsfunktioner för att skriva ut värden på etiketter.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 8c96aef5d66ed8f8c44d74eee9b60f0a7d38a46d
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017723"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="26cbf-103">Layout för dokumentflöde för ID-nummeretiketter</span><span class="sxs-lookup"><span data-stu-id="26cbf-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26cbf-104">Layouten för dokumentflöde definierar layouten för etiketter för ID-nummer och de data som skrivs ut på dem.</span><span class="sxs-lookup"><span data-stu-id="26cbf-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="26cbf-105">Du konfigurerar utlösningspunkterna för utskrivning när du ställer in menyalternativ för mobilenheter och arbetsmallar.</span><span class="sxs-lookup"><span data-stu-id="26cbf-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="26cbf-106">I ett typiskt scenario skriver inleveransansvarige på lagerstället ut ID-nummeretiketter direkt efter att de har noterat innehållet i lastpallar som anländer till mottagningsområdet.</span><span class="sxs-lookup"><span data-stu-id="26cbf-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="26cbf-107">De fysiska etiketterna används för lastpallarna.</span><span class="sxs-lookup"><span data-stu-id="26cbf-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="26cbf-108">De kan sedan användas för validering som en del av en artikelinförselprocess som följer och framtida utgående plockningsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="26cbf-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="26cbf-109">Du kan skriva ut mycket komplexa etiketter, förutsatt att utskriftsenheten kan tolka texten som skickas till den.</span><span class="sxs-lookup"><span data-stu-id="26cbf-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="26cbf-110">En ZPL-layout (Zebra Programming Language) som innehåller en streckkod kan till exempel likna följande exempel.</span><span class="sxs-lookup"><span data-stu-id="26cbf-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="26cbf-111">Som en del av etikettens utskriftsprocess kommer texten `$LicensePlateId$` i det här exemplet att ersättas med ett datavärde.</span><span class="sxs-lookup"><span data-stu-id="26cbf-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="26cbf-112">Om du vill se vilka värden som kommer att skrivas ut **Lagerstyrning \> Förfrågningar och rapporter \> ID-nummeretiketter**.</span><span class="sxs-lookup"><span data-stu-id="26cbf-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="26cbf-113">Många av de vanligaste verktygen för att skapa etiketter kan användas för att formatera texten i etikettexten.</span><span class="sxs-lookup"><span data-stu-id="26cbf-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="26cbf-114">Många av dessa verktyg stöder `$FieldName$`-formatet.</span><span class="sxs-lookup"><span data-stu-id="26cbf-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="26cbf-115">Dessutom använder Microsoft Dynamics 365 Supply Chain Management särskild formatlogik som en del av fältmappningen för layouten för dokumentflödet.</span><span class="sxs-lookup"><span data-stu-id="26cbf-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="26cbf-116">Anpassade nummerformat</span><span class="sxs-lookup"><span data-stu-id="26cbf-116">Custom number formats</span></span>

<span data-ttu-id="26cbf-117">Du kan anpassa formateringen av numeriska fältvärden som skrivs ut med hjälp av koder som har följande format.</span><span class="sxs-lookup"><span data-stu-id="26cbf-117">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="26cbf-118">Här följer en förklaring av detta format:</span><span class="sxs-lookup"><span data-stu-id="26cbf-118">Here is an explanation of this format:</span></span>

- <span data-ttu-id="26cbf-119">`FieldName` är namnet på datafältet (t.ex. **antal** ).</span><span class="sxs-lookup"><span data-stu-id="26cbf-119">`FieldName` is the name of the data field (such as **Qty** ).</span></span>
- <span data-ttu-id="26cbf-120">`FormatString` definierar hur data måste skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="26cbf-120">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="26cbf-121">Följande exempel visar hur du kan anpassa fältet arbetskvantitet ( **antal** ):</span><span class="sxs-lookup"><span data-stu-id="26cbf-121">The following examples show how you can customize the work quantity ( **Qty** ) field:</span></span>

- <span data-ttu-id="26cbf-122">Om du alltid vill visa fyra siffror (genom att använda nollor som platshållare) ska du använda `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="26cbf-122">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="26cbf-123">Om kvantiteten till exempel är 10 visas etiketten "0010".</span><span class="sxs-lookup"><span data-stu-id="26cbf-123">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="26cbf-124">Om du alltid vill visa två decimaler använder du `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="26cbf-124">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="26cbf-125">Om kvantiteten till exempel är 10 visas etiketten "10,00".</span><span class="sxs-lookup"><span data-stu-id="26cbf-125">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="26cbf-126">En fullständig lista över tillgängliga nummerformatsträngar finns i [Anpassade nummerformatsträngar](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="26cbf-126">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="26cbf-127">Anpassade strängformat</span><span class="sxs-lookup"><span data-stu-id="26cbf-127">Custom string formats</span></span>

<span data-ttu-id="26cbf-128">Du kan ta bort de första tecknen i en sträng med hjälp av följande fält och formatkod.</span><span class="sxs-lookup"><span data-stu-id="26cbf-128">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="26cbf-129">Här `#` anger du antalet tecken som ska hoppas över.</span><span class="sxs-lookup"><span data-stu-id="26cbf-129">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="26cbf-130">Om du t.ex. vill skriva ut ett ID-nummer med SSCC (Serial Shipping Container Code) som inte innehåller de första två tecknen använder du `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="26cbf-130">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="26cbf-131">I det här fallet skrivs ID-numret 0011111111111222221 ut som "11111111111222221."</span><span class="sxs-lookup"><span data-stu-id="26cbf-131">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="26cbf-132">Anpassade datum- och tidsformat</span><span class="sxs-lookup"><span data-stu-id="26cbf-132">Custom date/time formats</span></span>

<span data-ttu-id="26cbf-133">I följande exempel visas hur du kan styra det format som används för att skriva ut datum.</span><span class="sxs-lookup"><span data-stu-id="26cbf-133">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="26cbf-134">I det här exemplet skrivs 30 april 2020 ut som "30-04-2020".</span><span class="sxs-lookup"><span data-stu-id="26cbf-134">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="26cbf-135">En fullständig lista över tillgängliga datum-/tidsformat finns i [Anpassade formatsträngar för datum och tid](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="26cbf-135">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="26cbf-136">Skriva ut enskilda rader från samköpsdata</span><span class="sxs-lookup"><span data-stu-id="26cbf-136">Print individual lines from multiline data</span></span>

<span data-ttu-id="26cbf-137">Om ett datafält innehåller flera rader (dvs. rader som är avgränsade med radbrytningar), kan du skriva ut en enskild rad genom att använda följande format.</span><span class="sxs-lookup"><span data-stu-id="26cbf-137">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="26cbf-138">Här är `#` radnumret som du vill skriva ut.</span><span class="sxs-lookup"><span data-stu-id="26cbf-138">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="26cbf-139">(Använd 1 för den första raden.)</span><span class="sxs-lookup"><span data-stu-id="26cbf-139">(Use 1 for the first line.)</span></span>

<span data-ttu-id="26cbf-140">Ditt system har till exempel ett fält `AdditionalAddress` som lagrar följande radadress:</span><span class="sxs-lookup"><span data-stu-id="26cbf-140">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="26cbf-141">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="26cbf-141">Contoso Inc.</span></span>  
<span data-ttu-id="26cbf-142">123 gatunamn</span><span class="sxs-lookup"><span data-stu-id="26cbf-142">123 Street Name</span></span>  
<span data-ttu-id="26cbf-143">Någon stad, någon delstat</span><span class="sxs-lookup"><span data-stu-id="26cbf-143">Some City, Some State</span></span>

<span data-ttu-id="26cbf-144">Du kan skriva ut den här adressen, en rad i taget, med hjälp av följande koder.</span><span class="sxs-lookup"><span data-stu-id="26cbf-144">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="26cbf-145">Kod</span><span class="sxs-lookup"><span data-stu-id="26cbf-145">Code</span></span> | <span data-ttu-id="26cbf-146">Text som skrivs ut</span><span class="sxs-lookup"><span data-stu-id="26cbf-146">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="26cbf-147">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="26cbf-147">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="26cbf-148">123 gatunamn</span><span class="sxs-lookup"><span data-stu-id="26cbf-148">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="26cbf-149">Någon stad, någon delstat</span><span class="sxs-lookup"><span data-stu-id="26cbf-149">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="26cbf-150">Skriva ut och formatera från en visningsmetod</span><span class="sxs-lookup"><span data-stu-id="26cbf-150">Print and format from a display method</span></span>

<span data-ttu-id="26cbf-151">Du kan skriva ut från en visningsmetod med hjälp av följande format.</span><span class="sxs-lookup"><span data-stu-id="26cbf-151">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="26cbf-152">Du kan kombinera det här formatet med andra typer som beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="26cbf-152">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="26cbf-153">Du har till exempel en visningsmetod med namnet `DisplayListOfItemsNumbers()` och du vill skriva ut det första artikelnumret för den här metoden.</span><span class="sxs-lookup"><span data-stu-id="26cbf-153">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="26cbf-154">I det här fallet kan du använda följande kod.</span><span class="sxs-lookup"><span data-stu-id="26cbf-154">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="26cbf-155">Mer information om hur du skriver ut etiketter</span><span class="sxs-lookup"><span data-stu-id="26cbf-155">More information about how to print labels</span></span>

<span data-ttu-id="26cbf-156">Mer information om hur du ställer in och skriver ut etiketter finns i [Aktivera utskrift av ID-nummeretikett](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="26cbf-156">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>
