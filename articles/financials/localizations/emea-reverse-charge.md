---
title: Omvänd moms
description: Det här avsnittet beskriver hur du ställer in omvänd moms (VAT) för europeiska länder och Saudiarabien.
author: epodkolz
manager: AnnBe
ms.date: 04/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 26f7f3f11408cac387c58a5345b566ac50ed426f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "371859"
---
# <a name="reverse-charge-vat"></a><span data-ttu-id="254fd-103">Omvänd moms</span><span class="sxs-lookup"><span data-stu-id="254fd-103">Reverse charge VAT</span></span>


[!include [banner](../includes/banner.md)]


<span data-ttu-id="254fd-104">Det här avsnittet beskriver en allmän metod för att ställa in omvänd moms (VAT) för Saudiarabien och europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="254fd-104">This topic describes a generic approach for setting up reverse charge value-added tax (VAT) for Saudi Arabia and European countries.</span></span>

<span data-ttu-id="254fd-105">Omvänd moms är ett skatteschema som har ansvaret för redovisning och rapportering av moms från säljaren till köparen av varor eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="254fd-105">Reverse Charge is a tax schema that moves the responsibility for the accounting and reporting of VAT from the seller to the buyer of goods and/or services.</span></span> <span data-ttu-id="254fd-106">Därför rapporterar mottagaren av varor eller tjänster både utgående moms (i rollen som säljare) och ingående moms (i rollen som inköpare) i deras momsrapport.</span><span class="sxs-lookup"><span data-stu-id="254fd-106">Therefore, recipients of goods and/or services report both the output VAT (in the role of a seller) and the input VAT (in the role of a purchaser) on their VAT statement.</span></span>

<span data-ttu-id="254fd-107">I vissa länder används omvänt momsschema endast för vissa varor eller tjänster och det finns ytterligare villkor eller tröskelvärden för försäljningsbelopp.</span><span class="sxs-lookup"><span data-stu-id="254fd-107">In some countries or regions, the Reverse Charge schema is implemented only for some goods and/or services, and there are additional conditions or thresholds on sales amounts.</span></span> <span data-ttu-id="254fd-108">I andra länder eller region beror ansvaret för momsbetalning på status för leverantören och köparen.</span><span class="sxs-lookup"><span data-stu-id="254fd-108">In other countries or regions, the responsibility for VAT payment depends on the status of the supplier and the buyer.</span></span> <span data-ttu-id="254fd-109">Om köparen är skyldig att betala moms anges detta klart på fakturan som leverantören utfärdar.</span><span class="sxs-lookup"><span data-stu-id="254fd-109">If the buyer is liable to pay VAT, this fact must be clearly indicated on the invoice that the supplier issues.</span></span> <span data-ttu-id="254fd-110">Fakturan måste t.ex. innehålla orden ”omvänd moms” och ange vilka befattningar som är under omvänt momsschema.</span><span class="sxs-lookup"><span data-stu-id="254fd-110">For example, the invoice must include the words "Reverse charge" and must indicate which positions are under the Reverse Charge schema.</span></span> 

<span data-ttu-id="254fd-111">Du måste utföra följande inställningar om du vill använda omvänd moms.</span><span class="sxs-lookup"><span data-stu-id="254fd-111">To apply the reverse charge, you must complete the following setup.</span></span>

## <a name="set-up-sales-tax-codes"></a><span data-ttu-id="254fd-112">Ställ in momskoder</span><span class="sxs-lookup"><span data-stu-id="254fd-112">Set up sales tax codes</span></span>
<span data-ttu-id="254fd-113">Vi rekommenderar att du använder olika momskoder för försäljning och inköp.</span><span class="sxs-lookup"><span data-stu-id="254fd-113">We recommend that you use separate sales tax codes for sales operations and purchase operations.</span></span>

<table>
<body>
<tr>
<td><span data-ttu-id="254fd-114"><strong>Momskoder för försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="254fd-114"><strong>Sales tax code for sales</strong></span></span></td>
<td><span data-ttu-id="254fd-115">Skapa en momskod för försäljningsoperationer med omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momskoder</strong>).</span><span class="sxs-lookup"><span data-stu-id="254fd-115">Create a sales tax code for reverse charge sales operations (<strong>Tax</strong> &gt; <strong>Indirect taxes</strong> &gt; <strong>Sales tax</strong> &gt; <strong>Sales tax codes</strong>).</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="254fd-116"><strong>Momskoder för inköp</strong></span><span class="sxs-lookup"><span data-stu-id="254fd-116"><strong>Sales tax code for purchases</strong></span></span></td>
<td><p><span data-ttu-id="254fd-117">Skapa positiva och negativa momskoder för omvänd moms för inköp (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momskoder</strong>).</span><span class="sxs-lookup"><span data-stu-id="254fd-117">Create positive and negative sales tax codes for the reverse charge VAT for purchases (<strong>Tax</strong> &gt; <strong>Indirect taxes</strong> &gt; <strong>Sales tax</strong> &gt; <strong>Sales tax codes</strong>).</span></span></p>
<ol>
<li><span data-ttu-id="254fd-118">Skapa en momskod som har ett positivt värde.</span><span class="sxs-lookup"><span data-stu-id="254fd-118">Create a sales tax code that has a positive value.</span></span></li>
<li><span data-ttu-id="254fd-119">Skapa en momskod som har ett negativt värde.</span><span class="sxs-lookup"><span data-stu-id="254fd-119">Create a sales tax code that has a negative value.</span></span> <span data-ttu-id="254fd-120">Ange alternativet <strong>Tillåt negativ momsprocent</strong> till <strong>Ja</strong>.</span><span class="sxs-lookup"><span data-stu-id="254fd-120">Set the <strong>Allow negative sales tax percentage</strong> option to <strong>Yes</strong>.</span></span>
<span data-ttu-id="254fd-121">Den måste tilldela denna negativa momskod till en artikelmomsgrupp, och därefter tilldelar du artikelmomsgruppen till de artiklar som omvänd moms tillämpas för.</span><span class="sxs-lookup"><span data-stu-id="254fd-121">You must assign this negative sales tax code to an item sales tax group and then assign that item sales tax group to the items that are subject to the reverse charge VAT.</span></span></li>
</ol>
<p><span data-ttu-id="254fd-122">Mer information om &quot;Ange momsgrupper och artikelmomsgrupper&quot; finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="254fd-122">For more information, see the next section, &quot;Set up sales tax groups and item sales tax groups.&quot;</span></span></p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="254fd-123">Ställ in momsgrupper och artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="254fd-123">Set up sales tax groups and item sales tax groups</span></span>
<span data-ttu-id="254fd-124">Vi rekommenderar att du använder olika momsgrupper för försäljning och inköp.</span><span class="sxs-lookup"><span data-stu-id="254fd-124">We recommend that you use separate sales tax groups for sales operations and purchase operations.</span></span>

<table>
<tr>
<td><span data-ttu-id="254fd-125"><strong>Momsgrupper för försäljning</strong></span><span class="sxs-lookup"><span data-stu-id="254fd-125"><strong>Sales tax groups for sales</strong></span></span></td>
<td><span data-ttu-id="254fd-126">Skapa en momsgrupp för försäljningsoperationer som har omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momsgrupper</strong>).</span><span class="sxs-lookup"><span data-stu-id="254fd-126">Create a sales tax group for sales operations that have the reverse charge (<strong>Tax</strong> &gt; <strong>Indirect taxes</strong> &gt; <strong>Sales tax</strong> &gt; <strong>Sales tax groups</strong>).</span></span> <span data-ttu-id="254fd-127">På fliken <strong>inställningar</strong>, inkludera momskoden för omvänd moms i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="254fd-127">On the <strong>Setup</strong> tab, include the sales tax code for the reverse charge in this group.</span></span> <span data-ttu-id="254fd-128">Markera kryssrutorna <strong>undanta</strong> och <strong>omvänd moms</strong> för momskoden.</span><span class="sxs-lookup"><span data-stu-id="254fd-128">Select the <strong>Exempt</strong> and <strong>Reverse charge</strong> check boxes for the sales tax code.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="254fd-129"><strong>Momsgrupper för inköp</strong></span><span class="sxs-lookup"><span data-stu-id="254fd-129"><strong>Sales tax groups for purchases</strong></span></span></td>
<td><span data-ttu-id="254fd-130">Skapa en momsgrupp för inköpsoperationer som har omvänd moms (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Momsgrupper</strong>).</span><span class="sxs-lookup"><span data-stu-id="254fd-130">Create a sales tax group for purchase operations that have the reverse charge (<strong>Tax</strong> &gt; <strong>Indirect taxes</strong> &gt; <strong>Sales tax</strong> &gt; <strong>Sales tax groups</strong>).</span></span> <span data-ttu-id="254fd-131">På fliken <strong>inställningar</strong>, inkluderar du både positiva och negativa momskoder i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="254fd-131">On the <strong>Setup</strong> tab, include both positive and negative sales tax codes in this group.</span></span> <span data-ttu-id="254fd-132">Markera kryssrutan <strong>omvänd moms</strong> för momskoden som har ett negativt värde.</span><span class="sxs-lookup"><span data-stu-id="254fd-132">Select the <strong>Reverse charge</strong> check box for the sales tax code that has a negative value.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="254fd-133"><strong>Artikelmomsgrupper</strong></span><span class="sxs-lookup"><span data-stu-id="254fd-133"><strong>Item sales tax groups</strong></span></span></td>
<td><span data-ttu-id="254fd-134">Skapa eller uppdatera artikelmomsgrupp med momskoder som har ett negativt värde (<strong>Skatt</strong> &gt; <strong>Indirekta skatter</strong> &gt; <strong>Moms</strong> &gt; <strong>Artikelmomsgrupper</strong>).</span><span class="sxs-lookup"><span data-stu-id="254fd-134">Create or update the item sales tax group with the sales tax code that has a negative value (<strong>Tax</strong> &gt; <strong>Indirect taxes</strong> &gt; <strong>Sales tax</strong> &gt; <strong>Item sales tax groups</strong>).</span></span> <span data-ttu-id="254fd-135">Du måste tilldela standardartikelmomsgruppen till produkterna och kategoriera som är föremål för omvänd moms.</span><span class="sxs-lookup"><span data-stu-id="254fd-135">You must assign the default item sales tax group to the products and categories that are subject to the reverse charge.</span></span></td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a><span data-ttu-id="254fd-136">Ställ in information för omvända momsgrupper</span><span class="sxs-lookup"><span data-stu-id="254fd-136">Set up reverse charge groups</span></span>
<span data-ttu-id="254fd-137">På sidan omvänd momsartikelgrupper **Artikelgrupper för återfört tillägg** (**Moms** &gt; **Inställningar** &gt; **Moms** &gt; **Artikelgrupper för återfört tillägg**), kan du definiera grupper av produkter eller tjänster, eller enskilda produkter eller tjänster som omvänd moms kan tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="254fd-137">On the **Reverse charge item groups** page (**Tax** &gt; **Setup** &gt; **Sales tax** &gt; **Reverse charge item groups**), you can define groups of products or services, or individual products or services, that the reverse charge can be applied to.</span></span> <span data-ttu-id="254fd-138">Definiera listan med artiklar, artikelgrupper och kategorier för försäljning och inköp för varje artikelgrupp för omvänd moms.</span><span class="sxs-lookup"><span data-stu-id="254fd-138">For each reverse charge item group, define the list of items, item groups, and categories for sales and/or purchases.</span></span>

## <a name="set-up-reverse-charge-rules"></a><span data-ttu-id="254fd-139">Ställ in regler för omvänd moms</span><span class="sxs-lookup"><span data-stu-id="254fd-139">Set up reverse charge rules</span></span>
<span data-ttu-id="254fd-140">På sidan **Regler för återfört tillägg** (**Skatt** &gt; **Inställningar** &gt; **Moms** &gt; **Regler för återfört tillägg**), kan du definiera tillämpningsreglerna för inköp och försäljning.</span><span class="sxs-lookup"><span data-stu-id="254fd-140">On the **Reverse charge rules** page (**Tax** &gt; **Setup** &gt; **Sales tax** &gt; **Reverse charge rules**), you can define the applicability rules for purchase and sales purposes.</span></span> <span data-ttu-id="254fd-141">Du kan konfigurera en uppställning med regler för omvänd moms.</span><span class="sxs-lookup"><span data-stu-id="254fd-141">You can configure a set of reverse charge applicability rules.</span></span> <span data-ttu-id="254fd-142">För varje regel anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="254fd-142">For each rule, set the following fields:</span></span>

- <span data-ttu-id="254fd-143">**Dokumenttyp** – Välj **inköpsorder**, **leverantörsfakturajournal**, **försäljningsorder**, **fritextfaktura**, **Kundfakturajournal**, och/eller **leverantörsfakturan**.</span><span class="sxs-lookup"><span data-stu-id="254fd-143">**Document type** – Select **Purchase order**, **Vendor invoice journal**, **Sales order**, **Free text invoice**, **Customer invoice journal**, and/or **Vendor invoice**.</span></span>
- <span data-ttu-id="254fd-144">**Partnerns land/regions-typ** – Välj **lokal**, **EU**, eller **utländsk**.</span><span class="sxs-lookup"><span data-stu-id="254fd-144">**Country/region type of the partner** – Select **Domestic**, **EU**, or **Foreign**.</span></span> <span data-ttu-id="254fd-145">Alternativt om regeln kan kopplas till alla handelspartner oavsett land eller region för adressen kan du välja **alla**.</span><span class="sxs-lookup"><span data-stu-id="254fd-145">Alternatively, if the rule can be applied to all trade partners, regardless of the country or region of their address, select **All**.</span></span>
- <span data-ttu-id="254fd-146">**Lokal leveransadress** – Markera den här kryssrutan om du vill använda regeln för leveranser inom samma land eller region.</span><span class="sxs-lookup"><span data-stu-id="254fd-146">**Domestic delivery address** – Select this check box to apply the rule to deliveries within the same country or region.</span></span> <span data-ttu-id="254fd-147">Den här kryssrutan kan inte väljas för dokumenttyperna **leverantörsfakturajournal** och **Kundfakturajournal**.</span><span class="sxs-lookup"><span data-stu-id="254fd-147">This check box can't be selected for the **Vendor invoice journal** and **Customer invoice journal** document types.</span></span>
- <span data-ttu-id="254fd-148">**Artikelgrupp för omvänd moms** – Välj den grupp som regeln kan tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="254fd-148">**Reverse charge item group** – Select the group that the rule can be applied to.</span></span>
- <span data-ttu-id="254fd-149">**Tröskelbelopp** – används endast i schemat för omvänd moms till en faktura om värdet på artiklarna eller tjänsterna som ingår i artikelgruppen för omvänd moms överskrider den gräns som du anger här.</span><span class="sxs-lookup"><span data-stu-id="254fd-149">**Threshold amount** – The Reverse Charge schema is applied to an invoice only if the value of items and/or services that are included in the reverse charge item group exceeds the limit that you specify here.</span></span>

<span data-ttu-id="254fd-150">Du kan även använda fälten **giltighetsdatum** och **förfallodatum** för att anger perioden då regeln ska gälla.</span><span class="sxs-lookup"><span data-stu-id="254fd-150">You can also use the **Effective date** and **Expiration date** fields to define the period when the rule is effective.</span></span>

<span data-ttu-id="254fd-151">Du kan också ange om ett meddelande visas och dokumentraden uppdateras med momsgrupp för omvänd moms om villkoret för den dokumentraden uppfylls.</span><span class="sxs-lookup"><span data-stu-id="254fd-151">Additionally, you can specify whether a notification appears and the document line is updated with the default reverse charge sales tax group if the condition for that document line is met.</span></span> <span data-ttu-id="254fd-152">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="254fd-152">The following options are available:</span></span>

- <span data-ttu-id="254fd-153">**Ingen** – dokumentraden uppdateras inte.</span><span class="sxs-lookup"><span data-stu-id="254fd-153">**None** – The document line isn't updated.</span></span>
- <span data-ttu-id="254fd-154">**Fråga** – ett meddelande visas som bekräftar att omvänd moms kan användas.</span><span class="sxs-lookup"><span data-stu-id="254fd-154">**Prompt** – A notification appears to confirm that the reverse charge can be applied.</span></span>
- <span data-ttu-id="254fd-155">**Ange** – dokumentraden uppdateras utan meddelande.</span><span class="sxs-lookup"><span data-stu-id="254fd-155">**Set** – The document line is updated without additional notification.</span></span>

## <a name="set-up-default-parameters"></a><span data-ttu-id="254fd-156">Ställ in standardparametrar</span><span class="sxs-lookup"><span data-stu-id="254fd-156">Set up default parameters</span></span>
<span data-ttu-id="254fd-157">Om du vill aktivera funktionen för återföring av moms på sidan **allmänna redovisningsparametrar** på fliken **omvänd moms** anger du alternativet **aktivera omvänd moms** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="254fd-157">To enable the functionality for reverse charge VAT, on the **General ledger parameters** page, on the **Reverse charge** tab, set the **Enable reverse charge** option to **Yes**.</span></span> <span data-ttu-id="254fd-158">I fälten **Momsgrupp för inköpsorder** och **Momsgrupp för försäljningsorder** väljer du standardmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="254fd-158">In the **Purchase order sales tax group** and **Sales order tax group** fields, select the default sales tax groups.</span></span> <span data-ttu-id="254fd-159">När villkoren för omvänd moms uppfylls kommer försäljnings- eller inköpsordern att uppdateras med de här momsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="254fd-159">When a reverse charge applicability condition is met, the sales or purchase order line is updated with these sales tax groups.</span></span>

## <a name="reverse-charge-on-a-sales-invoice"></a><span data-ttu-id="254fd-160">Omvänd moms på en försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="254fd-160">Reverse charge on a sales invoice</span></span>
<span data-ttu-id="254fd-161">För försäljningen under schema för omvänd moms debiterar inte säljaren moms.</span><span class="sxs-lookup"><span data-stu-id="254fd-161">For sales under the Reverse Charge schema, the seller doesn't charge VAT.</span></span> <span data-ttu-id="254fd-162">Istället indikerar fakturan både artiklarna för vilka momsen ska återföras och det totala beloppet för den återförda momsen noteras på fakturan.</span><span class="sxs-lookup"><span data-stu-id="254fd-162">Instead, the invoice indicates both the items that are subject to the reverse charge VAT and the total amount of the reverse charge VAT.</span></span>

<span data-ttu-id="254fd-163">När en försäljningsfaktura bokförs med omvänd momstransaktion har kryssrutorna **Momsskuld** momsriktning och nollmom och **omvänd moms** markerats.</span><span class="sxs-lookup"><span data-stu-id="254fd-163">When a sales invoice that has the reverse charge is posted, the sales tax transactions have the **Sales tax payable** tax direction and zero sales tax, and the **Reverse charge** check box is selected.</span></span>

## <a name="reverse-charge-on-a-purchase-invoice"></a><span data-ttu-id="254fd-164">Omvänd moms på en inköpsfaktura</span><span class="sxs-lookup"><span data-stu-id="254fd-164">Reverse charge on a purchase invoice</span></span>
<span data-ttu-id="254fd-165">För inköpare under schemat omvänd moms agerar inköparen som tar emot fakturan som har omvänd moms som en köpare och säljare för redovisningsändamål.</span><span class="sxs-lookup"><span data-stu-id="254fd-165">For purchases under the Reverse Charge schema, the purchaser who receives the invoice that has the reverse charge acts as a buyer and a seller for VAT accounting purposes.</span></span>

<span data-ttu-id="254fd-166">När en inköpsfaktura med omvänd moms bokförs, skapas två momstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="254fd-166">When a purchase invoice that has the reverse charge is posted, two sales tax transactions are created.</span></span> <span data-ttu-id="254fd-167">En transaktion har skatteriktningen **Momsfordran**.</span><span class="sxs-lookup"><span data-stu-id="254fd-167">One transaction has the **Sales tax receivable** tax direction.</span></span> <span data-ttu-id="254fd-168">Den andra transaktionen har skatteriktningen **Momsskuld** och kryssrutan **omvänd moms** är markerad.</span><span class="sxs-lookup"><span data-stu-id="254fd-168">The other transaction has the **Sales tax payable** tax direction, and the **Reverse charge** check box is selected.</span></span>

<span data-ttu-id="254fd-169">I följande skärmbild har en transaktion riktningen **Momsfordran** och den andra transaktionen har riktningen **Momsskuld**.</span><span class="sxs-lookup"><span data-stu-id="254fd-169">In the following screenshot, one transaction has the **Sales tax receivable** direction, and the other transaction has the **Sales tax payable** direction.</span></span> 

![Bokförd moms](media/apac-sau-posted-sales-tax.png)
