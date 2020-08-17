---
title: Bekräfta utgående leveranser från batchjobb
description: I det här avsnittet beskrivs hur du ställer in ett batchjobb som automatiskt bekräftar utgående överföringsorder leveranser för laster som är redo att skickas.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652268"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="56d6c-103">Bekräfta utgående leveranser från batchjobb</span><span class="sxs-lookup"><span data-stu-id="56d6c-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56d6c-104">I det här avsnittet beskrivs hur du ställer in ett batchjobb som automatiskt bekräftar utgående överföringsorder leveranser för laster som är redo att skickas.</span><span class="sxs-lookup"><span data-stu-id="56d6c-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="56d6c-105">Det batchjobb som beskrivs här gäller bara för överföring av orderleveranser, inte för försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="56d6c-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="56d6c-106">Aktivera funktionen Bekräfta utgående leveranser från batchjobb</span><span class="sxs-lookup"><span data-stu-id="56d6c-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="56d6c-107">Innan du kan använda den här funktionen måste du aktivera den i ditt system.</span><span class="sxs-lookup"><span data-stu-id="56d6c-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="56d6c-108">Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="56d6c-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="56d6c-109">Funktionen visas som:</span><span class="sxs-lookup"><span data-stu-id="56d6c-109">The feature is listed as:</span></span>

- <span data-ttu-id="56d6c-110">**Modul** - *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="56d6c-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="56d6c-111">**Funktionens namn** - *Bekräfta utgående leveranser från batchjobb*</span><span class="sxs-lookup"><span data-stu-id="56d6c-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="56d6c-112">Bearbeta utgående leveranser</span><span class="sxs-lookup"><span data-stu-id="56d6c-112">Process outbound shipments</span></span>

<span data-ttu-id="56d6c-113">Så här ställer du in ett tidsplanerat batchjobb för att köra bekräftelse av utgående leverans för laster som är klara att levereras:</span><span class="sxs-lookup"><span data-stu-id="56d6c-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="56d6c-114">Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta utgående leveranser**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="56d6c-115">Dialogrutan **Bekräfta leverans** öppnas.</span><span class="sxs-lookup"><span data-stu-id="56d6c-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="56d6c-116">På snabbfliken **Poster att inkludera**, välj **Filter**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="56d6c-117">Dialogrutan frågeredigeraren öppnas.</span><span class="sxs-lookup"><span data-stu-id="56d6c-117">The query editor dialog box opens.</span></span> <span data-ttu-id="56d6c-118">På fliken **intervall**, lägg till en rad med följande värden:</span><span class="sxs-lookup"><span data-stu-id="56d6c-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="56d6c-119">**Register** - *Laster*</span><span class="sxs-lookup"><span data-stu-id="56d6c-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="56d6c-120">**Härledda register** - *Laster*</span><span class="sxs-lookup"><span data-stu-id="56d6c-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="56d6c-121">**Fält** - *Laststatus*</span><span class="sxs-lookup"><span data-stu-id="56d6c-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="56d6c-122">**Kriterier** - *Lastad*</span><span class="sxs-lookup"><span data-stu-id="56d6c-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="56d6c-123">Välj **OK** om du vill gå tillbaka till dialogrutan **Bekräfta leverans**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="56d6c-124">På snabbfliken **Kör i bakgrunden** ange **Batchbearbetning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="56d6c-125">På snabbfliken **kör i bakgrunden** väljer du **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="56d6c-126">Dialogrutan **Definiera återkommande** öppnas.</span><span class="sxs-lookup"><span data-stu-id="56d6c-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="56d6c-127">Ange det körschema som behövs för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="56d6c-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="56d6c-128">Välj **OK** om du vill gå tillbaka till dialogrutan **Bekräfta leverans**.</span><span class="sxs-lookup"><span data-stu-id="56d6c-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="56d6c-129">Välj **OK** i dialogrutan **Bekräfta leverans** för att lägga till batchjobbet i batchkön.</span><span class="sxs-lookup"><span data-stu-id="56d6c-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="56d6c-130">Mer information finns i [Översikt över batchbearbetning](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56d6c-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>
