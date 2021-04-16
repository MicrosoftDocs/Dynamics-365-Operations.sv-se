---
title: Felsök inköpsorder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med inköpsorder.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 964f31c21faae6a947174f637624aca917881297
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841465"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="f38fa-103">Felsök inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f38fa-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="f38fa-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f38fa-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="f38fa-105">En åtgärd kan endast slutföras efter att radnumret har distribuerats fullständigt.</span><span class="sxs-lookup"><span data-stu-id="f38fa-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="f38fa-106">Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.</span><span class="sxs-lookup"><span data-stu-id="f38fa-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f38fa-107">Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="f38fa-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f38fa-108">Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f38fa-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="f38fa-109">När inköpsorder importeras via datahantering följer inte inköpsordernummer det steg som definieras i systemparametrar.</span><span class="sxs-lookup"><span data-stu-id="f38fa-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-110">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-110">Issue description</span></span>

<span data-ttu-id="f38fa-111">Som standard genereras automatiskt radnummer för inköpsorderrader som importeras via dataentiteten *Inköpsorderrader V2* använder inte det systemradnummer som anges i systemparametrar.</span><span class="sxs-lookup"><span data-stu-id="f38fa-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="f38fa-112">Om du skapar en inköpsorder manuellt och lägger till rader via användargränssnittet (UI), ökas radnumren korrekt.</span><span class="sxs-lookup"><span data-stu-id="f38fa-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="f38fa-113">Om du använder DMF (ramverk för datahantering) ökas de emellertid inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="f38fa-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="f38fa-114">Det här problemet beror på att när du importerar rader via DMF, om radnummer inte redan har tilldelats i den importerade enheten, använder systemet DMF-metoden för att tilldela dem.</span><span class="sxs-lookup"><span data-stu-id="f38fa-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="f38fa-115">Den metoden ökar alltid radnummer med en.</span><span class="sxs-lookup"><span data-stu-id="f38fa-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="f38fa-116">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-116">Issue workaround</span></span>

<span data-ttu-id="f38fa-117">Kontrollera att de önskade radnumren redan ges i fälten för radnummer för dataenhet när du importerar inköpsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="f38fa-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="f38fa-118">I det här fallet skrivs inte radnumren över med DMF.</span><span class="sxs-lookup"><span data-stu-id="f38fa-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="f38fa-119">En standard momsgrupp och en standard kassarabatt fylls inte i från fakturakontot.</span><span class="sxs-lookup"><span data-stu-id="f38fa-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="f38fa-120">Om du använder ett fakturakonto som skiljer sig från kundkontot, fylls inte en standard momsgrupp och en standard kassarabatt i från fakturakontot när en inköpsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="f38fa-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="f38fa-121">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f38fa-121">This behavior is by design.</span></span> <span data-ttu-id="f38fa-122">Standardvärdena för momsgrupp, kassarabatter och annan prisinformation baseras på kundkontot, inte på fakturakontot.</span><span class="sxs-lookup"><span data-stu-id="f38fa-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="f38fa-123">Jag får felmeddelandet "objektreferensen har inte angetts" vid en inköpsorderbekräftelse, eller ett undantag har utlösts av målet för ett anropsundantag uppstår under bokföringen av leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="f38fa-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="f38fa-124">Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.</span><span class="sxs-lookup"><span data-stu-id="f38fa-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f38fa-125">Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="f38fa-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f38fa-126">Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f38fa-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="f38fa-127">En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade.</span><span class="sxs-lookup"><span data-stu-id="f38fa-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-128">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-128">Issue description</span></span>

<span data-ttu-id="f38fa-129">Du får följande fel: "En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade."</span><span class="sxs-lookup"><span data-stu-id="f38fa-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f38fa-130">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-130">Issue resolution</span></span>

<span data-ttu-id="f38fa-131">Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.</span><span class="sxs-lookup"><span data-stu-id="f38fa-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f38fa-132">Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="f38fa-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f38fa-133">Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f38fa-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="f38fa-134">Kan jag bara visa inköpsorder som jag har skapat?</span><span class="sxs-lookup"><span data-stu-id="f38fa-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="f38fa-135">Den här funktionen är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="f38fa-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="f38fa-136">Kan jag reservera lager och skapa transaktioner mot registrerat lager på en inköpsorder?</span><span class="sxs-lookup"><span data-stu-id="f38fa-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-137">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-137">Issue description</span></span>

<span data-ttu-id="f38fa-138">Även när artiklar är i ett *registrerat* tillstånd på en inköpsorder kan du ändå reservera lagret.</span><span class="sxs-lookup"><span data-stu-id="f38fa-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="f38fa-139">Med andra ord kan du skapa transaktioner mot det registrerade lagret.</span><span class="sxs-lookup"><span data-stu-id="f38fa-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f38fa-140">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="f38fa-140">Reproduce the issue</span></span>

<span data-ttu-id="f38fa-141">Följande procedur anger ett sätt att skapa reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="f38fa-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f38fa-142">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f38fa-142">Create a purchase order.</span></span>
2. <span data-ttu-id="f38fa-143">Registrera inköpsorderrad.</span><span class="sxs-lookup"><span data-stu-id="f38fa-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="f38fa-144">Lägg märke till att du kan generera reservationer eller transaktioner mot det registrerade lagret.</span><span class="sxs-lookup"><span data-stu-id="f38fa-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f38fa-145">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-145">Issue resolution</span></span>

<span data-ttu-id="f38fa-146">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f38fa-146">This behavior is by design.</span></span> <span data-ttu-id="f38fa-147">Förväntat är att registrerade artiklar har anlänt fysiskt i lagret eller lagret och att de därför är tillgängliga för reservation.</span><span class="sxs-lookup"><span data-stu-id="f38fa-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="f38fa-148">Inköpsorder avspeglar inte språkinställningarna för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="f38fa-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-149">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-149">Issue description</span></span>

<span data-ttu-id="f38fa-150">Produktnamnet på en inköpsorder visas på systemspråket i stället för språket som är inställt för den juridiska person där inköpsordern skapades.</span><span class="sxs-lookup"><span data-stu-id="f38fa-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f38fa-151">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="f38fa-151">Reproduce the issue</span></span>

<span data-ttu-id="f38fa-152">Följande procedur anger ett sätt att skapa reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="f38fa-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f38fa-153">Ställ in system språket på *EN-US* (amerikansk engelska).</span><span class="sxs-lookup"><span data-stu-id="f38fa-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="f38fa-154">Kontrollera att det finns en produkt där *EN-US* och *DE* (tyska) språken finns kvar för översättningar av produktnamnet.</span><span class="sxs-lookup"><span data-stu-id="f38fa-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="f38fa-155">Ändra språket för en juridisk person till *DE*.</span><span class="sxs-lookup"><span data-stu-id="f38fa-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="f38fa-156">I den juridiska personen där *DE* har ställts in som språk skapar du en inköpsorder som innehåller produkten.</span><span class="sxs-lookup"><span data-stu-id="f38fa-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="f38fa-157">Observera att produktnamnet fortfarande visas i amerikansk engelska (systemspråket).</span><span class="sxs-lookup"><span data-stu-id="f38fa-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f38fa-158">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-158">Issue resolution</span></span>

<span data-ttu-id="f38fa-159">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f38fa-159">This behavior is by design.</span></span> <span data-ttu-id="f38fa-160">På inköpsorder visas produkten alltid på systemspråket.</span><span class="sxs-lookup"><span data-stu-id="f38fa-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="f38fa-161">Inköpsorderns språk används när en bekräftelsejournal skapas.</span><span class="sxs-lookup"><span data-stu-id="f38fa-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="f38fa-162">Den lista över godkända leverantörer per produktenhet tillåter inte att giltighetsdatumet ändras.</span><span class="sxs-lookup"><span data-stu-id="f38fa-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-163">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-163">Issue description</span></span>

<span data-ttu-id="f38fa-164">En produkt har en godkänd leverantör som t.ex. är ett giltighetsdatum på 11 januari 2018 (*01/11/2018*) och ett utgångsdatum för *aldrig*.</span><span class="sxs-lookup"><span data-stu-id="f38fa-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 (*01/11/2018*), and an expiration date of *Never*.</span></span> <span data-ttu-id="f38fa-165">Om du försöker ändra giltighetsdatum till 10 januari 2018 (*01/10/2018*) eller 12 januari 2018 (*01/12/2018*) visas följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="f38fa-165">If you try to change the effective date to January 10, 2018 (*01/10/2018*), or January 12, 2018 (*01/12/2018*), you receive the following error:</span></span>

> <span data-ttu-id="f38fa-166">Det går inte att skapa en post i listan över godkända leverantörer (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="f38fa-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="f38fa-167">Värdet för utgångsdatum måste vara större än eller lika med värdet effektiv.</span><span class="sxs-lookup"><span data-stu-id="f38fa-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f38fa-168">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-168">Issue resolution</span></span>

<span data-ttu-id="f38fa-169">Du kan bara utöka den period som leverantören är godkänd för.</span><span class="sxs-lookup"><span data-stu-id="f38fa-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="f38fa-170">Följande regler gäller:</span><span class="sxs-lookup"><span data-stu-id="f38fa-170">The following rules apply:</span></span>

- <span data-ttu-id="f38fa-171">Om du vill ändra giltighetsdatumet så att det är tidigare än någon av de befintliga posterna (perioderna) för artikelleverantören, måste utgångsdatumet för den nya perioden vara före alla utgångsdatum i de befintliga posterna.</span><span class="sxs-lookup"><span data-stu-id="f38fa-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="f38fa-172">Om du vill ändra utgångsdatum så att det blir senare än någon av de befintliga perioderna måste giltighetsdatumet vara efter det senaste utgångsdatumet i någon befintlig post.</span><span class="sxs-lookup"><span data-stu-id="f38fa-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="f38fa-173">Om du vill minska den totala perioden som leverantören har godkänts för måste du ta bort eller ändra befintliga poster.</span><span class="sxs-lookup"><span data-stu-id="f38fa-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="f38fa-174">Alternativt kan du använda växeln **trunkera** under importen.</span><span class="sxs-lookup"><span data-stu-id="f38fa-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="f38fa-175">Den här växeln tar bort alla befintliga poster i registret för godkända leverantörer per artikel.</span><span class="sxs-lookup"><span data-stu-id="f38fa-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="f38fa-176">I det här scenariot som beskrivs i ärendebeskrivningen, där en post har giltighetsdatumet *01/11/2018* och ett utgångsdatum för *aldrig*, kan du importera en ny post som har ett giltighetsdatum på *01/10/2018* och ett utgångsdatum för *aldrig*.</span><span class="sxs-lookup"><span data-stu-id="f38fa-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never*, you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="f38fa-177">Du kan dock inte förkorta perioden så att giltighetsdatumet uppdateras till *01/12/2018* via datahantering.</span><span class="sxs-lookup"><span data-stu-id="f38fa-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="f38fa-178">Du måste göra ändringen genom användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="f38fa-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-name-isnt-synced"></a><span data-ttu-id="f38fa-179">När jag har ändrat leveransadressen i ett inköpsorderhuvud synkroniseras inte leveransnamnet.</span><span class="sxs-lookup"><span data-stu-id="f38fa-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f38fa-180">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f38fa-180">Issue description</span></span>

<span data-ttu-id="f38fa-181">Adressen i huvudet på en inköpsorder uppdateras till en adress som inte är en leveransadress.</span><span class="sxs-lookup"><span data-stu-id="f38fa-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="f38fa-182">Även om adressen uppdateras på inköpsordern uppdateras inte leveransnamnet baserat på den uppdaterade adressen.</span><span class="sxs-lookup"><span data-stu-id="f38fa-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f38fa-183">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f38fa-183">Issue resolution</span></span>

<span data-ttu-id="f38fa-184">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f38fa-184">This behavior is by design.</span></span> <span data-ttu-id="f38fa-185">Den valda adressen måste klassificeras som en leveransadress.</span><span class="sxs-lookup"><span data-stu-id="f38fa-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="f38fa-186">Annars uppdateras inte leveransnamnet utifrån den valda adressen.</span><span class="sxs-lookup"><span data-stu-id="f38fa-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="f38fa-187">Kan jag hitta användaren som annullerade en inköpsorder?</span><span class="sxs-lookup"><span data-stu-id="f38fa-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="f38fa-188">Den här informationen spåras bara om inköpsordern är föremål för ändringshantering.</span><span class="sxs-lookup"><span data-stu-id="f38fa-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="f38fa-189">Om du använder ändringshantering kan du se vem som skickade ändringen (annulleringen) och vem som godkände den.</span><span class="sxs-lookup"><span data-stu-id="f38fa-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]