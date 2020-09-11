---
title: Konfigurera tjänstledighets- och frånvaroparametrar
description: Definiera personalparametrar för tjänstledighet och frånvaro i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712386"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="140c4-103">Konfigurera tjänstledighets- och frånvaroparametrar</span><span class="sxs-lookup"><span data-stu-id="140c4-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="140c4-104">Innan du ställer in tjänstledighets- och frånvaroplan i Dynamics 365 Human Resources kan det vara en bra idé att kontrollera inställningarna för alla relaterade personalparametrar, t.ex.:</span><span class="sxs-lookup"><span data-stu-id="140c4-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="140c4-105">Nummerserie för tjänstledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="140c4-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="140c4-106">Inställning av Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="140c4-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="140c4-107">Inställningar för självbetjäning för medarbetare för tjänstledighets- och frånvaroansökningar</span><span class="sxs-lookup"><span data-stu-id="140c4-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="140c4-108">Parametrar för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="140c4-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="140c4-109">Visa och ändra personalparametrar</span><span class="sxs-lookup"><span data-stu-id="140c4-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="140c4-110">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="140c4-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="140c4-111">Under **Inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="140c4-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="140c4-112">På fliken **nummerserier** kontrollerar du **nummerseriekod** för **begäran om tjänstledighet-ID** och ändrar vid behov.</span><span class="sxs-lookup"><span data-stu-id="140c4-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="140c4-113">Den här inställningen avgör vilken sekvens som används för automatiskt tilldelning av ID:n för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="140c4-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="140c4-114">På fliken **FMLA** kontrollera FMLA-inställningar och ändra efter behov.</span><span class="sxs-lookup"><span data-stu-id="140c4-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="140c4-115">På fliken **Självbetjäning för medarbetare** anger du om chefer kan ange tjänstledighets- och frånvaroansökningar för medarbetarnas räkning.</span><span class="sxs-lookup"><span data-stu-id="140c4-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="140c4-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="140c4-116">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="140c4-117">Visa och ändra parametrar för ledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="140c4-117">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="140c4-118">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="140c4-118">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="140c4-119">Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="140c4-119">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="140c4-120">Ange följande parametrar på fliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="140c4-120">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="140c4-121">Ställ in **Enhet för tjänstledighet och frånvaro** till antingen timmar eller dagar.</span><span class="sxs-lookup"><span data-stu-id="140c4-121">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="140c4-122">Om dagar kan du välja **aktivera halvdags definition** om du vill tillåta att medarbetare väljer antingen första eller andra halvan av dagen i sina ledighetsbegäran.</span><span class="sxs-lookup"><span data-stu-id="140c4-122">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="140c4-123">Välj **tjänstmånaders giltighetsdatum** om du vill ange när periodiseringspriser ska gälla för tjänstledighetsplaner med hjälp av tjänstmånader.</span><span class="sxs-lookup"><span data-stu-id="140c4-123">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="140c4-124">Välj **saldoberäkning** om du vill visa saldon som visas från och med den period som ska periodiseras.</span><span class="sxs-lookup"><span data-stu-id="140c4-124">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="140c4-125">Om du väljer **saldo från idag** visar saldot summan av alla periodiseringar, justeringar och begäranden från och med idag.</span><span class="sxs-lookup"><span data-stu-id="140c4-125">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="140c4-126">Om du väljer **saldo för en periodiseringsperiod**, visar saldot summan av alla periodiseringar, justeringar och förfrågningar per den periodiseringsperiod som definieras av frekvensen i planen för tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="140c4-126">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="140c4-127">Ange starttiden för batchjobbet för förfallet av överföringsdatumet.</span><span class="sxs-lookup"><span data-stu-id="140c4-127">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="140c4-128">Välj **Ja** om **låt medarbetare köpa tjänstledighet** och **låta medarbetare sälja sina tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="140c4-128">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="140c4-129">Om du väljer **Ja** för dessa alternativ kan du skapa inköps- och försäljningsprincip för tjänstledighet och göra det möjligt för medarbetare att skicka in begäran inköps- och försäljningsprincip.</span><span class="sxs-lookup"><span data-stu-id="140c4-129">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="140c4-130">Konfigurera kalenderparametrar</span><span class="sxs-lookup"><span data-stu-id="140c4-130">Configure calendar parameters</span></span>

1. <span data-ttu-id="140c4-131">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="140c4-131">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="140c4-132">Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="140c4-132">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="140c4-133">På fliken **Kalender** ändra kalenderinställningar och efter behov.</span><span class="sxs-lookup"><span data-stu-id="140c4-133">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="140c4-134">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="140c4-134">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="140c4-135">Se även</span><span class="sxs-lookup"><span data-stu-id="140c4-135">See also</span></span>

- [<span data-ttu-id="140c4-136">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="140c4-136">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
