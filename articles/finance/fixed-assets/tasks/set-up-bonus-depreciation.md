---
title: Ställ in bonusavskrivning
description: I den här proceduren visas hur du skapar en särskild avskrivning och kopplar den till en förteckning över anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91243a4cee44410a221902990d31a10f1805eb08
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447928"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="d53e9-103">Ställ in bonusavskrivning</span><span class="sxs-lookup"><span data-stu-id="d53e9-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d53e9-104">I den här proceduren visas hur du skapar en särskild avskrivning och kopplar den till en förteckning över anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="d53e9-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="d53e9-105">Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.</span><span class="sxs-lookup"><span data-stu-id="d53e9-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="d53e9-106">Skapa en särskild avskrivning</span><span class="sxs-lookup"><span data-stu-id="d53e9-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="d53e9-107">Gå till Anläggningstillgångar > Inställningar > Särskild avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d53e9-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="d53e9-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d53e9-108">Click New.</span></span>
3. <span data-ttu-id="d53e9-109">Skriv ett värde i fältet Särskild avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d53e9-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="d53e9-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d53e9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d53e9-111">Välj ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="d53e9-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="d53e9-112">Ange ett belopp om ingen procentsats indikerades.</span><span class="sxs-lookup"><span data-stu-id="d53e9-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="d53e9-113">Associera en särskild avskrivning med en räkenskapsbok för anläggningstillgångsgrupp</span><span class="sxs-lookup"><span data-stu-id="d53e9-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="d53e9-114">Gå till Anläggningstillgångar > Inställningar > Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="d53e9-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="d53e9-115">I listan, välj nläggningstillgångsgruppen som är kopplad till den särskilda avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="d53e9-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="d53e9-116">Klicka på Books.</span><span class="sxs-lookup"><span data-stu-id="d53e9-116">Click Books.</span></span>
4. <span data-ttu-id="d53e9-117">I listan väljer du den räkenskapsbok som är associerad med den särskilda avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="d53e9-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="d53e9-118">Klicka på Särskild avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d53e9-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="d53e9-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d53e9-119">Click New.</span></span>
7. <span data-ttu-id="d53e9-120">Ange eller välj ett värde i fältet Special depreciation allowance.</span><span class="sxs-lookup"><span data-stu-id="d53e9-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="d53e9-121">Förvalet för procentandel eller belopp stammar från de särskilda avskrivningsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="d53e9-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="d53e9-122">Välj ett tal i fältet Prioritet.</span><span class="sxs-lookup"><span data-stu-id="d53e9-122">In the Priority field, enter a number.</span></span>

