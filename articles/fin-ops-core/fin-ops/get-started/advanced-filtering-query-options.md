---
title: Avancerad filtrerings- och frågesyntax
description: Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn matchar i den avancerade filtrerings-/sorteringsdialogen.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15805e24c46603afd34d40c5f94c1422b01cab4c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566076"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="63430-103">Avancerad filtrerings- och frågesyntax</span><span class="sxs-lookup"><span data-stu-id="63430-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63430-104">Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn **matchar** i den avancerade filtrerings-/sorteringsdialogen.</span><span class="sxs-lookup"><span data-stu-id="63430-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="63430-105">Avancerad frågesyntax</span><span class="sxs-lookup"><span data-stu-id="63430-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="63430-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="63430-106">Syntax</span></span></th>
<th><span data-ttu-id="63430-107">Teckenbeskrivning</span><span class="sxs-lookup"><span data-stu-id="63430-107">Character description</span></span></th>
<th><span data-ttu-id="63430-108">beskrivning</span><span class="sxs-lookup"><span data-stu-id="63430-108">Description</span></span></th>
<th><span data-ttu-id="63430-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="63430-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="63430-110"><em>värde</em></span><span class="sxs-lookup"><span data-stu-id="63430-110"><em>value</em></span></span></td>
<td><span data-ttu-id="63430-111">Motsvarar värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="63430-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="63430-112">Skriv in värdet som du vill hitta.</span><span class="sxs-lookup"><span data-stu-id="63430-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="63430-113"><strong>Smith</strong> hittar &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-114">!<em>-värde</em> (utropstecken)</span><span class="sxs-lookup"><span data-stu-id="63430-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="63430-115">Motsvarar inte värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="63430-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="63430-116">Skriv in ett utropstecken och sedan värdet som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="63430-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="63430-117"><strong>!Smith</strong> hittar alla värden utom &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-118"><em>värdet Från</em>.<em>värdet Till</em> (dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="63430-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="63430-119">Mellan de två värdena som angavs åtskilda med dubbla punkter</span><span class="sxs-lookup"><span data-stu-id="63430-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="63430-120">Skriv in värdet Från, sedan två punkter och sist värdet Till.</span><span class="sxs-lookup"><span data-stu-id="63430-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="63430-121"><strong>1..10</strong> hittar alla värden från 1 till 10.</span><span class="sxs-lookup"><span data-stu-id="63430-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="63430-122">I ett strängfält hittar dock <strong>A..C</strong> alla värden som börjar med &quot;A&quot; och &quot;B&quot; och värden som exakt motsvarar &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="63430-123">Till exempel kommer denna fråga inte att hitta &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="63430-124">Om du vill hitta alla värden från &quot;A<em>&quot; till &quot;C</em>&quot;, skriv då <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-125">..<em>värde</em> (dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="63430-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="63430-126">Mindre än eller lika med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="63430-127">Skriv in de två punkterna och sedan värdet.</span><span class="sxs-lookup"><span data-stu-id="63430-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="63430-128"><strong>..1000</strong> hittar alla tal som är mindre än eller lika med 1 000, t.ex. &quot;100&quot;, &quot;999,95&quot; och &quot;1 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-129"><em>värde</em>..</span><span class="sxs-lookup"><span data-stu-id="63430-129"><em>value</em>..</span></span> <span data-ttu-id="63430-130">(dubbla punkter)</span><span class="sxs-lookup"><span data-stu-id="63430-130">(double period)</span></span></td>
<td><span data-ttu-id="63430-131">Större än eller lika med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="63430-132">Skriv in värdet och sen två punkter.</span><span class="sxs-lookup"><span data-stu-id="63430-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="63430-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="63430-133"><strong>1000..</strong></span></span> <span data-ttu-id="63430-134">hittar alla tal som är större än eller lika med 1 000, t.ex. &quot;1 000&quot;, &quot;1 000,01&quot; och &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-135">&gt;<em>värde</em> (tecknet för "större än")</span><span class="sxs-lookup"><span data-stu-id="63430-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="63430-136">Större än värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="63430-137">Ange tecknet för "större än" (<strong>&gt;</strong>) och därefter värdet.</span><span class="sxs-lookup"><span data-stu-id="63430-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="63430-138"><strong>&gt;1 000</strong> hittar alla tal som är större än 1 000, t.ex.s &quot;1000,01&quot;, &quot;20 000&quot; och &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-139">&lt;<em>värde</em> (tecknet för "mindre än")</span><span class="sxs-lookup"><span data-stu-id="63430-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="63430-140">Mindere än värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="63430-141">Skriv in tecknet för "mindre än" (<strong>&lt;</strong>) och därefter värdet.</span><span class="sxs-lookup"><span data-stu-id="63430-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="63430-142"><strong>&lt;1 000</strong> hittar alla tal, som är mindre än 1 000, t.ex. &quot;999,99&quot;, &quot;1&quot; och &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-143"><em>värde</em>\* (asterisk)</span><span class="sxs-lookup"><span data-stu-id="63430-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="63430-144">Startar från värdet som angavs</span><span class="sxs-lookup"><span data-stu-id="63430-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="63430-145">Skriv in startvärdet och sedan en asterisk (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="63430-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="63430-146"><strong>S\*</strong> hittar alla strängar som börjar med &quot;S&quot;, t.ex. &quot;Stockholm&quot;, &quot;Sydney&quot; eller &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-147">\*<em>värde</em> (asterisk)</span><span class="sxs-lookup"><span data-stu-id="63430-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="63430-148">Slutar med värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="63430-149">Skriv in en asterisk och sedan slutvärdet.</span><span class="sxs-lookup"><span data-stu-id="63430-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="63430-150"><strong>\*öst</strong> hittar alla strängar som slutar med &quot;öst&quot;, t.ex. &quot;Nordöst&quot; och &quot;Sydöst&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-151">*<em>värde</em>* (asterisk)</span><span class="sxs-lookup"><span data-stu-id="63430-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="63430-152">Innehåller värdet som angavs.</span><span class="sxs-lookup"><span data-stu-id="63430-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="63430-153">Skriv in en asterisk, sedan ett värde och slutligen en till asterisk.</span><span class="sxs-lookup"><span data-stu-id="63430-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="63430-154"><strong>*st*</strong> hittar alla strängar som innehåller &quot;st&quot;, t.ex. &quot;Nordöst&quot; och &quot;Sydöst&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-155">?</span><span class="sxs-lookup"><span data-stu-id="63430-155">?</span></span> <span data-ttu-id="63430-156">(frågetecken)</span><span class="sxs-lookup"><span data-stu-id="63430-156">(question mark)</span></span></td>
<td><span data-ttu-id="63430-157">Har ett eller flera okända tecken</span><span class="sxs-lookup"><span data-stu-id="63430-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="63430-158">Skriv in ett frågetecken vid det okända tecknets placering i värdet.</span><span class="sxs-lookup"><span data-stu-id="63430-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="63430-159"><strong>Sm?th</strong> hittar &quot;Smith&quot; och &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-160"><em>värde</em>,<em>värde</em> (kommatecken)</span><span class="sxs-lookup"><span data-stu-id="63430-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="63430-161">Matchar värdena som angavs åtskilda med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="63430-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="63430-162">Skriv in alla kriterier och skilj dem åt med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="63430-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="63430-163"><strong>A, D, F, G</strong> hittar exakt &quot;A&quot;, &quot;D&quot;, &quot;F&quot; och &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="63430-164"><strong>10, 20, 30, 100</strong> hittar exakt &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="63430-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-165">"" (två dubbla citationstecken)</span><span class="sxs-lookup"><span data-stu-id="63430-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="63430-166">Matcha ett tomt värde</span><span class="sxs-lookup"><span data-stu-id="63430-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="63430-167">Skriv två dubbla citationstecken i följd för att filtrera efter tomma värden i det fältet.</span><span class="sxs-lookup"><span data-stu-id="63430-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="63430-168">Två raka dubbla citationstecken (<strong>""</strong>) hittar rader utan värde för den aktuella kolumnen.</span><span class="sxs-lookup"><span data-stu-id="63430-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-169">(<span class="code">Finance and Operations fråga</span>) (Finance and Operations fråga mellan parenteser)</span><span class="sxs-lookup"><span data-stu-id="63430-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="63430-170">Matchar en definierad fråga</span><span class="sxs-lookup"><span data-stu-id="63430-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="63430-171">Skriv en fråga som ett SQL-uttryck inom parenteser med hjälp av Finance and Operations frågespråk.</span><span class="sxs-lookup"><span data-stu-id="63430-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="63430-172"><strong><span class="code">((AccountNum SOM "US *") && (DirPartyTable.Name SOM "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="63430-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="63430-173">Exempel på syntax för ett filtervillkor för ett fält från rotdatakällan och ett fält från en annan datakälla (för sidan Alla kunder)</span><span class="sxs-lookup"><span data-stu-id="63430-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-174">V</span><span class="sxs-lookup"><span data-stu-id="63430-174">T</span></span></td>
<td><span data-ttu-id="63430-175">Dagens datum</span><span class="sxs-lookup"><span data-stu-id="63430-175">Today's date</span></span></td>
<td><span data-ttu-id="63430-176">Skriv in <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="63430-177"><strong>T</strong> matchar dagens datum.</span><span class="sxs-lookup"><span data-stu-id="63430-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="63430-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metod mellan parentes)</span><span class="sxs-lookup"><span data-stu-id="63430-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="63430-179">Matcha värdet eller intervallet av värden som anges av parametrar för metoden <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="63430-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="63430-180">Skriv en <strong>SysQueryRangeUtil</strong>-metod med parametrar som specificerar värdet eller intervallet av värden.</span><span class="sxs-lookup"><span data-stu-id="63430-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="63430-181">Klicka på <strong>Kundreskontra</strong> &gt; <strong>Fakturor</strong> &gt; <strong>Öppna kundfakturor</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="63430-182">Tryck på Ctrl+Shift+F3 om du vill öppna sidan <strong>Förfrågan</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="63430-183">På fliken <strong>Intervall</strong> klickar du på <strong>Anslutning</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="63430-184">I fältet <strong>Tabell</strong> väljer du <strong>Öppna kundtransaktioner</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="63430-185">I fältet <strong>Fält</strong> väljer du <strong>Förfallodatum</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="63430-186">I fältet <strong>Kriterium</strong> anger du <strong>2(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="63430-187">Klicka på <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="63430-188">Listsidan uppdateras och visar de fakturor som matchar kriteriet som du angav.</span><span class="sxs-lookup"><span data-stu-id="63430-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="63430-189">För det här exemplet registreras specifika fakturor som förfallit under de föregående två åren.</span><span class="sxs-lookup"><span data-stu-id="63430-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="63430-190">Se tabellen i nästa avsnittet för ytterligare information om <strong>SysQueryRangeUtil</strong>-datummetoder och flera exempel.</span><span class="sxs-lookup"><span data-stu-id="63430-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="63430-191">Avancerade datumfrågor som använder SysQueryRangeUtil-metoder</span><span class="sxs-lookup"><span data-stu-id="63430-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="63430-192">Metod</span><span class="sxs-lookup"><span data-stu-id="63430-192">Method</span></span></th>
<th><span data-ttu-id="63430-193">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="63430-193">Description</span></span></th>
<th><span data-ttu-id="63430-194">Exempel</span><span class="sxs-lookup"><span data-stu-id="63430-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="63430-195">Dag (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="63430-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="63430-196">Sök efter en datumrelativ till sessionsdatumet.</span><span class="sxs-lookup"><span data-stu-id="63430-196">Find a date relative to the session date.</span></span> <span data-ttu-id="63430-197">Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="63430-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-198"><strong>Imorgon</strong> – Ange <strong>(Dag(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="63430-199"><strong>I dag</strong> – Ange <strong>(Dag(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="63430-200"><strong>Igår</strong> – Ange <strong>(Dag(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="63430-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="63430-202">Hitta ett intervall med datumrelativ till sessionsdatumet.</span><span class="sxs-lookup"><span data-stu-id="63430-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="63430-203">Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="63430-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-204"><strong>De 30 senaste dagarna</strong> – Ange <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="63430-205"><strong>Föregående 30 dagar och framtida 30 dagar</strong> – Ange <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="63430-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="63430-207">Sök efter alla data efter det angivna relativa datumet.</span><span class="sxs-lookup"><span data-stu-id="63430-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-208"><strong>Mer än 30 dagar från och med nu</strong> – Ange <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="63430-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="63430-210">Sök efter alla datum/tidposter efter den aktuella tiden.</span><span class="sxs-lookup"><span data-stu-id="63430-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-211"><strong>Alla framtida datum/tider</strong> – Ange <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="63430-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="63430-213">Sök efter alla data före det angivna relativa datumet.</span><span class="sxs-lookup"><span data-stu-id="63430-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-214"><strong>Mindre än sju dagar från och med nu</strong> – Ange <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="63430-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="63430-216">Sök efter alla datum/tidposter före den aktuella tiden.</span><span class="sxs-lookup"><span data-stu-id="63430-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-217"><strong>Alla förfallna datum/tider</strong> – Ange <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="63430-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="63430-219">Hitta ett datumintervall baserat på månader i förhållande till den aktuella månaden.</span><span class="sxs-lookup"><span data-stu-id="63430-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-220"><strong>Tidigare två månader</strong> – Ange <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="63430-221"><strong>Nästa tre månader</strong> – Ange <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="63430-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="63430-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="63430-223">Hitta ett datumintervall baserat på år i förhållande till det aktuella året.</span><span class="sxs-lookup"><span data-stu-id="63430-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="63430-224"><strong>Nästa år</strong> – Ange <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="63430-225"><strong>Föregående år</strong> – Ange <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="63430-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]