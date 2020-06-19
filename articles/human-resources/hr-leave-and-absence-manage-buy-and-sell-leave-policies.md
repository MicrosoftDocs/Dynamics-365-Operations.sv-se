---
title: Hantera policyer för köpa och sälja tjänstledighet
description: Du kan göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429023"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="999c1-103">Hantera policyer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="999c1-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="999c1-104">Du kan göra det möjligt för medarbetare att köpa tjänstledighet genom att skapa en policy för köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="999c1-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="999c1-105">Göra det möjligt för medarbetare att köpa och sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="999c1-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="999c1-106">På sidan **Parametrar för tjänstledighet och frånvaro** välj **Ja** för **Tillåt medarbetare att köpa tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="999c1-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="999c1-107">Skapa en policy för att köpa tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="999c1-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="999c1-108">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="999c1-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="999c1-109">Välj **policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="999c1-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="999c1-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="999c1-110">Select **New**.</span></span>

4. <span data-ttu-id="999c1-111">Ange ett **Namn** och **Beskrivning** för policyn under **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="999c1-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="999c1-112">Välj en **Policytyp**.</span><span class="sxs-lookup"><span data-stu-id="999c1-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="999c1-113">De tillgängliga policytyperna är **belopp** och **timmar per vecka**.</span><span class="sxs-lookup"><span data-stu-id="999c1-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="999c1-114">Välj **belopp** för att ange ett **fast belopp** för de maximala belopp som medarbetarna kan köpa och sälja.</span><span class="sxs-lookup"><span data-stu-id="999c1-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="999c1-115">Om du väljer **timmar per vecka**, används den arbetstid som definierats i medarbetarens tilldelade arbetstidskalender för att bestämma det maximala beloppet för policyn.</span><span class="sxs-lookup"><span data-stu-id="999c1-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="999c1-116">Välj ett **startdatum** och ett **slutdatum** för policyn.</span><span class="sxs-lookup"><span data-stu-id="999c1-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="999c1-117">Begäran om att köpa eller sälja tjänstledighet är bara tillgänglig för överföring under den här tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="999c1-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="999c1-118">Under **köppolicy** väljer du **Heltidslön** (FTE) för att göra proportionell fördelning det högsta beloppet baserat på den heltidslön som definierats för medarbetarens befattning.</span><span class="sxs-lookup"><span data-stu-id="999c1-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="999c1-119">Om policytypen är **belopp** anger du ett **maximalt fast belopp**.</span><span class="sxs-lookup"><span data-stu-id="999c1-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="999c1-120">Välj **Lägg till** om du vill lägga till tjänstledighetstyperna för medarbetare att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="999c1-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="999c1-121">Du kan lägga till flera tjänstledighetstyper till policyn.</span><span class="sxs-lookup"><span data-stu-id="999c1-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="999c1-122">Ange **servicemånader** för den tjänstledighetstyp om du vill tillåta olika månaders service att avgöra det maximala belopp en medarbetare kan köpa.</span><span class="sxs-lookup"><span data-stu-id="999c1-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="999c1-123">Ange det **högsta beloppet** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="999c1-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="999c1-124">Ange **Priset** som medarbetaren ska köpa tjänstledigheten för.</span><span class="sxs-lookup"><span data-stu-id="999c1-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="999c1-125">Alternativt kan du ange den **Inkomstkod** som ska användas för att köpa tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="999c1-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="999c1-126">Ange om du vill använda en motsvarande avskrivningstyp för att fastställa det högsta beloppet för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="999c1-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="999c1-127">Lägg till policyn köp och försäljning av tjänstledighet till en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="999c1-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="999c1-128">På sidan **Tjänstledighet och frånvaro** väljer du en tjänstledighets- och frånvaroplan.</span><span class="sxs-lookup"><span data-stu-id="999c1-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="999c1-129">Under **Regler**, välj **Policy för att köpa och sälja tjänstledighet**.</span><span class="sxs-lookup"><span data-stu-id="999c1-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="999c1-130">Se även</span><span class="sxs-lookup"><span data-stu-id="999c1-130">See also</span></span>

[<span data-ttu-id="999c1-131">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="999c1-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="999c1-132">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="999c1-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="999c1-133">Periodisera planer för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="999c1-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="999c1-134">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="999c1-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

