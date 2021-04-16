---
title: Synkronisera på begäran med prissättningsmotorn Supply Chain Management
description: I det här avsnittet beskrivs hur du använder prissättningsmotorn Microsoft Dynamics 365 Supply Chain Management från Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: bf4154816f01040a236dde77b92ee69396158614
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750774"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a><span data-ttu-id="ff5af-103">Synkronisera på begäran med prissättningsmotorn Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ff5af-103">Sync on-demand with the Supply Chain Management pricing engine</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ff5af-104">Microsoft Dynamics 365 Supply Chain Management inkluderar en prissättningsmotor för hantering av handelsavtal, prislistor, kundbonusprogram, erbjudanden och rabatter.</span><span class="sxs-lookup"><span data-stu-id="ff5af-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="ff5af-105">Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order.</span><span class="sxs-lookup"><span data-stu-id="ff5af-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="ff5af-106">När du använder dubbelriktad skrivning använder du antingen statiska priser eller prissättningsmotorn från Dynamics 365 Supply Chain Management på sidorna offert och order i Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5af-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="ff5af-107">Använd prissättningsmotorn från Supply Chain Management i Sales</span><span class="sxs-lookup"><span data-stu-id="ff5af-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="ff5af-108">I Sales, gå till **Sales \> Order**.</span><span class="sxs-lookup"><span data-stu-id="ff5af-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="ff5af-109">Välj **Ny** för att skapa en ny order eller välj en befintlig order i listan **Mina order**.</span><span class="sxs-lookup"><span data-stu-id="ff5af-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="ff5af-110">Lägg till en ny orderrad.</span><span class="sxs-lookup"><span data-stu-id="ff5af-110">Add a new order line.</span></span>
4. <span data-ttu-id="ff5af-111">Om du skapar en ny order väljer du **Prisorder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ff5af-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="ff5af-112">Om du uppdaterar en befintlig order väljer du **Beräkna om** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ff5af-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="ff5af-113">Följande kolumner fylls i automatiskt:</span><span class="sxs-lookup"><span data-stu-id="ff5af-113">The following columns are automatically filled in:</span></span>

    + <span data-ttu-id="ff5af-114">Detaljbelopp</span><span class="sxs-lookup"><span data-stu-id="ff5af-114">Detail Amount</span></span>
    + <span data-ttu-id="ff5af-115">Rabatt i %</span><span class="sxs-lookup"><span data-stu-id="ff5af-115">Discount %</span></span>
    + <span data-ttu-id="ff5af-116">Rabatt</span><span class="sxs-lookup"><span data-stu-id="ff5af-116">Discount</span></span>
    + <span data-ttu-id="ff5af-117">Belopp före frakt</span><span class="sxs-lookup"><span data-stu-id="ff5af-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="ff5af-118">Fraktbelopp</span><span class="sxs-lookup"><span data-stu-id="ff5af-118">Freight Amount</span></span>
    + <span data-ttu-id="ff5af-119">Summa moms</span><span class="sxs-lookup"><span data-stu-id="ff5af-119">Total Tax</span></span>
    + <span data-ttu-id="ff5af-120">Totalt belopp</span><span class="sxs-lookup"><span data-stu-id="ff5af-120">Total Amount</span></span>
    
5. <span data-ttu-id="ff5af-121">För att säkerställa att systemet beaktar handels- och försäljningsavtal vid beräkningen av priset:</span><span class="sxs-lookup"><span data-stu-id="ff5af-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="ff5af-122">Navigera till din miljö för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff5af-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="ff5af-123">Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="ff5af-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="ff5af-124">Klicka på fliken **priser** i navigeringsfältet på sidan.</span><span class="sxs-lookup"><span data-stu-id="ff5af-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="ff5af-125">Under snabbfliken **Utvärdering av handelsavtal** avmarkerar du alternativet **manuell inmatning**.</span><span class="sxs-lookup"><span data-stu-id="ff5af-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ff5af-126">Hur det fungerar</span><span class="sxs-lookup"><span data-stu-id="ff5af-126">How it works</span></span>

<span data-ttu-id="ff5af-127">När du väljer **prisorder** i Sales anropar funktionen **summor** på fliken **försäljningsorder \> vy** i Supply Chain Management anropas för tillhörande försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ff5af-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="ff5af-128">Värdena i ordersumman i Sales används för att fylla i motsvarande kolumner i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff5af-128">The values in the order total in Sales are used to fill in the corresponding columns in Supply Chain Management.</span></span>

<span data-ttu-id="ff5af-129">När försäljningsordersumman beräknas i Supply Chain Management., evaluerar beräkningen de befintliga handelsavtalen och försäljningsavtalen för kunden och de produkter som anges i försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="ff5af-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="ff5af-130">Denna information används för att beräkna summorna.</span><span class="sxs-lookup"><span data-stu-id="ff5af-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="ff5af-131">När **prisorder** har valts visar Sales automatiskt alla inställningar som har gjorts i hanteringen av Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff5af-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="ff5af-132">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="ff5af-132">Limitations</span></span>

<span data-ttu-id="ff5af-133">När kolumnerna i Sales fylls i gäller följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="ff5af-133">When the columns in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="ff5af-134">Inställningarna för avgifter och debiteringar i Supply Chain Management replikeras inte i Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5af-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="ff5af-135">Priserna anser inte vara särskilda detaljhandelspris som är angivna i kolumnen **butikskanal** på sidan försäljningsorderrad i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff5af-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** column on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="ff5af-136">Rabatter som definieras i avsnittet **Hantering av handelsavdrag** i Supply Chain Management beaktas inte.</span><span class="sxs-lookup"><span data-stu-id="ff5af-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]