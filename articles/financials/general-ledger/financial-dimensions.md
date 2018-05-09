---
title: Ekonomiska dimensioner
description: "Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: dccd8cc7e99454a2adb1c710d73792e62d510bd7
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="financial-dimensions"></a><span data-ttu-id="c82e3-103">Ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="c82e3-103">Financial dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c82e3-104">Den här ämnet beskriver de olika typerna av ekonomiska dimensioner och hur de ställs in.</span><span class="sxs-lookup"><span data-stu-id="c82e3-104">This topic explains the various types of financial dimensions and how they are set up.</span></span>

<span data-ttu-id="c82e3-105">Använd sidan **Ekonomiska dimensioner** om du vill skapa ekonomiska dimensioner som du kan använda som kontosegment för delade kontoplaner.</span><span class="sxs-lookup"><span data-stu-id="c82e3-105">Use the **Financial dimensions** page to create financial dimensions that you can use as account segments for charts of accounts.</span></span> <span data-ttu-id="c82e3-106">Det finns två typer av ekonomiska dimensioner: anpassade dimensioner och enhetsbaserad dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c82e3-106">There are two types of financial dimensions: custom dimensions and entity-backed dimensions.</span></span> <span data-ttu-id="c82e3-107">Anpassade dimensioner delas av alla juridiska personer, och värdena anges och hanteras av användaren.</span><span class="sxs-lookup"><span data-stu-id="c82e3-107">Custom dimensions are shared across legal entities, and the values are entered and maintained by users.</span></span> <span data-ttu-id="c82e3-108">För enhetsbaserade dimensioner definieras värden på andra ställen i systemet, till exempel kunder och butiker.</span><span class="sxs-lookup"><span data-stu-id="c82e3-108">For entity-backed dimensions, the values are defined somewhere else in the system, such as Customers or Stores entities.</span></span> <span data-ttu-id="c82e3-109">Vissa enhetsbaserade dimensioner delas av alla juridiska personer och enhetsbaserade dimensioner är företagsspecifka.</span><span class="sxs-lookup"><span data-stu-id="c82e3-109">Some entity-backed dimensions are shared across legal entities, whereas other entity-backed dimensions are company-specific.</span></span> 

<span data-ttu-id="c82e3-110">Använd formuläret om du vill tilldela ytterligare egenskaper för varje **Värden för ekonomiska dimensioner** efter att du har skapat ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c82e3-110">After you've created the financial dimensions, use the **Financial dimension values** page to assign additional properties to each financial dimension.</span></span> 

<span data-ttu-id="c82e3-111">Du kan använda ekonomiska dimensioner som representerar juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="c82e3-111">You can use financial dimensions to represent legal entities.</span></span> <span data-ttu-id="c82e3-112">Du behöver inte skapa de juridiska personerna i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c82e3-112">You don't have to create the legal entities in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c82e3-113">Ekonomiska dimensioner är inte emellertid avsedda för för juridiska personers drift- eller affärskrav.</span><span class="sxs-lookup"><span data-stu-id="c82e3-113">However, financial dimensions aren’t designed to address the operational or business requirements of legal entities.</span></span> <span data-ttu-id="c82e3-114">Internredovisningsfunktionen i Finance and Operations har utformats att endast fokusera på de redovisningsposter som skapas av respektive transaktion.</span><span class="sxs-lookup"><span data-stu-id="c82e3-114">The interunit accounting functionality in Finance and Operations is designed to address only the accounting entries that are created by each transaction.</span></span> 

<span data-ttu-id="c82e3-115">Utvärdera dina arbetsprocesser i följande områden för att avgöra, innan du ställer in ekonomiska dimensioner som juridiska personer, om den här inställningen kommer att fungera i din organisation:</span><span class="sxs-lookup"><span data-stu-id="c82e3-115">Before you set up financial dimensions as legal entities, evaluate your business processes in the following areas to determine whether this setup will work for your organization:</span></span>

- <span data-ttu-id="c82e3-116">Lager</span><span class="sxs-lookup"><span data-stu-id="c82e3-116">Inventory</span></span>
- <span data-ttu-id="c82e3-117">Försäljning och inköp mellan ekonomiska dimensioner och juridiska personer</span><span class="sxs-lookup"><span data-stu-id="c82e3-117">Sales and purchases between financial dimensions and legal entities</span></span>
- <span data-ttu-id="c82e3-118">Mmomsberäkning och rapportering</span><span class="sxs-lookup"><span data-stu-id="c82e3-118">Sales tax calculation and reporting</span></span>
- <span data-ttu-id="c82e3-119">Driftsrapportering</span><span class="sxs-lookup"><span data-stu-id="c82e3-119">Operational reporting</span></span>

<span data-ttu-id="c82e3-120">Nedan följer några av begränsningarna:</span><span class="sxs-lookup"><span data-stu-id="c82e3-120">Here are some of the limitations:</span></span>

- <span data-ttu-id="c82e3-121">Du kan bara använda momsfunktioner med juridiska personer, inte med ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c82e3-121">You can use sales tax functionality only with legal entities, not with financial dimensions.</span></span>
- <span data-ttu-id="c82e3-122">Vissa rapporter omfattar inte ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c82e3-122">Some reports don't include financial dimensions.</span></span> <span data-ttu-id="c82e3-123">Därför kan du behöva ändra rapporterna om du vill rapportera per ekonomiska dimension.</span><span class="sxs-lookup"><span data-stu-id="c82e3-123">Therefore, to report by financial dimension, you might have to modify the reports.</span></span>

## <a name="custom-dimensions"></a><span data-ttu-id="c82e3-124">Anpassade dimensioner</span><span class="sxs-lookup"><span data-stu-id="c82e3-124">Custom dimensions</span></span>

<span data-ttu-id="c82e3-125">Om du vill skapa en användardefinierad ekonomisk dimension väljer du fältet **Använd värden från** och **&lt; Anpassad dimension &gt;**.</span><span class="sxs-lookup"><span data-stu-id="c82e3-125">To create a user-defined financial dimension, in the **Use values from** field, select **&lt; Custom dimension &gt;**.</span></span> <span data-ttu-id="c82e3-126">Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="c82e3-126">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span> <span data-ttu-id="c82e3-127">Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck (-).</span><span class="sxs-lookup"><span data-stu-id="c82e3-127">You can enter characters that remain the same for each dimension value, such as letters or a hyphen (-).</span></span> <span data-ttu-id="c82e3-128">Du kan även ange nummertecken (\#) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång ett dimensionsvärde skapas.</span><span class="sxs-lookup"><span data-stu-id="c82e3-128">You can also enter number signs (\#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="c82e3-129">Använd ett nummertecken (\#) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav.</span><span class="sxs-lookup"><span data-stu-id="c82e3-129">Use a number sign (\#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span> <span data-ttu-id="c82e3-130">Det här fältet för formatmask är bara tillgängligt när du väljer **&lt; Anpassad dimension &gt;** i fältet **Använd värden från**.</span><span class="sxs-lookup"><span data-stu-id="c82e3-130">The field for the format mask is available only when you select **&lt; Custom dimension &gt;** in the **Use values from** field.</span></span>

<span data-ttu-id="c82e3-131">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="c82e3-131">**Example**</span></span>

<span data-ttu-id="c82e3-132">Om du vill begränsa dimensionsvärdet till bokstäverna "CC" och tre siffror anger du **CC-\#\#\#** som formatmask.</span><span class="sxs-lookup"><span data-stu-id="c82e3-132">To limit the dimension value to the letters "CC" and three numbers, enter **CC-\#\#\#** as the format mask.</span></span>

## <a name="entity-backed-dimensions"></a><span data-ttu-id="c82e3-133">Enhetsstödda dimensioner</span><span class="sxs-lookup"><span data-stu-id="c82e3-133">Entity-backed dimensions</span></span>

<span data-ttu-id="c82e3-134">Om du vill skapa en enhetsstödd ekonomisk dimension väljer du en systemdefinierad enhet på vilken den ekonomiska dimensionen ska baseras i fältet **Använd värden från**.</span><span class="sxs-lookup"><span data-stu-id="c82e3-134">To create an entity-backed financial dimension, in the **Use values from** field, select a system-defined entity to base the financial dimension on.</span></span> <span data-ttu-id="c82e3-135">Värden för ekonomisk dimension skapas utifrån den här entiteten.</span><span class="sxs-lookup"><span data-stu-id="c82e3-135">Financial dimension values are then created from that entity.</span></span> <span data-ttu-id="c82e3-136">Om du till exempel vill skapa dimensionsvärden för projekt väljer du **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c82e3-136">For example, to create dimension values for projects, select **Projects**.</span></span> <span data-ttu-id="c82e3-137">Ett dimensionsvärde skapas sedan för varje projektnamnet.</span><span class="sxs-lookup"><span data-stu-id="c82e3-137">A dimension value is then created for each project name.</span></span> <span data-ttu-id="c82e3-138">Sidan **värden för ekonomiska dimensioner** visar värdena för entiteten.</span><span class="sxs-lookup"><span data-stu-id="c82e3-138">The **Financial dimension values** page shows the values for the entity.</span></span> <span data-ttu-id="c82e3-139">Om dessa värden är företagsspecifika visar sidan också företaget.</span><span class="sxs-lookup"><span data-stu-id="c82e3-139">If those values are company-specific, the page also shows the company.</span></span>

## <a name="activating-dimensions"></a><span data-ttu-id="c82e3-140">Dimensionsaktivering</span><span class="sxs-lookup"><span data-stu-id="c82e3-140">Activating dimensions</span></span>

<span data-ttu-id="c82e3-141">När du aktiverar en ekonomisk dimension uppdateras registret så att det inkluderar namnet på den ekonomiska dimensionen.</span><span class="sxs-lookup"><span data-stu-id="c82e3-141">When you activate a financial dimension, the table is updated so that it includes the name of the financial dimension.</span></span> <span data-ttu-id="c82e3-142">Borttagna dimensioner raderas.</span><span class="sxs-lookup"><span data-stu-id="c82e3-142">Deleted dimensions are removed.</span></span> <span data-ttu-id="c82e3-143">Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="c82e3-143">You can enter dimension values before you activate a financial dimension.</span></span> <span data-ttu-id="c82e3-144">Men en ekonomisk dimension kan inte utnyttjas någonstans tills den har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c82e3-144">However, a financial dimension can't be consumed anywhere until it's activated.</span></span> <span data-ttu-id="c82e3-145">Du kan t.ex. inte lägga till en ekonomisk dimension till en kontostruktur förrän den ekonomiska dimensionen har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c82e3-145">For example, you can't add a financial dimension to an account structure until the financial dimension has been activated.</span></span> <span data-ttu-id="c82e3-146">När du klickar på **aktivera**, uppdateras alla dimensioner och visar statusändringar.</span><span class="sxs-lookup"><span data-stu-id="c82e3-146">When you click **Activate**, all dimensions are updated and show status changes.</span></span> 

## <a name="translations"></a><span data-ttu-id="c82e3-147">Översättningar</span><span class="sxs-lookup"><span data-stu-id="c82e3-147">Translations</span></span>

<span data-ttu-id="c82e3-148">På sidan **textöversättning** kan du ange text för den valda ekonomiska dimensionen på olika språk.</span><span class="sxs-lookup"><span data-stu-id="c82e3-148">On the **Text translation** page, you can enter text for the selected financial dimension in various languages.</span></span> <span data-ttu-id="c82e3-149">På sidan **Huvudkontoöversättning** kan du ange text för huvudkontot på olika språk.</span><span class="sxs-lookup"><span data-stu-id="c82e3-149">On the **Main account translation** page, you can enter text for the main account in various languages.</span></span> 

## <a name="legal-entity-overrides"></a><span data-ttu-id="c82e3-150">Juridisk person åsidosätter</span><span class="sxs-lookup"><span data-stu-id="c82e3-150">Legal entity overrides</span></span>

<span data-ttu-id="c82e3-151">Alla dimensioner är inte giltiga för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="c82e3-151">Not all dimensions are valid for all legal entities.</span></span> <span data-ttu-id="c82e3-152">Vissa dimensioner är dessutom endast relevanta för en viss period.</span><span class="sxs-lookup"><span data-stu-id="c82e3-152">Additionally, some dimensions might be relevant only for a specific period.</span></span> <span data-ttu-id="c82e3-153">I dessa fall kan du använda avsnittet **Juridisk person åsidosätter** för att identifiera vilka företag som dimensionen ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.</span><span class="sxs-lookup"><span data-stu-id="c82e3-153">In these cases, you can use the **Legal entity overrides** section to specify the companies that the dimension should be suspended for, the owner, and the period when the dimension is active.</span></span>

## <a name="deleting-financial-dimensions"></a><span data-ttu-id="c82e3-154">Ta bort ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="c82e3-154">Deleting financial dimensions</span></span>

<span data-ttu-id="c82e3-155">För att upprätthålla datans referensintegritet kan ekonomiska dimensioner sällan tas bort.</span><span class="sxs-lookup"><span data-stu-id="c82e3-155">To help maintain referential integrity of the data, financial dimensions can rarely be deleted.</span></span> <span data-ttu-id="c82e3-156">Om du försöker ta bort en ekonomisk dimension utvärderas följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="c82e3-156">If you try to delete a financial dimension, the following criteria are evaluated:</span></span>

- <span data-ttu-id="c82e3-157">Har den ekonomiska dimensionen använts på bokförda eller ej bokförda transaktioner eller någon typ av dimensionsvärdekombination?</span><span class="sxs-lookup"><span data-stu-id="c82e3-157">Has the financial dimension been used on any posted or unposted transactions, or any type of dimension value combination?</span></span>
- <span data-ttu-id="c82e3-158">Är den ekonomiska dimensionen i en aktiv kontostruktur, avancerad regelstruktur, eller ekonomisk dimension angiven?</span><span class="sxs-lookup"><span data-stu-id="c82e3-158">Is the financial dimension used in any active account structure, advanced rule structure, or financial dimension set?</span></span>
- <span data-ttu-id="c82e3-159">Ingår den ekonomiska dimensionen i standardformat för integrering av ekonomisk dimension?</span><span class="sxs-lookup"><span data-stu-id="c82e3-159">Is the financial dimension part of a default financial dimension integration format?</span></span>
- <span data-ttu-id="c82e3-160">Har den ekonomiska dimensionen ställts in som standarddimension?</span><span class="sxs-lookup"><span data-stu-id="c82e3-160">Has the financial dimension been set up as a default dimension?</span></span>

<span data-ttu-id="c82e3-161">Du kan inte radera den ekonomiska dimensionen om något av villkoren är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="c82e3-161">If any of the criteria are met, you can't delete the financial dimension.</span></span>


<span data-ttu-id="c82e3-162">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="c82e3-162">For more information, see the following topics:</span></span>
- [<span data-ttu-id="c82e3-163">Definiera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="c82e3-163">Define financial dimensions</span></span>](tasks/define-financial-dimensions.md)
- [<span data-ttu-id="c82e3-164">Underhåll standardmallar för ekonomisk dimension</span><span class="sxs-lookup"><span data-stu-id="c82e3-164">Maintain financial dimension default templates</span></span>](tasks/maintain-financial-dimension-default-templates.md)

