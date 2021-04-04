---
title: Rapportdefinitioner i designer för ekonomiska rapporter
description: Den här artikeln innehåller information om rapportdefinitioner.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 073df430892e01d4842b2af147b0ae2765b1c66a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570352"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="5187d-103">Rapportdefinitioner i designer för ekonomiska rapporter</span><span class="sxs-lookup"><span data-stu-id="5187d-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5187d-104">Den här artikeln innehåller information om rapportdefinitioner.</span><span class="sxs-lookup"><span data-stu-id="5187d-104">This article provides information about report definitions.</span></span> <span data-ttu-id="5187d-105">En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="5187d-106">En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="5187d-107">En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="5187d-108">En rapportdefinition innehåller också alternativ och inställningar som du kan använda för att anpassa en rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="5187d-109">När du har definierat raddefinitioner och kolumndefinitioner, måste du kombinera dem i en rapportdefinition.</span><span class="sxs-lookup"><span data-stu-id="5187d-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="5187d-110">I det här läget definierar du också andra aspekter av definitioner, till exempel detaljnivå och rapportdatum.</span><span class="sxs-lookup"><span data-stu-id="5187d-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="5187d-111">Du kan sedan spara och skapa en rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-111">You can then save and generate a report.</span></span> <span data-ttu-id="5187d-112">Ekonomist rapportering omfattar följande detaljnivåer:</span><span class="sxs-lookup"><span data-stu-id="5187d-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="5187d-113">Ekonomi</span><span class="sxs-lookup"><span data-stu-id="5187d-113">Financial</span></span>
- <span data-ttu-id="5187d-114">Ekonomisk och Konto</span><span class="sxs-lookup"><span data-stu-id="5187d-114">Financial and Account</span></span>
- <span data-ttu-id="5187d-115">Ekonomisk, Konto och Transaktion</span><span class="sxs-lookup"><span data-stu-id="5187d-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="5187d-116">Däremot är det inte säkert att transaktionsinformation finns tillgänglig i rapporter, beroende på hur informationen är lagrad i Microsoft Dynamics ERP-systemet.</span><span class="sxs-lookup"><span data-stu-id="5187d-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="5187d-117">Skapa en rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="5187d-117">Create a report definition</span></span>
1. <span data-ttu-id="5187d-118">I Report Designer i menyn **Fil** klickar du på **Nytt** och väljer sedan **Rapportdefinition**.</span><span class="sxs-lookup"><span data-stu-id="5187d-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="5187d-119">Ange lämplig information i flikarna **Rapport** som krävs på **Utleverans och fördelning**, **Sidhuvud och sidfot** och **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="5187d-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="5187d-120">Innehåll i en rapportdefinition</span><span class="sxs-lookup"><span data-stu-id="5187d-120">Contents of a report definition</span></span>
<span data-ttu-id="5187d-121">I följande register finns beskrivningar av flikarna i en rapportdefinition och hur informationen används.</span><span class="sxs-lookup"><span data-stu-id="5187d-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5187d-122">Tabb</span><span class="sxs-lookup"><span data-stu-id="5187d-122">Tab</span></span></th>
<th><span data-ttu-id="5187d-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5187d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5187d-124">Rapport</span><span class="sxs-lookup"><span data-stu-id="5187d-124">Report</span></span></td>
<td><span data-ttu-id="5187d-125">Skapa en rapport, konfigurera en rapport eller ändra en befintlig rapport.</span><span class="sxs-lookup"><span data-stu-id="5187d-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5187d-126">Utleverans och fördelning</span><span class="sxs-lookup"><span data-stu-id="5187d-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="5187d-127">Ändra rapportens utleveranstyp och mål.</span><span class="sxs-lookup"><span data-stu-id="5187d-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5187d-128">Huvud och sidfot</span><span class="sxs-lookup"><span data-stu-id="5187d-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="5187d-129">Definiera och formatera rapportens sidhuvud och sidfot.</span><span class="sxs-lookup"><span data-stu-id="5187d-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="5187d-130">Du kan till exempel lägga till text eller bilder till sidhuvudet eller sidfoten.</span><span class="sxs-lookup"><span data-stu-id="5187d-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="5187d-131">Ekonomisk rapportering stöder .bmp-, .jpg- och .png-filer för bilder.</span><span class="sxs-lookup"><span data-stu-id="5187d-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="5187d-132">Du kan också lägga till autotextkoder om du vill infoga annan information som till exempel företagsnamn, rapportnamn eller sidnummer.</span><span class="sxs-lookup"><span data-stu-id="5187d-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5187d-133">Inställningar</span><span class="sxs-lookup"><span data-stu-id="5187d-133">Settings</span></span></td>
<td><span data-ttu-id="5187d-134">Ange rapportdefinitioninställningar, till exempel följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="5187d-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="5187d-135">Formatering och avrundningsbelopp</span><span class="sxs-lookup"><span data-stu-id="5187d-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="5187d-136">Formatdetaljrapporter</span><span class="sxs-lookup"><span data-stu-id="5187d-136">Format detail reports</span></span></li>
<li><span data-ttu-id="5187d-137">Formatrapporteringsträd</span><span class="sxs-lookup"><span data-stu-id="5187d-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="5187d-138">Skapa rapport över inleveransavvikelser</span><span class="sxs-lookup"><span data-stu-id="5187d-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="5187d-139">Ange valutakonvertering</span><span class="sxs-lookup"><span data-stu-id="5187d-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="5187d-140">Delsumma- och filterkontodetaljer</span><span class="sxs-lookup"><span data-stu-id="5187d-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="5187d-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5187d-141">Additional resources</span></span>

[<span data-ttu-id="5187d-142">Ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="5187d-142">Financial reporting</span></span>](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]