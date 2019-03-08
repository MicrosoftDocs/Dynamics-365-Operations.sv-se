---
title: Inkludera fysiskt värde
description: Du använder kryssrutan Inkludera fysiskt värde på snabbfliken Lagermodell på sidan Artikelmodellgrupper för att ange om fysiskt uppdaterade transaktioner ska beaktas vid beräkningen av den löpande genomsnittliga självkostnaden för en artikel.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e96d5e2a658a027d66663868329cf4eedcb1d46f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "357322"
---
# <a name="include-physical-value"></a><span data-ttu-id="9d37d-103">Inkludera fysiskt värde</span><span class="sxs-lookup"><span data-stu-id="9d37d-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d37d-104">Du använder kryssrutan Inkludera fysiskt värde på snabbfliken Lagermodell på sidan Artikelmodellgrupper för att ange om fysiskt uppdaterade transaktioner ska beaktas vid beräkningen av den löpande genomsnittliga självkostnaden för en artikel.</span><span class="sxs-lookup"><span data-stu-id="9d37d-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="9d37d-105">Kryssrutan **Inkludera fysiskt värde** har följande värden.</span><span class="sxs-lookup"><span data-stu-id="9d37d-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="9d37d-106">Värde</span><span class="sxs-lookup"><span data-stu-id="9d37d-106">Value</span></span>    | <span data-ttu-id="9d37d-107">Resultat</span><span class="sxs-lookup"><span data-stu-id="9d37d-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9d37d-108">Markerad</span><span class="sxs-lookup"><span data-stu-id="9d37d-108">Selected</span></span> | <span data-ttu-id="9d37d-109">Både fysiskt och ekonomiskt uppdaterade transaktioner används för att beräkna löpande genomsnittlig självkostnad.</span><span class="sxs-lookup"><span data-stu-id="9d37d-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="9d37d-110">Reglerat</span><span class="sxs-lookup"><span data-stu-id="9d37d-110">Cleared</span></span>  | <span data-ttu-id="9d37d-111">Endast ekonomiskt uppdaterade transaktioner används för att beräkna löpande genomsnittlig självkostnad.</span><span class="sxs-lookup"><span data-stu-id="9d37d-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="9d37d-112">Kryssrutan har något olika effekter, beroende på vilken lagermodell som du använder.</span><span class="sxs-lookup"><span data-stu-id="9d37d-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="9d37d-113">Om du markerar **Inkludera fysiskt värde**-kryssrutan när du använder FIFO (först in, först ut), LIFO (sist in, först ut) eller LIFO-datumlagermodellen, lagerstängningen också justerar fysiskt uppdaterade transaktioner.</span><span class="sxs-lookup"><span data-stu-id="9d37d-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="9d37d-114">Om du inte markerar kryssrutan **Inkludera fysiskt värde** när du använder dessa lagermodeller, lagerstängningen skapar kvittningar enbart för transaktioner som är ekonomiskt uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="9d37d-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="9d37d-115">När du använder lagermodellen för viktat medelvärde eller viktat genomsnittligt datum kvittar lagerstängningen bara ekonomiskt uppdaterade transaktioner oavsett om du markerar kryssrutan **Inkludera fysiskt värde** eller inte.</span><span class="sxs-lookup"><span data-stu-id="9d37d-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="9d37d-116">**Exempel 1** Du har markerat **Inkludera fysiskt värde**-kryssrutan och får följande inköpsorder:</span><span class="sxs-lookup"><span data-stu-id="9d37d-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="9d37d-117">En inköpsorder för kvantiteten 2 och en självkostnad på 100,00 kronor som har följesedelsuppdaterats</span><span class="sxs-lookup"><span data-stu-id="9d37d-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated</span></span>
-   <span data-ttu-id="9d37d-118">En inköpsorder för kvantiteten 2 och en självkostnad på 120,00 kronor som har fakturauppdaterats</span><span class="sxs-lookup"><span data-stu-id="9d37d-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated</span></span>

<span data-ttu-id="9d37d-119">I det här fallet blir den genomsnittliga självkostnaden 112,00 kronor eftersom både fysiskt och ekonomiskt uppdaterade transaktioner används för att beräkna självkostnaden.</span><span class="sxs-lookup"><span data-stu-id="9d37d-119">In this case, the running average cost price will be USD 11.20, because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> <span data-ttu-id="9d37d-120">**Exempel 2** Du har inte markerat **Inkludera fysiskt värde**-kryssrutan och självkostnaden för artikelns inställningar är 100,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="9d37d-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> <span data-ttu-id="9d37d-121">Du tar emot en inköpsorder för kvantiteten 20 och en självkostnad på 120,00 kronor som har följesedelsuppdaterats.</span><span class="sxs-lookup"><span data-stu-id="9d37d-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span> <span data-ttu-id="9d37d-122">När en försäljningsorder bokförs, bokförs beloppet 100,00 kronor eftersom den genomsnittliga självkostnaden inte inkluderar fysiskt bokförda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="9d37d-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> <span data-ttu-id="9d37d-123">**Obs!** Jämfört med, om du markerar **Inkludera fysiskt värde**-kryssrutan för den här artikeln, när en försäljningsorder bokförs, det bokförda kostnadsbeloppet är 120,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="9d37d-123">**Note:** For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>



