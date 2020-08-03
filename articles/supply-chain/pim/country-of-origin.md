---
title: Ursprungsland
description: Många organisationer utfärdar certifikat till sina leverantörer för att säkerställa att produkterna uppfyller specifika certifieringsstandarder. Dessa certifikat beror ofta på ursprungslandet. Det här avsnittet innehåller information om funktionens ursprungsland där du kan koppla en produkt till dess ursprungsland och hålla reda på produktens certifiering.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fd234c57bf9893e9b8bcfa5ada7439a642f7a288
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596278"
---
# <a name="country-of-origin"></a><span data-ttu-id="4e4e2-105">Ursprungsland</span><span class="sxs-lookup"><span data-stu-id="4e4e2-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e4e2-106">Många organisationer utfärdar certifikat till sina leverantörer för att säkerställa att produkterna uppfyller specifika certifieringsstandarder.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="4e4e2-107">Dessa certifikat beror ofta på ursprungslandet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="4e4e2-108">Funktionens ursprungsland där du kan koppla en produkt till dess ursprungsland och hålla reda på produktens certifiering.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="4e4e2-109">Konfigurera käll- och målländer</span><span class="sxs-lookup"><span data-stu-id="4e4e2-109">Configure source and destination countries</span></span>

<span data-ttu-id="4e4e2-110">Innan du utfärdar ett certifikat för en produkt måste du länka produkten till mållandet och ursprungslandet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-110">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="4e4e2-111">Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets regler**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-111">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="4e4e2-112">Välj en befintlig landsinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny landsinställning.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-112">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="4e4e2-113">Ange följande värden för det valda eller nya landet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-113">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="4e4e2-114">Fält</span><span class="sxs-lookup"><span data-stu-id="4e4e2-114">Field</span></span> | <span data-ttu-id="4e4e2-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4e4e2-115">Description</span></span> |
    |---|---|
    | <span data-ttu-id="4e4e2-116">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="4e4e2-116">Item number</span></span> | <span data-ttu-id="4e4e2-117">Välj produktens artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-117">Select the item number of the product.</span></span> |
    | <span data-ttu-id="4e4e2-118">Destinationsland</span><span class="sxs-lookup"><span data-stu-id="4e4e2-118">Destination country</span></span> | <span data-ttu-id="4e4e2-119">Välj det land som du ska skicka produkten till.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-119">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="4e4e2-120">Ursprungsland</span><span class="sxs-lookup"><span data-stu-id="4e4e2-120">Origin country</span></span> | <span data-ttu-id="4e4e2-121">Välj det land som du ska skicka produkten från.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-121">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="4e4e2-122">Syftet med den här inställningen är att hjälpa dig att generera en strukturlista (BOM) där du kan inkludera ursprungslandet för varje del som käll- och målländer har angetts för.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-122">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="4e4e2-123">I den här rapporten får du hjälp att få en helhetsbild av var dina delar kommer och var de kommer.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-123">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="4e4e2-124">Hålla reda på leverantörscertifikat</span><span class="sxs-lookup"><span data-stu-id="4e4e2-124">Keep track of vendor certificates</span></span>

<span data-ttu-id="4e4e2-125">Du kan använda sidan **leverantörscertifikat för ursprungslandet** för att hålla reda på de certifikat som du skickar till leverantörerna.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-125">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="4e4e2-126">Du måste bestämma vilka certifikat som du ska utfärda och hur de ska rapporteras till kunderna.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-126">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="4e4e2-127">Med hjälp av den här funktionen kan du hålla reda på dina certifikat.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-127">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="4e4e2-128">Du kan också välja om de relevanta certifikatnumren visas på fakturor, följesedlar och/eller orderbekräftelser.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-128">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="4e4e2-129">Så här ställs certifikatinformation in.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-129">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="4e4e2-130">Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets leverantörscertifikat**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-130">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="4e4e2-131">Välj en befintlig certifikatinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny certifikatinställning.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-131">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="4e4e2-132">Ange följande inställningar för det valda eller nya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-132">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="4e4e2-133">Fält</span><span class="sxs-lookup"><span data-stu-id="4e4e2-133">Field</span></span> | <span data-ttu-id="4e4e2-134">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4e4e2-134">Description</span></span> |
    |---|---|
    | <span data-ttu-id="4e4e2-135">Leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="4e4e2-135">Vendor account</span></span> | <span data-ttu-id="4e4e2-136">Välj den leverantör som du har utfärdat certifikatet till.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-136">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="4e4e2-137">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="4e4e2-137">Item number</span></span> | <span data-ttu-id="4e4e2-138">Välj det objekt leverantör som du har utfärdat certifikatet för.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-138">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="4e4e2-139">Land/region</span><span class="sxs-lookup"><span data-stu-id="4e4e2-139">Country/region</span></span> | <span data-ttu-id="4e4e2-140">Destinationsland eller -region där du måste använda det här certifikatet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-140">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="4e4e2-141">Certifikatnummer</span><span class="sxs-lookup"><span data-stu-id="4e4e2-141">Certificate number</span></span> | <span data-ttu-id="4e4e2-142">Ange ID-numret för det certifikat som du har utfärdat.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-142">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="4e4e2-143">Giltighet</span><span class="sxs-lookup"><span data-stu-id="4e4e2-143">Effective</span></span> | <span data-ttu-id="4e4e2-144">Välj det första datumet när det aktuella certifikatet är giltigt.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-144">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="4e4e2-145">Förfallotid</span><span class="sxs-lookup"><span data-stu-id="4e4e2-145">Expiration</span></span> | <span data-ttu-id="4e4e2-146">Välj det sista datumet när det aktuella certifikatet är giltigt.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-146">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="4e4e2-147">Skriv ut på faktura</span><span class="sxs-lookup"><span data-stu-id="4e4e2-147">Print on invoice</span></span> | <span data-ttu-id="4e4e2-148">Markera den här kryssrutan om du vill skriva ut certifikatnumret på fakturor som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-148">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="4e4e2-149">Skriv ut på följesedel</span><span class="sxs-lookup"><span data-stu-id="4e4e2-149">Print on packing slip</span></span> | <span data-ttu-id="4e4e2-150">Markera den här kryssrutan om du vill skriva ut certifikatnumret på följesedel som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-150">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="4e4e2-151">Skriv ut på försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="4e4e2-151">Print on sales order</span></span> | <span data-ttu-id="4e4e2-152">Markera den här kryssrutan om du vill skriva ut certifikatnumret på försäljningsorder som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-152">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="4e4e2-153">Inkludera ursprungslandet i strukturlisterapporter</span><span class="sxs-lookup"><span data-stu-id="4e4e2-153">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="4e4e2-154">När du genererar en strukturlisterapport kan du inkludera ursprungslandet för varje del som du har angett käll- och målländer för sidan **Regler för ursprungsland**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-154">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="4e4e2-155">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-155">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="4e4e2-156">Välj eller skapa en produkt för att öppna dess sida **Information om frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-156">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="4e4e2-157">I Åtgärdsfönstret, på fliken **Konstruera**, i gruppen **Strukturlista**, markerar du **Designer**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-157">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="4e4e2-158">På den sida som visas väljer du **Strukturlista \> Skriv ut** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-158">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="4e4e2-159">I dialogrutan **strukturlisterader** ange fältet **målland** till det målland som du vill visa i rapporten.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-159">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="4e4e2-160">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-160">Select **OK**.</span></span>

<span data-ttu-id="4e4e2-161">En rapport som visar information om ursprungslandet för varje del genereras och visas.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-161">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="4e4e2-162">Här följer ett exempel på rapporten.</span><span class="sxs-lookup"><span data-stu-id="4e4e2-162">Here is an example of the report.</span></span>

<span data-ttu-id="4e4e2-163">![Ursprungsland, rapport](media/country-of-origin-report.png "Ursprungsland, rapport")</span><span class="sxs-lookup"><span data-stu-id="4e4e2-163">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
