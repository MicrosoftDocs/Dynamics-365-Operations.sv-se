---
title: Abonnemangsförsäljningspriser
description: När du skapar ett abonnemang hämtas försäljningspriset från inställningarna för försäljningspris som skapats i formuläret Försäljningspris (abonnemang).
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e18690f7e9b790ecbd0ac0de1955fc95ab1f082
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560699"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="6d986-103">Abonnemangsförsäljningspriser</span><span class="sxs-lookup"><span data-stu-id="6d986-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6d986-104">När du skapar ett abonnemang hämtas försäljningspriset från inställningarna för försäljningspris som skapats i formuläret **Försäljningspris (abonnemang)**.</span><span class="sxs-lookup"><span data-stu-id="6d986-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="6d986-105">I formuläret **Försäljningspris (abonnemang)** kan du skapa försäljningspriser för ett visst abonnemang, eller också kan du skapa försäljningspriser som har ett bredare tillämpningsområde.</span><span class="sxs-lookup"><span data-stu-id="6d986-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="6d986-106">Om du ska kunna tillämpa ett försäljningspris på ett abonnemang måste periodkoden och valutan för abonnemanget måste vara identisk med periodkoden och försäljningsprisets valuta.</span><span class="sxs-lookup"><span data-stu-id="6d986-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="6d986-107">Om periodkoden och valutan är identiska för både abonnemang och försäljningspris väljs försäljningspriser för abonnemanget utifrån de prioriteringar som listas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6d986-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="6d986-108">En tom cell i tabellen indikerar tomt fält och X anger ett värde som är lika med värdet i abonnemanget som transaktionen genererats från.</span><span class="sxs-lookup"><span data-stu-id="6d986-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-109">Prioritet </span><span class="sxs-lookup"><span data-stu-id="6d986-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="6d986-110"><strong>Kategori</strong></span><span class="sxs-lookup"><span data-stu-id="6d986-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="6d986-111"><strong>Projekt-ID</strong></span><span class="sxs-lookup"><span data-stu-id="6d986-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="6d986-112"><strong>Abonnemang</strong></span><span class="sxs-lookup"><span data-stu-id="6d986-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="6d986-113"><strong>Försäljningsvaluta</strong></span><span class="sxs-lookup"><span data-stu-id="6d986-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="6d986-114"><strong>Periodkod</strong></span><span class="sxs-lookup"><span data-stu-id="6d986-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-115">1</span><span class="sxs-lookup"><span data-stu-id="6d986-115">1</span></span></p></td>
<td><p><span data-ttu-id="6d986-116">X</span><span class="sxs-lookup"><span data-stu-id="6d986-116">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-117">X</span><span class="sxs-lookup"><span data-stu-id="6d986-117">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-118">X</span><span class="sxs-lookup"><span data-stu-id="6d986-118">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-119">X</span><span class="sxs-lookup"><span data-stu-id="6d986-119">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-120">X</span><span class="sxs-lookup"><span data-stu-id="6d986-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-121">2</span><span class="sxs-lookup"><span data-stu-id="6d986-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-122">X</span><span class="sxs-lookup"><span data-stu-id="6d986-122">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-123">X</span><span class="sxs-lookup"><span data-stu-id="6d986-123">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-124">X</span><span class="sxs-lookup"><span data-stu-id="6d986-124">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-125">X</span><span class="sxs-lookup"><span data-stu-id="6d986-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d986-126">3</span><span class="sxs-lookup"><span data-stu-id="6d986-126">3</span></span></p></td>
<td><p><span data-ttu-id="6d986-127">X</span><span class="sxs-lookup"><span data-stu-id="6d986-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-128">X</span><span class="sxs-lookup"><span data-stu-id="6d986-128">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-129">X</span><span class="sxs-lookup"><span data-stu-id="6d986-129">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-130">X</span><span class="sxs-lookup"><span data-stu-id="6d986-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-131">4</span><span class="sxs-lookup"><span data-stu-id="6d986-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-132">X</span><span class="sxs-lookup"><span data-stu-id="6d986-132">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-133">X</span><span class="sxs-lookup"><span data-stu-id="6d986-133">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-134">X</span><span class="sxs-lookup"><span data-stu-id="6d986-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d986-135">5</span><span class="sxs-lookup"><span data-stu-id="6d986-135">5</span></span></p></td>
<td><p><span data-ttu-id="6d986-136">X</span><span class="sxs-lookup"><span data-stu-id="6d986-136">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-137">X</span><span class="sxs-lookup"><span data-stu-id="6d986-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-138">X</span><span class="sxs-lookup"><span data-stu-id="6d986-138">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-139">X</span><span class="sxs-lookup"><span data-stu-id="6d986-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-140">6</span><span class="sxs-lookup"><span data-stu-id="6d986-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-141">X</span><span class="sxs-lookup"><span data-stu-id="6d986-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-142">X</span><span class="sxs-lookup"><span data-stu-id="6d986-142">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-143">X</span><span class="sxs-lookup"><span data-stu-id="6d986-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d986-144">7</span><span class="sxs-lookup"><span data-stu-id="6d986-144">7</span></span></p></td>
<td><p><span data-ttu-id="6d986-145">X</span><span class="sxs-lookup"><span data-stu-id="6d986-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-146">X</span><span class="sxs-lookup"><span data-stu-id="6d986-146">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-147">X</span><span class="sxs-lookup"><span data-stu-id="6d986-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-148">8</span><span class="sxs-lookup"><span data-stu-id="6d986-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="6d986-149">X</span><span class="sxs-lookup"><span data-stu-id="6d986-149">X</span></span></p></td>
<td><p><span data-ttu-id="6d986-150">X</span><span class="sxs-lookup"><span data-stu-id="6d986-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-151">När en abonnemangsavgift skapas väljs försäljningspriset med högst detaljnivå (enligt uppgifterna i tabellen ovan) som försäljningspris för abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="6d986-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="6d986-152">Uppdatera och indexera abonnemangsförsäljningspriser</span><span class="sxs-lookup"><span data-stu-id="6d986-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="6d986-153">Du kan uppdatera försäljningspriset för abonnemanget genom att uppdatera baspris eller index.</span><span class="sxs-lookup"><span data-stu-id="6d986-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="6d986-154">Du kan uppdatera med en procentsats eller till ett nytt värde.</span><span class="sxs-lookup"><span data-stu-id="6d986-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="6d986-155">Försäljningspriser för abonnemangsavgift</span><span class="sxs-lookup"><span data-stu-id="6d986-155">Subscription fee sales prices</span></span>

<span data-ttu-id="6d986-156">När du skapar en abonnemangsavgift baseras försäljningspriset på abonnemangets inställda försäljningspris.</span><span class="sxs-lookup"><span data-stu-id="6d986-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="6d986-157">Du kan använda baspriset från prisinställningarna från abonnemanget eller så kan du skapa indexerade försäljningspriser.</span><span class="sxs-lookup"><span data-stu-id="6d986-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="6d986-158">Exempel</span><span class="sxs-lookup"><span data-stu-id="6d986-158">Example</span></span>

<span data-ttu-id="6d986-159">Du vill skapa ett försäljningspris för abonnemang på 500 EUR för det nya projektet 9030.</span><span class="sxs-lookup"><span data-stu-id="6d986-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="6d986-160">I formuläret **försäljningspris (abonnemang)** kan du skapa en försäljningsprisrad enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="6d986-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-161">Giltig från</span><span class="sxs-lookup"><span data-stu-id="6d986-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="6d986-162">Kategori</span><span class="sxs-lookup"><span data-stu-id="6d986-162">Category</span></span></p></th>
<th><p><span data-ttu-id="6d986-163">Project</span><span class="sxs-lookup"><span data-stu-id="6d986-163">Project</span></span></p></th>
<th><p><span data-ttu-id="6d986-164">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="6d986-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="6d986-165">Periodkod</span><span class="sxs-lookup"><span data-stu-id="6d986-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="6d986-166">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="6d986-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="6d986-167">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="6d986-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-168">2006-08-28</span><span class="sxs-lookup"><span data-stu-id="6d986-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d986-169">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d986-170">Månad</span><span class="sxs-lookup"><span data-stu-id="6d986-170">Month</span></span></p></td>
<td><p><span data-ttu-id="6d986-171">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-172">500</span><span class="sxs-lookup"><span data-stu-id="6d986-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-173">Observera att fälten **Kategori** och **Abonnemang** är tomma.</span><span class="sxs-lookup"><span data-stu-id="6d986-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="6d986-174">Du skapar sedan följande abonnemang:</span><span class="sxs-lookup"><span data-stu-id="6d986-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-175">Serviceabonnemang</span><span class="sxs-lookup"><span data-stu-id="6d986-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="6d986-176">Project</span><span class="sxs-lookup"><span data-stu-id="6d986-176">Project</span></span></p></th>
<th><p><span data-ttu-id="6d986-177">Abonnemangsgrupp</span><span class="sxs-lookup"><span data-stu-id="6d986-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="6d986-178">Kategori</span><span class="sxs-lookup"><span data-stu-id="6d986-178">Category</span></span></p></th>
<th><p><span data-ttu-id="6d986-179">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d986-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="6d986-180">Periodkod</span><span class="sxs-lookup"><span data-stu-id="6d986-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="6d986-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-182">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-182">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-183">Ab1</span><span class="sxs-lookup"><span data-stu-id="6d986-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="6d986-184">AbKat1</span><span class="sxs-lookup"><span data-stu-id="6d986-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="6d986-185">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-186">Månatligen</span><span class="sxs-lookup"><span data-stu-id="6d986-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="6d986-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-188">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-188">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-189">Ab1</span><span class="sxs-lookup"><span data-stu-id="6d986-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="6d986-190">AbKat2</span><span class="sxs-lookup"><span data-stu-id="6d986-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="6d986-191">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-192">Månatligen</span><span class="sxs-lookup"><span data-stu-id="6d986-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-193">Nu skapar du abonnemangsavgifter för båda abonnemangen i abonnemangsgruppen Ab1:</span><span class="sxs-lookup"><span data-stu-id="6d986-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="6d986-194">Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="6d986-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="6d986-195">I formuläret **abonnemangsgrupper** klickar du på **funktion**\>**Skapa abonnemangsavgift**.</span><span class="sxs-lookup"><span data-stu-id="6d986-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="6d986-196">På formuläret **Skapa abonnemangsavgift** ange lämplig information i fälten i formuläret.</span><span class="sxs-lookup"><span data-stu-id="6d986-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="6d986-197">Mer information finns i [Skapa transaktioner för abonnemangsavgifter](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="6d986-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="6d986-198">Abonnemangsavgifter med försäljningspriset 500 EUR skapas för båda abonnemangen som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6d986-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-199">Projektdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="6d986-200">Serviceabonnemang</span><span class="sxs-lookup"><span data-stu-id="6d986-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="6d986-201">Project</span><span class="sxs-lookup"><span data-stu-id="6d986-201">Project</span></span></p></th>
<th><p><span data-ttu-id="6d986-202">Kategori</span><span class="sxs-lookup"><span data-stu-id="6d986-202">Category</span></span></p></th>
<th><p><span data-ttu-id="6d986-203">Startdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="6d986-204">Slutdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-204">End date</span></span></p></th>
<th><p><span data-ttu-id="6d986-205">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="6d986-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="6d986-206">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="6d986-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-207">2006-08-28</span><span class="sxs-lookup"><span data-stu-id="6d986-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="6d986-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="6d986-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-209">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-209">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-210">AbKat1</span><span class="sxs-lookup"><span data-stu-id="6d986-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="6d986-211">2007-01-01</span><span class="sxs-lookup"><span data-stu-id="6d986-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-212">2007-03-31</span><span class="sxs-lookup"><span data-stu-id="6d986-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-213">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-214">500</span><span class="sxs-lookup"><span data-stu-id="6d986-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-215">2006-08-28</span><span class="sxs-lookup"><span data-stu-id="6d986-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="6d986-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="6d986-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-217">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-217">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-218">AbKat2</span><span class="sxs-lookup"><span data-stu-id="6d986-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="6d986-219">2007-01-01</span><span class="sxs-lookup"><span data-stu-id="6d986-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-220">2007-03-31</span><span class="sxs-lookup"><span data-stu-id="6d986-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-221">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-222">500</span><span class="sxs-lookup"><span data-stu-id="6d986-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-223">Senare beslutar du dig för att du vill ange försäljningspriser för kategorin AbKat1 för projekt 9030.</span><span class="sxs-lookup"><span data-stu-id="6d986-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="6d986-224">Därför skapar du en ny försäljningsprisrad med försäljningspriset EUR 550 för kombinationen projekt 9030 och avgiftskategori AbKat1.</span><span class="sxs-lookup"><span data-stu-id="6d986-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="6d986-225">Det finns nu två abonnemangsprisrader för projekt 9030 enligt följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6d986-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-226">Giltig från</span><span class="sxs-lookup"><span data-stu-id="6d986-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="6d986-227">Kategori</span><span class="sxs-lookup"><span data-stu-id="6d986-227">Category</span></span></p></th>
<th><p><span data-ttu-id="6d986-228">Project</span><span class="sxs-lookup"><span data-stu-id="6d986-228">Project</span></span></p></th>
<th><p><span data-ttu-id="6d986-229">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="6d986-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="6d986-230">Periodkod</span><span class="sxs-lookup"><span data-stu-id="6d986-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="6d986-231">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d986-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="6d986-232">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="6d986-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-233">2007-08-28</span><span class="sxs-lookup"><span data-stu-id="6d986-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d986-234">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d986-235">Månad</span><span class="sxs-lookup"><span data-stu-id="6d986-235">Month</span></span></p></td>
<td><p><span data-ttu-id="6d986-236">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-237">500</span><span class="sxs-lookup"><span data-stu-id="6d986-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-238">2007-08-28</span><span class="sxs-lookup"><span data-stu-id="6d986-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-239">AbKat1</span><span class="sxs-lookup"><span data-stu-id="6d986-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="6d986-240">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d986-241">Månad</span><span class="sxs-lookup"><span data-stu-id="6d986-241">Month</span></span></p></td>
<td><p><span data-ttu-id="6d986-242">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-243">550</span><span class="sxs-lookup"><span data-stu-id="6d986-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-244">Du upprepar proceduren ovan och skapar abonnemangsavgifter för båda abonnemangen i abonnemangsgruppen Ab1.</span><span class="sxs-lookup"><span data-stu-id="6d986-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="6d986-245">Följande tabell visar de transaktioner som skapas för varje abonnemang som är kopplat till abonnemangsgruppen:</span><span class="sxs-lookup"><span data-stu-id="6d986-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6d986-246">Projektdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="6d986-247">Abonnemang</span><span class="sxs-lookup"><span data-stu-id="6d986-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="6d986-248">Project</span><span class="sxs-lookup"><span data-stu-id="6d986-248">Project</span></span></p></th>
<th><p><span data-ttu-id="6d986-249">Kategori</span><span class="sxs-lookup"><span data-stu-id="6d986-249">Category</span></span></p></th>
<th><p><span data-ttu-id="6d986-250">Startdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="6d986-251">Slutdatum</span><span class="sxs-lookup"><span data-stu-id="6d986-251">End date</span></span></p></th>
<th><p><span data-ttu-id="6d986-252">Försäljningsvaluta</span><span class="sxs-lookup"><span data-stu-id="6d986-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="6d986-253">Försäljningspris</span><span class="sxs-lookup"><span data-stu-id="6d986-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d986-254">2007-07-28</span><span class="sxs-lookup"><span data-stu-id="6d986-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="6d986-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="6d986-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-256">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-256">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-257">AbKat1</span><span class="sxs-lookup"><span data-stu-id="6d986-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="6d986-258">2008-01-01</span><span class="sxs-lookup"><span data-stu-id="6d986-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="6d986-259">2008-03-31</span><span class="sxs-lookup"><span data-stu-id="6d986-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="6d986-260">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-261">550</span><span class="sxs-lookup"><span data-stu-id="6d986-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d986-262">2008-07-28</span><span class="sxs-lookup"><span data-stu-id="6d986-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="6d986-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="6d986-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="6d986-264">9030</span><span class="sxs-lookup"><span data-stu-id="6d986-264">9030</span></span></p></td>
<td><p><span data-ttu-id="6d986-265">AbKat2</span><span class="sxs-lookup"><span data-stu-id="6d986-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="6d986-266">2008-01-01</span><span class="sxs-lookup"><span data-stu-id="6d986-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="6d986-267">2008-03-31</span><span class="sxs-lookup"><span data-stu-id="6d986-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="6d986-268">Euro</span><span class="sxs-lookup"><span data-stu-id="6d986-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="6d986-269">500</span><span class="sxs-lookup"><span data-stu-id="6d986-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d986-270">I den första transaktionen för abonnemang 00020\_135, kommer försäljningspriset på 550 EUR från det abonnemangsförsäljningspris som skapats för den specifika kombinationen av projekt och kategori.</span><span class="sxs-lookup"><span data-stu-id="6d986-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="6d986-271">I den andra transaktionen för abonnemang 00021\_135, används försäljningspriset 500 EUR som projektets abonnemangsförsäljningspris eftersom inget pris skapats för kombinationen av projekt 9030 och kategori AbKat2.</span><span class="sxs-lookup"><span data-stu-id="6d986-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d986-272">Se även</span><span class="sxs-lookup"><span data-stu-id="6d986-272">See also</span></span>

[<span data-ttu-id="6d986-273">Uppdatera och indexera abonnemangsförsäljningspriser</span><span class="sxs-lookup"><span data-stu-id="6d986-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


