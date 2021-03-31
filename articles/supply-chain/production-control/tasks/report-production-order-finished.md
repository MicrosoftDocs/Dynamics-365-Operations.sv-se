---
title: Rapportera en produktionsorder som färdig
description: I den här proceduren visas hur du rapporterar en produktionsorder som färdig.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4848093bd4901d3aa801fc09d7ee3e79d65ebb0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204477"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="6cdbd-103">Rapportera en produktionsorder som färdig</span><span class="sxs-lookup"><span data-stu-id="6cdbd-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6cdbd-104">I den här proceduren visas hur du rapporterar en produktionsorder som färdig.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="6cdbd-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6cdbd-106">Detta är den sjätte proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="6cdbd-107">Rapportera en produktionsorder som färdig</span><span class="sxs-lookup"><span data-stu-id="6cdbd-107">Report a production order as finished</span></span>
1. <span data-ttu-id="6cdbd-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="6cdbd-109">Välj en produktionsorder som har statusen Startat.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="6cdbd-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="6cdbd-111">Klicka på Rapportera som färdig.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-111">Click Report as finished.</span></span>
    * <span data-ttu-id="6cdbd-112">På den här sidan kan du bekräfta kvantiteten av den färdiga produkten som ska rapporteras som färdig.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="6cdbd-113">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-113">Click the General tab.</span></span>
5. <span data-ttu-id="6cdbd-114">Ställ in Godkänd kvantitet på 18.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="6cdbd-115">Ställ in Antal fel på 2.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="6cdbd-116">Välj Material i fältet Felorsak.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="6cdbd-117">Markera eller avmarkera kryssrutan Slutjobb.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="6cdbd-118">Markera eller avmarkera kryssrutan Godta fel.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="6cdbd-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="6cdbd-120">Verifiera journalen Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="6cdbd-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="6cdbd-121">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="6cdbd-122">Klicka på Rapporterat som färdigt.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="6cdbd-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6cdbd-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6cdbd-125">Journalen för rapportering som slutfört bokförs.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="6cdbd-126">Om du vill göra justeringar i journalen, kan du manuellt skapa en ny journal där du kan göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="6cdbd-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]