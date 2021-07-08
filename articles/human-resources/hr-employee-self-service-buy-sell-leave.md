---
title: Köpa och sälja tjänstledighet
description: I Dynamics 365 Human Resources kan du skicka en begäran om att köpa och sälja på grund val av principerna köp och försäljning som ställs in av ditt företag.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271505"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="7fb97-103">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7fb97-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7fb97-104">I Dynamics 365 Human Resources kan du skicka en begäran om att köpa och sälja på grund val av principerna köp och försäljning som ställs in av ditt företag.</span><span class="sxs-lookup"><span data-stu-id="7fb97-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="7fb97-105">Begäran om att köpa tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7fb97-105">Request to buy leave</span></span>

1. <span data-ttu-id="7fb97-106">I arbetsyta **Självbetjäning för medarbetare**, välj **Begäran om att köpa tjänstledighet** panelen **ledighetssaldon**.</span><span class="sxs-lookup"><span data-stu-id="7fb97-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="7fb97-107">Lägg till en **Tjänstledighetstyp** och ange ett **Belopp** för den mängd tjänstledighet du vill köpa.</span><span class="sxs-lookup"><span data-stu-id="7fb97-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="7fb97-108">Välj **skicka** när du är redo att skicka din begäran.</span><span class="sxs-lookup"><span data-stu-id="7fb97-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="7fb97-109">Dina saldon kommer antingen att uppdateras automatiskt eller gå igenom en godkännande process innan du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="7fb97-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="7fb97-110">Detta beror på hur inköpsprincipen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="7fb97-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="7fb97-111">Begäran om att sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7fb97-111">Request to sell leave</span></span>

1. <span data-ttu-id="7fb97-112">I arbetsyta **Självbetjäning för medarbetare**, välj **Begäran om att sälja tjänstledighet** panelen **ledighetssaldon**.</span><span class="sxs-lookup"><span data-stu-id="7fb97-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="7fb97-113">Lägg till en **Tjänstledighetstyp** och ange ett **Belopp** för den mängd tjänstledighet du vill sälja.</span><span class="sxs-lookup"><span data-stu-id="7fb97-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="7fb97-114">Välj **skicka** när du är redo att skicka din begäran.</span><span class="sxs-lookup"><span data-stu-id="7fb97-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="7fb97-115">Dina saldon kommer antingen att uppdateras automatiskt eller gå igenom en godkännande process innan du uppdaterar.</span><span class="sxs-lookup"><span data-stu-id="7fb97-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="7fb97-116">Detta beror på hur inköpsprincipen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="7fb97-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="7fb97-117">Felsökning</span><span class="sxs-lookup"><span data-stu-id="7fb97-117">Troubleshooting</span></span> 

<span data-ttu-id="7fb97-118">Om ett arbetsflöde för begäran om köp eller försäljning misslyckas misslyckas användare med **EssLeaveBuySellRequestApprover** privilegium kan granska meddelandeloggen för alla begäran om köp och försäljning.</span><span class="sxs-lookup"><span data-stu-id="7fb97-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="7fb97-119">För att göra detta, gå till **Tjänstledighet > Länk > Köpa och sälja tjänstledighetsansökningar > Meddelandelogg** (upp till vänster).</span><span class="sxs-lookup"><span data-stu-id="7fb97-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="7fb97-120">I **meddelandeloggen** visas hur transaktionerna bearbetas och vilken arbetsflödeshistorik som har associerats.</span><span class="sxs-lookup"><span data-stu-id="7fb97-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="7fb97-121">Se även</span><span class="sxs-lookup"><span data-stu-id="7fb97-121">See also</span></span>

[<span data-ttu-id="7fb97-122">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="7fb97-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="7fb97-123">Hantera policyer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="7fb97-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
