--- 
title: "Rapportera en produktionsorder som färdig"
description: "I den här proceduren visas hur du rapporterar en produktionsorder som färdig."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 17b2285e4669f1ad8fa6cea1250693a2a70c7dfa
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="11f44-103">Rapportera en produktionsorder som färdig</span><span class="sxs-lookup"><span data-stu-id="11f44-103">Report a production order as finished</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="11f44-104">I den här proceduren visas hur du rapporterar en produktionsorder som färdig.</span><span class="sxs-lookup"><span data-stu-id="11f44-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="11f44-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="11f44-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="11f44-106">Detta är den sjätte proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="11f44-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="11f44-107">Rapportera en produktionsorder som färdig</span><span class="sxs-lookup"><span data-stu-id="11f44-107">Report a production order as finished</span></span>
1. <span data-ttu-id="11f44-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="11f44-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="11f44-109">Välj en produktionsorder som har statusen Startat.</span><span class="sxs-lookup"><span data-stu-id="11f44-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="11f44-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="11f44-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="11f44-111">Klicka på Rapportera som färdig.</span><span class="sxs-lookup"><span data-stu-id="11f44-111">Click Report as finished.</span></span>
    * <span data-ttu-id="11f44-112">På den här sidan kan du bekräfta kvantiteten av den färdiga produkten som ska rapporteras som färdig.</span><span class="sxs-lookup"><span data-stu-id="11f44-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="11f44-113">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="11f44-113">Click the General tab.</span></span>
5. <span data-ttu-id="11f44-114">Ställ in Godkänd kvantitet på 18.</span><span class="sxs-lookup"><span data-stu-id="11f44-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="11f44-115">Ställ in Antal fel på 2.</span><span class="sxs-lookup"><span data-stu-id="11f44-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="11f44-116">Välj Material i fältet Felorsak.</span><span class="sxs-lookup"><span data-stu-id="11f44-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="11f44-117">Markera eller avmarkera kryssrutan Slutjobb.</span><span class="sxs-lookup"><span data-stu-id="11f44-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="11f44-118">Markera eller avmarkera kryssrutan Godta fel.</span><span class="sxs-lookup"><span data-stu-id="11f44-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="11f44-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="11f44-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="11f44-120">Verifiera journalen Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="11f44-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="11f44-121">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="11f44-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="11f44-122">Klicka på Rapporterat som färdigt.</span><span class="sxs-lookup"><span data-stu-id="11f44-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="11f44-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="11f44-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="11f44-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="11f44-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="11f44-125">Journalen för rapportering som slutfört bokförs.</span><span class="sxs-lookup"><span data-stu-id="11f44-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="11f44-126">Om du vill göra justeringar i journalen, kan du manuellt skapa en ny journal där du kan göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="11f44-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  


