---
title: Momsfunktionens stöd för överföringsorder
description: Det här ämnet innehåller information om det nya momsfunktionen som stöder överföringsorder genom att använda tjänsten för momsberäkning.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920965"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="a2768-103">Momsfunktionens stöd för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="a2768-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2768-104">Det här ämnet ger information om momsberäkning och bokföringsintegrering i överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="a2768-105">Med hjälp av den här funktionen kan du ställa in momsberäkning och bokföring i överföringsorder för lageröverföringar.</span><span class="sxs-lookup"><span data-stu-id="a2768-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="a2768-106">Inom EU behandlas lageröverföringar inomeuropeisk anskaffning och anskaffning inomeuropeisk moms.</span><span class="sxs-lookup"><span data-stu-id="a2768-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="a2768-107">Om du vill konfigurera och använda denna funktion måste du utföra tre huvudsteg:</span><span class="sxs-lookup"><span data-stu-id="a2768-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="a2768-108">**RCS-inställning:** I Regulatory Configuration Service, ställ in momsfunktionen, momskoder och tillämplighet för momskoder för bestämning av momskod i överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="a2768-109">**Ekonomiska inställningar:** I Microsoft Dynamics 365 Finance, aktivera funktionen **Moms i överföringsordning**, ställa in skattetjänstparametrar för lager och ställa in huvudsakliga momsparametrar.</span><span class="sxs-lookup"><span data-stu-id="a2768-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="a2768-110">**Lagerinställningar:** Ställ in lagerkonfigurationen för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a2768-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="a2768-111">Ställa in RCS för moms- och överföringsordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="a2768-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="a2768-112">Följ dessa steg för att ställa in momsen som ingår i en överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="a2768-113">I exemplet som visas här är överföringsordern från Nederländerna till Belgien.</span><span class="sxs-lookup"><span data-stu-id="a2768-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="a2768-114">På sidan **Momsfunktioner**, på fliken **Versioner**, välj versionen av utkastfunktionen och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="a2768-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Välja Redigera](../media/image1.png)

2. <span data-ttu-id="a2768-116">På sidan **Inställning av momsfunktioner** på fliken **Momskoder**, välj **Lägg till** för att skapa nya momskoder.</span><span class="sxs-lookup"><span data-stu-id="a2768-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="a2768-117">I det här exemplet skapas tre momskoder: **NL-undantagen**, **BE-RC-21** och **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="a2768-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="a2768-118">När en överföringsorder levereras från ett lagerställe i Nederländerna används den momsbefriade momskoden (**NL-undantagen**) använd.</span><span class="sxs-lookup"><span data-stu-id="a2768-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="a2768-119">Skapa momskoden **NL-undantagen**.</span><span class="sxs-lookup"><span data-stu-id="a2768-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="a2768-120">Välj **Lägg till**, ange **NL-undantag** i fältet **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="a2768-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="a2768-121">Välj **Efter nettobelopp** i fältet **Momskomponent**.</span><span class="sxs-lookup"><span data-stu-id="a2768-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="a2768-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2768-122">Select **Save**.</span></span>
        4. <span data-ttu-id="a2768-123">Välj **Lägg till** i tabellen **Kurs**.</span><span class="sxs-lookup"><span data-stu-id="a2768-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="a2768-124">Växla **Är undantagen** till **Ja** i avsnittet **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="a2768-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![NL-undantagen momskod](../media/image2.png)

    - <span data-ttu-id="a2768-126">När en överföringsorder tas emot på ett belgiskt lagerställe används omvänd momsmekanism med hjälp av momskoderna **BE-RC-21** och **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="a2768-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="a2768-127">Skapa momskoden **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="a2768-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="a2768-128">Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="a2768-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="a2768-129">Välj **Efter nettobelopp** i fältet **Momskomponent**.</span><span class="sxs-lookup"><span data-stu-id="a2768-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="a2768-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2768-130">Select **Save**.</span></span>
        4. <span data-ttu-id="a2768-131">Välj **Lägg till** i tabellen **Kurs**.</span><span class="sxs-lookup"><span data-stu-id="a2768-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="a2768-132">Ange **-21** i fältet **Momssats**.</span><span class="sxs-lookup"><span data-stu-id="a2768-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="a2768-133">Växla **Är återförd avgift** till **Ja** i avsnittet **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="a2768-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="a2768-134">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2768-134">Select **Save**.</span></span>

        ![BE-RC-21-momskod för omvänd moms](../media/image3.png)
        
        <span data-ttu-id="a2768-136">Skapa momskoden **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="a2768-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="a2768-137">Välj **Lägg till**, ange **BE-RC-21** i fältet **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="a2768-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="a2768-138">Välj **Efter nettobelopp** i fältet **Momskomponent**.</span><span class="sxs-lookup"><span data-stu-id="a2768-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="a2768-139">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2768-139">Select **Save**.</span></span>
        4. <span data-ttu-id="a2768-140">Välj **Lägg till** i tabellen **Kurs**.</span><span class="sxs-lookup"><span data-stu-id="a2768-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="a2768-141">Ange **21** i fältet **Momssats**.</span><span class="sxs-lookup"><span data-stu-id="a2768-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="a2768-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2768-142">Select **Save**.</span></span>

        ![BE-RC+21-momskod för omvänd moms](../media/image4.png)

3. <span data-ttu-id="a2768-144">Definiera tillämplighet för momskoderna.</span><span class="sxs-lookup"><span data-stu-id="a2768-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="a2768-145">Markera **Hantera kolumner** och välj sedan kolumner som ska användas för att bygga tillämplighetsregler.</span><span class="sxs-lookup"><span data-stu-id="a2768-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a2768-146">Se till att du lägger till kolumnerna **Affärsprocess** och **Momsriktningar**.</span><span class="sxs-lookup"><span data-stu-id="a2768-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="a2768-147">Båda kolumnerna är nödvändiga för funktionen för moms i överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="a2768-148">Lägg tillämplighetsregler.</span><span class="sxs-lookup"><span data-stu-id="a2768-148">Add applicability rules.</span></span> <span data-ttu-id="a2768-149">Lämna inte fälten **Momskoder**, **Momsgrupp** och **Artikelmomsgrupp** tomma.</span><span class="sxs-lookup"><span data-stu-id="a2768-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="a2768-150">Lägg till en ny regel för överföringsorderförsändelse.</span><span class="sxs-lookup"><span data-stu-id="a2768-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="a2768-151">Välj **Lägg till** i tabellen **Tillämplighetsregler**.</span><span class="sxs-lookup"><span data-stu-id="a2768-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="a2768-152">I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="a2768-153">I fältet **Sänd från land/region**, ange **NLD**.</span><span class="sxs-lookup"><span data-stu-id="a2768-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="a2768-154">I fältet **Sänd till land/region**, ange **BEL**.</span><span class="sxs-lookup"><span data-stu-id="a2768-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="a2768-155">I fältet **Momsriktning**, välj **Utgång** för att göra regeln tillämplig för överföring av orderförsändelse.</span><span class="sxs-lookup"><span data-stu-id="a2768-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="a2768-156">I fältet **Momskoder**, välj **NL-undantag**.</span><span class="sxs-lookup"><span data-stu-id="a2768-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="a2768-157">I fältet **Momsgrupp** och **Artikelmomsgrupp**, ange den relaterade momsgruppen och artikelns momsgrupp som definieras i ditt Finance-system.</span><span class="sxs-lookup"><span data-stu-id="a2768-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="a2768-158">Lägg till en annan regel för inleverans av överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="a2768-159">Välj **Lägg till** i tabellen **Tillämplighetsregler**.</span><span class="sxs-lookup"><span data-stu-id="a2768-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="a2768-160">I fältet **Affärsprocess**, välj **Lager** för att göra regeln tillämplig för en överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="a2768-161">I fältet **Sänd från land/region**, ange **NLD**.</span><span class="sxs-lookup"><span data-stu-id="a2768-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="a2768-162">I fältet **Sänd till land/region**, ange **BEL**.</span><span class="sxs-lookup"><span data-stu-id="a2768-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="a2768-163">I fältet **Momsriktning**, välj **Ingång** för att göra regeln tillämplig för inleverans av överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="a2768-164">I fältet **Momskoder**, välj **BE-RC+21** och **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="a2768-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="a2768-165">I fältet **Momsgrupp** och **Artikelmomsgrupp**, ange den relaterade momsgruppen och artikelns momsgrupp som definieras i ditt Finance-system.</span><span class="sxs-lookup"><span data-stu-id="a2768-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Tillämplighetsregler](../media/image5.png)

4. <span data-ttu-id="a2768-167">Slutför och publicera den nya versionen av skattefunktionen.</span><span class="sxs-lookup"><span data-stu-id="a2768-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="a2768-168">[![Ändra status för den nya versionen](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="a2768-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="a2768-169">Ställa in Finance för moms- och överföringsordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="a2768-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="a2768-170">Följ dessa steg för att aktivera och ställa in skatter för överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="a2768-171">I Finance, gå till **Arbetsytor** \> **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="a2768-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="a2768-172">I listan, hitta och välj funktionen **Moms i överföringsorder** och välj sedan **Aktivera nu** för att aktivera den.</span><span class="sxs-lookup"><span data-stu-id="a2768-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a2768-173">Funktionen **Moms i överföringsorder** är helt beroende av momstjänst.</span><span class="sxs-lookup"><span data-stu-id="a2768-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="a2768-174">Det kan därför endast aktiveras när du har installerat skattetjänsten.</span><span class="sxs-lookup"><span data-stu-id="a2768-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Moms i överföringsfunktionen](../media/image7.png)

3. <span data-ttu-id="a2768-176">Aktivera skattetjänsten och välj affärsprocessen **Lager**.</span><span class="sxs-lookup"><span data-stu-id="a2768-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a2768-177">Du måste genomföra det här steget för varje juridisk person i Finance där du vill att momstjänsten och momsfunktionerna i överföringsorder ska vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="a2768-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="a2768-178">Gå till **Moms** \> **Inställningar** \> **Momskonfiguration** \> **Installation av momstjänst**.</span><span class="sxs-lookup"><span data-stu-id="a2768-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="a2768-179">I fälten **Affärsprocess**, välj **Lager**.</span><span class="sxs-lookup"><span data-stu-id="a2768-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Ställa in affärsprocessfältet](../media/image8.png)

4. <span data-ttu-id="a2768-181">Kontrollera att omvänd avgiftsmekanism har ställts in.</span><span class="sxs-lookup"><span data-stu-id="a2768-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="a2768-182">Gå till **Redovisning** \> **Inställning** \> **Parametrar** och sedan på **Omvänd debitering**, kontrollera att alternativet **Aktivera omvänd moms** anges **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a2768-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Aktivera alternativet återföring](../media/image9.png)

5. <span data-ttu-id="a2768-184">Kontrollera att de relaterade momskoderna, momsgrupperna, artikelmomsgrupperna och momsregistreringsnumren har ställts in i Finance enligt momstjänstens riktlinjer.</span><span class="sxs-lookup"><span data-stu-id="a2768-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="a2768-185">Ställ in ett mellanliggande transitkonto.</span><span class="sxs-lookup"><span data-stu-id="a2768-185">Set up an interim transit account.</span></span> <span data-ttu-id="a2768-186">Detta steg är endast nödvändigt när den skatt som tillämpas på en överföringsorder, inte gäller för en momsbefriad eller återförd avgiftsmekanism.</span><span class="sxs-lookup"><span data-stu-id="a2768-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="a2768-187">Gå till **Moms** \> **Inställningar** \> **Moms** \> **Redovisningsbokföringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="a2768-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="a2768-188">I fältet **mellanliggande transit**, välj redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="a2768-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Ställ in ett mellanliggande transitkonto](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="a2768-190">Ställ in grundläggande inventering för moms- och överföringsordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="a2768-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="a2768-191">Följ dessa steg om du vill ställa in grundläggande lager för att aktivera överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a2768-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="a2768-192">Skapa från- och leveransplatser för dina lagerställen i olika länder eller regioner och lägg till den primära adressen för respektive webbplats.</span><span class="sxs-lookup"><span data-stu-id="a2768-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="a2768-193">Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Webbplats**.</span><span class="sxs-lookup"><span data-stu-id="a2768-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="a2768-194">Välj **Ny** för att skapa den webbplats som du tilldelar till ett lager senare.</span><span class="sxs-lookup"><span data-stu-id="a2768-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="a2768-195">Upprepa steg 2 för alla andra siter som du måste skapa.</span><span class="sxs-lookup"><span data-stu-id="a2768-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2768-196">En av de webbplatser som du skapar ska få namnet **Transit**.</span><span class="sxs-lookup"><span data-stu-id="a2768-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="a2768-197">Senare tilldelar du den här siten till transitlagret så att momsrelaterade lagerverifikationer kan bokföras i "skeppa" och "ta emot"-transaktioner för överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a2768-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="a2768-198">Adressen till transitplatsen är inte relevant för momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="a2768-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="a2768-199">Därför kan du lämna det tomt.</span><span class="sxs-lookup"><span data-stu-id="a2768-199">Therefore, you can leave it blank.</span></span>

    ![Ställa in webbplatser](../media/image11.png)

2. <span data-ttu-id="a2768-201">Skapa leverans-, transit- och leverans till lagerställen.</span><span class="sxs-lookup"><span data-stu-id="a2768-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="a2768-202">All adressinformation som finns i ett lagerställe åsidosätter siteadressen vid momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="a2768-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="a2768-203">Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="a2768-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="a2768-204">Välj **Ny** för att skapa ett lager och tilldela det till motsvarande webbplats.</span><span class="sxs-lookup"><span data-stu-id="a2768-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="a2768-205">Upprepa steg 2 om du vill skapa ett lagerställe för respektive webbplats efter behov.</span><span class="sxs-lookup"><span data-stu-id="a2768-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Ställa in lagerställen](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="a2768-207">För ett lagerställe för leverans från måste ett transitlager väljas i fältet **Transitlagerställe** för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a2768-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Välja ett transitlager](../media/image13.png)

3. <span data-ttu-id="a2768-209">Kontrollera att konfiguration av lagerbokföring har ställts in för överföringsordertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a2768-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="a2768-210">Gå till **Lagerhantering** \> **Inställningar** \> **Bokföring** \> **Bokföring**.</span><span class="sxs-lookup"><span data-stu-id="a2768-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="a2768-211">Kontrollera på fliken **Lager**, verifiera att ett huvudbokskonto är konfigurerat för båda bokföring av **lagerutleverans** och **lagerinleverans**.</span><span class="sxs-lookup"><span data-stu-id="a2768-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Ställa in bokföring av lagerutleverans och lagerinleverans](../media/image14.png)

    3. <span data-ttu-id="a2768-213">Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern skuld**.</span><span class="sxs-lookup"><span data-stu-id="a2768-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Ställa in bokföring mellan enhetsreskontra](../media/image15.png)

    4. <span data-ttu-id="a2768-215">Kontrollera att ett huvudkontokonfigureras för bokföring av **Enhetsintern fordran**.</span><span class="sxs-lookup"><span data-stu-id="a2768-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Ställa in bokföring av enhetsintern fordran](../media/image16.png)
