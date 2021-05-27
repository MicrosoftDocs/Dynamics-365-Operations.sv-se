---
title: Diagnostyper för avvikelser
description: I det här ämnet beskrivs hur du använder och skapar diagnostyper som kan användas med avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022286"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="198a5-103">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="198a5-104">I det här ämnet beskrivs hur du använder och skapar diagnostyper som kan användas med avvikelser.</span><span class="sxs-lookup"><span data-stu-id="198a5-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="198a5-105">Du kan använda sidan **Diagnostyper** för att definiera klassificeringen av diagnosåtgärder.</span><span class="sxs-lookup"><span data-stu-id="198a5-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="198a5-106">När du sedan skapar en korrigering för en avvikelse väljer du en diagnos.</span><span class="sxs-lookup"><span data-stu-id="198a5-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="198a5-107">En korrigering specificerar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, och vem som ska genomföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="198a5-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="198a5-108">Även det begärda slutförandedatumet och det planerade slutförandedatumet anges.</span><span class="sxs-lookup"><span data-stu-id="198a5-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="198a5-109">Exempel på diagnostyper</span><span class="sxs-lookup"><span data-stu-id="198a5-109">Examples of diagnostic types</span></span>

<span data-ttu-id="198a5-110">Du arbetar för ett tillverkningsföretag, och flera artiklar har misslyckats i kvalitetstester.</span><span class="sxs-lookup"><span data-stu-id="198a5-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="198a5-111">Artiklarna flyttas till ett karantänområde och markeras som avvikelseprodukter.</span><span class="sxs-lookup"><span data-stu-id="198a5-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="198a5-112">En avvikelsepost skapas i Microsoft Dynamics 365 Supply Chain Management i syfte att spåra informationen genom ut ärendelösning.</span><span class="sxs-lookup"><span data-stu-id="198a5-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="198a5-113">I det här fallet uppstår kvalitetsproblemen eftersom lager i maskinen som paketerar artiklarna har drabbats av slitage och överhettas.</span><span class="sxs-lookup"><span data-stu-id="198a5-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="198a5-114">Korrigeringen av det här problemet är att byta ut delarna i maskinen.</span><span class="sxs-lookup"><span data-stu-id="198a5-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="198a5-115">När du konfigurerar diagnostyperna kan du skapa flera poster som vardera representerar olika typer av problem som maskinen kan ha.</span><span class="sxs-lookup"><span data-stu-id="198a5-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="198a5-116">Du kan också skapa en allmän diagnostyp som representerar maskinreparationer.</span><span class="sxs-lookup"><span data-stu-id="198a5-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="198a5-117">Skapa en diagnostyp</span><span class="sxs-lookup"><span data-stu-id="198a5-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="198a5-118">Gåtill **Lagerhantering \> Inställningar \> Kvalitetshantering \> Diagnostyper**.</span><span class="sxs-lookup"><span data-stu-id="198a5-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="198a5-119">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="198a5-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="198a5-120">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="198a5-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="198a5-121">**Diagnos** – Ange ett unikt ID eller namn för diagnostypen.</span><span class="sxs-lookup"><span data-stu-id="198a5-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="198a5-122">**Beskrivning** – Ange en detaljerad beskrivning av diagnostypen.</span><span class="sxs-lookup"><span data-stu-id="198a5-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="198a5-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="198a5-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="198a5-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="198a5-124">Additional resources</span></span>

- [<span data-ttu-id="198a5-125">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="198a5-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="198a5-126">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="198a5-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="198a5-127">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="198a5-128">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="198a5-129">Problemtyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="198a5-130">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="198a5-131">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="198a5-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="198a5-132">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="198a5-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]