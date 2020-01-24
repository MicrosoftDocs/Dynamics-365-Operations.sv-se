---
title: Kassaapparatfunktioner för Sverige
description: Det här avsnittet innehåller en översikt över kassaapparatfunktioner för Sverige.
author: EvgenyPopovMBS
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, RetailFunctionalityProfile, RetailFormLayout, RetailHardwareProfile, RetailFiscalPrinterConfigTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Sweden
ms.search.industry: retail
ms.author: epopov
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 7dcd5a17e428a3e6c464918be0dc7df515b50991
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915309"
---
# <a name="cash-register-functionality-for-sweden"></a><span data-ttu-id="45672-103">Kassaapparatfunktioner för Sverige</span><span class="sxs-lookup"><span data-stu-id="45672-103">Cash register functionality for Sweden</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45672-104">Det här avsnittet innehåller en översikt över kassaapparatfunktioner för Sverige i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="45672-104">This topic provides an overview of the cash register functionality that is available for Sweden in Dynamics 365 Retail.</span></span> <span data-ttu-id="45672-105">Den innehåller även riktlinjer för att ställa in funktionen.</span><span class="sxs-lookup"><span data-stu-id="45672-105">It also provides guidelines for setting up the functionality.</span></span> <span data-ttu-id="45672-106">Funktionen innehåller följande delar:</span><span class="sxs-lookup"><span data-stu-id="45672-106">The functionality consists of the following parts:</span></span>

- <span data-ttu-id="45672-107">Vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner som ett alternativ för att förhindra försäljning och returer från att slås samman i ett butikskvitto</span><span class="sxs-lookup"><span data-stu-id="45672-107">Common point-of sale (POS) features that are made available to customers in all countries or regions, such as an option to prevent sales and returns from being combined on one retail receipt</span></span>
- <span data-ttu-id="45672-108">Sverige-specifika funktioner, t.ex. ytterligare räknare i dagliga kassarapporter</span><span class="sxs-lookup"><span data-stu-id="45672-108">Sweden-specific features, such as additional counters in daily POS reports</span></span>
- <span data-ttu-id="45672-109">Ett exempel för att integrera Retail POS med Sverige-specifika kvittoskrivarenheter som kallas kontrollenheter.</span><span class="sxs-lookup"><span data-stu-id="45672-109">A sample for integration of Retail POS with Sweden-specific fiscal devices that are known as control units.</span></span>

## <a name="overview-of-cash-register-functionality-for-sweden"></a><span data-ttu-id="45672-110">Översikt över kassaapparatfunktioner för Sverige</span><span class="sxs-lookup"><span data-stu-id="45672-110">Overview of cash register functionality for Sweden</span></span>

### <a name="common-pos-features"></a><span data-ttu-id="45672-111">Vanliga kassafunktioner</span><span class="sxs-lookup"><span data-stu-id="45672-111">Common POS features</span></span>

<span data-ttu-id="45672-112">Mer information om vanliga kassafunktioner som är tillgängliga för kunder i alla länder eller regioner finns i [Hjälpresurser för Dynamics 365 Retail](../index.md).</span><span class="sxs-lookup"><span data-stu-id="45672-112">To learn about common POS features that are available to customers in all countries or regions, see [Help resources for Dynamics 365 Retail](../index.md).</span></span>

<span data-ttu-id="45672-113">Dessutom har följande kassafunktioner som implementerades för Sverige gjorts tillgängliga för kunder i alla länder eller regioner:</span><span class="sxs-lookup"><span data-stu-id="45672-113">Additionally, the following POS features that were implemented for Sweden have been made available to customers in all countries or regions:</span></span>

- <span data-ttu-id="45672-114">**Förbjuda försäljning och returer från att slås samman i ett butikskvitto.**</span><span class="sxs-lookup"><span data-stu-id="45672-114">**Prohibit sales and returns from being combined on one retail receipt.**</span></span> <span data-ttu-id="45672-115">När du anger parametern **förbjuda blandning av försäljning och returer i ett kvitto** i kassafunktionsprofilen till **Ja**, kommer Cloud POS och Modern POS inte låta användarna skapa en transaktion som innehåller både positiva och negativa rader.</span><span class="sxs-lookup"><span data-stu-id="45672-115">When you set the **Prohibit mixing sales and returns in one receipt** parameter in the POS functionality profile to **Yes**, Cloud POS and Modern POS won't let users create a transaction that contains both positive and negative lines.</span></span>
- <span data-ttu-id="45672-116">**Skriva ut textfälten på kvittot i en stor teckenstorlek.**</span><span class="sxs-lookup"><span data-stu-id="45672-116">**Print text fields on the receipt in a large font size.**</span></span> <span data-ttu-id="45672-117">Du kan använda parametern **Teckenstorlekstorlek** i kvittoformatdesignern för att ange att stort teckenstorlek ska användas för ett fält i ett kvittoformat.</span><span class="sxs-lookup"><span data-stu-id="45672-117">You can use the **Font size** parameter in the Receipt format designer to specify that the large font size should be used for a field in a receipt format.</span></span> <span data-ttu-id="45672-118">(Stor teckenstorlek är ungefär dubbelt så stor som normal storlek.) Du kan exempelvis använda denna parameter för att skriva ut indikatorn ”kopia” på ett kvitto med stora bokstäver.</span><span class="sxs-lookup"><span data-stu-id="45672-118">(The large font size is approximately double the usual font size.) For example, you can use this parameter to print the "Copy" indicator on a receipt copy in large characters.</span></span>
- <span data-ttu-id="45672-119">**Registrera utskrift av kvittokopior i händelseloggen kassagranskning.**</span><span class="sxs-lookup"><span data-stu-id="45672-119">**Register the printing of receipt copies in the POS audit event log.**</span></span> <span data-ttu-id="45672-120">Du kan använda parametern **granska** i kassafunktionsprofilen för utskrift av kvittokopior och andra kassagranskningshändelser som ska registreras.</span><span class="sxs-lookup"><span data-stu-id="45672-120">You can use the **Audit** parameter in the POS functionality profile to enable the printing of receipt copies and other POS audit events to be registered.</span></span> <span data-ttu-id="45672-121">Granskningshändelserna registreras i kanaldatabasen och i butiksadministrationen.</span><span class="sxs-lookup"><span data-stu-id="45672-121">The audit events are registered in the channel database and in Retail headquarters.</span></span> <span data-ttu-id="45672-122">Du kan visa granskningshändelser på sidan **granskningshändelser**.</span><span class="sxs-lookup"><span data-stu-id="45672-122">You can view the audit events on the **Audit events** page.</span></span>
- <span data-ttu-id="45672-123">**Förhindra att en kopia av ett kvitto skrivs ut mer än en gång.**</span><span class="sxs-lookup"><span data-stu-id="45672-123">**Prevent a copy of a receipt from being printed more than one time.**</span></span> <span data-ttu-id="45672-124">När parametern **granska** i kassafunktionsprofilen är aktiverad kan kassabehörigheten **Tillåt utskrift av kassakopior** kontrollera om kvittokopiorna kan skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="45672-124">When the parameter **Audit** in the POS functionality profile is enabled, the **Allow printing receipt copies** POS permission controls whether receipt copies can be printed.</span></span> <span data-ttu-id="45672-125">Det finns också ett alternativ för att förhindra att en kopia av ett kvitto skrivs ut mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="45672-125">There is also an option to prevent a copy of a receipt from being printed more than one time.</span></span>

### <a name="sweden-specific-pos-features"></a><span data-ttu-id="45672-126">Sverige-specifika kassafunktioner</span><span class="sxs-lookup"><span data-stu-id="45672-126">Sweden-specific POS features</span></span>

<span data-ttu-id="45672-127">Följande Sverige-specifika kassafunktioner aktiveras när parametern **ISO-kod** i kassafunktionsprofilen ställs in till **SE**:</span><span class="sxs-lookup"><span data-stu-id="45672-127">The following Sweden-specific POS features are enabled when the **ISO code** parameter in the POS functionality profile is set to **SE**:</span></span>

- <span data-ttu-id="45672-128">Extra räknare i daglga kassarapporter som X- och Z-rapporter:</span><span class="sxs-lookup"><span data-stu-id="45672-128">Additional counters on daily POS reports, such as X-reports and Z-reports:</span></span>

    - <span data-ttu-id="45672-129">Antal kvittokopior och totalt belopp</span><span class="sxs-lookup"><span data-stu-id="45672-129">Receipt copy count and total amount</span></span>
    - <span data-ttu-id="45672-130">Momsbelopp per momssats</span><span class="sxs-lookup"><span data-stu-id="45672-130">Value added tax amounts per tax rate</span></span>
    - <span data-ttu-id="45672-131">Totala kvantiteter för artiklar och tjänster som säljs</span><span class="sxs-lookup"><span data-stu-id="45672-131">Total quantities of items and services sold</span></span>
    - <span data-ttu-id="45672-132">Total försäljning exklusive och inklusive skatt</span><span class="sxs-lookup"><span data-stu-id="45672-132">Total sales excluding and including VAT</span></span>
    - <span data-ttu-id="45672-133">Totalförsäljning, returer och netto</span><span class="sxs-lookup"><span data-stu-id="45672-133">Grand total sales, returns, and net</span></span>

- <span data-ttu-id="45672-134">En kanalrapport för **elektronisk journal (Sverige)** som listar användningshändelser i kassan, till exempel försäljning, returer, kvittokopior, kassalådöppningar och prisåsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="45672-134">An **Electronic journal (Sweden)** channel report that lists continuous use events in the POS, such as sales, returns, receipt copies, drawer openings, and price overrides.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45672-135">För närvarande kan rapporten **elektronisk journal (Sverige)** inte exporteras eller skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="45672-135">Currently, the **Electronic journal (Sweden)** report can't be exported or printed.</span></span> <span data-ttu-id="45672-136">Men funktionen för export och utskrift av rapportenkommer att läggas till senare.</span><span class="sxs-lookup"><span data-stu-id="45672-136">However, functionality for exporting and printing the report will be added later.</span></span>

### <a name="integration-of-retail-pos-with-control-units"></a><span data-ttu-id="45672-137">Integrering med kontrollenheter i Retail POS</span><span class="sxs-lookup"><span data-stu-id="45672-137">Integration of Retail POS with control units</span></span>


   # <a name="retail-1006-and-earliertabretail-10-0-6"></a>[<span data-ttu-id="45672-138">Retail 10.0.6 och tidigare</span><span class="sxs-lookup"><span data-stu-id="45672-138">Retail 10.0.6 and earlier</span></span>](#tab/retail-10-0-6)

  <span data-ttu-id="45672-139">Mer information om integrationen med styrenheter som är tillgängliga i återförsäljarversioner till och med Retail 10.0.6 finns i [exempel för Retail POS-integrering med styrenheter för Sverige (äldre).](./retail-sdk-control-unit-sample.md#overview-of-integration-with-control-units)</span><span class="sxs-lookup"><span data-stu-id="45672-139">For more information about the integration with control units that is available in Retail versions up to and including Retail 10.0.6, see [Sample for Retail POS integration with control units for Sweden (legacy)](./retail-sdk-control-unit-sample.md#overview-of-integration-with-control-units).</span></span> 


   # <a name="retail-1007-and-latertabretail-10-0-7"></a>[<span data-ttu-id="45672-140">Retail 10.0.7 och senare</span><span class="sxs-lookup"><span data-stu-id="45672-140">Retail 10.0.7 and later</span></span>](#tab/retail-10-0-7)

  <span data-ttu-id="45672-141">Mer information om styrenhetens integrationsprov finns i [Exempel på integration av kontrollenhet för Sverige](./emea-swe-fi-sample.md).</span><span class="sxs-lookup"><span data-stu-id="45672-141">For more information about the control unit integration sample, see [Control unit integration sample for Sweden](./emea-swe-fi-sample.md).</span></span>

---


## <a name="setting-up-retail-for-sweden"></a><span data-ttu-id="45672-142">Konfigurera Retail för Sverige</span><span class="sxs-lookup"><span data-stu-id="45672-142">Setting up Retail for Sweden</span></span>

<span data-ttu-id="45672-143">Det här avsnittet beskriver inställningar som avser och rekommenderas för Sverige.</span><span class="sxs-lookup"><span data-stu-id="45672-143">This section describes the settings that are specific to and recommended for Sweden.</span></span> <span data-ttu-id="45672-144">Mer information om hur du ställer in ett standardlagerställe för butiker finns i [Hjälpresurser för Dynamics 365 Retail](../index.md).</span><span class="sxs-lookup"><span data-stu-id="45672-144">For more information about how to set up Retail, see [Help resources for Dynamics 365 Retail](../index.md).</span></span>

<span data-ttu-id="45672-145">Om du vill använda Sverige-specifika funktioner måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="45672-145">To use the Sweden-specific functionality, you must complete these tasks:</span></span>

- <span data-ttu-id="45672-146">Ange fältet **land/region** till **SWE** (Sverige) i den primära adressen för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="45672-146">Set the **Country/region** field to **SWE** (Sweden) in the primary address of the legal entity.</span></span>
- <span data-ttu-id="45672-147">Ange fältet **ISO-kod** till **SE** (Sverige) i funktionsprofil för kassa för alla butiker som finns i Sverige.</span><span class="sxs-lookup"><span data-stu-id="45672-147">Set the **ISO code** field to **SE** (Sweden) in the POS functionality profile of every store that is located in Sweden.</span></span>

<span data-ttu-id="45672-148">Sverige-specifika inställningar kan delas in i två grupper:</span><span class="sxs-lookup"><span data-stu-id="45672-148">Sweden-specific settings can be divided into two groups:</span></span>

- <span data-ttu-id="45672-149">Allmänna inställningar</span><span class="sxs-lookup"><span data-stu-id="45672-149">General settings</span></span>
- <span data-ttu-id="45672-150">Styrenhet - specifika inställningar</span><span class="sxs-lookup"><span data-stu-id="45672-150">Control unit–specific settings</span></span>

### <a name="general-settings"></a><span data-ttu-id="45672-151">Allmänna inställningar</span><span class="sxs-lookup"><span data-stu-id="45672-151">General settings</span></span>

<span data-ttu-id="45672-152">Du måste ange följande allmänna inställningar för Sverige.</span><span class="sxs-lookup"><span data-stu-id="45672-152">You must specify the following general settings for Sweden.</span></span>

1. <span data-ttu-id="45672-153">Ange följande parametrar för skatt (VAT) enligt svenska krav:</span><span class="sxs-lookup"><span data-stu-id="45672-153">Set up the following parameters for value-added tax (VAT) per Swedish requirements:</span></span>

    - <span data-ttu-id="45672-154">Momskoder</span><span class="sxs-lookup"><span data-stu-id="45672-154">Sales tax codes</span></span>
    - <span data-ttu-id="45672-155">Momsgrupper</span><span class="sxs-lookup"><span data-stu-id="45672-155">Sales tax groups</span></span>
    - <span data-ttu-id="45672-156">Artikelmomsgrupper</span><span class="sxs-lookup"><span data-stu-id="45672-156">Item sales tax groups</span></span>
    - <span data-ttu-id="45672-157">Momsinställningar i artiklar (artikelmomsgrupper för försäljning)</span><span class="sxs-lookup"><span data-stu-id="45672-157">Sales tax settings in items (item sales tax groups for sales)</span></span>

    <span data-ttu-id="45672-158">Mer information om hur du ställer in och använder moms finns i [Momsöversikt](../../financials/general-ledger/indirect-taxes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="45672-158">For more information about how to set up and use sales tax, see [Sales tax overview](../../financials/general-ledger/indirect-taxes-overview.md).</span></span>


2. <span data-ttu-id="45672-159">På sidan **Alla butiker** uppdaterar du butiksinformation.</span><span class="sxs-lookup"><span data-stu-id="45672-159">On the **All retail stores** page, update retail store details.</span></span> <span data-ttu-id="45672-160">Du måste speciellt ställa in följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="45672-160">Specifically, set the following parameters:</span></span>

    - <span data-ttu-id="45672-161">I fältet **Momsgrupp** anger du en momsgrupp som ska användas för försäljning till butikskund.</span><span class="sxs-lookup"><span data-stu-id="45672-161">In the **Sales tax group** field, set the sales tax group that should be used for sales to the default retail customer.</span></span>
    - <span data-ttu-id="45672-162">Markera kryssrutan **Moms ingår i priserna**.</span><span class="sxs-lookup"><span data-stu-id="45672-162">Select the **Prices include sales tax** check box.</span></span>
    - <span data-ttu-id="45672-163">Ange fältet **Butiksnamn** till att inkludera företagets namn.</span><span class="sxs-lookup"><span data-stu-id="45672-163">Set the **Store name** field so that it includes the company name.</span></span> <span data-ttu-id="45672-164">Den här ändringen hjälper till att garantera att företagsnamnet visas på ett försäljningskvittot.</span><span class="sxs-lookup"><span data-stu-id="45672-164">This change helps guarantee that the company name appears on a sales receipt.</span></span> <span data-ttu-id="45672-165">Alternativt kan du kan lägga till företagsnamnet på layouten av försäljningskvittot i fritt format.</span><span class="sxs-lookup"><span data-stu-id="45672-165">Alternatively, you can add the company name to the sales receipt layout as free-format text.</span></span>
    - <span data-ttu-id="45672-166">Ange fältet **Skatteidentifieringsnummer (TIN)** så att det inkluderar företagets identifieringnummer.</span><span class="sxs-lookup"><span data-stu-id="45672-166">Set the **Tax identification number (TIN)** field so that it includes the company identification number.</span></span> <span data-ttu-id="45672-167">Den här ändringen hjälper till att garantera att företagets identifieringnummer visas på ett försäljningskvittot.</span><span class="sxs-lookup"><span data-stu-id="45672-167">This change helps guarantee that the company identification number appears on a sales receipt.</span></span> <span data-ttu-id="45672-168">Alternativt kan du kan lägga till företagets identifieringnummer på försäljningskvittot i fritt format.</span><span class="sxs-lookup"><span data-stu-id="45672-168">Alternatively, you can add the company identification number to the sales receipt layout as free-format text.</span></span>

3. <span data-ttu-id="45672-169">Ställa in kassafunktionsprofiler:</span><span class="sxs-lookup"><span data-stu-id="45672-169">Set up POS functionality profiles:</span></span>

    - <span data-ttu-id="45672-170">På snabbfliken **funktioner** markerar du kryssrutorna **Granskning** och **Förhindra att försäljning och returer blandas på ett kvitto**.</span><span class="sxs-lookup"><span data-stu-id="45672-170">On the **Functions** FastTab, select the **Audit** and **Prohibit mixing sales and returns in one receipt** check boxes.</span></span>
    - <span data-ttu-id="45672-171">På snabbfliken **Kvittonumrering** anger du kvittonumrering.</span><span class="sxs-lookup"><span data-stu-id="45672-171">On the **Receipt numbering** FastTab, set up receipt numbering.</span></span> <span data-ttu-id="45672-172">Skapa eller uppdatera poster för kvittotransaktionstyperna **försäljning** och **returer**.</span><span class="sxs-lookup"><span data-stu-id="45672-172">Create or update records for the **Sale** and **Return** receipt transaction types.</span></span> <span data-ttu-id="45672-173">Ange formaten så att endast innehåller numeriska tecken.</span><span class="sxs-lookup"><span data-stu-id="45672-173">Set the formats so that they include only numeric characters.</span></span> <span data-ttu-id="45672-174">Avmarkera kryssrutan **oberoende sekvens** i båda posterna.</span><span class="sxs-lookup"><span data-stu-id="45672-174">Clear the **Independent sequence** check box in both records.</span></span>

4. <span data-ttu-id="45672-175">Uppdatera kassabehörighetsgrupper och enskilda behörighetsinställningar för arbetare i butiken.</span><span class="sxs-lookup"><span data-stu-id="45672-175">Update POS permissions groups and individual permission settings for store workers.</span></span> <span data-ttu-id="45672-176">Ange behörigheten **Tillåt utskrift av kvittokopia** till lämpligt värde:</span><span class="sxs-lookup"><span data-stu-id="45672-176">Set the **Allow printing receipt copy** permission to an appropriate value:</span></span>

    - <span data-ttu-id="45672-177">**Tillåt alltid** – operatören kan skriva ut en kopia av ett kvitto flera gånger.</span><span class="sxs-lookup"><span data-stu-id="45672-177">**Allow always** – The operator can print a copy of a receipt multiple times.</span></span>
    - <span data-ttu-id="45672-178">**Tillåt endast en gång** – operatören kan skriva ut en kopia av ett kvitto en gång.</span><span class="sxs-lookup"><span data-stu-id="45672-178">**Allow only once** – The operator can print a copy of a receipt only one time.</span></span>
    - <span data-ttu-id="45672-179">**Tillåt endast en gång och endast om HQ DB är tillgängligt** – operatören kan skriva ut en kopia av ett kvitto bara en gång och endast om huvudkontorets databas är tillgänglig via Realtidstjänst så att systemet kan kontrollera att inga kopior av kvittona har skrivits ut tidigare i någon butik.</span><span class="sxs-lookup"><span data-stu-id="45672-179">**Allow only once, and only if HQ DB is available** – The operator can print a copy of a receipt only one time, and only if the headquarters database is available through Real-Time service, so that the system can verify that no copies of the receipt have previously been printed in any store.</span></span>
    - <span data-ttu-id="45672-180">**Aldrig** – operatören kan inte skriva ut en kopia av ett kvitto.</span><span class="sxs-lookup"><span data-stu-id="45672-180">**Never** – The operator can't print a copy of a receipt.</span></span>

5. <span data-ttu-id="45672-181">Gör nödvändiga ändringar i kvittoformat för försäljningskvitton:</span><span class="sxs-lookup"><span data-stu-id="45672-181">Make the required changes to receipt formats for sales receipts:</span></span>

    - <span data-ttu-id="45672-182">Ändra värdet i fältet **Utskriftssätt** till **Skriv alltid ut** för kvittoformatet.</span><span class="sxs-lookup"><span data-stu-id="45672-182">Change the value of the **Print behavior** field to **Always print** for the receipt format.</span></span>
    - <span data-ttu-id="45672-183">Gör följande ändringar i Layoutdesigner för kvitto:</span><span class="sxs-lookup"><span data-stu-id="45672-183">In the Receipt format designer, make these changes:</span></span>

        - <span data-ttu-id="45672-184">Lägg till minst följande fält till **Rubrik**-delen på kvittolayouten:</span><span class="sxs-lookup"><span data-stu-id="45672-184">Add at least the following fields to the **Header** section of the receipt layout:</span></span>

            - <span data-ttu-id="45672-185">Fälten **Butiksnamn** och **momsidentifieringsnummer** så att företagsnamnet och identitetnumret är utskrivna kvitton.</span><span class="sxs-lookup"><span data-stu-id="45672-185">**Store name** and **Tax Identification Number** fields, so that the company name and identity number are printed receipts.</span></span> <span data-ttu-id="45672-186">Alternativt kan du kan lägga till företagsnamn och identitetsnummer på layouten i fritt format.</span><span class="sxs-lookup"><span data-stu-id="45672-186">Alternatively, you can add the company name and identity number to the layout as free-format text.</span></span>
            - <span data-ttu-id="45672-187">Fälten **Butiksadress**, **datum**, **Tid, 24 h**, **kvittonummer**, och **registreringsnummer**.</span><span class="sxs-lookup"><span data-stu-id="45672-187">**Store address**, **Date**, **Time 24H**, **Receipt Number**, and **Register number** fields.</span></span>
            - <span data-ttu-id="45672-188">Fältet **Skriv ut meddelande på nytt** så att indikatorn ”kopia” skrivs ut på kvittokopior.</span><span class="sxs-lookup"><span data-stu-id="45672-188">**Reprint Message** field, so that the "Copy" indicator is printed on receipt copies.</span></span> <span data-ttu-id="45672-189">Ange fältet **Teckenstorlek** för fältet **Skriv ut meddelande på nytt** till **Stor**.</span><span class="sxs-lookup"><span data-stu-id="45672-189">Set the **Font size** field for the **Reprint Message** field to **Large**.</span></span>

        - <span data-ttu-id="45672-190">Lägger till minst i följande fält på **rader**-delen av kvittolayouten: **artikelnamn**, **kvantitet**, och **totalpris inkl. skatt**.</span><span class="sxs-lookup"><span data-stu-id="45672-190">Add at least the following field to the **Lines** section of the receipt layout: **Item name**, **Qty**, and **Total price with tax**.</span></span>
        - <span data-ttu-id="45672-191">Lägg till minst följande fält till **Sidfot**-delen på kvittolayouten:</span><span class="sxs-lookup"><span data-stu-id="45672-191">Add at least the following fields to the **Footer** section of the receipt layout:</span></span>

            - <span data-ttu-id="45672-192">Momsfält så att momsbeloppen för varje momssats skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="45672-192">Tax fields, so that the receipt tax amounts for each tax rate are printed.</span></span> <span data-ttu-id="45672-193">Lägg till exempel till fälten **skatte-Id**, **momsprocent**, och **Momsbelopp** till en rad i layouten.</span><span class="sxs-lookup"><span data-stu-id="45672-193">For example, add the **Tax Id**, **Tax percentage**, and **Tax amounts** fields to one line of the layout.</span></span>
            - <span data-ttu-id="45672-194">Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="45672-194">Payment fields, so that the payment amounts for each payment method are printed.</span></span> <span data-ttu-id="45672-195">Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.</span><span class="sxs-lookup"><span data-stu-id="45672-195">For example, add the **Tender name** and **Tender amount** fields to one line of the layout.</span></span>

6. <span data-ttu-id="45672-196">På sidan **Konfiguration av kanalrapporter** anger du rapporten **elektronisk journal (Sverige)**.</span><span class="sxs-lookup"><span data-stu-id="45672-196">On the **Channel reports configuration** page, set up the **Electronic journal (Sweden)** report.</span></span> <span data-ttu-id="45672-197">I fältet **behörighetsgrupper** väljer du kassabehörighetsgrupper som får köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="45672-197">In the  **Permission groups** field, select the POS permission groups that should be allowed to run the report.</span></span>

### <a name="control-unitspecific-settings"></a><span data-ttu-id="45672-198">Styrenhet - specifika inställningar</span><span class="sxs-lookup"><span data-stu-id="45672-198">Control unit–specific settings</span></span>

   # <a name="retail-1006-and-earliertabretail-10-0-6"></a>[<span data-ttu-id="45672-199">Retail 10.0.6 och tidigare</span><span class="sxs-lookup"><span data-stu-id="45672-199">Retail 10.0.6 and earlier</span></span>](#tab/retail-10-0-6)

  <span data-ttu-id="45672-200">Mer information om inställning och konfiguration av integrationen med styrenheter som är tillgängliga i återförsäljarversioner till och med Retail 10.0.6 finns i [exempel för Retail POS-integrering med styrenheter för Sverige (äldre).](./retail-sdk-control-unit-sample.md#setting-up-integration-with-control-units)</span><span class="sxs-lookup"><span data-stu-id="45672-200">For more information about setting up and configuring the integration with control units that is available in Retail versions up to and including Retail 10.0.6, see [Sample for Retail POS integration with control units for Sweden (legacy)](./retail-sdk-control-unit-sample.md#setting-up-integration-with-control-units).</span></span> 

   # <a name="retail-1007-and-latertabretail-10-0-7"></a>[<span data-ttu-id="45672-201">Retail 10.0.7 och senare</span><span class="sxs-lookup"><span data-stu-id="45672-201">Retail 10.0.7 and later</span></span>](#tab/retail-10-0-7)

  <span data-ttu-id="45672-202">Mer information om inställning och konfiguration av styrenhetens integrationsprov finns i [Exempel på integration av kontrollenhet för Sverige](./emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).</span><span class="sxs-lookup"><span data-stu-id="45672-202">For more information about setting up and configuring the control unit integration sample, see [Control unit integration sample for Sweden](./emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).</span></span>

---

    

