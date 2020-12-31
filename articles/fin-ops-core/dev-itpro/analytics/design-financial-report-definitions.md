---
title: Rapportdefinitioner i designer för ekonomiska rapporter
description: Den här artikeln innehåller information om rapportdefinitioner. En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 779548dc49be0a92456df791017045803f70bd86
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683121"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="ce8a3-105">Rapportdefinitioner i designer för ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="ce8a3-105">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce8a3-106">Den här artikeln innehåller information om rapportdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-106">This article provides information about report definitions.</span></span> <span data-ttu-id="ce8a3-107">En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="ce8a3-108">En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="ce8a3-109">En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="ce8a3-110">En rapportdefinition innehåller också alternativ och inställningar som du kan använda för att anpassa en rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="ce8a3-111">När du har definierat raddefinitioner och kolumndefinitioner, måste du kombinera dem i en rapportdefinition.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="ce8a3-112">I det här läget definierar du också andra aspekter av definitioner, till exempel detaljnivå och rapportdatum.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="ce8a3-113">Du kan sedan spara och skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-113">You can then save and generate a report.</span></span> <span data-ttu-id="ce8a3-114">Ekonomist rapportering omfattar följande detaljnivåer:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-114">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="ce8a3-115">Ekonomi</span><span class="sxs-lookup"><span data-stu-id="ce8a3-115">Financial</span></span>
- <span data-ttu-id="ce8a3-116">Ekonomisk och Konto</span><span class="sxs-lookup"><span data-stu-id="ce8a3-116">Financial and Account</span></span>
- <span data-ttu-id="ce8a3-117">Ekonomisk, Konto och Transaktion</span><span class="sxs-lookup"><span data-stu-id="ce8a3-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="ce8a3-118">Däremot är det inte säkert att transaktionsinformation finns tillgänglig i rapporter, beroende på hur informationen är lagrad i Microsoft Dynamics ERP-systemet.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="ce8a3-119">Skapa en rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="ce8a3-119">Create a report definition</span></span>
1. <span data-ttu-id="ce8a3-120">I Report Designer i menyn **Fil** klickar du på **Nytt** och väljer sedan **Rapportdefinition**.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="ce8a3-121">Ange lämplig information i flikarna **Rapport** som krävs på **Utleverans och fördelning**, **Sidhuvud och sidfot** och **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="ce8a3-122">Innehåll i en rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="ce8a3-122">Contents of a report definition</span></span>
<span data-ttu-id="ce8a3-123">I följande register finns beskrivningar av flikarna i en rapportdefinition och hur informationen används.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce8a3-124">Tabb</span><span class="sxs-lookup"><span data-stu-id="ce8a3-124">Tab</span></span></th>
<th><span data-ttu-id="ce8a3-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ce8a3-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce8a3-126">Rapport</span><span class="sxs-lookup"><span data-stu-id="ce8a3-126">Report</span></span></td>
<td><span data-ttu-id="ce8a3-127">Skapa en rapport, konfigurera en rapport eller ändra en befintlig rapport.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce8a3-128">Utleverans och fördelning</span><span class="sxs-lookup"><span data-stu-id="ce8a3-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="ce8a3-129">Ändra rapportens utleveranstyp och mål.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce8a3-130">Huvud och sidfot</span><span class="sxs-lookup"><span data-stu-id="ce8a3-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="ce8a3-131">Definiera och formatera rapportens sidhuvud och sidfot.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="ce8a3-132">Du kan till exempel lägga till text eller bilder till sidhuvudet eller sidfoten.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="ce8a3-133">Ekonomisk rapportering stöder .bmp-, .jpg- och .png-filer för bilder.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="ce8a3-134">Du kan också lägga till autotextkoder om du vill infoga annan information som till exempel företagsnamn, rapportnamn eller sidnummer.</span><span class="sxs-lookup"><span data-stu-id="ce8a3-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce8a3-135">Inställningar</span><span class="sxs-lookup"><span data-stu-id="ce8a3-135">Settings</span></span></td>
<td><span data-ttu-id="ce8a3-136">Ange rapportdefinitioninställningar, till exempel följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ce8a3-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="ce8a3-137">Formatering och avrundningsbelopp</span><span class="sxs-lookup"><span data-stu-id="ce8a3-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="ce8a3-138">Formatdetaljrapporter</span><span class="sxs-lookup"><span data-stu-id="ce8a3-138">Format detail reports</span></span></li>
<li><span data-ttu-id="ce8a3-139">Formatrapporteringsträd</span><span class="sxs-lookup"><span data-stu-id="ce8a3-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="ce8a3-140">Skapa rapport över inleveransavvikelser</span><span class="sxs-lookup"><span data-stu-id="ce8a3-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="ce8a3-141">Ange valutakonvertering</span><span class="sxs-lookup"><span data-stu-id="ce8a3-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="ce8a3-142">Delsumma- och filterkontodetaljer</span><span class="sxs-lookup"><span data-stu-id="ce8a3-142">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="ce8a3-143">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ce8a3-143">Additional resources</span></span>

[<span data-ttu-id="ce8a3-144">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="ce8a3-144">Financial reporting</span></span>](financial-reporting-intro.md)
