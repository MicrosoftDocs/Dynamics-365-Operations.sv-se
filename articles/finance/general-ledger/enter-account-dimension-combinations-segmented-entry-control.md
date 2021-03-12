---
title: Ange konto- och dimensionskombinationer (segmenterad postkontroll)
description: Det här avsnittet innehåller en beskrivning av hur du anger konto och dimensionskombinationer eller redovisningskonton. Posterfarenheten kallas ofta för segmenterad postkontroll.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1e35f5fb4400f849e9a139e1a96b18e8b9df384
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968789"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="80a75-104">Ange konto- och dimensionskombinationer (segmenterad postkontroll)</span><span class="sxs-lookup"><span data-stu-id="80a75-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80a75-105">Det här avsnittet innehåller en beskrivning av hur du anger konto och dimensionskombinationer eller redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="80a75-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="80a75-106">Posterfarenheten kallas ofta för segmenterad postkontroll.</span><span class="sxs-lookup"><span data-stu-id="80a75-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="80a75-107">Användare anger konto- och dimensionskombinationer på olika sidor, till exempel sidor för allmänna journaler, budgetar och bokföring av defintions.</span><span class="sxs-lookup"><span data-stu-id="80a75-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="80a75-108">De giltiga konto- och dimensionskombinationerna beror på kontostrukturerna som tilldelas redovisningen och de avancerade regler som är tilldelade kontostrukturerna.</span><span class="sxs-lookup"><span data-stu-id="80a75-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="80a75-109">När användarna anger en kombination, kan de antingen skriva värdena manuellt eller använda en avancerad sökfunktion.</span><span class="sxs-lookup"><span data-stu-id="80a75-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="80a75-110">När du anger det här fältet kan du börja skirve och det söker värdet och beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="80a75-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="80a75-111">Om du till exempel skriver 180, sökar programmet alla värden som börjar med den nummerkombinationen.</span><span class="sxs-lookup"><span data-stu-id="80a75-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="80a75-112">Du kan skriva in Kontant och programmet söker alla värden som har en beskrivning som börjar med Kontant.</span><span class="sxs-lookup"><span data-stu-id="80a75-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="80a75-113">Du kan också använda jokertecken, t ex \*Kontant eller \*180 vid sökning om värdet eller beskrivningen innehåller sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="80a75-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="80a75-114">I följande tabell beskrivnings av kortkommandona som kan användas när sökningen stängs.</span><span class="sxs-lookup"><span data-stu-id="80a75-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a75-115">Tangentbordsgenväg</span><span class="sxs-lookup"><span data-stu-id="80a75-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="80a75-116">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="80a75-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="80a75-117">Alt+nedpil</span><span class="sxs-lookup"><span data-stu-id="80a75-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="80a75-118">Öppnar sökningen.</span><span class="sxs-lookup"><span data-stu-id="80a75-118">Open the lookup.</span></span> <span data-ttu-id="80a75-119">Om du trycker på Alt+nedpil en gång till flyttas fokus till segmenten i den utfällbara menyn.</span><span class="sxs-lookup"><span data-stu-id="80a75-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="80a75-120">Retur och skift+retur</span><span class="sxs-lookup"><span data-stu-id="80a75-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="80a75-121">Kontoplansavgränsare</span><span class="sxs-lookup"><span data-stu-id="80a75-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="80a75-122">Högerpil och vänsterpil</span><span class="sxs-lookup"><span data-stu-id="80a75-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="80a75-123">Flytta till nästa eller föregående segment.</span><span class="sxs-lookup"><span data-stu-id="80a75-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="80a75-124">Tabb</span><span class="sxs-lookup"><span data-stu-id="80a75-124">Tab</span></span></td>
<td><span data-ttu-id="80a75-125">Flytta till nästa fält i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="80a75-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="80a75-126">I följande tabell beskrivnings av kortkommandona som kan användas när sökningen öppnas.</span><span class="sxs-lookup"><span data-stu-id="80a75-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a75-127">Tangentbordsgenväg</span><span class="sxs-lookup"><span data-stu-id="80a75-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="80a75-128">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="80a75-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="80a75-129">Esc</span><span class="sxs-lookup"><span data-stu-id="80a75-129">Esc</span></span></td>
<td><span data-ttu-id="80a75-130">Stänger sökningen.</span><span class="sxs-lookup"><span data-stu-id="80a75-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="80a75-131">Uppil och nedpil</span><span class="sxs-lookup"><span data-stu-id="80a75-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="80a75-132">Page Up och Page Down</span><span class="sxs-lookup"><span data-stu-id="80a75-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="80a75-133">Home och End</span><span class="sxs-lookup"><span data-stu-id="80a75-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="80a75-134">Flytta till nästa eller föregående värde i listan, till föregående eller nästa grupp av värden eller till det första eller sista elementet i sökningen.</span><span class="sxs-lookup"><span data-stu-id="80a75-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="80a75-135">Kontoplansavgränsare</span><span class="sxs-lookup"><span data-stu-id="80a75-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="80a75-136">Högerpil och vänsterpil</span><span class="sxs-lookup"><span data-stu-id="80a75-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="80a75-137">Flytta till nästa eller föregående segment.</span><span class="sxs-lookup"><span data-stu-id="80a75-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="80a75-138">Flik</span><span class="sxs-lookup"><span data-stu-id="80a75-138">Tab</span></span></td>
<td><span data-ttu-id="80a75-139">Flytta till nästa fält i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="80a75-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="80a75-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="80a75-140">Alt+W</span></span></td>
<td><span data-ttu-id="80a75-141">Växla mellan <strong>Visa alla</strong> och <strong>Visa giltigt</strong>.</span><span class="sxs-lookup"><span data-stu-id="80a75-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>





