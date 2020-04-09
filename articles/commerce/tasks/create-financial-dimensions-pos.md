---
title: " Skapa ekonomiska dimensioner för kassaregister och konfigurera dimensionsvärden för register"
description: Den här proceduren går igenom hur du skapar ekonomiska dimensioner för kassaregister (POS) och visar hur du konfigurerar värden för ekonomiska dimension i kassor.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be50eba098b7b28594c8e18c721579f4bb2e879
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141001"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="1dcef-103"> Skapa ekonomiska dimensioner för kassaregister och konfigurera dimensionsvärden för register</span><span class="sxs-lookup"><span data-stu-id="1dcef-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1dcef-104">Den här proceduren går igenom hur du skapar ekonomiska dimensioner för kassaregister (POS) och visar hur du konfigurerar värden för ekonomiska dimension i kassor.</span><span class="sxs-lookup"><span data-stu-id="1dcef-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="1dcef-105">Detta förfarande inte omfattar andra åtgärder, såsom att skapa dimensionen ställer och strukturer.</span><span class="sxs-lookup"><span data-stu-id="1dcef-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="1dcef-106">Dessa uppgifter hittar du i andra avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1dcef-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="1dcef-107">I den här registreringen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="1dcef-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="1dcef-108">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="1dcef-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="1dcef-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1dcef-109">Click New.</span></span>
3. <span data-ttu-id="1dcef-110">Välj ett alternativ i fältet Använd värden från.</span><span class="sxs-lookup"><span data-stu-id="1dcef-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="1dcef-111">I fältet Dimensionsnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="1dcef-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="1dcef-112">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="1dcef-112">Click Activate.</span></span>
6. <span data-ttu-id="1dcef-113">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="1dcef-113">Click Close.</span></span>
7. <span data-ttu-id="1dcef-114">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="1dcef-114">Click Activate.</span></span>
8. <span data-ttu-id="1dcef-115">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="1dcef-115">Click Dimension values.</span></span>
9. <span data-ttu-id="1dcef-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1dcef-116">Close the page.</span></span>
10. <span data-ttu-id="1dcef-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1dcef-117">Click Save.</span></span>
11. <span data-ttu-id="1dcef-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1dcef-118">Close the page.</span></span>
12. <span data-ttu-id="1dcef-119">Gå till Butik och handel > kanalinställning > POS inställning > register.</span><span class="sxs-lookup"><span data-stu-id="1dcef-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="1dcef-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1dcef-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="1dcef-121">Växla expansionen av avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="1dcef-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="1dcef-122">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="1dcef-122">Click Edit.</span></span>
16. <span data-ttu-id="1dcef-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Terminal.</span><span class="sxs-lookup"><span data-stu-id="1dcef-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="1dcef-124">I listan du söker efter och väljer dimensionsvärdet för registret som uppdateras.</span><span class="sxs-lookup"><span data-stu-id="1dcef-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="1dcef-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1dcef-125">Click Save.</span></span>

