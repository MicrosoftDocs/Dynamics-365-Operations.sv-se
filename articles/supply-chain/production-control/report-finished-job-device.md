---
title: Rapportera som färdigt från jobbkortsenheten
description: I det här avsnittet beskrivs hur du konfigurerar systemet så att användarna av en jobbkort kan rapportera färdiga produkter från en tillverkningsorder till lagret.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403272"
---
# <a name="report-as-finished-from-the-job-card-device"></a><span data-ttu-id="aeb49-103">Rapportera som färdigt från jobbkortsenheten</span><span class="sxs-lookup"><span data-stu-id="aeb49-103">Report as finished from the job card device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeb49-104">Arbetstagarna använder **rapportförlopp** på jobbkortsenheten för att rapportera kvantiteter som har slutförts för ett produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="aeb49-104">Workers use the **Report progress** page on the job card device to report quantities that have been completed for a production job.</span></span>

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a><span data-ttu-id="aeb49-105">Kontrollera om kvantiteter som rapporteras som färdiga ska läggas till i lagret</span><span class="sxs-lookup"><span data-stu-id="aeb49-105">Control whether quantities that are reported as finished are added to inventory</span></span>

<span data-ttu-id="aeb49-106">Följ de här stegen om du vill kontrollera om och hur de kvantiteter som rapporteras som färdiga i den sista operationen ska läggas till i lagret.</span><span class="sxs-lookup"><span data-stu-id="aeb49-106">To control whether and how the quantities that are reported as finished on the last operation should be added to inventory, follow these steps.</span></span>

1. <span data-ttu-id="aeb49-107">Gå till **Produktionsstyrning \> Inställningar \> Tillverkningskörning \> Standarder för produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-107">Go to **Product control \> Setup \> Manufacturing execution \> Production order defaults**.</span></span>
1. <span data-ttu-id="aeb49-108">På fliken **rapportera som färdigt** anger du fältet **Uppdatera färdig rapport online** till något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="aeb49-108">On the **Report as finished** tab, set the **Update finished report on-line** field to one of the following values:</span></span>

    - <span data-ttu-id="aeb49-109">**Nej** – Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste operationen.</span><span class="sxs-lookup"><span data-stu-id="aeb49-109">**No** – No quantity will be added to inventory when quantities are reported on the last operation.</span></span> <span data-ttu-id="aeb49-110">Status för produktionsorder kommer aldrig att förändras.</span><span class="sxs-lookup"><span data-stu-id="aeb49-110">The status of the production order will never change.</span></span>
    - <span data-ttu-id="aeb49-111">**Status + kvantitet** – status för tillverkningsordern ändras till *rapporterat som färdigt* och kvantiteten rapporteras som färdig till lagret.</span><span class="sxs-lookup"><span data-stu-id="aeb49-111">**Status + Quantity** – The status of the production order will change to *Reported as finished*, and the quantity will be reported as finished to inventory.</span></span>
    - <span data-ttu-id="aeb49-112">**Kvantitet** – Kvantiteten kommer att rapporteras som färdig till lager, men status för produktionsordern kommer aldrig att förändras.</span><span class="sxs-lookup"><span data-stu-id="aeb49-112">**Quantity** – The quantity will be reported as finished to inventory, but the status of the production order will never change.</span></span>
    - <span data-ttu-id="aeb49-113">**Status** – Endast status produktion kommer aldrig att förändras.</span><span class="sxs-lookup"><span data-stu-id="aeb49-113">**Status** – Only the status of the production order will change.</span></span> <span data-ttu-id="aeb49-114">Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste operationen.</span><span class="sxs-lookup"><span data-stu-id="aeb49-114">No quantities will be added to inventory when quantities are reported on the last operation.</span></span>

> [!NOTE]
> <span data-ttu-id="aeb49-115">Kvantiteter spåras inte i lagret om de operationer som de rapporteras som färdiga inte definieras som den senaste operationen.</span><span class="sxs-lookup"><span data-stu-id="aeb49-115">Quantities aren't tracked in inventory if the operations that they are reported as finished on aren't defined as the last operation.</span></span> <span data-ttu-id="aeb49-116">Dessa kvantiteter kan dock användas för att visa förloppet.</span><span class="sxs-lookup"><span data-stu-id="aeb49-116">However, those quantities can be used to view progress.</span></span> <span data-ttu-id="aeb49-117">De kan också inkluderas i regler som kontrollerar om arbetare kan starta nästa operation innan en definierad tröskel för rapporterade kvantiteter för den föregående operationen uppnås.</span><span class="sxs-lookup"><span data-stu-id="aeb49-117">They can also be included in rules that control whether workers can start the next operation before a defined threshold of reported quantities on the previous operation is reached.</span></span> <span data-ttu-id="aeb49-118">Du kan definiera dessa regler på fliken **Kvantitetsvalidering** på sidan **Produktionsorderns standardvärden**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-118">You can define these rules on the **Quantity validation** tab of the **Production order defaults** page.</span></span>

<span data-ttu-id="aeb49-119">För mer information om hur du arbetar med sidan **Standarder för produktionsorder** se [produktionsparametrar i tillverkningskörning](production-parameters-manufacturing-execution.md).</span><span class="sxs-lookup"><span data-stu-id="aeb49-119">For more information about how to work with the **Production order defaults** page, see [Production parameters in Manufacturing execution](production-parameters-manufacturing-execution.md).</span></span>

## <a name="report-batch-controlled-items-as-finished"></a><span data-ttu-id="aeb49-120">Rapportera batchkontrollerade artiklar som färdiga</span><span class="sxs-lookup"><span data-stu-id="aeb49-120">Report batch-controlled items as finished</span></span>

<span data-ttu-id="aeb49-121">Jobbkortsenheten stöder tre scenarier för rapportering av batch-artiklar.</span><span class="sxs-lookup"><span data-stu-id="aeb49-121">The job card device supports three scenarios for reporting on batch items.</span></span> <span data-ttu-id="aeb49-122">Dessa scenarier gäller både artiklar som aktiveras för avancerade lagerprocesser och artiklar som inte är aktiverade för avancerade lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="aeb49-122">These scenarios apply both to items that are enabled for advanced warehouse processes and to items that aren't enabled for advanced warehouse processes.</span></span>

- <span data-ttu-id="aeb49-123">**Manuellt tilldelade batchnummer:** arbetare registrerar ett anpassat batchnummer.</span><span class="sxs-lookup"><span data-stu-id="aeb49-123">**Manually assigned batch numbers:** Workers enter a custom batch number.</span></span> <span data-ttu-id="aeb49-124">Det här batchnumret kan komma från en extern källa som inte är känd för systemet.</span><span class="sxs-lookup"><span data-stu-id="aeb49-124">This batch number might come from an external source that isn't known to the system.</span></span>
- <span data-ttu-id="aeb49-125">**Fördefinierade batchnummer:** arbetare väljer ett batchnummer i en lista med batchnummer som genereras automatiskt innan tillverknings ordern frisläpps till jobbkortsenheten.</span><span class="sxs-lookup"><span data-stu-id="aeb49-125">**Predefined batch numbers:** Workers select a batch number in a list of batch numbers that the system automatically generates before the production order is released to the job card device.</span></span>
- <span data-ttu-id="aeb49-126">**Fast batchnummer:** arbetare anger eller väljer inte ett batchnummer.</span><span class="sxs-lookup"><span data-stu-id="aeb49-126">**Fixed batch numbers:** Workers don't enter or select a batch number.</span></span> <span data-ttu-id="aeb49-127">I stället tilldelar systemet automatiskt ett batchnummer till produktionsordern innan den frigörs.</span><span class="sxs-lookup"><span data-stu-id="aeb49-127">Instead, the system automatically assigns a batch number to the production order before it's released.</span></span>

<span data-ttu-id="aeb49-128">För att aktivera varje scenario följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="aeb49-128">To enable each scenario, follow these steps.</span></span>

1. <span data-ttu-id="aeb49-129">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-129">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="aeb49-130">Välj produkten som ska konfigureras.</span><span class="sxs-lookup"><span data-stu-id="aeb49-130">Select the product to configure.</span></span>
1. <span data-ttu-id="aeb49-131">På snabbfliken **Hantera lager** i fältet **batchnummergrupp** väljer du den spårningsnummergrupp som har angetts som stöd för ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="aeb49-131">On the **Manage inventory** FastTab, in the **Batch number group** field, select the tracking number group that is set up to support your scenario.</span></span>

> [!NOTE]
> <span data-ttu-id="aeb49-132">Om ingen batchnummergrupp tilldelas till en batchkontrollerad produkt innehåller jobbkortsenheten som standard manuell inmatning för batchnumret vid rapportering som färdigt.</span><span class="sxs-lookup"><span data-stu-id="aeb49-132">By default, if no batch number group is assigned to a batch-controlled product, the job card device provides manual entry for the batch number during reporting as finished.</span></span>

<span data-ttu-id="aeb49-133">I följande underavsnitt beskrivs hur du ställer in spårningsnummergrupper för att stödja var och en av de tre scenarierna för rapportering av batch-artiklar.</span><span class="sxs-lookup"><span data-stu-id="aeb49-133">The following subsections describe how to set up tracking number groups to support each of the three scenarios for reporting on batch items.</span></span>

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a><span data-ttu-id="aeb49-134">Aktivera rapportering av batchnummer på jobbkortsenheten</span><span class="sxs-lookup"><span data-stu-id="aeb49-134">Enable batch number reporting on the job card device</span></span>

<span data-ttu-id="aeb49-135">Om du vill att dina jobbkortsenheter ska kunna acceptera ett batchnummer när de rapporteras som färdiga, måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner (i den här ordningen):</span><span class="sxs-lookup"><span data-stu-id="aeb49-135">To enable your job card devices to accept a batch number during reporting as finished, you must use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the following features (in this order):</span></span>

1. <span data-ttu-id="aeb49-136">Förbättrad användarupplevelse för dialogrutan Rapportförlopp i jobbkortenheten</span><span class="sxs-lookup"><span data-stu-id="aeb49-136">Improved user experience for the Report progress dialog in the Job Card Device</span></span>
1. <span data-ttu-id="aeb49-137">Aktivera för att ange batch- och serienummer vid rapportering som färdiga från jobbkortenheten (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="aeb49-137">Enable to enter batch and serial numbers while reporting as finished from the Job Card Device (Preview)</span></span>

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a><span data-ttu-id="aeb49-138">Skapa en spårningsnummergrupp som gör att arbetare manuellt kan tilldela ett batchnummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-138">Set up a tracking number group that lets workers manually assign a batch number</span></span>

<span data-ttu-id="aeb49-139">För att tillåta manuellt tilldelade batchnummer följer du dessa steg för att ställa in en spårningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="aeb49-139">To allow for manually assigned batch numbers, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="aeb49-140">Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-140">Go to **Inventory management \> Setup \> Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="aeb49-141">Skapa eller välj den spårningsnummergrupp som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="aeb49-141">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="aeb49-142">På snabbfliken **Allmänt** ställer du in **Manuellt** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-142">On the **General** FastTab, set the **Manual** option to **Yes**.</span></span>

    <span data-ttu-id="aeb49-143">![Sidan spårningsnummergrupper](media/tracking-number-group-manual.png "Sidan spårningsnummergrupper")</span><span class="sxs-lookup"><span data-stu-id="aeb49-143">![Tracking number groups page](media/tracking-number-group-manual.png "Tracking number groups page")</span></span>

1. <span data-ttu-id="aeb49-144">Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.</span><span class="sxs-lookup"><span data-stu-id="aeb49-144">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="aeb49-145">När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger är en textruta där arbetare kan ange vilket värde som helst.</span><span class="sxs-lookup"><span data-stu-id="aeb49-145">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides is a text box where workers can enter any value.</span></span>

<span data-ttu-id="aeb49-146">![Rapportstatussida med ett fält för manuella batchnummer](media/job-card-device-batch-manual.png "Rapportstatussida med ett fält för manuella batchnummer")</span><span class="sxs-lookup"><span data-stu-id="aeb49-146">![Report progress page with a field for manual batch numbers](media/job-card-device-batch-manual.png "Report progress page with a field for manual batch numbers")</span></span>

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a><span data-ttu-id="aeb49-147">Ställ in en spårningsnummergrupp som innehåller en lista över fördefinierade batchnummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-147">Set up a tracking number group that provides a list of predefined batch numbers</span></span>

<span data-ttu-id="aeb49-148">För att tillhandahålla fördefinierade batchnummer följer du dessa steg för att ställa in en spårningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="aeb49-148">To provide a list of predefined batch numbers, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="aeb49-149">Gå till **Lagerhantering \> Inställning > Dimensioner \> Spårningsnummergrupper**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-149">Go to **Inventory management \> Setup > Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="aeb49-150">Skapa eller välj den spårningsnummergrupp som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="aeb49-150">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="aeb49-151">På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-151">On the **General** FastTab, set the **Only for inventory transactions** option to **Yes**.</span></span>
1. <span data-ttu-id="aeb49-152">Använd fältet **per kvantitet** om du vill dela upp batchnummer per kvantitet, baserat på det värde som du anger.</span><span class="sxs-lookup"><span data-stu-id="aeb49-152">Use the **Per qty.** field to split batch numbers per quantity, based on the value that you enter.</span></span> <span data-ttu-id="aeb49-153">Du har till exempel en tillverkningsorder på tio enheter och fältet **per kvantitet** anges till *2*.</span><span class="sxs-lookup"><span data-stu-id="aeb49-153">For example, you have a production order for ten pieces, and the **Per qty.** field is set to *2*.</span></span> <span data-ttu-id="aeb49-154">I det här fallet kommer fem batchnummer att tilldelas tillverkningsordern när den skapas.</span><span class="sxs-lookup"><span data-stu-id="aeb49-154">In this case, five batch numbers will be assigned to the production order when it's created.</span></span>

    <span data-ttu-id="aeb49-155">![Sidan spårningsnummergrupper](media/tracking-number-group-predefined.png "Sidan spårningsnummergrupper")</span><span class="sxs-lookup"><span data-stu-id="aeb49-155">![Tracking number groups page](media/tracking-number-group-predefined.png "The Tracking number groups page")</span></span>

1. <span data-ttu-id="aeb49-156">Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.</span><span class="sxs-lookup"><span data-stu-id="aeb49-156">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="aeb49-157">När du använder det här scenario kommer fältet **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten är en listruta där arbetare måste välja ett fördefinierat värde.</span><span class="sxs-lookup"><span data-stu-id="aeb49-157">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides is a drop-down list where workers must select a predefined value.</span></span>

<span data-ttu-id="aeb49-158">![Rapportstatussida med en lista över fördefinierade batchnummer](media/job-card-device-batch-predefined.png "Rapportstatussida med en lista över fördefinierade batchnummer")</span><span class="sxs-lookup"><span data-stu-id="aeb49-158">![Report progress page with a list of predefined batch numbers](media/job-card-device-batch-predefined.png "Report progress page with a list of predefined batch numbers")</span></span>

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a><span data-ttu-id="aeb49-159">Skapa en spårningsnummergrupp som automatiskt tilldelar batchnummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-159">Set up a tracking number group that automatically assigns batch numbers</span></span>

<span data-ttu-id="aeb49-160">Om batchnummer ska tilldelas automatiskt, utan indata från arbetare, följer du dessa steg för att skapa en spårningsnummergrupp.</span><span class="sxs-lookup"><span data-stu-id="aeb49-160">If batch numbers should be assigned automatically, without worker input, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="aeb49-161">Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-161">Go to **Inventory management \> Setup \> Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="aeb49-162">Skapa eller välj den spårningsnummergrupp som du vill ställa in.</span><span class="sxs-lookup"><span data-stu-id="aeb49-162">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="aeb49-163">På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-163">On the **General** FastTab, set the **Only for inventory transactions** option to **No**.</span></span>
1. <span data-ttu-id="aeb49-164">Ange alternativet **Manuell** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-164">Set the **Manual** option to **No**.</span></span>

    <span data-ttu-id="aeb49-165">![Sidan spårningsnummergrupper](media/tracking-number-group-fixed.png "Sidan spårningsnummergrupper")</span><span class="sxs-lookup"><span data-stu-id="aeb49-165">![Tracking number groups page](media/tracking-number-group-fixed.png "Tracking number groups page")</span></span>

1. <span data-ttu-id="aeb49-166">Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.</span><span class="sxs-lookup"><span data-stu-id="aeb49-166">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="aeb49-167">När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger visas ett värde med arbetare kan inte redigera det.</span><span class="sxs-lookup"><span data-stu-id="aeb49-167">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides shows a value, but workers can't edit it.</span></span>

<span data-ttu-id="aeb49-168">![Rapportstatussida med ett fast batchnummer](media/job-card-device-batch-fixed.png "Rapportstatussida med ett fast batchnummer")</span><span class="sxs-lookup"><span data-stu-id="aeb49-168">![Report progress page with a fixed batch number](media/job-card-device-batch-fixed.png "Report progress page with a fixed batch number")</span></span>

## <a name="report-as-finished-to-a-license-plate"></a><span data-ttu-id="aeb49-169">Rapportera som färdig till ett ID-nummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-169">Report as finished to a license plate</span></span>

<span data-ttu-id="aeb49-170">Avancerade lagerprocesser kan använda dimensionen ID-nummer för att spåra lager på lagerställen som har ställts in för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="aeb49-170">Advanced warehouse processes can use the license plate dimension to track inventory on warehouse locations that have been set up for this purpose.</span></span> <span data-ttu-id="aeb49-171">I det här fallet krävs ID-nummer när en arbetare rapporterar kvantiteter som färdiga.</span><span class="sxs-lookup"><span data-stu-id="aeb49-171">In this case, the license plate number is required when a worker reports quantities as finished.</span></span>

### <a name="enable-license-plate-reporting-and-label-printing"></a><span data-ttu-id="aeb49-172">Aktivera rapportering och etikettutskrift av ID-nummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-172">Enable license plate reporting and label printing</span></span>

<span data-ttu-id="aeb49-173">Om du vill använda funktionerna som beskrivs i det här avsnittet måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner (i den här ordningen):</span><span class="sxs-lookup"><span data-stu-id="aeb49-173">To use the features that are described in this section, you must use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the following features (in this order):</span></span>

1. <span data-ttu-id="aeb49-174">ID-nummer för rapportering som färdig har lagts till på jobbkortenheten</span><span class="sxs-lookup"><span data-stu-id="aeb49-174">License plate for reporting as finished added to the Job Card Device</span></span>
1. <span data-ttu-id="aeb49-175">Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten</span><span class="sxs-lookup"><span data-stu-id="aeb49-175">Enable automatic generation of license plate number when reporting as finished in the job card device</span></span>
1. <span data-ttu-id="aeb49-176">Skriv ut etikett från jobbkortenhet</span><span class="sxs-lookup"><span data-stu-id="aeb49-176">Print label from Job Card Device</span></span>

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a><span data-ttu-id="aeb49-177">Konfigurera rapportering som färdig till ett ID-nummer</span><span class="sxs-lookup"><span data-stu-id="aeb49-177">Set up reporting as finished to a license plate</span></span>

<span data-ttu-id="aeb49-178">Om du vill kontrollera om arbetare ska återanvända ett befintligt ID-nummer eller skapa ett nytt ID-nummer när de rapporterar kvantiteter som färdiga följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="aeb49-178">To control whether workers should reuse an existing license plate or generate a new license plate when they report quantities as finished, follow these steps.</span></span>

1. <span data-ttu-id="aeb49-179">Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera jobbkort för enheter**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-179">Go to **Production control \> Setup \> Manufacturing execution \> Configure job card for devices**.</span></span>
2. <span data-ttu-id="aeb49-180">Ställ in följande alternativ för varje enhet:</span><span class="sxs-lookup"><span data-stu-id="aeb49-180">Set the following options for each device:</span></span>

    - <span data-ttu-id="aeb49-181">**Generera ID-nummer** – Ange det här alternativet **Ja** om du vill generera ett nytt ID-nummer för varje rapport som färdig.</span><span class="sxs-lookup"><span data-stu-id="aeb49-181">**Generate license plate** – Set this option to **Yes** to generate a new license plate for each report as finished.</span></span> <span data-ttu-id="aeb49-182">Ställ in det på **Nej** om ett befintligt ID-nummer ska användas för varje rapport som färdig.</span><span class="sxs-lookup"><span data-stu-id="aeb49-182">Set it to **No** if an existing license plate should be used for each report as finished.</span></span>
    - <span data-ttu-id="aeb49-183">**Skriv ut etikett** – Ställ in det här alternativet på **Ja** om arbetare måste skriva ut ett ID-nummer för varje rapport som färdig.</span><span class="sxs-lookup"><span data-stu-id="aeb49-183">**Print label** – Set this option to **Yes** if the worker must print a license plate label for each report as finished.</span></span> <span data-ttu-id="aeb49-184">Ställ in det på **Nej** om ingen etikett behövs.</span><span class="sxs-lookup"><span data-stu-id="aeb49-184">Set it to **No** if no label is required.</span></span> 

<span data-ttu-id="aeb49-185">![Konfigurera jobbkort för enhetssidan](media/config-job-card-raf.png "Konfigurera jobbkort för enhetssidan")</span><span class="sxs-lookup"><span data-stu-id="aeb49-185">![Configure job card for devices page](media/config-job-card-raf.png "Configure job card for devices page")</span></span>

> [!NOTE]
> <span data-ttu-id="aeb49-186">För att konfigurera etiketten, gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Dokumentflöde**.</span><span class="sxs-lookup"><span data-stu-id="aeb49-186">To configure the label, go to **Warehouse management \> Setup \> Document routing \> Document routing**.</span></span> <span data-ttu-id="aeb49-187">Mer information finns i [Aktivera utskrift av ID-nummeretiketter](../warehousing/tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="aeb49-187">For more information, see [Enable license plate label printing](../warehousing/tasks/license-plate-label-printing.md).</span></span>
