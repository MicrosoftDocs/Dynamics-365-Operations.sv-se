---
title: "Justera kostnadsvärden för lagerbehållning"
description: "Använd sidan Justering av lagerbehållning för att justera kostnadsvärdet för lagerbehållningskvantiteter efter att en lagerstängningsprocess har körts."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 78a97e1ff893ecfb864052b79e56ad48efa5191c
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="5dc59-103">Justera kostnadsvärden för lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="5dc59-103">Adjust on-hand inventory cost values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5dc59-104">Använd sidan Justering av lagerbehållning för att justera kostnadsvärdet för lagerbehållningskvantiteter efter att en lagerstängningsprocess har körts.</span><span class="sxs-lookup"><span data-stu-id="5dc59-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="5dc59-105">På sidan **Justering av lagerbehållning** kan du justera justera kostnadsvärdet för lagerbehållningskvantiteter när en lagerstängningsprocess körs.</span><span class="sxs-lookup"><span data-stu-id="5dc59-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="5dc59-106">**Obs!** Om du vill öppna sidan **Justering av lagerbehållning** går du till sidan **Stängning och justering** och markerar posten för en slutförd lagerstängningsprocess. Klicka sedan på **Justering** &gt; **Behållning**.</span><span class="sxs-lookup"><span data-stu-id="5dc59-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="5dc59-107">**Exempel:** Du har följande transaktioner i februari:</span><span class="sxs-lookup"><span data-stu-id="5dc59-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="5dc59-108">1 februari: en ekonomisk lagerinleverans för kvantiteten 2 till en kostnad av 100 SEK.</span><span class="sxs-lookup"><span data-stu-id="5dc59-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="5dc59-109">5 februari: en ekonomisk lagerinleverans för kvantiteten 1 till en kostnad av 130 SEK.</span><span class="sxs-lookup"><span data-stu-id="5dc59-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="5dc59-110">19 februari: en ekonomisk lagerutleverans för en kvantitet på 1 till en genomsnittlig driftskostnad på 110 SEK.</span><span class="sxs-lookup"><span data-stu-id="5dc59-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="5dc59-111">Denna artikel skapades med FIFO-lagermodellen (först in, först ut), och lagerstängningen genomfördes den 28 februari.</span><span class="sxs-lookup"><span data-stu-id="5dc59-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="5dc59-112">Den ekonomiska utleveranstransaktionen på SEK 110,00 kommer att kvittas mot den ekonomiska inleveransen daterad den 1 februari, och en justering på SEK 10,00 kommer att göras.</span><span class="sxs-lookup"><span data-stu-id="5dc59-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="5dc59-113">Följande lagerinleveranser kommer därefter att innehålla öppna lagerkvantiteter:</span><span class="sxs-lookup"><span data-stu-id="5dc59-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="5dc59-114">1 februari: en kvantitet på 1 till en kostnad av 100 SEK.</span><span class="sxs-lookup"><span data-stu-id="5dc59-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="5dc59-115">5 februari: en kvantitet på 1 till en kostnad av 130 SEK.</span><span class="sxs-lookup"><span data-stu-id="5dc59-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="5dc59-116">Ange kostnaden för dessa två artiklar till SEK 150,00 med hjälp av alternativet för justering av lagerbehållning så att de öppna behållningarna justeras per den sista lagerstängningsperioden.</span><span class="sxs-lookup"><span data-stu-id="5dc59-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="5dc59-117">**Obs!** Bokföringsdatumet för transaktionen för behållningsjustering är datumet för den senaste lagerstängningen.</span><span class="sxs-lookup"><span data-stu-id="5dc59-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="5dc59-118">Datumet går inte att ändra.</span><span class="sxs-lookup"><span data-stu-id="5dc59-118">This date can't be modified.</span></span>

