---
title: Skapa ett avskrivningsförslag
description: Det här avsnittet beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07337063c01f146c72ca6d9e0f9096907cdc9638
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142834"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="eba3e-103">Skapa ett avskrivningsförslag</span><span class="sxs-lookup"><span data-stu-id="eba3e-103">Create a depreciation proposal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eba3e-104">Det här avsnittet beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="eba3e-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="eba3e-105">I denna uppgift används USMF-demonstrationföretaget och revisorrollen.</span><span class="sxs-lookup"><span data-stu-id="eba3e-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="eba3e-106">Skapa ett avskrivningsförslag</span><span class="sxs-lookup"><span data-stu-id="eba3e-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="eba3e-107">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag**.</span><span class="sxs-lookup"><span data-stu-id="eba3e-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="eba3e-108">I fältet **Journalnamn** väljer du ett alternativ i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="eba3e-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="eba3e-109">I fältet **Till-datum**, anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="eba3e-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="eba3e-110">Välj alternativet **Summera avskrivning** för att summera månadsvisa avskrivningar till en journalrad.</span><span class="sxs-lookup"><span data-stu-id="eba3e-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="eba3e-111">Till exempel om värdet för Till-datum är 31 mars 2015 skapas följande beskrivning: ”avskrivning sedan 31 januari 31 2015”.</span><span class="sxs-lookup"><span data-stu-id="eba3e-111">For example, if the To date value is March 31, 2015, the following description is generated: "Depreciation since January 31, 2015."</span></span> <span data-ttu-id="eba3e-112">Fältet **Datum** på de föreslagna journalraderna ställs sedan in till 31 mars 2015.</span><span class="sxs-lookup"><span data-stu-id="eba3e-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="eba3e-113">Avskrivningsförslaget kan filtreras per tillgång, tillgångsgrupp eller andra kriterier med hjälp av alternativet **Filter**.</span><span class="sxs-lookup"><span data-stu-id="eba3e-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="eba3e-114">När du använder formuläret **Skapa förvärvs- eller avskrivningsförslag för anläggningstillgångar**, kan du ange avskrivning i batchar.</span><span class="sxs-lookup"><span data-stu-id="eba3e-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="eba3e-115">Detta rekommenderas för större förslag som kräver mer systemresurser.</span><span class="sxs-lookup"><span data-stu-id="eba3e-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="eba3e-116">Om du väljer batchalternativet, kan du fortfarande använda slutföra andra uppgifter under den tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="eba3e-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="eba3e-117">När du föreslår avskrivning på detta sätt, beräknas avskrivningen för värdemodeller för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="eba3e-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="eba3e-118">Välj **Skapa journal**.</span><span class="sxs-lookup"><span data-stu-id="eba3e-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="eba3e-119">Granska avskrivningposter</span><span class="sxs-lookup"><span data-stu-id="eba3e-119">Review depreciation entries</span></span>
1. <span data-ttu-id="eba3e-120">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="eba3e-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="eba3e-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="eba3e-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="eba3e-122">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="eba3e-122">Select **Lines**.</span></span>
4. <span data-ttu-id="eba3e-123">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="eba3e-123">Select **Post**.</span></span>

