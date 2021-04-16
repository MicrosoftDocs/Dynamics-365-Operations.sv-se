---
title: Regler för tillgångsleasing
description: Detta ämne beskriver konventioner för leasade tillgångar.
author: moaamer
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e6450438a6e8c594590df3cc4502895913f50d01
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842404"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="42f7e-103">Regler för tillgångsleasing</span><span class="sxs-lookup"><span data-stu-id="42f7e-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="42f7e-104">Detta ämne beskriver konventioner för leasade tillgångar.</span><span class="sxs-lookup"><span data-stu-id="42f7e-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="42f7e-105">Leasingkonventioner används för att bestämma uppfyllelsedatum för en leasingbok.</span><span class="sxs-lookup"><span data-stu-id="42f7e-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="42f7e-106">Om leasingkonventionen har ställts in på **Ingen** är startdatumet detsamma som startdatumet för leasingavtalet (det vill säga värdet i fältet **Startdatum för leasingavtal**).</span><span class="sxs-lookup"><span data-stu-id="42f7e-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="42f7e-107">Om leasingkonventionen anges som **Hel månad** blir startdatumet den första dagen i månaden som leasingavtalets startdatum faller inom.</span><span class="sxs-lookup"><span data-stu-id="42f7e-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="42f7e-108">Startdatumet avgör startdatumet för perioden för skuldamorteringen och tidsplanerna för tillgångsavskrivning.</span><span class="sxs-lookup"><span data-stu-id="42f7e-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="42f7e-109">Ränte- och avskrivningsutgifter bokförs på periodens slutdatum i motsvarande tidsplaner.</span><span class="sxs-lookup"><span data-stu-id="42f7e-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="42f7e-110">Den första redovisnings- och justeringsjournalposten bokförs på avslutningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="42f7e-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="42f7e-111">Funktionen för leasingkonventioner måste aktiveras via funktionshanteringen.</span><span class="sxs-lookup"><span data-stu-id="42f7e-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="42f7e-112">I arbetsytan **Funktionshantering** väljer du funktionen kallad **Leasingkonvention för tillgångsleasing** och sedan **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="42f7e-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="42f7e-113">Leasingkonventioner tilldelas inställningen för en leasingbok.</span><span class="sxs-lookup"><span data-stu-id="42f7e-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="42f7e-114">Följ de här stegen om du vill visa eller tilldela leasingkonventionen.</span><span class="sxs-lookup"><span data-stu-id="42f7e-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="42f7e-115">Gå till **Leasing av tillgångar \> Konfigurera \> Leasingböcker**.</span><span class="sxs-lookup"><span data-stu-id="42f7e-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="42f7e-116">I fältet **Leasingkonvention** väljer du ett av följande värden.</span><span class="sxs-lookup"><span data-stu-id="42f7e-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="42f7e-117">Leasingkonvention</span><span class="sxs-lookup"><span data-stu-id="42f7e-117">Leasing convention</span></span> | <span data-ttu-id="42f7e-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="42f7e-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="42f7e-119">None</span><span class="sxs-lookup"><span data-stu-id="42f7e-119">None</span></span>               | <span data-ttu-id="42f7e-120">Skuldamorteringen och avskrivningsschemat för tillgångar börjar på leasingavtalets startdatum, detta eftersom startdatumet är lika med leasingavtalets startdatum.</span><span class="sxs-lookup"><span data-stu-id="42f7e-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="42f7e-121">Slutdatumet är en månad senare.</span><span class="sxs-lookup"><span data-stu-id="42f7e-121">The end date is one month later.</span></span> <span data-ttu-id="42f7e-122">Denna leasingkonvention garanterar inte att räntan bokförs den sista dagen i varje månad.</span><span class="sxs-lookup"><span data-stu-id="42f7e-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="42f7e-123">Hel månad</span><span class="sxs-lookup"><span data-stu-id="42f7e-123">Full month</span></span>         | <span data-ttu-id="42f7e-124">För leasingavtal med startdatum som infaller när som helst under månaden börjar skuldamorteringen och tidsplanerna för tillgångsavskrivning att periodisera utgifter den första dagen i månaden.</span><span class="sxs-lookup"><span data-stu-id="42f7e-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="42f7e-125">Denna leasingkonvention säkerställer att ränta periodiseras på den sista dagen i varje månad för hela månaden.</span><span class="sxs-lookup"><span data-stu-id="42f7e-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="42f7e-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="42f7e-126">Select **Save**.</span></span>

<span data-ttu-id="42f7e-127">När ett leasingavtal skapas, anges startdatum för när respektive bok anges automatiskt baserat på det startdatum som angetts för leasingavtalet och den leasingkonvention som angetts för boken.</span><span class="sxs-lookup"><span data-stu-id="42f7e-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]