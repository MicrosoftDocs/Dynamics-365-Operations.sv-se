---
title: Automatisk bekräftelse med planeringsoptimering
description: I det här avsnittet beskrivs hur du använder automatisk bekräftelse för planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 9106137fe6dd097beea9914cdde541e581946f46
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227808"
---
# <a name="autofirming-with-planning-optimization"></a><span data-ttu-id="3ba00-103">Automatisk bekräftelse med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="3ba00-103">Autofirming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ba00-104">Med automatisk bekräftelse kan du bekräfta (dvs frisläppa) planerade order som en del av huvudplaneringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3ba00-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="3ba00-105">När planerade order bekräftas omvandlas de till faktiska inköpsorder, överföringsorder eller tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="3ba00-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="3ba00-106">När planeringsoptimering används bekräftas planerade order under en huvudplaneringskörning när orderdatumet (startdatumet) ligger inom tidsgränsen för bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="3ba00-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="3ba00-107">Automatisk bekräftelse av en planerad inköpsorder kan endast äga rum om artikel kopplades till en leverantör.</span><span class="sxs-lookup"><span data-stu-id="3ba00-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>

## <a name="turn-on-autofirming"></a><span data-ttu-id="3ba00-108">Aktivera automatisk bekräftelse</span><span class="sxs-lookup"><span data-stu-id="3ba00-108">Turn on autofirming</span></span>

<span data-ttu-id="3ba00-109">Så här aktiverar du automatisk bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="3ba00-109">To turn on autofirming, follow these steps.</span></span>

1. <span data-ttu-id="3ba00-110">I arbetsytan **Funktionshantering** på fliken **Ny**, välj **Automatisk bekräftelse för planeringsoptimering** i listan.</span><span class="sxs-lookup"><span data-stu-id="3ba00-110">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="3ba00-111">Om funktionen inte visas på fliken **Ny** tittar du på flikarna **Ej aktiverad** och **Alla**.</span><span class="sxs-lookup"><span data-stu-id="3ba00-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="3ba00-112">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="3ba00-112">Select **Enable now**.</span></span> <span data-ttu-id="3ba00-113">Du kan också välja **schema** och sedan välja den tidpunkt då funktionen ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="3ba00-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="3ba00-114">Ställ in bekräftad tidsgräns</span><span class="sxs-lookup"><span data-stu-id="3ba00-114">Set up the firming time fence</span></span>

<span data-ttu-id="3ba00-115">Bekräftad tidsgräns beräknas framåt från körningsdatumet för huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="3ba00-115">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="3ba00-116">Det definieras av antalet dagar som du anger.</span><span class="sxs-lookup"><span data-stu-id="3ba00-116">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="3ba00-117">Du kan kontrollera bekräftad tidsgräns på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3ba00-117">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="3ba00-118">Om du vill definiera standard bekräftad tidsgräns för en disponeringsgrupp går du till **Huvudplanering** \> **Inställningar** \> **Disponering** \> **Disponeringsgrupper** och väljer en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="3ba00-118">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="3ba00-119">Ange sedan antalet dagar på snabbfliken **övrigt** i fältet **Automatisk bekräftelse av tidsgräns (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="3ba00-119">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="3ba00-120">Om du vill skriva över den bekräftelse av tidsgräns som har definierats för disponeringsgruppen för en viss artikel går du till **Produktinformationshantering** \> **Släppta produkter**. I åtgärdsfönstret väljer du sedan **Plan** och därefter **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="3ba00-120">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the Action Pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="3ba00-121">Sedan på fliken **Allmänt** väljer du **Åsidosätt tidsgränser** och i fältet **Automatisk bekräftelse av tidsgräns (dagar)** anger du antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="3ba00-121">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="3ba00-122">Om du vill skriva över den bekräftelse av tidsgräns som har definierats för disponeringsgruppen och artikeldisponering för en viss huvudplan går du till **Huvudplanering** \> **Inställningar** \> **Huvudplaner** och välj en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="3ba00-122">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="3ba00-123">Sedan på snabbfliken **tidsgräns i dagar** ange **Bekräftelse** till **Ja** och ange antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="3ba00-123">Then, on the **Time fence in days** FastTab, set **Firming** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="3ba00-124">Om automatisk bekräftelse aktiveras för en huvudplaneringskörning där planeringsoptimering används, utförs automatiskt bekräftelseprocess enligt inställningen för automatisk bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="3ba00-124">If autofirming is turned on for a master planning run that uses Planning Optimization, the autofirming process is done according to the autofirming setup.</span></span> <span data-ttu-id="3ba00-125">Om automatisk bekräftelse inte är aktiverad eller om planeringen startas från sidan **nettobehov** hoppas den automatiska bekräftelseprocessen över.</span><span class="sxs-lookup"><span data-stu-id="3ba00-125">If autofirming isn't turned on, or if planning is started from the **Net requirements** page, the autofirming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="3ba00-126">Planeringsoptimering jämfört med den inbyggda planeringsmotorn för Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3ba00-126">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="3ba00-127">Både planeringsoptimering och planeringsmotorn som är inbyggd i Microsoft Dynamics 365 Supply Chain Management kan användas för att automatiskt bekräfta planerade order.</span><span class="sxs-lookup"><span data-stu-id="3ba00-127">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to autofirm planned orders.</span></span> <span data-ttu-id="3ba00-128">Det finns emellertid några viktiga skillnader.</span><span class="sxs-lookup"><span data-stu-id="3ba00-128">However, there are some important differences.</span></span> <span data-ttu-id="3ba00-129">Exempel: planeringsoptimering använder orderdatum (dvs. startdatum) för att avgöra vilka planerade order som ska bekräftas, den inbyggda planeringsmotorn för Supply Chain Management använder behovsdatum (dvs. slutdatumet).</span><span class="sxs-lookup"><span data-stu-id="3ba00-129">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="3ba00-130">Här följer en sammanfattning av skillnaderna.</span><span class="sxs-lookup"><span data-stu-id="3ba00-130">Here is a summary of the differences.</span></span>

<span data-ttu-id="3ba00-131">**Planeringsoptimering**</span><span class="sxs-lookup"><span data-stu-id="3ba00-131">**Planning Optimization**</span></span>

- <span data-ttu-id="3ba00-132">Automatisk bekräftelse baseras på orderdatumet (startdatum).</span><span class="sxs-lookup"><span data-stu-id="3ba00-132">Autofirming is based on the order date (start date).</span></span>
- <span data-ttu-id="3ba00-133">Eftersom orderdatumet (startdatum) utlöser bekräftelsen behöver du inte tänka på produktionstiden som en del av den bekräftade tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="3ba00-133">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="3ba00-134">Om du vill bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade tidsgränsen vara en vecka.</span><span class="sxs-lookup"><span data-stu-id="3ba00-134">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="3ba00-135">**Inbyggd planeringsmotor för Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="3ba00-135">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="3ba00-136">Automatisk bekräftelse baseras på behovsdatum (slutdatum).</span><span class="sxs-lookup"><span data-stu-id="3ba00-136">Autofirming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="3ba00-137">För att garantera att order bekräftas i tid måste den bekräftade tidsgränsen vara längre än produktionstiden.</span><span class="sxs-lookup"><span data-stu-id="3ba00-137">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="3ba00-138">Om du vill bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade produktionstid plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="3ba00-138">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]