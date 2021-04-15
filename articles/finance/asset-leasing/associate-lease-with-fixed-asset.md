---
title: Associera anläggningstillgångar med leasingar
description: Ämnet förklarar hur du associerar en befintlig anläggningstillgång med en ny leasing.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e2261755d98ee38564b4b864daf8e79551d1239
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814090"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="26508-103">Associera anläggningstillgångar med leasingar</span><span class="sxs-lookup"><span data-stu-id="26508-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26508-104">Ämnet förklarar hur du associerar en befintlig anläggningstillgång med en ny leasing.</span><span class="sxs-lookup"><span data-stu-id="26508-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="26508-105">När du associerar en anläggningstillgång med en leasing blir ROU-tillgångsvärdet vid det första redovisningstillfället anskaffningskostnaden för anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="26508-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="26508-106">Innan du kan associera en anläggningstillgång till en leasing måste du skapa en post för anläggningstillgången i Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="26508-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="26508-107">Därefter, på sidan **Sammanfattning av leasing**, måste du skapa en leasing och en länk till tillgången för den leasingen.</span><span class="sxs-lookup"><span data-stu-id="26508-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="26508-108">Lägg till en leasing genom att följa stegen i [Lägga till och kopiera leasing](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="26508-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="26508-109">Välj den tillgång som ännu inte har anskaffats i fältet **Nummer för anläggningstillgång**, på sidan **Lägg till leasing**.</span><span class="sxs-lookup"><span data-stu-id="26508-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="26508-110">Välj **Böcker** och bekräfta betalningsplanen.</span><span class="sxs-lookup"><span data-stu-id="26508-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="26508-111">Välj **Första redovisningstillfälle**.</span><span class="sxs-lookup"><span data-stu-id="26508-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="26508-112">Välj **Journal för leasing av tillgång**.</span><span class="sxs-lookup"><span data-stu-id="26508-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="26508-113">Den första redovisningsjournalposten för leasingen debiterar anläggningstillgången för det belopp som vanligtvis debiteras till ROU-tillgångskontot.</span><span class="sxs-lookup"><span data-stu-id="26508-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="26508-114">Du kan nu visa transaktionstypen och boken för anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="26508-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="26508-115">Välj **Journaluppgifter**.</span><span class="sxs-lookup"><span data-stu-id="26508-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="26508-116">Välj **Rader** för att visa de enskilda raderna för journalposten.</span><span class="sxs-lookup"><span data-stu-id="26508-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="26508-117">Välj den journalrad som innehåller tillgången och välj sedan fliken **Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="26508-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="26508-118">På fliken **Anläggningstillgångar** visas transaktionstypen och boken.</span><span class="sxs-lookup"><span data-stu-id="26508-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="26508-119">Som standard är fältet **Transaktionstyp** inställt på **Anskaffning**, och fältet **Bok** är inställt på den aktuella boken för anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="26508-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="26508-120">När du har bokfört den första redovisningsjournalposten visas transaktionen som en anskaffningstransaktion för anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="26508-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="26508-121">Om du vill visa transaktionstabellen går du till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**, väljer lämplig tillgång och väljer **Värderingar**.</span><span class="sxs-lookup"><span data-stu-id="26508-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="26508-122">Du bör se att den första redovisningsjournalposten har skapat en anskaffningstransaktion för den angivna anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="26508-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="26508-123">Anläggningstillgången kan nu skrivas av med hjälp av standardavskrivningsfunktionen i Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="26508-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="26508-124">Mer information finns om avskrivning finns i [Avskrivningsmetoder och avskrivningspraxis](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="26508-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="26508-125">Om du associerar en anläggningstillgång med en leasing inaktiveras knapparna **Avskrivning av tillgång** och **Leasingnedskrivning** i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="26508-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="26508-126">Du kan visa tillgångsavskrivningar och transaktioner för leasingnedskrivning från Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="26508-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="26508-127">Knappen **Transaktioner för tillgångar**, som öppnar ett frågeformulär inaktiveras också.</span><span class="sxs-lookup"><span data-stu-id="26508-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="26508-128">Du kan också öppna föreformuläret **Transaktioner för tillgångar** i Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="26508-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]