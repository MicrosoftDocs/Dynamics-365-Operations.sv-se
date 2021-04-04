---
title: Hantera policyer för köpa och sälja tjänstledighet
description: Du kan göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ccc6bf2e8b070e92cc4dbb98d8ec35ce60723516
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468093"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="7f442-103">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7f442-103">Manage buy and sell leave policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7f442-104">Du kan göra det möjligt för medarbetare att sälja tjänstledighet genom att skapa en policy för sälja tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="7f442-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="7f442-105">Du kan konfigurera dessa principer till att använda arbetsflöden för godkännanden, ställa in högsta belopp och tariffer och ange kostnader för inköp och försäljning.</span><span class="sxs-lookup"><span data-stu-id="7f442-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="7f442-106">Göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="7f442-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="7f442-107">På sidan **Parametrar för tjänstledighet** och frånvaro välj **Ja** för **Tillåt medarbetare att köpa tjänstledighet** och **Tillåt medarbetare att sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="7f442-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="7f442-108">Skapa policy för att köpa och sälja tjänstledigt</span><span class="sxs-lookup"><span data-stu-id="7f442-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="7f442-109">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="7f442-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="7f442-110">Välj **policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="7f442-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="7f442-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="7f442-111">Select **New**.</span></span>

4. <span data-ttu-id="7f442-112">Ange ett **Namn** och **Beskrivning** för policyn under **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="7f442-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="7f442-113">Välj en **Policytyp**.</span><span class="sxs-lookup"><span data-stu-id="7f442-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="7f442-114">De tillgängliga policytyperna är **belopp** och **timmar per vecka**.</span><span class="sxs-lookup"><span data-stu-id="7f442-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="7f442-115">Välj **belopp** för att ange ett **fast belopp** för de maximala belopp som medarbetarna kan köpa och sälja.</span><span class="sxs-lookup"><span data-stu-id="7f442-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="7f442-116">Om du väljer **timmar per vecka**, används den arbetstid som definierats i medarbetarens tilldelade arbetstidskalender för att bestämma det maximala beloppet för policyn.</span><span class="sxs-lookup"><span data-stu-id="7f442-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="7f442-117">Välj ett **startdatum** och ett **slutdatum** för policyn.</span><span class="sxs-lookup"><span data-stu-id="7f442-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="7f442-118">Begäran om att köpa eller sälja tjänstledighet är bara tillgänglig för överföring under den här tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="7f442-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="7f442-119">Välj ett **arbetsflödes-ID** för policyn.</span><span class="sxs-lookup"><span data-stu-id="7f442-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="7f442-120">Alla köp- och säljbegäranden kommer att använda det här arbetsflödet för granskning och godkännande.</span><span class="sxs-lookup"><span data-stu-id="7f442-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="7f442-121">Under **köppolicy** väljer du **Heltidslön** (FTE) för att göra proportionell fördelning det högsta beloppet baserat på den heltidslön som definierats för medarbetarens befattning.</span><span class="sxs-lookup"><span data-stu-id="7f442-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="7f442-122">Om policytypen är **belopp** anger du ett **maximalt fast belopp**.</span><span class="sxs-lookup"><span data-stu-id="7f442-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="7f442-123">Välj **Lägg till** om du vill lägga till tjänstledighetstyperna för medarbetare att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="7f442-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="7f442-124">Du kan lägga till flera tjänstledighetstyper till policyn.</span><span class="sxs-lookup"><span data-stu-id="7f442-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="7f442-125">Ange **servicemånader** för den tjänstledighetstyp om du vill tillåta olika månaders service att avgöra det maximala belopp en medarbetare kan köpa.</span><span class="sxs-lookup"><span data-stu-id="7f442-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="7f442-126">Ange det **högsta beloppet** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="7f442-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="7f442-127">Ange **Priset** som medarbetaren ska köpa tjänstledigheten för.</span><span class="sxs-lookup"><span data-stu-id="7f442-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="7f442-128">Alternativt kan du ange den **Inkomstkod** som ska användas för att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="7f442-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="7f442-129">Ange om du vill använda en motsvarande avskrivningstyp för att fastställa det högsta beloppet för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="7f442-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="7f442-130">Skapa en försäljningspolicy genom att följa steg 8 till 14 under **försäljningspolicy**.</span><span class="sxs-lookup"><span data-stu-id="7f442-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="7f442-131">Lägg till policyn köp och försäljning av tjänstledighet till en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="7f442-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="7f442-132">På sidan **Tjänstledighet och frånvaro** väljer du en tjänstledighets- och frånvaroplan.</span><span class="sxs-lookup"><span data-stu-id="7f442-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="7f442-133">Under **Regler**, välj **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="7f442-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f442-134">Se även</span><span class="sxs-lookup"><span data-stu-id="7f442-134">See also</span></span>

[<span data-ttu-id="7f442-135">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="7f442-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="7f442-136">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="7f442-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="7f442-137">Periodisera planer för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="7f442-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="7f442-138">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7f442-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]