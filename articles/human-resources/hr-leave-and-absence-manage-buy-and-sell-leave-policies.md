---
title: Hantera policyer för köpa och sälja tjänstledighet
description: Du kan göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 491d1654bd219b487f95a1eb328e574114ec1f9f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051387"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="871b8-103">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="871b8-103">Manage buy and sell leave policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="871b8-104">Du kan göra det möjligt för medarbetare att sälja tjänstledighet genom att skapa en policy för sälja tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="871b8-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="871b8-105">Du kan konfigurera dessa principer till att använda arbetsflöden för godkännanden, ställa in högsta belopp och tariffer och ange kostnader för inköp och försäljning.</span><span class="sxs-lookup"><span data-stu-id="871b8-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="871b8-106">Göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="871b8-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="871b8-107">På sidan **Parametrar för tjänstledighet** och frånvaro välj **Ja** för **Tillåt medarbetare att köpa tjänstledighet** och **Tillåt medarbetare att sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="871b8-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="871b8-108">Skapa policy för att köpa och sälja tjänstledigt</span><span class="sxs-lookup"><span data-stu-id="871b8-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="871b8-109">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="871b8-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="871b8-110">Välj **policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="871b8-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="871b8-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="871b8-111">Select **New**.</span></span>

4. <span data-ttu-id="871b8-112">Ange ett **Namn** och **Beskrivning** för policyn under **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="871b8-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="871b8-113">Välj en **Policytyp**.</span><span class="sxs-lookup"><span data-stu-id="871b8-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="871b8-114">De tillgängliga policytyperna är **belopp** och **timmar per vecka**.</span><span class="sxs-lookup"><span data-stu-id="871b8-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="871b8-115">Välj **belopp** för att ange ett **fast belopp** för de maximala belopp som medarbetarna kan köpa och sälja.</span><span class="sxs-lookup"><span data-stu-id="871b8-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="871b8-116">Om du väljer **timmar per vecka**, används den arbetstid som definierats i medarbetarens tilldelade arbetstidskalender för att bestämma det maximala beloppet för policyn.</span><span class="sxs-lookup"><span data-stu-id="871b8-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="871b8-117">Välj ett **startdatum** och ett **slutdatum** för policyn.</span><span class="sxs-lookup"><span data-stu-id="871b8-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="871b8-118">Begäran om att köpa eller sälja tjänstledighet är bara tillgänglig för överföring under den här tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="871b8-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="871b8-119">Välj ett **arbetsflödes-ID** för policyn.</span><span class="sxs-lookup"><span data-stu-id="871b8-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="871b8-120">Alla köp- och säljbegäranden kommer att använda det här arbetsflödet för granskning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="871b8-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="871b8-121">Under **köppolicy** väljer du **Heltidslön** (FTE) för att göra proportionell fördelning det högsta beloppet baserat på den heltidslön som definierats för medarbetarens befattning.</span><span class="sxs-lookup"><span data-stu-id="871b8-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="871b8-122">Om policytypen är **belopp** anger du ett **maximalt fast belopp**.</span><span class="sxs-lookup"><span data-stu-id="871b8-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="871b8-123">Välj **Lägg till** om du vill lägga till tjänstledighetstyperna för medarbetare att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="871b8-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="871b8-124">Du kan lägga till flera tjänstledighetstyper till policyn.</span><span class="sxs-lookup"><span data-stu-id="871b8-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="871b8-125">Ange **servicemånader** för den tjänstledighetstyp om du vill tillåta olika månaders service att avgöra det maximala belopp en medarbetare kan köpa.</span><span class="sxs-lookup"><span data-stu-id="871b8-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="871b8-126">Ange det **högsta beloppet** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="871b8-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="871b8-127">Ange **Priset** som medarbetaren ska köpa tjänstledigheten för.</span><span class="sxs-lookup"><span data-stu-id="871b8-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="871b8-128">Alternativt kan du ange den **Inkomstkod** som ska användas för att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="871b8-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="871b8-129">Ange om du vill använda en motsvarande avskrivningstyp för att fastställa det högsta beloppet för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="871b8-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="871b8-130">Skapa en försäljningspolicy genom att följa steg 8 till 14 under **försäljningspolicy**.</span><span class="sxs-lookup"><span data-stu-id="871b8-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="871b8-131">Lägg till policyn köp och försäljning av tjänstledighet till en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="871b8-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="871b8-132">På sidan **Tjänstledighet och frånvaro** väljer du en tjänstledighets- och frånvaroplan.</span><span class="sxs-lookup"><span data-stu-id="871b8-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="871b8-133">Under **Regler**, välj **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="871b8-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="871b8-134">Se även</span><span class="sxs-lookup"><span data-stu-id="871b8-134">See also</span></span>

[<span data-ttu-id="871b8-135">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="871b8-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="871b8-136">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="871b8-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="871b8-137">Periodisera planer för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="871b8-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="871b8-138">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="871b8-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]