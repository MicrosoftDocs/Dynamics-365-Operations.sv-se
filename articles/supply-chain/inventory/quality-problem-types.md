---
title: Problemtyper för avvikelser
description: I detta ämne beskrivs hur du skapar och använder problemtyper för avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022166"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="3cedc-103">Problemtyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cedc-104">I detta ämne beskrivs hur du skapar och använder problemtyper för avvikelser.</span><span class="sxs-lookup"><span data-stu-id="3cedc-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="3cedc-105">Du använder sidan **Problemtyper** för att definiera en klassificering av de kvalitetsproblem som kan uppstå i de olika avvikelsetyperna.</span><span class="sxs-lookup"><span data-stu-id="3cedc-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="3cedc-106">För varje problemtyp som du skapar måste du ange vilka typer av avvikelser som problemtypen kan användas med.</span><span class="sxs-lookup"><span data-stu-id="3cedc-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="3cedc-107">Du kan ställa in följande avvikelsetyper:</span><span class="sxs-lookup"><span data-stu-id="3cedc-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="3cedc-108">**Intern** – Avvikelser av den här typen är relaterade till lagerbehållning (till exempel kvalitetsorder eller karantänorder).</span><span class="sxs-lookup"><span data-stu-id="3cedc-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="3cedc-109">**Kund** – Avvikelseer av den här typen är relaterade till försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="3cedc-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="3cedc-110">**Leverantör** – Avvikelser av den här typen är relaterade till inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="3cedc-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="3cedc-111">**Servicebegäran** – Avvikelser av den här typen är relaterade till serviceorder.</span><span class="sxs-lookup"><span data-stu-id="3cedc-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="3cedc-112">**Produktion** – Avvikelser av den här typen är relaterade till batch- eller produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="3cedc-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="3cedc-113">**Framställning av samprodukt** – Avvikelser av den här typen är relaterade till batchorder för samprodukter.</span><span class="sxs-lookup"><span data-stu-id="3cedc-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="3cedc-114">När du skapar en ny problemtyp väljer du **Avvikelsetyper** i åtgärdsfönstret om du vill skapa en lista över en eller flera avvikelsetyper som är behöriga för problemtypen.</span><span class="sxs-lookup"><span data-stu-id="3cedc-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="3cedc-115">Till exempel kan en problemtyp som är relaterad till en defektkod gälla för alla avvikelsetyper.</span><span class="sxs-lookup"><span data-stu-id="3cedc-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="3cedc-116">En problemtyp som rör kundklagomål kan dock endast gälla avvikelsetyperna **Kund** och **Serviceförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="3cedc-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="3cedc-117">Exempel på problemtyper</span><span class="sxs-lookup"><span data-stu-id="3cedc-117">Examples of problem types</span></span>

<span data-ttu-id="3cedc-118">Här följer några exempel på scenarier för problemtyper som kan användas med de olika avvikelsetyperna:</span><span class="sxs-lookup"><span data-stu-id="3cedc-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="3cedc-119">**Kund:** En kund har lämnat in ett klagomål, en kund har lämnat in en retur eller också har kvalitetsspecifikationer inte uppfyllts.</span><span class="sxs-lookup"><span data-stu-id="3cedc-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="3cedc-120">**Leverantör:** Produkten har skadats, kvalitetsspecifikationerna har inte uppfyllts, eller också har fel produkt inkommit.</span><span class="sxs-lookup"><span data-stu-id="3cedc-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="3cedc-121">**Serviceförfrågan:** Kvalitetsspecifikationer har inte uppfyllts, en kund har lämnat in ett klagomål, eller maskinunderhåll krävs.</span><span class="sxs-lookup"><span data-stu-id="3cedc-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="3cedc-122">**Produktion:** Kvalitetsspecifikationer har inte uppfyllts, maskinunderhåll krävs eller produkten har skadats.</span><span class="sxs-lookup"><span data-stu-id="3cedc-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="3cedc-123">**Framställning av samprodukt:** Kvalitetsspecifikationer har inte uppfyllts, maskinunderhåll krävs eller produkten har skadats.</span><span class="sxs-lookup"><span data-stu-id="3cedc-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="3cedc-124">Skapa en problemtyp och tilldela den till avvikelsetyper</span><span class="sxs-lookup"><span data-stu-id="3cedc-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="3cedc-125">Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Problemtyper**.</span><span class="sxs-lookup"><span data-stu-id="3cedc-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="3cedc-126">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="3cedc-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="3cedc-127">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="3cedc-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="3cedc-128">**Problemtyp** – Ange ett unikt ID eller namn för problemtypen.</span><span class="sxs-lookup"><span data-stu-id="3cedc-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="3cedc-129">**Beskrivning** – Ange en detaljerad beskrivning av problemtypen.</span><span class="sxs-lookup"><span data-stu-id="3cedc-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="3cedc-130">Välj **Avvikelsetyper** i åtgärdsfönstret när den nya raden är vald.</span><span class="sxs-lookup"><span data-stu-id="3cedc-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="3cedc-131">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="3cedc-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="3cedc-132">Ställ sedan in fältet **Avvikelsetyp** för den nya raden till den avvikelsetyp som du vill tillåta för problemtypen.</span><span class="sxs-lookup"><span data-stu-id="3cedc-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="3cedc-133">Upprepa föregående steg för varje ytterligare avvikelsetyp som du vill auktorisera för problemtypen.</span><span class="sxs-lookup"><span data-stu-id="3cedc-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="3cedc-134">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="3cedc-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3cedc-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3cedc-135">Additional resources</span></span>

- [<span data-ttu-id="3cedc-136">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="3cedc-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="3cedc-137">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="3cedc-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="3cedc-138">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="3cedc-139">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="3cedc-140">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="3cedc-141">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="3cedc-142">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="3cedc-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="3cedc-143">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="3cedc-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
