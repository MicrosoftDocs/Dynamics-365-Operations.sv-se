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
ms.openlocfilehash: d0d93a02817bab8e188818862c1bb7f84b498fc1
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802807"
---
# <a name="country-of-origin"></a><span data-ttu-id="79f7a-105">Ursprungsland</span><span class="sxs-lookup"><span data-stu-id="79f7a-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="79f7a-106">Många organisationer utfärdar certifikat till sina leverantörer för att säkerställa att produkterna uppfyller specifika certifieringsstandarder.</span><span class="sxs-lookup"><span data-stu-id="79f7a-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="79f7a-107">Dessa certifikat beror ofta på ursprungslandet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="79f7a-108">Funktionens ursprungsland där du kan koppla en produkt till dess ursprungsland och hålla reda på produktens certifiering.</span><span class="sxs-lookup"><span data-stu-id="79f7a-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="79f7a-109">Aktivera funktionen för ursprungsland</span><span class="sxs-lookup"><span data-stu-id="79f7a-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="79f7a-110">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="79f7a-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="79f7a-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="79f7a-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="79f7a-112">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="79f7a-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="79f7a-113">**Modul:** *Produktinformationshantering*</span><span class="sxs-lookup"><span data-stu-id="79f7a-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="79f7a-114">**Funktionsnamn:** *funktionen hantering av ursprungsland*</span><span class="sxs-lookup"><span data-stu-id="79f7a-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="79f7a-115">Konfigurera käll- och målländer</span><span class="sxs-lookup"><span data-stu-id="79f7a-115">Configure source and destination countries</span></span>

<span data-ttu-id="79f7a-116">Innan du utfärdar ett certifikat för en produkt måste du länka produkten till mållandet och ursprungslandet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="79f7a-117">Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets regler**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="79f7a-118">Välj en befintlig landsinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny landsinställning.</span><span class="sxs-lookup"><span data-stu-id="79f7a-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="79f7a-119">Ange följande värden för det valda eller nya landet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="79f7a-120">Fält</span><span class="sxs-lookup"><span data-stu-id="79f7a-120">Field</span></span> | <span data-ttu-id="79f7a-121">beskrivning</span><span class="sxs-lookup"><span data-stu-id="79f7a-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="79f7a-122">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="79f7a-122">Item number</span></span> | <span data-ttu-id="79f7a-123">Välj produktens artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="79f7a-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="79f7a-124">Destinationsland</span><span class="sxs-lookup"><span data-stu-id="79f7a-124">Destination country</span></span> | <span data-ttu-id="79f7a-125">Välj det land som du ska skicka produkten till.</span><span class="sxs-lookup"><span data-stu-id="79f7a-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="79f7a-126">Ursprungsland</span><span class="sxs-lookup"><span data-stu-id="79f7a-126">Origin country</span></span> | <span data-ttu-id="79f7a-127">Välj det land som du ska skicka produkten från.</span><span class="sxs-lookup"><span data-stu-id="79f7a-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="79f7a-128">Syftet med den här inställningen är att hjälpa dig att generera en strukturlista (BOM) där du kan inkludera ursprungslandet för varje del som käll- och målländer har angetts för.</span><span class="sxs-lookup"><span data-stu-id="79f7a-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="79f7a-129">I den här rapporten får du hjälp att få en helhetsbild av var dina delar kommer och var de kommer.</span><span class="sxs-lookup"><span data-stu-id="79f7a-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="79f7a-130">Hålla reda på leverantörscertifikat</span><span class="sxs-lookup"><span data-stu-id="79f7a-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="79f7a-131">Du kan använda sidan **leverantörscertifikat för ursprungslandet** för att hålla reda på de certifikat som du skickar till leverantörerna.</span><span class="sxs-lookup"><span data-stu-id="79f7a-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="79f7a-132">Du måste bestämma vilka certifikat som du ska utfärda och hur de ska rapporteras till kunderna.</span><span class="sxs-lookup"><span data-stu-id="79f7a-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="79f7a-133">Med hjälp av den här funktionen kan du hålla reda på dina certifikat.</span><span class="sxs-lookup"><span data-stu-id="79f7a-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="79f7a-134">Du kan också välja om de relevanta certifikatnumren visas på fakturor, följesedlar och/eller orderbekräftelser.</span><span class="sxs-lookup"><span data-stu-id="79f7a-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="79f7a-135">Så här ställs certifikatinformation in.</span><span class="sxs-lookup"><span data-stu-id="79f7a-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="79f7a-136">Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets leverantörscertifikat**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="79f7a-137">Välj en befintlig certifikatinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny certifikatinställning.</span><span class="sxs-lookup"><span data-stu-id="79f7a-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="79f7a-138">Ange följande inställningar för det valda eller nya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="79f7a-139">Fält</span><span class="sxs-lookup"><span data-stu-id="79f7a-139">Field</span></span> | <span data-ttu-id="79f7a-140">beskrivning</span><span class="sxs-lookup"><span data-stu-id="79f7a-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="79f7a-141">Leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="79f7a-141">Vendor account</span></span> | <span data-ttu-id="79f7a-142">Välj den leverantör som du har utfärdat certifikatet till.</span><span class="sxs-lookup"><span data-stu-id="79f7a-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="79f7a-143">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="79f7a-143">Item number</span></span> | <span data-ttu-id="79f7a-144">Välj det objekt leverantör som du har utfärdat certifikatet för.</span><span class="sxs-lookup"><span data-stu-id="79f7a-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="79f7a-145">Land/region</span><span class="sxs-lookup"><span data-stu-id="79f7a-145">Country/region</span></span> | <span data-ttu-id="79f7a-146">Destinationsland eller -region där du måste använda det här certifikatet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="79f7a-147">Certifikatnummer</span><span class="sxs-lookup"><span data-stu-id="79f7a-147">Certificate number</span></span> | <span data-ttu-id="79f7a-148">Ange ID-numret för det certifikat som du har utfärdat.</span><span class="sxs-lookup"><span data-stu-id="79f7a-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="79f7a-149">Giltighet</span><span class="sxs-lookup"><span data-stu-id="79f7a-149">Effective</span></span> | <span data-ttu-id="79f7a-150">Välj det första datumet när det aktuella certifikatet är giltigt.</span><span class="sxs-lookup"><span data-stu-id="79f7a-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="79f7a-151">Förfallotid</span><span class="sxs-lookup"><span data-stu-id="79f7a-151">Expiration</span></span> | <span data-ttu-id="79f7a-152">Välj det sista datumet när det aktuella certifikatet är giltigt.</span><span class="sxs-lookup"><span data-stu-id="79f7a-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="79f7a-153">Skriv ut på faktura</span><span class="sxs-lookup"><span data-stu-id="79f7a-153">Print on invoice</span></span> | <span data-ttu-id="79f7a-154">Markera den här kryssrutan om du vill skriva ut certifikatnumret på fakturor som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="79f7a-155">Skriv ut på följesedel</span><span class="sxs-lookup"><span data-stu-id="79f7a-155">Print on packing slip</span></span> | <span data-ttu-id="79f7a-156">Markera den här kryssrutan om du vill skriva ut certifikatnumret på följesedel som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="79f7a-157">Skriv ut på försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="79f7a-157">Print on sales order</span></span> | <span data-ttu-id="79f7a-158">Markera den här kryssrutan om du vill skriva ut certifikatnumret på försäljningsorder som är adresserade till det angivna landet under det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="79f7a-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="79f7a-159">Inkludera ursprungslandet i strukturlisterapporter</span><span class="sxs-lookup"><span data-stu-id="79f7a-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="79f7a-160">När du genererar en strukturlisterapport kan du inkludera ursprungslandet för varje del som du har angett käll- och målländer för sidan **Regler för ursprungsland**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="79f7a-161">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="79f7a-162">Välj eller skapa en produkt för att öppna dess sida **Information om frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="79f7a-163">I Åtgärdsfönstret, på fliken **Konstruera**, i gruppen **Strukturlista**, markerar du **Designer**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="79f7a-164">På den sida som visas väljer du **Strukturlista \> Skriv ut** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="79f7a-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="79f7a-165">I dialogrutan **strukturlisterader** ange fältet **målland** till det målland som du vill visa i rapporten.</span><span class="sxs-lookup"><span data-stu-id="79f7a-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="79f7a-166">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="79f7a-166">Select **OK**.</span></span>

<span data-ttu-id="79f7a-167">En rapport som visar information om ursprungslandet för varje del genereras och visas.</span><span class="sxs-lookup"><span data-stu-id="79f7a-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="79f7a-168">Här följer ett exempel på rapporten.</span><span class="sxs-lookup"><span data-stu-id="79f7a-168">Here is an example of the report.</span></span>

<span data-ttu-id="79f7a-169">![Ursprungsland, rapport](media/country-of-origin-report.png "Ursprungsland, rapport")</span><span class="sxs-lookup"><span data-stu-id="79f7a-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
