--- 
title: "Ställa in nummerserier med hjälp av en guide"
description: "Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e7d988cd1261c00925ad7ae612a947a0083028ee
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="5e582-103">Ställa in nummerserier med hjälp av en guide</span><span class="sxs-lookup"><span data-stu-id="5e582-103">Set up number sequences by using a wizard</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e582-104">Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem.</span><span class="sxs-lookup"><span data-stu-id="5e582-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="5e582-105">En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens.</span><span class="sxs-lookup"><span data-stu-id="5e582-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="5e582-106">Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen.</span><span class="sxs-lookup"><span data-stu-id="5e582-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="5e582-107">I den här proceduren förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide.</span><span class="sxs-lookup"><span data-stu-id="5e582-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="5e582-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5e582-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="5e582-109">Gå till Organisationsadministration > Nummerserier > Nummerserier.</span><span class="sxs-lookup"><span data-stu-id="5e582-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="5e582-110">Klicka på Generera.</span><span class="sxs-lookup"><span data-stu-id="5e582-110">Click Generate.</span></span>
3. <span data-ttu-id="5e582-111">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="5e582-111">Click Next.</span></span>
    * <span data-ttu-id="5e582-112">På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet.</span><span class="sxs-lookup"><span data-stu-id="5e582-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="5e582-113">Dessutom kan du ange om nummerserien måste vara löpande.</span><span class="sxs-lookup"><span data-stu-id="5e582-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="5e582-114">Välj inte alternativet Kontinuerlig om du måste förallokera nummer för nummerserien.</span><span class="sxs-lookup"><span data-stu-id="5e582-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="5e582-115">Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och klickar på Inkludera område i format.</span><span class="sxs-lookup"><span data-stu-id="5e582-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="5e582-116">Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och klickar på Ta bort område från format.</span><span class="sxs-lookup"><span data-stu-id="5e582-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="5e582-117">Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och klickar på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="5e582-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="5e582-118">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="5e582-118">Click Next.</span></span>
5. <span data-ttu-id="5e582-119">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="5e582-119">Click Finish.</span></span>


