---
title: Manuell uppdatering av tillgångsräknare
description: Det här avsnittet beskriver manuell uppdatering av tillgångsräknare i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4618ff2d6880f478683fbed0ed716af5ab8d4d9c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842259"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="bb801-103">Manuell uppdatering av tillgångsräknare</span><span class="sxs-lookup"><span data-stu-id="bb801-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bb801-104">Räknare används för att skapa registreringar för en tillgång, t.ex. registreringar om antalet timmar som tillgången har varit i drift eller den kvantitet som har producerats.</span><span class="sxs-lookup"><span data-stu-id="bb801-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="bb801-105">Den räknartyp som valts för en räknare kan vara inställd på att ärva räknarvärden.</span><span class="sxs-lookup"><span data-stu-id="bb801-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="bb801-106">Med andra ord ställs alternativet **Ärv värden för tillgångsräknare** på **Ja** på snabbfliken **allmänt** på sidan **räknare** (**Tillgångshantering** > **Inställningar** > **Tillgångstyper** > **Räknare**).</span><span class="sxs-lookup"><span data-stu-id="bb801-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="bb801-107">När du i detta fall skapar en ny räknarrad av den typen, uppdateras alla underordnade tillgångar som använder samma räknartyp automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bb801-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="bb801-108">På sidan I **Alla tillgångar** kan du skapa tim- eller kvantitetsräknarregistreringar för en tillgång, baserat på dina avläsningar av tillgången.</span><span class="sxs-lookup"><span data-stu-id="bb801-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="bb801-109">Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="bb801-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="bb801-110">Välj tillgången och sedan, i åtgärdsfönstret på fliken **Tillgång** i gruppen **Förebyggande** väljer du **Räknare**.</span><span class="sxs-lookup"><span data-stu-id="bb801-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="bb801-111">Sidan **Tillgångsräknare** visas en lista över alla tidigare räknarregistreringar som har gjorts för den valda tillgången.</span><span class="sxs-lookup"><span data-stu-id="bb801-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="bb801-112">Skapa en ny registrering genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="bb801-112">Select **New** to create a registration.</span></span> <span data-ttu-id="bb801-113">Tillgångs-ID anges automatiskt i fältet **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="bb801-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="bb801-114">Välj relevant räknare i fältet **Räknare**.</span><span class="sxs-lookup"><span data-stu-id="bb801-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="bb801-115">Endast räknare som hör till den tillgångstyp som valts i tillgången är tillgängliga för val.</span><span class="sxs-lookup"><span data-stu-id="bb801-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="bb801-116">Den relaterade enheten anges automatiskt i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="bb801-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="bb801-117">I fältet **Registrerad** välj datum och tid för räknaregistreringen.</span><span class="sxs-lookup"><span data-stu-id="bb801-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="bb801-118">I fältet **värde** anger du numret sedan den senaste räknarregistreringen.</span><span class="sxs-lookup"><span data-stu-id="bb801-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="bb801-119">I fältet **aggregerad värde** kan du också ange det totala inventeringsnumret.</span><span class="sxs-lookup"><span data-stu-id="bb801-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="bb801-120">Observera följande:</span><span class="sxs-lookup"><span data-stu-id="bb801-120">Note the following points:</span></span>

- <span data-ttu-id="bb801-121">Om du installerar en ny räknare för en tillgång fysiskt måste du registrera ändringen i tillgången på sidan **Tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="bb801-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="bb801-122">Sedan måste du skapa två registreringsrader som har identiska tidsstämplar.</span><span class="sxs-lookup"><span data-stu-id="bb801-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="bb801-123">Den första raden måste vara för den räknare som du ersätter.</span><span class="sxs-lookup"><span data-stu-id="bb801-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="bb801-124">På raden som är relaterad till den nya räknaren markerar du kryssrutan **Återställ räknare**.</span><span class="sxs-lookup"><span data-stu-id="bb801-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="bb801-125">I fältet **Summor** är den totala räknarsumman summan av alla registrerade värden på den räknartypen.</span><span class="sxs-lookup"><span data-stu-id="bb801-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="bb801-126">Om kryssrutan **Återställ räknare** har markerats för en tillgång med en underhållsplan med intervalltypen "En gång från..." eller "När...nås" är räknaren fortfarande aktiv på den nya räknarraden, eftersom du skapar en separat räknarrad och börjar om med en ny räknare.</span><span class="sxs-lookup"><span data-stu-id="bb801-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="bb801-127">Bilden nedan visar ett exempel på sidan **Tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="bb801-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Figur 1](media/11-work-orders.png)

<span data-ttu-id="bb801-129">På sidan **Tillgångsräknare** (**Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Tillgångsräknare**) kan du göra räknarregistreringar på flera tillgångar samtidigt, efter behov.</span><span class="sxs-lookup"><span data-stu-id="bb801-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="bb801-130">Du kan ställa in ett intervall för att definiera avvikelser i manuella räknarregistreringar.</span><span class="sxs-lookup"><span data-stu-id="bb801-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="bb801-131">Du kan även ange vilken typ av meddelande som visas om registreringarna ligger utanför det definierade intervallet.</span><span class="sxs-lookup"><span data-stu-id="bb801-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="bb801-132">Mer information om hur du ställer in räknare finns i [räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="bb801-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]