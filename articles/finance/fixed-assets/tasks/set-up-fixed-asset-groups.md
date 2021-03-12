---
title: Ställ in anläggningstillgångsgrupper
description: I det här avsnittet förklaras hur du skapar en ny anläggningstillgångsgrupp.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4eead36e1274194b151b230767a4d6385173b12f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994850"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="6b5a5-103">Ställ in anläggningstillgångsgrupper</span><span class="sxs-lookup"><span data-stu-id="6b5a5-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6b5a5-104">I det här avsnittet förklaras hur du skapar en ny anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="6b5a5-105">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="6b5a5-106">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Inställningar > Anläggningstillgångsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="6b5a5-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-107">Select **New**.</span></span>
3. <span data-ttu-id="6b5a5-108">Skriv ett värde i fältet **Anläggningstillgångsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="6b5a5-109">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="6b5a5-110">Autonummer för anläggningstillgångar och nummerseriekoden i **anläggningstillgångsgruppen** ska åsidosätta inställningarna i anläggningstillgångparametrarna.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="6b5a5-111">Du kan ändra här, om tillgången i denna anläggningstillgångsgrupp ska ha ett nummer från andra grupper.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="6b5a5-112">Välj **Räkenskapsböcker**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-112">Select **Books**.</span></span>
6. <span data-ttu-id="6b5a5-113">Ange eller välj ett värde i fältet **Bok**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="6b5a5-114">Fältet **Beräkna avskrivning** är inställt på **Ja**, varför tillgångsförteckningen kommer att tas med i avskrivningsförslagen.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="6b5a5-115">Om **Beräkna avskrivning** är **Nej**, skrivs tillgången inte automatiskt av.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="6b5a5-116">Ange tillgångens tjänstelivstid, i antal år.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="6b5a5-117">Värdet i fältet **Avskrivningsperioder** beräknas efter att du har angett tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="6b5a5-118">Välj alternativ i fältet **Avskrivningspraxis**.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="6b5a5-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-119">Close the page.</span></span>

