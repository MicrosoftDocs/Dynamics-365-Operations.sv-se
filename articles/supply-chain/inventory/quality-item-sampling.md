---
title: Artikelsampling för kvalitetshantering
description: I det här avsnittet beskrivs hur du ställer in artikelsampling.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 495bef32d63738e367167ee69f2028bc77945cc4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956827"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="a2a01-103">Artikelsampling för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="a2a01-103">Quality management item sampling</span></span>

<span data-ttu-id="a2a01-104">Artikelsampling används som en del av en kvalitetsassociation.</span><span class="sxs-lookup"><span data-stu-id="a2a01-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="a2a01-105">Den definierar mängden aktuellt fysiskt lager som måste inspekteras.</span><span class="sxs-lookup"><span data-stu-id="a2a01-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="a2a01-106">Samplingen kan baseras på fasta kvantiteter, en procentsats eller komplett registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="a2a01-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="a2a01-107">Ställ in artikelsampling</span><span class="sxs-lookup"><span data-stu-id="a2a01-107">Set up item sampling</span></span>

<span data-ttu-id="a2a01-108">Följ dessa steg för att konfigurera artikelsamplingen:</span><span class="sxs-lookup"><span data-stu-id="a2a01-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="a2a01-109">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="a2a01-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="a2a01-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a2a01-110">Select **New**.</span></span>
1. <span data-ttu-id="a2a01-111">Ange ett värde i fältet **Artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="a2a01-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="a2a01-112">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="a2a01-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="a2a01-113">Ange ett nummer i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="a2a01-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="a2a01-114">Detta värde är relaterat till det värde för kvantitetsspecifikation som valts i fältet bredvid.</span><span class="sxs-lookup"><span data-stu-id="a2a01-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="a2a01-115">I avsnittet **Process** väljer du kryssrutan **Fullständig spärr** om hela partiet eller kvantiteten på orderraden ska spärras om ett test skulle misslyckas.</span><span class="sxs-lookup"><span data-stu-id="a2a01-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="a2a01-116">Om denna kryssruta avmarkeras blockeras bara artiklarna i kvalitetsordern om ett test misslyckas.</span><span class="sxs-lookup"><span data-stu-id="a2a01-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="a2a01-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a2a01-117">Select **Save**.</span></span>
1. <span data-ttu-id="a2a01-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a2a01-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="a2a01-119">Funktionen *Kvalitetshantering för lagerprocesser* omfattar ytterligare funktioner för artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="a2a01-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="a2a01-120">Det lägger till ett koncept för *artikelsamplingens omfång* och låter dig definiera en fullständig licensskylt som kvantitetspecifikation.</span><span class="sxs-lookup"><span data-stu-id="a2a01-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="a2a01-121">Om du har aktiverat denna funktion, se [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="a2a01-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
