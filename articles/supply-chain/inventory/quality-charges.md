---
title: Avgifter för avvikelsefunktioner
description: I det här ämnet beskrivs hur du skapar kvalitetsavgifter som kan användas med funktioner för en avvikelse.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfa424e94048aa9eb1ce4da9aa69e8d4df71cefb
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956832"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="6edbd-103">Avgifter för avvikelsefunktioner</span><span class="sxs-lookup"><span data-stu-id="6edbd-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6edbd-104">I det här ämnet beskrivs hur du skapar kvalitetsavgifter som kan användas med funktioner för en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="6edbd-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="6edbd-105">Du kan använda sidan **Kvalitetsavgifter** för att definiera de avgiftstyper som kan läggas till funktionerna för en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="6edbd-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="6edbd-106">Med avgifter kan du spåra detaljer om avgifter som du är skyldig en kund för avvikelseprodukter, eller som en leverantör är skyldig dig för avvikelseprodukter som du har fått.</span><span class="sxs-lookup"><span data-stu-id="6edbd-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="6edbd-107">Du kan också använda avgifter för att spåra kostnader som krävs för att externa leverantörer eller tjänster ska utföra en funktion.</span><span class="sxs-lookup"><span data-stu-id="6edbd-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="6edbd-108">Exempel på kvalitetsavgifter</span><span class="sxs-lookup"><span data-stu-id="6edbd-108">Examples of quality charges</span></span>

<span data-ttu-id="6edbd-109">Du arbetar för ett tillverkningsföretag.</span><span class="sxs-lookup"><span data-stu-id="6edbd-109">You work for a manufacturing company.</span></span> <span data-ttu-id="6edbd-110">Ditt företag har kontrakt med flera leverantörer.</span><span class="sxs-lookup"><span data-stu-id="6edbd-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="6edbd-111">Dessa kontrakt beskriver standarder för leverans i tid, skador och produktkvalitet för artiklar.</span><span class="sxs-lookup"><span data-stu-id="6edbd-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="6edbd-112">På samma sätt har flera av dina kunder kontrakt med ditt företag om returer, skador och produktkvalitet.</span><span class="sxs-lookup"><span data-stu-id="6edbd-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="6edbd-113">En avgiftsstruktur definieras för varje situation och anges i kontraktet.</span><span class="sxs-lookup"><span data-stu-id="6edbd-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="6edbd-114">Du kan konfigurera kvalitetsavgifter för att beskriva de olika typerna av avgifter, till exempel *Skador*, *Sen leverans* och *Kvalitet*.</span><span class="sxs-lookup"><span data-stu-id="6edbd-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="6edbd-115">När du sedan skapar en avvikelse lägger du till en eller flera funktioner.</span><span class="sxs-lookup"><span data-stu-id="6edbd-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="6edbd-116">För varje funktion väljer du **Tillägg** om du vill definiera detaljer om avgifterna.</span><span class="sxs-lookup"><span data-stu-id="6edbd-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="6edbd-117">Skapa en kvalitetsavgift</span><span class="sxs-lookup"><span data-stu-id="6edbd-117">Create a quality charge</span></span>

1. <span data-ttu-id="6edbd-118">Gå till **Lagrhantering \> Inställningar \> Kvalitetshantering \> Kvalitetsavgifter**.</span><span class="sxs-lookup"><span data-stu-id="6edbd-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="6edbd-119">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="6edbd-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="6edbd-120">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="6edbd-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="6edbd-121">**Avgiftskod** – Ange ett unikt ID eller namn för kvalitetsavgiften.</span><span class="sxs-lookup"><span data-stu-id="6edbd-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="6edbd-122">**Beskrivning** – Ange en detaljerad beskrivning av kvalitetsavgiften.</span><span class="sxs-lookup"><span data-stu-id="6edbd-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="6edbd-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6edbd-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="6edbd-124">Lägga till en kvalitetsavgift för en åtgärd för en avvikelse</span><span class="sxs-lookup"><span data-stu-id="6edbd-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="6edbd-125">Mer information om hur du lägger till funktioner för en avvikelse och tillämpar avgifter på dem finns i [Funktioner för avvikelser](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6edbd-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6edbd-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6edbd-126">Additional resources</span></span>

- [<span data-ttu-id="6edbd-127">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="6edbd-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="6edbd-128">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="6edbd-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="6edbd-129">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="6edbd-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="6edbd-130">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="6edbd-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="6edbd-131">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="6edbd-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="6edbd-132">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="6edbd-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="6edbd-133">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="6edbd-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="6edbd-134">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="6edbd-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
