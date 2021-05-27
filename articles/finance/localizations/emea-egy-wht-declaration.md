---
title: Källskattedeklaration för Egypten
description: I det här avsnittet beskrivs hur du konfigurerar och genererar formuläret för källskattedeklaration för Egypten.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8c9aaa3868167806ce3189d724621991ec7e53eb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022821"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="36b81-103">Källskattedeklaration för Egypten (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="36b81-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="36b81-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="36b81-104">Overview</span></span>
<span data-ttu-id="36b81-105">Det här ämnet beskriver hur du ställer in och genererar källskattedeklarationen och källskattedeklaration formulär 41 och 11 för juridiska personer i Egypten</span><span class="sxs-lookup"><span data-stu-id="36b81-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="36b81-106">Alla egyptiska företag måste förbereda formuläret 41, där det sammanfattas alla skatter som tas ut från lokala leverantörer och serviceleverantörer.</span><span class="sxs-lookup"><span data-stu-id="36b81-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="36b81-107">Utöver formulär 41 måste formulär 11 genereras om du vill detaljerad information om alla behållna skatter från utländska leverantörer.</span><span class="sxs-lookup"><span data-stu-id="36b81-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="36b81-108">Rapporten **Källskattedeklaration** i Dynamics 365 Finance inkluderar följande rapporter:</span><span class="sxs-lookup"><span data-stu-id="36b81-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="36b81-109">Deklarationsformulär nr.</span><span class="sxs-lookup"><span data-stu-id="36b81-109">Declaration form No.</span></span> <span data-ttu-id="36b81-110">41</span><span class="sxs-lookup"><span data-stu-id="36b81-110">41</span></span>
- <span data-ttu-id="36b81-111">Deklarationsformulär nr.</span><span class="sxs-lookup"><span data-stu-id="36b81-111">Declaration form No.</span></span> <span data-ttu-id="36b81-112">11</span><span class="sxs-lookup"><span data-stu-id="36b81-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="36b81-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="36b81-113">Prerequisites</span></span>
<span data-ttu-id="36b81-114">Den primära adressen för den juridiska personen måste dock finnas i Egypten.</span><span class="sxs-lookup"><span data-stu-id="36b81-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="36b81-115">I arbetsytan **utgiftshantering** aktiverar du följande funktion:</span><span class="sxs-lookup"><span data-stu-id="36b81-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="36b81-116">**Global källskatt**</span><span class="sxs-lookup"><span data-stu-id="36b81-116">**Global withholding tax**</span></span>

<span data-ttu-id="36b81-117">Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36b81-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="36b81-118">Gå till **Skatt** > **Inställningar** > **Parametrar** > **Redovisningsparametrar** och sedan, på fliken **Källskatt** anger du **Aktivera global källskatt** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="36b81-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="36b81-119">I arbetsytan **Elektroniskt rapportering**, importera följande elektroniskt rapporteringsformat från databasen:</span><span class="sxs-lookup"><span data-stu-id="36b81-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="36b81-120">Momsdeklaration Excel (EG)</span><span class="sxs-lookup"><span data-stu-id="36b81-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="36b81-121">Formatet ovan är baserat på **Skattedeklarationsmodell** och använder **Mappning för skattedeklarationsmodell**.</span><span class="sxs-lookup"><span data-stu-id="36b81-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="36b81-122">Denna ytterligare konfiguration importeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="36b81-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="36b81-123">Mer information om hur du importerar konfigurationer för elektronisk rapportering finns i [Hämta konfigurationer för elektronisk rapportering från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="36b81-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="36b81-124">Hämta konfigurationer för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="36b81-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="36b81-125">Implementeringen av WHT deklarationsformulär för Egypten är baserad på konfigurationer av Elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="36b81-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="36b81-126">Mer information om möjligheterna med och koncepten med konfigurerbara rapporter finns i [Elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="36b81-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="36b81-127">Information om hur du testar produktion och användares godkännande (UAT), följ instruktionerna i ämnet [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="36b81-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="36b81-128">Om du vill generera källskattedeklarationerna i en egyptisk juridisk person som är här måste du föra över följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="36b81-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="36b81-129">Skattedeklarationsmodell.version.82.xml eller senare version</span><span class="sxs-lookup"><span data-stu-id="36b81-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="36b81-130">Skattedeklarationsmodell mappning.version.82.133.xml eller senare version</span><span class="sxs-lookup"><span data-stu-id="36b81-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="36b81-131">Skattedeklaration Excel (EG).version.82.21 eller en senare version</span><span class="sxs-lookup"><span data-stu-id="36b81-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="36b81-132">När nedladdningen är klar av ER-konfigurationerna från Lifecycle Services (LCS) eller den globala databasen gör du så här.</span><span class="sxs-lookup"><span data-stu-id="36b81-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="36b81-133">På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="36b81-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="36b81-134">På sidan **Konfigurationer** på åtgärdspanelen väljer du **Exchange > Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="36b81-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="36b81-135">Ladda upp alla filer i den ordning som de finns listade i föregående punkter.</span><span class="sxs-lookup"><span data-stu-id="36b81-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="36b81-136">När alla konfigurationer har överförts ska konfigurationsträdet finnas med i Finance.</span><span class="sxs-lookup"><span data-stu-id="36b81-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="36b81-137">Ställa in appspecifika parametrar</span><span class="sxs-lookup"><span data-stu-id="36b81-137">Set up application-specific parameters</span></span>

<span data-ttu-id="36b81-138">Alternativet appspecifika parametrar låter användare fastställa kriterierna för hur skattetransaktioner kommer att klassificeras och beräknas på varje rad i en genererad rapport beroende på konfigurationen av **Källskattegrupp för artiklar** eller andra kriterier som upprättats i sökdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="36b81-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="36b81-139">Källdeklarationsformulär 41 innehåller en specifik kolumn där källskattetransaktionen måste klassificeras i enlighet med skattemyndighetens klassificering med namnet **Rabattkodtyp**.</span><span class="sxs-lookup"><span data-stu-id="36b81-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="36b81-140">I stället för att inkludera dessa nya klassificeringar som ny postdata när transaktionerna publiceras kommer klassificeringarna att bestämmas baserat på olika uppslag som introducerades i **Konfigurationer** > **ställa in programspecifika parametrar** > **inställning** för att uppfylla kraven för källskattrapporter för Egypten.</span><span class="sxs-lookup"><span data-stu-id="36b81-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="36b81-141">Följande konfiguration används för att klassificera transaktionerna i källdeklarationsformulär 41-rapporten:</span><span class="sxs-lookup"><span data-stu-id="36b81-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="36b81-142">**DiscountTaxTypeLookup** -> Kolumnnr 18</span><span class="sxs-lookup"><span data-stu-id="36b81-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="36b81-143">Gör på följande sätt om du vill ställa in de olika sökningar som används för att generera momsdeklarationer och relaterade redovisningsrapporter.</span><span class="sxs-lookup"><span data-stu-id="36b81-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="36b81-144">I arbetsytan **Elektronisk rapportering**, välj **Konfigurations** > **Inställningar** för att ställa in reglerna för att identifiera hur transaktioner klassificeras i WHT-deklarationsrapporten.</span><span class="sxs-lookup"><span data-stu-id="36b81-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="36b81-145">Markera den aktuella versionen och på snabbfliken **Uppslag** markera söknamnet.</span><span class="sxs-lookup"><span data-stu-id="36b81-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="36b81-146">Till exempel **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="36b81-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="36b81-147">I den här sökningen identifieras listan över rabatttyper som skattemyndigheten kräver.</span><span class="sxs-lookup"><span data-stu-id="36b81-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="36b81-148">På snabbfliken **Villkor** markerar du **Lägg till** och på den nya raden i kolumnen **Sökresultat** markerar du den relaterade rad som representerar klassificeringen i **Kolumn 18**.</span><span class="sxs-lookup"><span data-stu-id="36b81-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="36b81-149">I kolumnen **Källskattegrupp för artiklar** väljer du den relaterade kod som används för att identifiera klassificeringen.</span><span class="sxs-lookup"><span data-stu-id="36b81-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="36b81-150">Till exempel **Tillåten rabatt**.</span><span class="sxs-lookup"><span data-stu-id="36b81-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="36b81-151">Upprepa steg 3 och 4 för alla tillgängliga sökningar.</span><span class="sxs-lookup"><span data-stu-id="36b81-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="36b81-152">Välj **Lägg till** för att inkludera den sista postraden och i kolumnen **Sökresultat** välj **Inte aktuellt**.</span><span class="sxs-lookup"><span data-stu-id="36b81-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="36b81-153">Välj i de återstående kolumnerna **Ej tom**.</span><span class="sxs-lookup"><span data-stu-id="36b81-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="36b81-154">Ställ in redovisningsparametrar</span><span class="sxs-lookup"><span data-stu-id="36b81-154">Set up General ledger parameters</span></span>

<span data-ttu-id="36b81-155">Om du vill generera en rapport för deklarationsformulär i Microsoft Excel-format definierar du ett ER-format på sidan **Allmänna redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="36b81-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="36b81-156">Gå till **Skatt** > **Inställningar** > **Redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="36b81-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="36b81-157">På fliken **källskatt** i fältet **WHT mappning av deklarationsformat**, välj **WHT-deklaration Excel (EG)**.</span><span class="sxs-lookup"><span data-stu-id="36b81-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="36b81-158">Om du lämnar fältet tomt genereras standard momsrapporten i SSRS-format.</span><span class="sxs-lookup"><span data-stu-id="36b81-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Deklarationsformulär](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="36b81-160">Generera källdeklarationsformulären</span><span class="sxs-lookup"><span data-stu-id="36b81-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="36b81-161">Processen för att förbereda och skicka ett källskattedeklarationsformulär för en viss period baseras på källskattetransaktionerna som bokförs under kvittnings- och redovisningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="36b81-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="36b81-162">Mer information om global källskatt finns i [Global källskatt](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36b81-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="36b81-163">Gör på följande sätt när du vill generera skattedeklarationsrapporten.</span><span class="sxs-lookup"><span data-stu-id="36b81-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="36b81-164">Gå till **Skatt** > **Deklarationer** > **Källskatt** > \**Betalning av källskatt*.</span><span class="sxs-lookup"><span data-stu-id="36b81-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="36b81-165">Välj kvittningsperiod och sedan från-datum för rapporten.</span><span class="sxs-lookup"><span data-stu-id="36b81-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="36b81-166">Ange transaktionsdatum och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="36b81-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="36b81-167">I dialogrutan som öppnas väljer du en eller flera av formulärtyperna **Formulär nr. 41**, **Formulär nr. 11** eller **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="36b81-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="36b81-168">Om du väljer **Ingen** genereras standardrapporten.</span><span class="sxs-lookup"><span data-stu-id="36b81-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="36b81-169">Välj språk.</span><span class="sxs-lookup"><span data-stu-id="36b81-169">Select the language.</span></span> <span data-ttu-id="36b81-170">Alla rapporter översätts i **en-us** och **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="36b81-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="36b81-171">Ange filial och namn för den bank där skattebetalningen ska betalas.</span><span class="sxs-lookup"><span data-stu-id="36b81-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="36b81-172">Välj affärstyp och ange sedan check- och dokumentnummer.</span><span class="sxs-lookup"><span data-stu-id="36b81-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="36b81-173">Ange enhetstyp.</span><span class="sxs-lookup"><span data-stu-id="36b81-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="36b81-174">Ange namnet på den person som har registrerats för att tilldela formuläret och välj **OK** för att bekräfta rapportgenereringen.</span><span class="sxs-lookup"><span data-stu-id="36b81-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
