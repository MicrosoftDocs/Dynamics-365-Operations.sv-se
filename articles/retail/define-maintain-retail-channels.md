---
title: Definiera och underhåll butikskanaler
description: Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Retail. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.
author: mugunthanm
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f55099ad283e665965aad0684b3c9d87223d5ed7
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019380"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="a712b-104">Definiera och underhåll butikskanaler</span><span class="sxs-lookup"><span data-stu-id="a712b-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a712b-105">Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="a712b-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Dynamics 365 Retail.</span></span> <span data-ttu-id="a712b-106">Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.</span><span class="sxs-lookup"><span data-stu-id="a712b-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="a712b-107">Retail stöder flera butikskanaler, till exempel onlinebutiker, kundtjänst och fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="a712b-107">Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="a712b-108">En fysisk butik kallas för butik.</span><span class="sxs-lookup"><span data-stu-id="a712b-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="a712b-109">Varje butik kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="a712b-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="a712b-110">Du måste ställa in alla dessa element för en butik innan du skapar den.</span><span class="sxs-lookup"><span data-stu-id="a712b-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="a712b-111">När du har skapat en butik tilldelar du produkter som du vill ha i butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="a712b-112">Du tilldelar också medarbetare, register och kunder till butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="a712b-113">Slutligen lägger du till den nya butiken i en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="a712b-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="a712b-114">Ställa in butiker</span><span class="sxs-lookup"><span data-stu-id="a712b-114">Setting up retail stores</span></span>

<span data-ttu-id="a712b-115">Innan du kan ställa in en butik i Retail måste du utföra vissa obligatoriska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a712b-115">Before you can set up a retail store in Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="a712b-116">Du kan sedan skapa butiken och lägga till information.</span><span class="sxs-lookup"><span data-stu-id="a712b-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a712b-117">Krav</span><span class="sxs-lookup"><span data-stu-id="a712b-117">Prerequisites</span></span>

<span data-ttu-id="a712b-118">Du måste slutföra följande uppgifter innan du kan ställa in en butik:</span><span class="sxs-lookup"><span data-stu-id="a712b-118">You must complete the following tasks before you can set up a retail store:</span></span>

1. <span data-ttu-id="a712b-119">Konfigurera organisationsstrukturen och ställ in organisationshierarkier för butikssortiment, lagerpåfyllnad och rapportering.</span><span class="sxs-lookup"><span data-stu-id="a712b-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="a712b-120">Ställ in ett lager som avser butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-120">Set up a warehouse that represents the retail store.</span></span>
3. <span data-ttu-id="a712b-121">Ställa in nummerserier för butiker, butiksutdrag och utdragverifikationer.</span><span class="sxs-lookup"><span data-stu-id="a712b-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="a712b-122">Konfigurera parametrar för Detaljhandel.</span><span class="sxs-lookup"><span data-stu-id="a712b-122">Configure parameters for Retail.</span></span>
5. <span data-ttu-id="a712b-123">Ställa in betalningsmetoder som butiken godkänner.</span><span class="sxs-lookup"><span data-stu-id="a712b-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="a712b-124">Om du vill bearbeta kreditkortstransaktioner i butikskassorna kan du också ställa in betalningstjänster.</span><span class="sxs-lookup"><span data-stu-id="a712b-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="a712b-125">Ställa in momsgrupper.</span><span class="sxs-lookup"><span data-stu-id="a712b-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="a712b-126">Ställ in butiksprodukter.</span><span class="sxs-lookup"><span data-stu-id="a712b-126">Set up retail products.</span></span> <span data-ttu-id="a712b-127">Som en del av den här uppgiften ställer du även in butiksprodukthierarkier, produktvarianter och produktsortiment.</span><span class="sxs-lookup"><span data-stu-id="a712b-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="a712b-128">Ställa in produktprisgrupper.</span><span class="sxs-lookup"><span data-stu-id="a712b-128">Set up product price groups.</span></span>
10. <span data-ttu-id="a712b-129">Ställa in butiksproduktprissättning.</span><span class="sxs-lookup"><span data-stu-id="a712b-129">Set up retail product pricing.</span></span> <span data-ttu-id="a712b-130">Som en del av den här uppgiften ställer du också in prisjusteringar, rabatter och rabattperioder.</span><span class="sxs-lookup"><span data-stu-id="a712b-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="a712b-131">Ställa in anställda.</span><span class="sxs-lookup"><span data-stu-id="a712b-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a712b-132">Du måste också tilldela behörigheter till rätta arbetarna, så att de kan skriva in och utföra uppgifter genom att använda Retail POS-system.</span><span class="sxs-lookup"><span data-stu-id="a712b-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Retail POS system.</span></span>

12. <span data-ttu-id="a712b-133">Konfigurera Retail POS-profilerna som ska tilldelas till butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="a712b-134">Den här uppgiften innefattar många uppgifter, till exempel ställa in kassor, offlineprofiler, kvittoformat och kvittoprofiler.</span><span class="sxs-lookup"><span data-stu-id="a712b-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="a712b-135">Granska alla uppgifter som ingår i förutsättningarna och slutför alla uppgifter som gäller för dig.</span><span class="sxs-lookup"><span data-stu-id="a712b-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="a712b-136">Skapa en butik</span><span class="sxs-lookup"><span data-stu-id="a712b-136">Set up a retail store</span></span>

<span data-ttu-id="a712b-137">När du har slutfört de obligatoriska uppgifterna slutför du dessa uppgifter för att ställa in detaljer för butiken:</span><span class="sxs-lookup"><span data-stu-id="a712b-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1. <span data-ttu-id="a712b-138">Skapa en butik.</span><span class="sxs-lookup"><span data-stu-id="a712b-138">Create a retail store.</span></span>
2. <span data-ttu-id="a712b-139">Tilldela en momsgrupp till butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="a712b-140">Tilldela accepterade betalningsmetoder till butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="a712b-141">Lägg till uppgifter i produktbeskrivningarna för de produkter som du erbjuder i din butik.</span><span class="sxs-lookup"><span data-stu-id="a712b-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="a712b-142">Du kan till exempel lägga till oformaterad text och bilder.</span><span class="sxs-lookup"><span data-stu-id="a712b-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="a712b-143">Dessa produktdetaljer visas i olika kontext, till exempel i kassaregistret eller på utskrivna etiketter.</span><span class="sxs-lookup"><span data-stu-id="a712b-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="a712b-144">Lägg till butiken till en standardorganisationshierarki som tilldelas för syftet **Butikssortiment**, **Butikspåfyllnad** eller **Butiksrapportering**.</span><span class="sxs-lookup"><span data-stu-id="a712b-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="a712b-145">När du har ställt in en butik</span><span class="sxs-lookup"><span data-stu-id="a712b-145">After you set up a retail store</span></span>

<span data-ttu-id="a712b-146">När du har angett information för butiken slutför du dessa uppgifter för att skicka den nya butiksinformationen till Retail POS.</span><span class="sxs-lookup"><span data-stu-id="a712b-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1. <span data-ttu-id="a712b-147">Konfigurera kassaregister för butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="a712b-148">Tilldela produktsortiment i butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="a712b-149">Bearbeta sortiment för att generera listan med produkter som ingår i sortimentet och för att göra produkterna tillgängliga i butiken.</span><span class="sxs-lookup"><span data-stu-id="a712b-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4. <span data-ttu-id="a712b-150">Skicka data, till exempel nummerserier, maskinvaruprofiler, kassaskärmlayouter till Retail POS-kassorna.</span><span class="sxs-lookup"><span data-stu-id="a712b-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5. <span data-ttu-id="a712b-151">Publicera butiken för att skicka butiksdata till Retail POS.</span><span class="sxs-lookup"><span data-stu-id="a712b-151">Publish the retail store to send store data to Retail POS.</span></span>
6. <span data-ttu-id="a712b-152">Kör jobben för att skicka butiksinformationen till Retail POS.</span><span class="sxs-lookup"><span data-stu-id="a712b-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="a712b-153">Organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="a712b-153">Organization hierarchies</span></span>

<span data-ttu-id="a712b-154">Retail använder organisationshierarkier för att strukturera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="a712b-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="a712b-155">Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag.</span><span class="sxs-lookup"><span data-stu-id="a712b-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="a712b-156">När du ställer in butiker kan du lägga till dem till en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="a712b-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="a712b-157">Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering.</span><span class="sxs-lookup"><span data-stu-id="a712b-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>
