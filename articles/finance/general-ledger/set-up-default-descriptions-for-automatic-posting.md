---
title: Ställ in standardbeskrivningar för automatisk bokföring
description: Det här avsnittet förklarar hur du kan ställa in standardtext som används för att beskriva redovisningsposter som bokförs automatiskt i redovisningen. Du kan ställa in standardbeskrivningstext genom att använda fritext eller välja fasta variabler.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d1b73b104ed8a8a015cb97dcf3055a648cfb083d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994750"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="55ba3-104">Ställ in standardbeskrivningar för automatisk bokföring</span><span class="sxs-lookup"><span data-stu-id="55ba3-104">Set up default descriptions for automatic posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55ba3-105">Det här avsnittet förklarar hur du kan ställa in standardtext som används för att beskriva redovisningsposter som bokförs automatiskt i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="55ba3-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="55ba3-106">Du kan ställa in standardbeskrivningstext genom att använda fritext eller välja fasta variabler.</span><span class="sxs-lookup"><span data-stu-id="55ba3-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="55ba3-107">För vissa typer av transaktioner i vissa länder eller regioner kan du även ta med text från fält i Microsoft Dynamics AX-databasen som rör dessa transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="55ba3-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="55ba3-108">En lista över transaktionstyperna, samt länderna och regionerna, finns i avsnittet [Valfritt: Lägg till annan text i standardbeskrivningar](#optional-add-other-text-to-default-descriptions) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="55ba3-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="55ba3-109">Ställ in standardbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="55ba3-109">Set up default descriptions</span></span>

1. <span data-ttu-id="55ba3-110">Gå till **Organisationsadministration** \> **Inställningar** \> **Standardbeskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="55ba3-111">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="55ba3-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="55ba3-112">Välj transaktionstyp att skapa en standardbeskrivning för i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="55ba3-113">Välj språk som gäller för denna beskrivning i fältet **Språk**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="55ba3-114">Ange en standardbeskrivning av artikeln i fältet **Text**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="55ba3-115">Du kan ange text i fältet, eller använda en eller flera av följande fritextvariabler:</span><span class="sxs-lookup"><span data-stu-id="55ba3-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="55ba3-116">**%1** – Lägg till transaktionsdatumet.</span><span class="sxs-lookup"><span data-stu-id="55ba3-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="55ba3-117">**%2** – Lägg till en identifierare som motsvarar dokumenttypen som bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="55ba3-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="55ba3-118">Till exempel för transaktionstyper, som är relaterade till fakturor, lägger variabeln **%2** till fakturanumret.</span><span class="sxs-lookup"><span data-stu-id="55ba3-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="55ba3-119">**%3** – Lägg till en identifierare som relaterar till dokumenttypen som bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="55ba3-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="55ba3-120">Till exempel för transaktionstyper som är relaterade till fakturor lägger variabeln **%3** till kundkontonumret.</span><span class="sxs-lookup"><span data-stu-id="55ba3-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="55ba3-121">Du kan även: Lägg till annan text i standardbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="55ba3-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="55ba3-122">För vissa typer av transaktioner i vissa länder/regioner kan du även ta med text i din standardbeskrivning från fält i dina data som rör dessa transaktionstyper.</span><span class="sxs-lookup"><span data-stu-id="55ba3-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="55ba3-123">Följande lista visar de transaktionstyper och länder och regioner som det här alternativet är tillgängligt för.</span><span class="sxs-lookup"><span data-stu-id="55ba3-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="55ba3-124">**Transaktionstyper**</span><span class="sxs-lookup"><span data-stu-id="55ba3-124">**Transaction types**</span></span>

<span data-ttu-id="55ba3-125">Du kan lägga till annan text till standardinställningbeskrivningar för transaktionstyper som är relaterade till följande dokumenttyper:</span><span class="sxs-lookup"><span data-stu-id="55ba3-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="55ba3-126">Kundfakturor</span><span class="sxs-lookup"><span data-stu-id="55ba3-126">Customer invoices</span></span>
- <span data-ttu-id="55ba3-127">Kundkreditfakturor</span><span class="sxs-lookup"><span data-stu-id="55ba3-127">Customer credit notes</span></span>
- <span data-ttu-id="55ba3-128">Kundkontantbetalningar</span><span class="sxs-lookup"><span data-stu-id="55ba3-128">Customer cash payments</span></span>
- <span data-ttu-id="55ba3-129">Leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="55ba3-129">Vendor payments</span></span>
- <span data-ttu-id="55ba3-130">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="55ba3-130">Sales orders</span></span>
- <span data-ttu-id="55ba3-131">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="55ba3-131">Purchase orders</span></span>
- <span data-ttu-id="55ba3-132">Lagerjournaler</span><span class="sxs-lookup"><span data-stu-id="55ba3-132">Inventory journals</span></span>
- <span data-ttu-id="55ba3-133">Huvudplanering (MPS)</span><span class="sxs-lookup"><span data-stu-id="55ba3-133">Master planning (MRP)</span></span>
- <span data-ttu-id="55ba3-134">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="55ba3-134">Fixed assets</span></span>

<span data-ttu-id="55ba3-135">**Länder och regioner**</span><span class="sxs-lookup"><span data-stu-id="55ba3-135">**Countries and regions**</span></span>

<span data-ttu-id="55ba3-136">Det här alternativet finns bara för följande länder och regioner:</span><span class="sxs-lookup"><span data-stu-id="55ba3-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="55ba3-137">Brasilien</span><span class="sxs-lookup"><span data-stu-id="55ba3-137">Brazil</span></span>
- <span data-ttu-id="55ba3-138">Kina</span><span class="sxs-lookup"><span data-stu-id="55ba3-138">China</span></span>
- <span data-ttu-id="55ba3-139">Tjeckien</span><span class="sxs-lookup"><span data-stu-id="55ba3-139">Czech Republic</span></span>
- <span data-ttu-id="55ba3-140">Östeuropa</span><span class="sxs-lookup"><span data-stu-id="55ba3-140">Eastern Europe</span></span>
- <span data-ttu-id="55ba3-141">Ungern</span><span class="sxs-lookup"><span data-stu-id="55ba3-141">Hungary</span></span>
- <span data-ttu-id="55ba3-142">Indien</span><span class="sxs-lookup"><span data-stu-id="55ba3-142">India</span></span>
- <span data-ttu-id="55ba3-143">Japan</span><span class="sxs-lookup"><span data-stu-id="55ba3-143">Japan</span></span>
- <span data-ttu-id="55ba3-144">Litauen</span><span class="sxs-lookup"><span data-stu-id="55ba3-144">Lithuania</span></span>
- <span data-ttu-id="55ba3-145">Lettland</span><span class="sxs-lookup"><span data-stu-id="55ba3-145">Latvia</span></span>
- <span data-ttu-id="55ba3-146">Polen</span><span class="sxs-lookup"><span data-stu-id="55ba3-146">Poland</span></span>
- <span data-ttu-id="55ba3-147">Ryssland</span><span class="sxs-lookup"><span data-stu-id="55ba3-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="55ba3-148">Lägga till text i standardbeskrivningar</span><span class="sxs-lookup"><span data-stu-id="55ba3-148">Add text to default descriptions</span></span>

<span data-ttu-id="55ba3-149">När du har slutfört stegen i avsnittet [Ange standardbeskrivningar](#set-up-default-descriptions) tidigare i detta avsnitt följer du dessa steg för att lägga till annan text i standardbeskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="55ba3-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="55ba3-150">På snabbfliken **Parametrar** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="55ba3-151">Välj databasregistret från vilket du vill lägga till parameterdata i beskrivningen i fältet **Referenstabell**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="55ba3-152">Välj fältet från vilket du vill lägga till parameterdata i beskrivningen i fältet **Referensfält**.</span><span class="sxs-lookup"><span data-stu-id="55ba3-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="55ba3-153">Upprepa steg 1 till och med 3 om du vill lägga till fler parametrar.</span><span class="sxs-lookup"><span data-stu-id="55ba3-153">Repeat steps 1 through 3 to add more parameters.</span></span>
