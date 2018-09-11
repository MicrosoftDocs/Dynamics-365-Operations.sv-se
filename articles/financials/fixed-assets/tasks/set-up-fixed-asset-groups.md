--- 
title: "Ställ in anläggningstillgångsgrupper"
description: "I den här proceduren visas hur du skapar en ny anläggningstillgångsgrupp."
author: saraschi2
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 50942d6bb8da8ec7b63f3c18ef0421d69fb76859
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="15095-103">Ställ in anläggningstillgångsgrupper</span><span class="sxs-lookup"><span data-stu-id="15095-103">Set up fixed asset groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15095-104">I den här proceduren visas hur du skapar en ny anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="15095-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="15095-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="15095-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="15095-106">Gå till Anläggningstillgångar > Inställningar > Anläggningstillgångsgrupper.</span><span class="sxs-lookup"><span data-stu-id="15095-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="15095-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="15095-107">Click New.</span></span>
3. <span data-ttu-id="15095-108">Skriv ett värde i fältet Anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="15095-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="15095-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="15095-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="15095-110">Autonummer för anläggningstillgångar och nummerseriekoden i anläggningstillgångsgruppen ska åsidosätta inställningarna i anläggningstillgångparametrarna.</span><span class="sxs-lookup"><span data-stu-id="15095-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="15095-111">Du kan ändra här, om tillgången i denna anläggningstillgångsgrupp ska ha ett nummer från andra grupper.</span><span class="sxs-lookup"><span data-stu-id="15095-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="15095-112">Klicka på Books.</span><span class="sxs-lookup"><span data-stu-id="15095-112">Click Books.</span></span>
6. <span data-ttu-id="15095-113">Ange eller välj ett värde i fältet Book.</span><span class="sxs-lookup"><span data-stu-id="15095-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="15095-114">Fältet Beräkna avskrivning är inställt på Ja, varför tillgångsförteckningen kommer att tas med i avskrivningsförslagen.</span><span class="sxs-lookup"><span data-stu-id="15095-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="15095-115">Om Beräkna avskrivning är Nej, skrivs tillgången inte automatiskt av.</span><span class="sxs-lookup"><span data-stu-id="15095-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="15095-116">Ange tillgångens tjänstelivstid, i antal år.</span><span class="sxs-lookup"><span data-stu-id="15095-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="15095-117">Värdet i fältet Avskrivningsperioder beräknas efter att du har angett tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="15095-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="15095-118">Välj alternativ i fältet Avskrivningspraxis.</span><span class="sxs-lookup"><span data-stu-id="15095-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="15095-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="15095-119">Close the page.</span></span>


