---
title: Kostnadskontroll för tillgångsfel
description: I det här avsnittet förklaras kostnadskontroll för tillgångsfel i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 597e30db346e882a7002709be52ad1c2d0576099
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019963"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="6f235-103">Kostnadskontroll för tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="6f235-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6f235-104">I Tillgångshantering kan du beräkna kostnader för tillgångsfelregistreringar att få en översikt över de faktiska kostnaderna jämfört.</span><span class="sxs-lookup"><span data-stu-id="6f235-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="6f235-105">Faktiska kostnader baseras på bokförda transaktioner.</span><span class="sxs-lookup"><span data-stu-id="6f235-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="6f235-106">Datumet är feldatumet då symptomen registrerades.</span><span class="sxs-lookup"><span data-stu-id="6f235-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="6f235-107">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Kostnadskontroll för tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="6f235-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="6f235-108">I dialogrutan **Kostnadskontroll för tillgångsfel** väljer du en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen om det behövs.</span><span class="sxs-lookup"><span data-stu-id="6f235-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="6f235-109">Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.</span><span class="sxs-lookup"><span data-stu-id="6f235-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="6f235-110">Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="6f235-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="6f235-111">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla kostnadskontrollrader för tillgångsfel för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="6f235-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="6f235-112">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader för tillgångsfel på alla funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="6f235-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="6f235-113">Om du vill begränsa sökningen kan du välja specifika tillgångar, feldatum och felorsaker på snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="6f235-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="6f235-114">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="6f235-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="6f235-115">Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="6f235-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="6f235-116">De valda knapparna **Gruppera efter** markeras.</span><span class="sxs-lookup"><span data-stu-id="6f235-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="6f235-117">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="6f235-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="6f235-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="6f235-118">Example</span></span>

<span data-ttu-id="6f235-119">Det här exemplet visar en kostnadskontrollberäkning för tillgångsfel.</span><span class="sxs-lookup"><span data-stu-id="6f235-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="6f235-120">I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen.</span><span class="sxs-lookup"><span data-stu-id="6f235-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="6f235-121">I fältet **Faktisk kostnad** visas bokförda kostnader för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6f235-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="6f235-122">I fältet **Utfästa kostnader** visas det totala kostnaderna som ditt företag är förpliktigat att utföra i relation till arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6f235-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Figur 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="6f235-124">För information om hur du ställer in fel, se avsnittet [Felhantering](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="6f235-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
