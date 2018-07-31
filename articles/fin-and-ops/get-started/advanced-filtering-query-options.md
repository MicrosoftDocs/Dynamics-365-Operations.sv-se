---
title: "Avancerade filtrerings- och frågesyntax"
description: "Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn **matchar** i den avancerade filtrerings-/sorteringsdialogen."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: edff2fba7e231ae52abf7828d55c1fe4841ccd7f
ms.openlocfilehash: 3e7127a9412dcf9324872c06fbf6cc3cf61bf063
ms.contentlocale: sv-se
ms.lasthandoff: 07/06/2018

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="a2d9f-103">Avancerad filtrerings- och frågesyntax</span><span class="sxs-lookup"><span data-stu-id="a2d9f-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2d9f-104">Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn **matchar** i den avancerade filtrerings-/sorteringsdialogen.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span> 

<a name="advanced-query-syntax"></a><span data-ttu-id="a2d9f-105">Avancerad frågesyntax</span><span class="sxs-lookup"><span data-stu-id="a2d9f-105">Advanced query syntax</span></span>
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2d9f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2d9f-106">Syntax</span></span></th>
<th><span data-ttu-id="a2d9f-107">Teckenbeskrivning</span><span class="sxs-lookup"><span data-stu-id="a2d9f-107">Character description</span></span></th>
<th><span data-ttu-id="a2d9f-108">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a2d9f-108">Description</span></span></th>
<th><span data-ttu-id="a2d9f-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="a2d9f-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a2d9f-110"><em>värde</em></span><span class="sxs-lookup"><span data-stu-id="a2d9f-110"><em>value</em></span></span></td>
<td><span data-ttu-id="a2d9f-111">Motsvarar värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="a2d9f-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-112">Skriv in värdet som du vill hitta.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="a2d9f-113"><strong>Smith</strong> hittar &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-114">!<em>-värde</em> (utropstecken)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="a2d9f-115">Motsvarar inte värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="a2d9f-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-116">Skriv in ett utropstecken och sedan värdet som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="a2d9f-117"><strong>!Smith</strong> hittar alla värden utom &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-118"><em>värdet Från</em>.<em>värdet Till</em> (dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="a2d9f-119">Mellan de två värdena som angavs åtskilda med dubbla punkter</span><span class="sxs-lookup"><span data-stu-id="a2d9f-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="a2d9f-120">Skriv in värdet Från, sedan två punkter och sist värdet Till.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="a2d9f-121"><strong>1..10</strong> hittar alla värden från 1 till 10.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="a2d9f-122">I ett strängfält hittar dock <strong>A..C</strong> alla värden som börjar med &quot;A&quot; och &quot;B&quot; och värden som exakt motsvarar &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="a2d9f-123">Till exempel kommer denna fråga inte att hitta &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-123">For example, this query won&#39;t find &quot;Ca&quot;.</span></span> <span data-ttu-id="a2d9f-124">Om du vill hitta alla värden från &quot;A<em>&quot; till &quot;C</em>&quot;, skriv då <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-125">..<em>värde</em> (dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="a2d9f-126">Mindre än eller lika med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-127">Skriv in de två punkterna och sedan värdet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="a2d9f-128"><strong>..1000</strong> hittar alla tal som är mindre än eller lika med 1 000, t.ex. &quot;100&quot;, &quot;999,95&quot; och &quot;1 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-129"><em>värde</em>..</span><span class="sxs-lookup"><span data-stu-id="a2d9f-129"><em>value</em>..</span></span> <span data-ttu-id="a2d9f-130">(dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-130">(double period)</span></span></td>
<td><span data-ttu-id="a2d9f-131">Större än eller lika med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-132">Skriv in värdet och sen två punkter.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="a2d9f-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="a2d9f-133"><strong>1000..</strong></span></span> <span data-ttu-id="a2d9f-134">hittar alla tal som är större än eller lika med 1 000, t.ex. &quot;1 000&quot;, &quot;1 000,01&quot; och &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-135">&gt;<em>värde</em> (tecknet för "större än")</span><span class="sxs-lookup"><span data-stu-id="a2d9f-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="a2d9f-136">Större än värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-137">Ange tecknet för "större än" (<strong>&gt;</strong>) och därefter värdet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="a2d9f-138"><strong>&gt;1 000</strong> hittar alla tal som är större än 1 000, t.ex.s &quot;1000,01&quot;, &quot;20 000&quot; och &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-139">&lt;<em>värde</em> (tecknet för "mindre än")</span><span class="sxs-lookup"><span data-stu-id="a2d9f-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="a2d9f-140">Mindere än värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-141">Skriv in tecknet för "mindre än" (<strong>&lt;</strong>) och därefter värdet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="a2d9f-142"><strong>&lt;1 000</strong> hittar alla tal, som är mindre än 1 000, t.ex. &quot;999,99&quot;, &quot;1&quot; och &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-143"><em>värde</em>\* (asterisk)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="a2d9f-144">Startar från värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="a2d9f-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-145">Skriv in startvärdet och sedan en asterisk (<strong><em></strong>).</span><span class="sxs-lookup"><span data-stu-id="a2d9f-145">Type the starting value and then an asterisk (<strong><em></strong>).</span></span></td>
<td><span data-ttu-id="a2d9f-146"><strong>S</em></strong> hittar alla strängar som börjar med &quot;S&quot; som till exempel &quot;Stockholm&quot;, &quot;Sydney&quot; och &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-146"><strong>S</em></strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-147"><em><em>värde</em> (asterisk)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-147"><em><em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="a2d9f-148">Slutar med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-149">Skriv in en asterisk och sedan slutvärdet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="a2d9f-150"><strong></em>öst</strong>  hittar alla strängar som slutar med &quot;öst&quot; som till exempel &quot;nordöst&quot; och &quot;sydöst&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-150"><strong></em>east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-151"><em><em>värde</em></em> (asterisk)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-151"><em><em>value</em></em> (asterisk)</span></span></td>
<td><span data-ttu-id="a2d9f-152">Innehåller värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="a2d9f-153">Skriv in en asterisk, sedan ett värde och slutligen en till asterisk.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="a2d9f-154"><strong><em>st</em></strong> hittar alla strängar som innehåller &quot;st&quot;, t.ex. &quot;Nordöst&quot; och &quot;Sydöst&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-154"><strong><em>th</em></strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-155">?</span><span class="sxs-lookup"><span data-stu-id="a2d9f-155">?</span></span> <span data-ttu-id="a2d9f-156">(frågetecken)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-156">(question mark)</span></span></td>
<td><span data-ttu-id="a2d9f-157">Har ett eller flera okända tecken</span><span class="sxs-lookup"><span data-stu-id="a2d9f-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="a2d9f-158">Skriv in ett frågetecken vid det okända tecknets placering i värdet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="a2d9f-159"><strong>Sm?th</strong> hittar &quot;Smith&quot; och &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-160"><em>värde</em>,<em>värde</em> (kommatecken)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="a2d9f-161">Matchar värdena som angavs åtskilda med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="a2d9f-162">Skriv in alla kriterier och skilj dem åt med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="a2d9f-163"><strong>A, D, F, G</strong> hittar exakt &quot;A&quot;, &quot;D&quot;, &quot;F&quot; och &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="a2d9f-164"><strong>10, 20, 30, 100</strong> hittar exakt &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-165">(<span class="code">SQL-sats</span>) (SQL-sats inom parentes)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="a2d9f-166">Matchar en definierad fråga</span><span class="sxs-lookup"><span data-stu-id="a2d9f-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="a2d9f-167">Skriv in en fråga som en SQL-sats inom parentes.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="a2d9f-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="a2d9f-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-169">T</span><span class="sxs-lookup"><span data-stu-id="a2d9f-169">T</span></span></td>
<td><span data-ttu-id="a2d9f-170">Dagens datum</span><span class="sxs-lookup"><span data-stu-id="a2d9f-170">Today&#39;s date</span></span></td>
<td><span data-ttu-id="a2d9f-171">Skriv in <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="a2d9f-172"><strong>T</strong> matchar dagens datum.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-172"><strong>T</strong> matches today&#39;s date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metod mellan parentes)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="a2d9f-174">Matcha värdet eller intervallet av värden som anges av parametrar för metoden <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="a2d9f-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="a2d9f-175">Skriv en <strong>SysQueryRangeUtil</strong>-metod med parametrar som specificerar värdet eller intervallet av värden.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="a2d9f-176">Klicka på <strong>Kundreskontra</strong> &gt; <strong>Fakturor</strong> &gt; <strong>Öppna kundfakturor</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-177">Tryck på Ctrl+Shift+F3 om du vill öppna sidan <strong>Förfrågan</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="a2d9f-178">På fliken <strong>Intervall</strong> klickar du på <strong>Anslutning</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-179">I fältet <strong>Tabell</strong> väljer du <strong>Öppna kundtransaktioner</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-180">I fältet <strong>Fält</strong> väljer du <strong>Förfallodatum</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-181">I fältet <strong>Kriterium</strong> anger du <strong>2(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-182">Klicka på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="a2d9f-183">Listsidan uppdateras och visar de fakturor som matchar kriteriet som du angav.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="a2d9f-184">För det här exemplet registreras specifika fakturor som förfallit under de föregående två åren.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="a2d9f-185">Se tabellen i nästa avsnittet för ytterligare information om <strong>SysQueryRangeUtil</strong>-datummetoder och flera exempel.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="a2d9f-186">Avancerade datumfrågor som använder SysQueryRangeUtil-metoder</span><span class="sxs-lookup"><span data-stu-id="a2d9f-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2d9f-187">Metod</span><span class="sxs-lookup"><span data-stu-id="a2d9f-187">Method</span></span></th>
<th><span data-ttu-id="a2d9f-188">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a2d9f-188">Description</span></span></th>
<th><span data-ttu-id="a2d9f-189">Exempel</span><span class="sxs-lookup"><span data-stu-id="a2d9f-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a2d9f-190">Dag (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="a2d9f-191">Sök efter en datumrelativ till sessionsdatumet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-191">Find a date relative to the session date.</span></span> <span data-ttu-id="a2d9f-192">Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-193"><strong>Imorgon</strong> – Ange <strong>(Dag(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-194"><strong>I dag</strong> – Ange <strong>(Dag(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-195"><strong>Igår</strong> – Ange <strong>(Dag(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="a2d9f-197">Hitta ett intervall med datumrelativ till sessionsdatumet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="a2d9f-198">Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-199"><strong>De 30 senaste dagarna</strong> – Ange <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-200"><strong>Föregående 30 dagar och framtida 30 dagar</strong> – Ange <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="a2d9f-202">Sök efter alla data efter det angivna relativa datumet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-203"><strong>Mer än 30 dagar från och med nu</strong> – Ange <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="a2d9f-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="a2d9f-205">Sök efter alla datum/tidposter efter den aktuella tiden.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-206"><strong>Alla framtida datum/tider</strong> – Ange <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="a2d9f-208">Sök efter alla data före det angivna relativa datumet.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-209"><strong>Mindre än sju dagar från och med nu</strong> – Ange <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="a2d9f-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="a2d9f-211">Sök efter alla datum/tidposter före den aktuella tiden.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-212"><strong>Alla förfallna datum/tider</strong> – Ange <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a2d9f-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="a2d9f-214">Hitta ett datumintervall baserat på månader i förhållande till den aktuella månaden.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-215"><strong>Tidigare två månader</strong> – Ange <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-216"><strong>Nästa tre månader</strong> – Ange <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a2d9f-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="a2d9f-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="a2d9f-218">Hitta ett datumintervall baserat på år i förhållande till det aktuella året.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="a2d9f-219"><strong>Nästa år</strong> – Ange <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="a2d9f-220"><strong>Föregående år</strong> – Ange <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2d9f-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






