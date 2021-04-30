---
title: Leverans av små paket
description: Det här ämnet innehåller information om funktionen leverans av små paket (SPS). Med denna funktion kan Microsoft Dynamics 365 Supply Chain Management skicka uppgifter om en förpackad behållare till transportföretaget och sedan ta emot en leveransetikett, basleveranstariff och spårningsnummer tillbaka från det transportföretaget.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3e72959d79e9b3b03e061a0f26750e3bd025219e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910219"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="fedb6-104">Leverans av små paket</span><span class="sxs-lookup"><span data-stu-id="fedb6-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fedb6-105">Funktionen leverans av små paket (SPS) gör att Microsoft Dynamics 365 Supply Chain Management kan kommunicera direkt med transportföretag genom att tillhandahålla ett ramverk för kommunikation via transportföretags-API:er.</span><span class="sxs-lookup"><span data-stu-id="fedb6-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="fedb6-106">Den här funktionen är användbar när du levererar enskilda försäljningsorder via kommersiella transportföretag i stället för att använda leverans av behållare eller LTL-leverans (mindre än lastbilslasten).</span><span class="sxs-lookup"><span data-stu-id="fedb6-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="fedb6-107">SPS-funktionen kommunicerar med transportföretaget via en dedikerad *tariffmotor*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="fedb6-108">Din organisation måste utveckla den här tariffmotorn i samverkan med transportföretaget eller transportnavtjänsten.</span><span class="sxs-lookup"><span data-stu-id="fedb6-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="fedb6-109">Med tariffmotorn kan Supply Chain Management skicka uppgifter om en förpackad behållare till transportföretaget och sedan ta emot en leveransetikett, basleveranstariff och spårningsnummer tillbaka från det transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="fedb6-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="fedb6-110">Leveranskostnaden som returneras läggs till på den associerade försäljningsordern som ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="fedb6-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="fedb6-111">Leveransetiketten som returneras kan sedan skrivas ut automatiskt med hjälp av en ZPL-skrivare (Zebra Programming Language) och tillämpas på försändelsen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="fedb6-112">Transportföretaget skannar den här leveransetiketten när han eller hon hämtar paketen på ditt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="fedb6-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="fedb6-113">Förbereda ditt system för stöd för SPS</span><span class="sxs-lookup"><span data-stu-id="fedb6-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="fedb6-114">Innan du kan börja använda SPS-funktionen måste du aktivera SPS-funktionen i Funktionshantering, lägga till din tariffmotor och ställa in modulerna **Transporthantering** och **Lagerstyrning** för att stödja den.</span><span class="sxs-lookup"><span data-stu-id="fedb6-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="fedb6-115">Aktivera SPS-funktion</span><span class="sxs-lookup"><span data-stu-id="fedb6-115">Turn on the SPS feature</span></span>

<span data-ttu-id="fedb6-116">Innan du kan använda SPS-funktionen måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="fedb6-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="fedb6-117">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="fedb6-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fedb6-118">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="fedb6-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fedb6-119">**Modul:** *Transporthantering*</span><span class="sxs-lookup"><span data-stu-id="fedb6-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="fedb6-120">**Funktionsnamn:** *Leverans av små paket*</span><span class="sxs-lookup"><span data-stu-id="fedb6-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="fedb6-121">Distribuera och ställa in tariffmotor.</span><span class="sxs-lookup"><span data-stu-id="fedb6-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="fedb6-122">Supply Chain Management omfattar inte några tariffmotorer.</span><span class="sxs-lookup"><span data-stu-id="fedb6-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="fedb6-123">Du måste erhålla eller skapa eventuella tariffmotor som du behöver och sedan lägga till dem i systemet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="fedb6-124">Microsoft tillhandahåller dock en demotariffmotor som du kan använda för att testa.</span><span class="sxs-lookup"><span data-stu-id="fedb6-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="fedb6-125">Hämta och distribuera demotariffmotorn</span><span class="sxs-lookup"><span data-stu-id="fedb6-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="fedb6-126">Följ dessa steg för att hämta demotariffmotorn.</span><span class="sxs-lookup"><span data-stu-id="fedb6-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="fedb6-127">I GitHub, hämta [dynamic-link library (DLL) för demotariffmotor](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="fedb6-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="fedb6-128">I din Supply Chain Management-server, spara DLL i mappen **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="fedb6-129">Skapa och distribuera funktionella tariffmotorer.</span><span class="sxs-lookup"><span data-stu-id="fedb6-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="fedb6-130">Mer information om hur du skapar och distribuerar funktionella tariffmotorer så att de kan användas i en tillverknings- eller testmiljö finns i följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="fedb6-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="fedb6-131">Skapa en ny transporthanteringsmotor</span><span class="sxs-lookup"><span data-stu-id="fedb6-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="fedb6-132">Ställa in motorer för transporthantering</span><span class="sxs-lookup"><span data-stu-id="fedb6-132">Set up transportation management engines</span></span>](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="fedb6-133">Mer information om hur du skapar en SPS-tariffmotor finns i följande inlägg: [Leverans av små paket: Hur du använder funktionen för leverans av små paket i Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="fedb6-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="fedb6-134">Ställa in en tariffmotor i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="fedb6-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="fedb6-135">När du har skapat och distribuerat en tariffmotor för SPS följer du dessa steg och ställer in den.</span><span class="sxs-lookup"><span data-stu-id="fedb6-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="fedb6-136">Gå till **Transporthantering \> Inställningar \> Motorer \> Tariffmotor**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="fedb6-137">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="fedb6-138">I den nya raden anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="fedb6-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="fedb6-139">**Tariffmotor** – Ange ett unikt namn för tariffmotorn.</span><span class="sxs-lookup"><span data-stu-id="fedb6-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="fedb6-140">Om du använder demotariffmotorn anger du *demotariffmotor*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="fedb6-141">**Namn** – Ange en kort beskrivning av tariffmotorn.</span><span class="sxs-lookup"><span data-stu-id="fedb6-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="fedb6-142">Om du använder demotariffmotorn anger du *demotariffmotor*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="fedb6-143">**ID på metadata för bedömning** – Välj det underlag som ska användas för att beräkna tariffen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="fedb6-144">Din tariff kan till exempel beräknas utifrån körsträcka.</span><span class="sxs-lookup"><span data-stu-id="fedb6-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="fedb6-145">Om du använder demotariffmotorn kan du lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="fedb6-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="fedb6-146">**Montering av motor** – Ange filnamnet för DLL-paket som du distribuerade.</span><span class="sxs-lookup"><span data-stu-id="fedb6-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="fedb6-147">Om du använder demotariffmotorn anger du *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="fedb6-148">**Motorklass** – Ange klassnamnet som har upprättats för din tariffmotor.</span><span class="sxs-lookup"><span data-stu-id="fedb6-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="fedb6-149">Om du använder demotariffmotorn anger du *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="fedb6-150">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="fedb6-150">Example scenario</span></span>

<span data-ttu-id="fedb6-151">I det här exempelscenariot visas hur du ställer in och använder SPS efter att du har förberett systemet enligt beskrivningen tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="fedb6-152">I det här scenariot används den tidigare nämnda demotariffmotorn.</span><span class="sxs-lookup"><span data-stu-id="fedb6-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="fedb6-153">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="fedb6-153">Make demo data available</span></span>

<span data-ttu-id="fedb6-154">Om du vill arbeta genom detta scenario med hjälp av de demoposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="fedb6-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="fedb6-155">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="fedb6-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="fedb6-156">Ställ in scenario</span><span class="sxs-lookup"><span data-stu-id="fedb6-156">Set up the scenario</span></span>

<span data-ttu-id="fedb6-157">I det här exemplet måste du ha ett demotransportföretag, en transportföretagsgrupp, en förpackningspolicy och en förpackningsprofil.</span><span class="sxs-lookup"><span data-stu-id="fedb6-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="fedb6-158">Följande delgrupper förklarar hur du förbereder posterna som krävs för scenariot.</span><span class="sxs-lookup"><span data-stu-id="fedb6-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="fedb6-159">I ett produktionsscenario liknar inställningsprocessen vanligtvis den process som beskrivs här.</span><span class="sxs-lookup"><span data-stu-id="fedb6-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="fedb6-160">Du kommer dock att ställa in olika värden.</span><span class="sxs-lookup"><span data-stu-id="fedb6-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="fedb6-161">Konfigurera transportföretag</span><span class="sxs-lookup"><span data-stu-id="fedb6-161">Set up carriers</span></span>

<span data-ttu-id="fedb6-162">Följ dessa steg för att ställa in ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="fedb6-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="fedb6-163">Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="fedb6-164">I åtgärdsfönstret, välj **Ny** för att lägga till ett transportföretag.</span><span class="sxs-lookup"><span data-stu-id="fedb6-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="fedb6-165">I rubriken anger du följande värden:</span><span class="sxs-lookup"><span data-stu-id="fedb6-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="fedb6-166">**Transportföretag:** *Demotransportföretag*</span><span class="sxs-lookup"><span data-stu-id="fedb6-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="fedb6-167">**Namn:** *Demotransportföretag*</span><span class="sxs-lookup"><span data-stu-id="fedb6-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="fedb6-168">**Läge:** *Mark*</span><span class="sxs-lookup"><span data-stu-id="fedb6-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="fedb6-169">Ange följande värden på snabbfliken **Översikt**:</span><span class="sxs-lookup"><span data-stu-id="fedb6-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fedb6-170">**Aktivera transportföretag:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="fedb6-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="fedb6-171">**Aktivera värdering av transportföretag:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="fedb6-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="fedb6-172">På snabbfliken **Tjänster** välj **Ny** för att lägga till en tjänst i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="fedb6-173">Ställ in följande värden för den nya tjänsten:</span><span class="sxs-lookup"><span data-stu-id="fedb6-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="fedb6-174">**Transportföretagstjänst:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="fedb6-175">**Namn:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="fedb6-176">**Transportmetod:** *Mark*</span><span class="sxs-lookup"><span data-stu-id="fedb6-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="fedb6-177">Ange godtyckliga värden för alla andra fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="fedb6-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="fedb6-178">(När du sparar den nya transportföretagets post skapas ett nytt leveranssätt och fältet **Leveranssätt** ställs in automatiskt.)</span><span class="sxs-lookup"><span data-stu-id="fedb6-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="fedb6-179">På snabbfliken **Bedömningsprofiler** välj **Ny** för att lägga till skapa en bedömningsprofil till rutnätet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="fedb6-180">Ställ in följande värden för den nya profilen:</span><span class="sxs-lookup"><span data-stu-id="fedb6-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="fedb6-181">**Bedömningsprofil:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="fedb6-182">**Namn:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="fedb6-183">**Tariffmotor:** *Demotariffmotor*</span><span class="sxs-lookup"><span data-stu-id="fedb6-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="fedb6-184">Ange godtyckliga värden för alla andra fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="fedb6-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="fedb6-185">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fedb6-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="fedb6-186">Mer information om hur du ställer in transportföretag hittar du på [Ställ in transportföretag](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="fedb6-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="fedb6-187">Ställa in konton för transportföretag</span><span class="sxs-lookup"><span data-stu-id="fedb6-187">Set up carrier service accounts</span></span>

<span data-ttu-id="fedb6-188">Följ dessa steg för att ställa in ett konto för transportföretag.</span><span class="sxs-lookup"><span data-stu-id="fedb6-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="fedb6-189">Gå till **Transporthantering \> Inställningar \> Klassificering \> Konto för transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="fedb6-190">I åtgärdsfönstret, välj **Ny** du vill lägga till ett konto för transportföretag.</span><span class="sxs-lookup"><span data-stu-id="fedb6-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="fedb6-191">Ställ in följande värden för det nya kontot:</span><span class="sxs-lookup"><span data-stu-id="fedb6-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="fedb6-192">**Transportföretag:** *Demotransportföretag*</span><span class="sxs-lookup"><span data-stu-id="fedb6-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="fedb6-193">**Transportföretagstjänst:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="fedb6-194">**Transportföretagets kundkontonummer:** Transportföretagets kundkontonummer som används för att verifiera och autentisera anslutningen till transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="fedb6-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="fedb6-195">Transportföretaget tillhandahåller detta värde.</span><span class="sxs-lookup"><span data-stu-id="fedb6-195">Your carrier will provide this value.</span></span> <span data-ttu-id="fedb6-196">Om du använder demotjänsten kan du ange ett godtyckligt värde.</span><span class="sxs-lookup"><span data-stu-id="fedb6-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="fedb6-197">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="fedb6-197">**Site:** *6*</span></span>
    - <span data-ttu-id="fedb6-198">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="fedb6-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="fedb6-199">Ofta är värdet **kundkontonummer för transportföretaget** det enda värde som krävs för att autentisera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="fedb6-200">Om din transportföretag kräver fler autentiseringsparametrar bör din organisation anpassa den här sidan för att lägga till extra fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="fedb6-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="fedb6-201">Ställa in policy för packning av behållare</span><span class="sxs-lookup"><span data-stu-id="fedb6-201">Set up a container packing policy</span></span>

<span data-ttu-id="fedb6-202">Följ dessa steg för att ställa in en policy för packning av behållare.</span><span class="sxs-lookup"><span data-stu-id="fedb6-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="fedb6-203">Om du inte redan har ställt in en ZPL-skrivardefinition, ska du använda appen Dokumentflödesagenten för att konfigurera det.</span><span class="sxs-lookup"><span data-stu-id="fedb6-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="fedb6-204">Mer information finns i [översikten över utskrift av dokument och relaterade avsnitt](../../fin-ops-core/dev-itpro/analytics/print-documents.md).</span><span class="sxs-lookup"><span data-stu-id="fedb6-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="fedb6-205">Gå till **Lagerstyrning \> Inställningar \> Behållare \> Policyer för packning av behållare**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="fedb6-206">I åtgärdsfönstret, välj **Ny** du vill lägga till en policy för packning av behållare.</span><span class="sxs-lookup"><span data-stu-id="fedb6-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="fedb6-207">Ange följande värden i nya policyns rubrik:</span><span class="sxs-lookup"><span data-stu-id="fedb6-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="fedb6-208">**Förpackningspolicy för behållare:** *demopolicy för packning*</span><span class="sxs-lookup"><span data-stu-id="fedb6-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="fedb6-209">**Beskrivning:** Ange en beskrivning för policyn</span><span class="sxs-lookup"><span data-stu-id="fedb6-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="fedb6-210">Ange följande värden på snabbfliken **Översikt**:</span><span class="sxs-lookup"><span data-stu-id="fedb6-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fedb6-211">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="fedb6-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="fedb6-212">**Standardplats för slutgiltig leverans:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="fedb6-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="fedb6-213">**Viktenhet:** *KG*</span><span class="sxs-lookup"><span data-stu-id="fedb6-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="fedb6-214">**Policyn för stängning av behållare:** *Automatiskt släpp*</span><span class="sxs-lookup"><span data-stu-id="fedb6-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="fedb6-215">**Policyn för stängning av behållare:** *Gör tillgänglig vid slutlig leveransplats*</span><span class="sxs-lookup"><span data-stu-id="fedb6-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="fedb6-216">Ange följande värden på snabbfliken **Behållarmanifest**:</span><span class="sxs-lookup"><span data-stu-id="fedb6-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fedb6-217">**Automatisk stängning av behållare:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="fedb6-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="fedb6-218">**Manifestkrav för behållare:** *Transporthantering*</span><span class="sxs-lookup"><span data-stu-id="fedb6-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="fedb6-219">**Skriv ut behållarinnehåll:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="fedb6-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="fedb6-220">Ange följande värden på snabbfliken **Utskrift av transportföretagsetikett**:</span><span class="sxs-lookup"><span data-stu-id="fedb6-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fedb6-221">**Skriv ut leveransetikett för behållare:** *Alltid*</span><span class="sxs-lookup"><span data-stu-id="fedb6-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="fedb6-222">**Skrivarnamn:** Namnet på den ZPL-skrivare som ska skriva ut leveransetiketter</span><span class="sxs-lookup"><span data-stu-id="fedb6-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="fedb6-223">Ställa in en förpackningsprofil</span><span class="sxs-lookup"><span data-stu-id="fedb6-223">Set up a packing profile</span></span>

<span data-ttu-id="fedb6-224">Följ dessa steg för att skapa en förpackningsprofil.</span><span class="sxs-lookup"><span data-stu-id="fedb6-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="fedb6-225">Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="fedb6-226">I åtgärdsfönstret, välj **Ny** du vill lägga till en förpackningsprofil i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="fedb6-227">Ställ in följande värden för den nya profilen:</span><span class="sxs-lookup"><span data-stu-id="fedb6-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="fedb6-228">**Förpackningsprofil-ID:** *Demoförpackningsprofil*</span><span class="sxs-lookup"><span data-stu-id="fedb6-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="fedb6-229">**Beskrivning:** Ange en beskrivning för profilen</span><span class="sxs-lookup"><span data-stu-id="fedb6-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="fedb6-230">**Förpackningspolicy för behållare:** *demopolicy för packning*</span><span class="sxs-lookup"><span data-stu-id="fedb6-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="fedb6-231">**Läge för behållar-ID:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="fedb6-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="fedb6-232">**Behållartyp:** *SmallBox*</span><span class="sxs-lookup"><span data-stu-id="fedb6-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="fedb6-233">Ställ in en kund att använda SPS-transportföretaget</span><span class="sxs-lookup"><span data-stu-id="fedb6-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="fedb6-234">Följ dessa steg om du vill ställa in en kund så att den kan använda det transportföretag som du skapat.</span><span class="sxs-lookup"><span data-stu-id="fedb6-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="fedb6-235">Gå till **Leverantörsreskontra \> kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="fedb6-236">I rutnätet hittar och väljer du kund *US-027*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="fedb6-237">I Åtgärdsfönstret, på fliken **Allmän**, i gruppen **Ställ in**, markerar du **Kundkonton för transportföretag**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="fedb6-238">På sidan **Kundkonton för transportföretag** i åtgärdsfönstret väljer du **Ny** om du vill lägga till ett konto i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="fedb6-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="fedb6-239">Ställ in följande värden för det nya kontot:</span><span class="sxs-lookup"><span data-stu-id="fedb6-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="fedb6-240">**Transportföretag:** *Demotransportföretag*</span><span class="sxs-lookup"><span data-stu-id="fedb6-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="fedb6-241">**Kundkontonummer för transportföretaget:** *12345* (Värdet är inte viktigt för detta scenario, men det refereras till i nästa avsnitt.)</span><span class="sxs-lookup"><span data-stu-id="fedb6-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="fedb6-242">Gå igenom exempelscenariot</span><span class="sxs-lookup"><span data-stu-id="fedb6-242">Go through the example scenario</span></span>

<span data-ttu-id="fedb6-243">När du har ställt in alla exempeldata enligt beskrivningen i det föregående avsnittet kan du gå igenom exempelscenariot.</span><span class="sxs-lookup"><span data-stu-id="fedb6-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="fedb6-244">Skapa en försäljningsorder och bearbeta arbetet</span><span class="sxs-lookup"><span data-stu-id="fedb6-244">Create a sales order and process the work</span></span>

<span data-ttu-id="fedb6-245">Följ dessa steg för att skapa en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="fedb6-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="fedb6-246">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fedb6-247">Skapa en försäljningsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="fedb6-248">I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj *US-027*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="fedb6-249">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fedb6-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="fedb6-250">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="fedb6-250">The new sales order is opened.</span></span> <span data-ttu-id="fedb6-251">På snabbfliken **Försäljningsorderhuvud** ange fältet **Transportföretagets kundkontonummer** till det värde du valt för den här kunden tidigare (*12345*).</span><span class="sxs-lookup"><span data-stu-id="fedb6-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="fedb6-252">I området **försäljningsorderrad** lägg till en försäljningsrad och ställ in följande värden för den:</span><span class="sxs-lookup"><span data-stu-id="fedb6-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="fedb6-253">**Artikelnummer:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fedb6-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="fedb6-254">**Kvantitet:** *1*</span><span class="sxs-lookup"><span data-stu-id="fedb6-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="fedb6-255">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="fedb6-255">**Site:** *6*</span></span>
    - <span data-ttu-id="fedb6-256">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="fedb6-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fedb6-257">Växla till vyn **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="fedb6-258">Ange följande värden på snabbfliken **Leverans**:</span><span class="sxs-lookup"><span data-stu-id="fedb6-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fedb6-259">**Transportföretag:** *Demotransportföretag*</span><span class="sxs-lookup"><span data-stu-id="fedb6-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="fedb6-260">**Transportföretagstjänst:** *Demotransportföretagstjänst*</span><span class="sxs-lookup"><span data-stu-id="fedb6-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="fedb6-261">Växla tillbaka till vyn **Rader**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="fedb6-262">Om du uppmanas att uppdatera leveranssättet för försäljningsraderna väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="fedb6-263">I imorådet **Försäljningsorderrader**, välj den orderrad som du har ställt in tidigare och välj sedan **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="fedb6-264">På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="fedb6-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="fedb6-265">Stäng sidan **Reservation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fedb6-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="fedb6-266">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fedb6-267">Arbete skapas för att flytta artiklar från plockplatsen till förpackningsstationen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="fedb6-268">I avsnittet **försäljningsorderrad** välj **Lagerställe \> Leveransdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="fedb6-269">På sidan **leveransinformation** gör en notering av leverans-ID.</span><span class="sxs-lookup"><span data-stu-id="fedb6-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="fedb6-270">Du behöver det när du förpackar försändelsen i förpackningsstationen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="fedb6-271">Stäng sidan **leveransinformation** om du vill återgå till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fedb6-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="fedb6-272">Anteckna försäljningsordernumret och gå sedan till **Lagerstyrning \> Arbete \> Allt arbete**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="fedb6-273">Använd försäljningsordernumret för att söka efter och välja det arbete som skapades för ordern.</span><span class="sxs-lookup"><span data-stu-id="fedb6-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="fedb6-274">I åtgärdsfönstret på fliken **Arbete** välj **Slutför arbete**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="fedb6-275">På sidan **Arbetet slutförs** i fältet **Användar-ID** välj ett användar-ID.</span><span class="sxs-lookup"><span data-stu-id="fedb6-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="fedb6-276">Sedan i åtgärdsfönstret, välj **Validera arbete**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="fedb6-277">Om arbetet går igenom valideringen, välj **Slutför arbete** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fedb6-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="fedb6-278">Arbetet markeras som slutfört för att simulera förflyttningen av artiklar till förpackningsstationen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="fedb6-279">Förpacka leveransen</span><span class="sxs-lookup"><span data-stu-id="fedb6-279">Pack the shipment</span></span>

<span data-ttu-id="fedb6-280">Följ dessa steg för att förpacka leveransen.</span><span class="sxs-lookup"><span data-stu-id="fedb6-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="fedb6-281">Gå till **Lagerstyrning \> Inställning \> Arbetare** och se till att ditt användarkonto är kopplat till ett arbetarkonto för lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="fedb6-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="fedb6-282">Gå till **lagerstyrning \> plocka och skapa behållare \> packa**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="fedb6-283">I dialogrutan **Välj packningsstation** ställ in följande värden:</span><span class="sxs-lookup"><span data-stu-id="fedb6-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fedb6-284">**Plats:** *6*</span><span class="sxs-lookup"><span data-stu-id="fedb6-284">**Site:** *6*</span></span>
    - <span data-ttu-id="fedb6-285">**Lagerställe:** *62*</span><span class="sxs-lookup"><span data-stu-id="fedb6-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="fedb6-286">**Plats:** *Packa*</span><span class="sxs-lookup"><span data-stu-id="fedb6-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="fedb6-287">**Förpackningsprofil-ID:** *Demoförpackningsprofil*</span><span class="sxs-lookup"><span data-stu-id="fedb6-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="fedb6-288">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-288">Select **OK**.</span></span>
1. <span data-ttu-id="fedb6-289">Sidan **Förpacka** visas.</span><span class="sxs-lookup"><span data-stu-id="fedb6-289">The **Pack** page appears.</span></span> <span data-ttu-id="fedb6-290">I ett produktionsscenario skannar arbetaren en licensinnehavare eller ett försändelse-ID.</span><span class="sxs-lookup"><span data-stu-id="fedb6-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="fedb6-291">I det här scenariot öppnar du dock sidan **Alla leveranser** och söker efter leveransnumret för den leverans som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="fedb6-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="fedb6-292">Ange sedan detta värde i fältet **ID-nummer eller leverans** på sidan **Förpacka**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="fedb6-293">Du kan även ange det leverans-ID som du har gjort en anteckning av tidigare.</span><span class="sxs-lookup"><span data-stu-id="fedb6-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="fedb6-294">Klicka på **Ny behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fedb6-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="fedb6-295">I dialogrutan som visas visas information om den nya behållaren.</span><span class="sxs-lookup"><span data-stu-id="fedb6-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="fedb6-296">Lämna standardvärdena och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="fedb6-297">På sidan **Förpacka** på snabbfliken **Artikelpackning** i fältet **Identifierare**, välj *A0002* vill förpacka artikeln.</span><span class="sxs-lookup"><span data-stu-id="fedb6-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="fedb6-298">Artikeln läggs till i behållaren.</span><span class="sxs-lookup"><span data-stu-id="fedb6-298">The item is added to the container.</span></span>
1. <span data-ttu-id="fedb6-299">I åtgärdsfönstret väljer du **Behållare för leverans**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="fedb6-300">Sidan **Behållare för leverans** som visas har en rad för den behållare som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="fedb6-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="fedb6-301">Däremot är fältet **Behållarmanifest-ID** i den raden tomt, eftersom du ännu inte har fått leveransetiketten och spårningsnumret från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="fedb6-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="fedb6-302">Klicka på **Stäng behållare** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fedb6-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="fedb6-303">I dialogrutan **Stäng behållare** ange fältet **Bruttovikt** till *1 kg* och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fedb6-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="fedb6-304">Leveransetiketten ska nu skrivas ut på den ZPL-skrivare som du valde tidigare.</span><span class="sxs-lookup"><span data-stu-id="fedb6-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="fedb6-305">Det bör likna följande exempel:</span><span class="sxs-lookup"><span data-stu-id="fedb6-305">It should resemble the following example.</span></span>

    <span data-ttu-id="fedb6-306">![Exempel på leveransetikett](media/sps-label-example.png "Exempel på leveransetikett")</span><span class="sxs-lookup"><span data-stu-id="fedb6-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="fedb6-307">Observera att värdena **Behållarmanifest-ID** och **Total frakt** har lagts till som mottagna från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="fedb6-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]