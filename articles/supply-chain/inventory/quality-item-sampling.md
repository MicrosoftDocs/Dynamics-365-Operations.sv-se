---
title: Artikelsampling för kvalitetshantering
description: I det här avsnittet beskrivs hur du ställer in artikelsampling.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022238"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="611cc-103">Artikelsampling för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="611cc-103">Quality management item sampling</span></span>

<span data-ttu-id="611cc-104">Artikelsampling används som en del av en kvalitetsassociation.</span><span class="sxs-lookup"><span data-stu-id="611cc-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="611cc-105">Den definierar mängden aktuellt fysiskt lager som måste inspekteras.</span><span class="sxs-lookup"><span data-stu-id="611cc-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="611cc-106">Samplingen kan baseras på fasta kvantiteter, en procentsats eller komplett registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="611cc-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="611cc-107">Ställ in artikelsampling</span><span class="sxs-lookup"><span data-stu-id="611cc-107">Set up item sampling</span></span>

<span data-ttu-id="611cc-108">Följ dessa steg för att konfigurera artikelsamplingen:</span><span class="sxs-lookup"><span data-stu-id="611cc-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="611cc-109">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="611cc-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="611cc-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="611cc-110">Select **New**.</span></span>
1. <span data-ttu-id="611cc-111">Ange ett värde i fältet **Artikelsampling**.</span><span class="sxs-lookup"><span data-stu-id="611cc-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="611cc-112">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="611cc-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="611cc-113">Ange ett nummer i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="611cc-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="611cc-114">Detta värde är relaterat till det värde för kvantitetsspecifikation som valts i fältet bredvid.</span><span class="sxs-lookup"><span data-stu-id="611cc-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="611cc-115">I avsnittet **Process** väljer du kryssrutan **Fullständig spärr** om hela partiet eller kvantiteten på orderraden ska spärras om ett test skulle misslyckas.</span><span class="sxs-lookup"><span data-stu-id="611cc-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="611cc-116">Om denna kryssruta avmarkeras blockeras bara artiklarna i kvalitetsordern om ett test misslyckas.</span><span class="sxs-lookup"><span data-stu-id="611cc-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="611cc-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="611cc-117">Select **Save**.</span></span>
1. <span data-ttu-id="611cc-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="611cc-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="611cc-119">Funktionen *Kvalitetshantering för lagerprocesser* omfattar ytterligare funktioner för artikelsampling.</span><span class="sxs-lookup"><span data-stu-id="611cc-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="611cc-120">Det lägger till ett koncept för *artikelsamplingens omfång* och låter dig definiera en fullständig licensskylt som kvantitetspecifikation.</span><span class="sxs-lookup"><span data-stu-id="611cc-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="611cc-121">Om du har aktiverat denna funktion, se [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="611cc-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
