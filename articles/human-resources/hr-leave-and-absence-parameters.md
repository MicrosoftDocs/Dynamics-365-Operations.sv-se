---
title: Konfigurera tjänstledighets- och frånvaroparametrar
description: Definiera personalparametrar för tjänstledighet och frånvaro i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 45f5ebfe7bd11a529e871f5fd3244577954534f5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794647"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="ebfe3-103">Konfigurera tjänstledighets- och frånvaroparametrar</span><span class="sxs-lookup"><span data-stu-id="ebfe3-103">Configure leave and absence parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ebfe3-104">Innan du ställer in tjänstledighets- och frånvaroplan i Dynamics 365 Human Resources kan det vara en bra idé att kontrollera inställningarna för alla relaterade personalparametrar, t.ex.:</span><span class="sxs-lookup"><span data-stu-id="ebfe3-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="ebfe3-105">Nummerserie för tjänstledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="ebfe3-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="ebfe3-106">Inställning av Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="ebfe3-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="ebfe3-107">Inställningar för självbetjäning för medarbetare för tjänstledighets- och frånvaroansökningar</span><span class="sxs-lookup"><span data-stu-id="ebfe3-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="ebfe3-108">Parametrar för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="ebfe3-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="ebfe3-109">Visa och ändra personalparametrar</span><span class="sxs-lookup"><span data-stu-id="ebfe3-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="ebfe3-110">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ebfe3-111">Under **Inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="ebfe3-112">På fliken **nummerserier** kontrollerar du **nummerseriekod** för **begäran om tjänstledighet-ID** och ändrar vid behov.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="ebfe3-113">Den här inställningen avgör vilken sekvens som används för automatiskt tilldelning av ID:n för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="ebfe3-114">På fliken **FMLA** kontrollera FMLA-inställningar och ändra efter behov.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="ebfe3-115">På fliken **Självbetjäning för medarbetare** anger du om chefer kan ange tjänstledighets- och frånvaroansökningar för medarbetarnas räkning.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="ebfe3-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ebfe3-117">Att visa tjänstledighet och frånvaro för alla företag är för närvarande i förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="ebfe3-118">Du måste aktivera det i **sandbox-miljön** för att kunna visa alternativet tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="ebfe3-119">Mer information om att aktivera förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="ebfe3-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="ebfe3-120">Visa och ändra delade personalparametrar</span><span class="sxs-lookup"><span data-stu-id="ebfe3-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="ebfe3-121">På sidan **Personalhantering** väjer du fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ebfe3-122">Under **Inställningar**, välj **Delade personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="ebfe3-123">Under fliken **Tidig åtkomst** väljer du **Ja** för **Aktivera vy över företagsövergripande ledighet** för att visa ledighet över hela företaget.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="ebfe3-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="ebfe3-125">Visa och ändra parametrar för ledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="ebfe3-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="ebfe3-126">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ebfe3-127">Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="ebfe3-128">Ange följande parametrar på fliken **Allmänt**:</span><span class="sxs-lookup"><span data-stu-id="ebfe3-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="ebfe3-129">Ställ in **Enhet för tjänstledighet och frånvaro** till antingen timmar eller dagar.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="ebfe3-130">Om dagar kan du välja **aktivera halvdags definition** om du vill tillåta att medarbetare väljer antingen första eller andra halvan av dagen i sina ledighetsbegäran.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="ebfe3-131">Välj **tjänstmånaders giltighetsdatum** om du vill ange när periodiseringspriser ska gälla för tjänstledighetsplaner med hjälp av tjänstmånader.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="ebfe3-132">Välj **saldoberäkning** om du vill visa saldon som visas från och med den period som ska periodiseras.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="ebfe3-133">Om du väljer **saldo från idag** visar saldot summan av alla periodiseringar, justeringar och begäranden från och med idag.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="ebfe3-134">Om du väljer **saldo för en periodiseringsperiod**, visar saldot summan av alla periodiseringar, justeringar och förfrågningar per den periodiseringsperiod som definieras av frekvensen i planen för tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="ebfe3-135">Ange starttiden för batchjobbet för förfallet av överföringsdatumet.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="ebfe3-136">Välj **Ja** om **låt medarbetare köpa tjänstledighet** och **låta medarbetare sälja sina tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="ebfe3-137">Om du väljer **Ja** för dessa alternativ kan du skapa inköps- och försäljningsprincip för tjänstledighet och göra det möjligt för medarbetare att skicka in begäran inköps- och försäljningsprincip.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="ebfe3-138">Konfigurera kalenderparametrar</span><span class="sxs-lookup"><span data-stu-id="ebfe3-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="ebfe3-139">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ebfe3-140">Under **Inställningar**, välj **Parametrar för tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="ebfe3-141">På fliken **Kalender** ändra kalenderinställningar och efter behov.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="ebfe3-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ebfe3-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebfe3-143">Se även</span><span class="sxs-lookup"><span data-stu-id="ebfe3-143">See also</span></span>

- [<span data-ttu-id="ebfe3-144">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="ebfe3-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]