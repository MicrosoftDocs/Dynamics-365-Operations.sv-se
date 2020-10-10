---
title: Frisläpp en produktionsorder
description: I den här proceduren visas hur du frisläpper en produktionsorder.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826585"
---
# <a name="release-a-production-order"></a><span data-ttu-id="5c0e3-103">Frisläpp en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="5c0e3-103">Release a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5c0e3-104">I den här proceduren visas hur du frisläpper en produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="5c0e3-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="5c0e3-106">Detta är den fjärde proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="5c0e3-107">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="5c0e3-108">Markera en produktionsorder som har statusen Tidsplanerat i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="5c0e3-109">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="5c0e3-110">Klicka på Frisläpp.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-110">Click Release.</span></span>
    * <span data-ttu-id="5c0e3-111">På den här sidan kan du bekräfta leveransen av det valda intervallet av tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="5c0e3-112">Klicka på, Välj om du vill lägga till order.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="5c0e3-113">Leveranssteget anger när produktionsordern frisläpps till produktion butik våningen, så att operatörerna för arbetsstyrning kan rapportera framsteg på produktionsjobb.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="5c0e3-114">Produktionlegitimationshandlingar, som innehåller relevant information om bearbetning av jobb, kan utfärdas.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="5c0e3-115">Lagerställearbetet för råvaraplockning genereras för artiklarna som har ställts in för lagerställeprocessen.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="5c0e3-116">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-116">Click the General tab.</span></span>
    * <span data-ttu-id="5c0e3-117">Välj produktionrapporter som ska skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-117">Select which production reports should be printed.</span></span> <span data-ttu-id="5c0e3-118">Jobbkortsrapporten skriver ut en sida för varje schemalagt jobb och kräver att tillverkningsordern planeras på jobbnivån.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="5c0e3-119">Rapporten innehåller information om den schemalagda start - och sluttid, att producera kvantiteten, och resursen som behandlar jobbet.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="5c0e3-120">Flödesjobbrapporten samlar in samma information på samma sida, men inte skriver ut en sida för varje jobb.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="5c0e3-121">Flödeskortsrapporten bara vill visa operationerna men inte jobben.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="5c0e3-122">Därför måste den här rapporten kan inte finplanering, utan användas, när produktionsorder planeras på operationnivån.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="5c0e3-123">Klicka på kryssrutan Skriv ut ruttkort.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="5c0e3-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-124">Click OK.</span></span>
7. <span data-ttu-id="5c0e3-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5c0e3-125">Close the page.</span></span>

