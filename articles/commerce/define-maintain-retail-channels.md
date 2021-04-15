---
title: Definiera och underhåll butikskanaler
description: Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Commerce. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.
author: mugunthanm
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7a2db169adafa1b8a0113024f3f58522c2cee6d2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802031"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="4a4ca-104">Definiera och underhålla butikskanaler</span><span class="sxs-lookup"><span data-stu-id="4a4ca-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4a4ca-105">Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="4a4ca-106">Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="4a4ca-107">Commerce stöder flera kanaler, till exempel onlinebutiker, kundtjänst och fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="4a4ca-108">En fysisk butik kallas för butik.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="4a4ca-109">Varje butik kan ha egna betalsätt, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="4a4ca-110">Du måste ställa in alla dessa element för en butik innan du skapar den.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="4a4ca-111">När du har skapat en butik tilldelar du produkter som du vill ha i butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="4a4ca-112">Du tilldelar också medarbetare, register och kunder till butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="4a4ca-113">Slutligen lägger du till den nya butiken i en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="4a4ca-114">Ställa in butiker</span><span class="sxs-lookup"><span data-stu-id="4a4ca-114">Setting up stores</span></span>

<span data-ttu-id="4a4ca-115">Innan du kan ställa in en butik i Commerce måste du utföra vissa obligatoriska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="4a4ca-116">Du kan sedan skapa butiken och lägga till information.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="4a4ca-117">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4a4ca-117">Prerequisites</span></span>

<span data-ttu-id="4a4ca-118">Du måste slutföra följande uppgifter innan du kan ställa in en butik:</span><span class="sxs-lookup"><span data-stu-id="4a4ca-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="4a4ca-119">Konfigurera organisationsstrukturen och ställ in organisationshierarkier för butikssortiment, lagerpåfyllnad och rapportering.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="4a4ca-120">Ställ in ett lager som avser butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="4a4ca-121">Ställa in nummerserier för butiker, butiksutdrag och utdragverifikationer.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="4a4ca-122">Konfigurera parametrar för Commerce.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="4a4ca-123">Ställa in betalsätt som butiken godkänner.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="4a4ca-124">Om du vill bearbeta kreditkortstransaktioner i kassorna kan du också ställa in betalningstjänster.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-124">To process credit card transactions at POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="4a4ca-125">Ställa in momsgrupper.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="4a4ca-126">Ställ in produkter.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-126">Set up products.</span></span> <span data-ttu-id="4a4ca-127">Som en del av den här uppgiften ställer du även in produkthierarkier, produktvarianter och produktsortiment.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="4a4ca-128">Ställa in produktprisgrupper.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-128">Set up product price groups.</span></span>
10. <span data-ttu-id="4a4ca-129">Ställ in produktprissättning.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-129">Set up product pricing.</span></span> <span data-ttu-id="4a4ca-130">Som en del av den här uppgiften ställer du också in prisjusteringar, rabatter och rabattperioder.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="4a4ca-131">Ställa in anställda.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a4ca-132">Du måste också tilldela behörigheter till rätta arbetarna, så att de kan skriva in och utföra uppgifter genom att använda kassasystem.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="4a4ca-133">Konfigurera kassaprofilerna som ska tilldelas till butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="4a4ca-134">Den här uppgiften innefattar många uppgifter, till exempel ställa in kassor, offlineprofiler, kvittoformat och kvittoprofiler.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="4a4ca-135">Granska alla uppgifter som ingår i förutsättningarna och slutför alla uppgifter som gäller för dig.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="4a4ca-136">Ställ in en butik</span><span class="sxs-lookup"><span data-stu-id="4a4ca-136">Set up a store</span></span>

<span data-ttu-id="4a4ca-137">När du har slutfört de obligatoriska uppgifterna slutför du dessa uppgifter för att ställa in detaljer för butiken:</span><span class="sxs-lookup"><span data-stu-id="4a4ca-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="4a4ca-138">Skapa en butik.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-138">Create a store.</span></span>
2. <span data-ttu-id="4a4ca-139">Tilldela en momsgrupp till butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="4a4ca-140">Tilldela accepterade betalsätt till butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="4a4ca-141">Lägg till uppgifter i produktbeskrivningarna för de produkter som du erbjuder i din butik.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="4a4ca-142">Du kan till exempel lägga till oformaterad text och bilder.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="4a4ca-143">Dessa produktdetaljer visas i olika kontext, till exempel i kassaregistret eller på utskrivna etiketter.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="4a4ca-144">Lägg till butiken till en standardorganisationshierarki som tilldelas för syftet **Butikssortiment**, **Butikspåfyllnad** eller **Butiksrapportering**.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="4a4ca-145">När du har ställt in en butik</span><span class="sxs-lookup"><span data-stu-id="4a4ca-145">After you set up a store</span></span>

<span data-ttu-id="4a4ca-146">När du har angett information för butiken slutför du dessa uppgifter för att skicka den nya butiksinformationen till POS.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="4a4ca-147">Konfigurera kassaregister för butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="4a4ca-148">Tilldela produktsortiment i butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="4a4ca-149">Bearbeta sortiment för att generera listan med produkter som ingår i sortimentet och för att göra produkterna tillgängliga i butiken.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="4a4ca-150">Skicka data, till exempel nummerserier, maskinvaruprofiler, kassaskärmlayouter till kassorna.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="4a4ca-151">Publicera butiken för att skicka butikdata till POS.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="4a4ca-152">Kör jobben för att skicka butiksinformationen till POS.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="4a4ca-153">Organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="4a4ca-153">Organization hierarchies</span></span>

<span data-ttu-id="4a4ca-154">Commerce använder organisationshierarkier för att strukturera kanaler.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="4a4ca-155">Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="4a4ca-156">När du ställer in butiker kan du lägga till dem till en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="4a4ca-157">Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="4a4ca-158">Om du vill använda Commerce säljfunktioner, måste konfigurationsnyckeln **Flera leveransadresser** till aktiveras.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-158">To use Commerce sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="4a4ca-159">Den här konfigurationsnyckeln finns i den konfigurationsnyckel för **handel** under **Systemadministration**\> **Konfiguration** \> **Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="4a4ca-160">Detta krävs på grund av olika valideringar baserat på leveransadressen som konfigurerats på försäljningsorderradnivå.</span><span class="sxs-lookup"><span data-stu-id="4a4ca-160">This is required due to various validations based on the delivery address configured at the sales order line level.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]