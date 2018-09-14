--- 
title: "Visa utgående planerad koncernintern efterfrågan"
description: "I den här proceduren anges hur du visar alla planerade beställningar som ska genomföras av en koncernintern leverantör."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 2e0e3a4613e5598e725c475c7dff7662bf4169a7
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="07cf5-103">Visa utgående planerad koncernintern efterfrågan</span><span class="sxs-lookup"><span data-stu-id="07cf5-103">View outbound planned intercompany demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07cf5-104">I den här proceduren anges hur du visar alla planerade beställningar som ska genomföras av en koncernintern leverantör.</span><span class="sxs-lookup"><span data-stu-id="07cf5-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="07cf5-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="07cf5-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="07cf5-106">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="07cf5-106">Click Master planning.</span></span>
2. <span data-ttu-id="07cf5-107">I fältet Plan, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="07cf5-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="07cf5-108">Välj plan 10 i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="07cf5-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="07cf5-109">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="07cf5-109">Click Run.</span></span>
4. <span data-ttu-id="07cf5-110">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="07cf5-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="07cf5-111">Detta representerar antalet parallella trådar parallella som ska användas för huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="07cf5-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="07cf5-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="07cf5-112">Click OK.</span></span>
    * <span data-ttu-id="07cf5-113">Detta kan ta ett tag.</span><span class="sxs-lookup"><span data-stu-id="07cf5-113">This may take a while.</span></span>  
6. <span data-ttu-id="07cf5-114">Klicka på Planned intercompany demand.</span><span class="sxs-lookup"><span data-stu-id="07cf5-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="07cf5-115">Klicka på Outbound planned intercompany demand.</span><span class="sxs-lookup"><span data-stu-id="07cf5-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="07cf5-116">På den här sidan finns en översikt över all planerad efterfrågan som ska uppfyllas av en intern leveranskedjeleverantör.</span><span class="sxs-lookup"><span data-stu-id="07cf5-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="07cf5-117">Expandera avsnittet Upstream demand details.</span><span class="sxs-lookup"><span data-stu-id="07cf5-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="07cf5-118">I det här avsnittet får du information om hur efterfrågan möts.</span><span class="sxs-lookup"><span data-stu-id="07cf5-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="07cf5-119">Du kan behöva vänta på att huvudplanering körs i leveransföretaget innan du kan se ytterligare information här.</span><span class="sxs-lookup"><span data-stu-id="07cf5-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  


