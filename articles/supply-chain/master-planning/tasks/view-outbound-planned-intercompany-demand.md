---
title: Visa utgående planerad koncernintern efterfrågan
description: I den här proceduren anges hur du visar alla planerade beställningar som ska genomföras av en koncernintern leverantör.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8740846a6c6ba9e61c73ebce532d3bec525c2cc7
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148042"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="aad9c-103">Visa utgående planerad koncernintern efterfrågan</span><span class="sxs-lookup"><span data-stu-id="aad9c-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aad9c-104">I den här proceduren anges hur du visar alla planerade beställningar som ska genomföras av en koncernintern leverantör.</span><span class="sxs-lookup"><span data-stu-id="aad9c-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="aad9c-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="aad9c-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="aad9c-106">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="aad9c-106">Click Master planning.</span></span>
2. <span data-ttu-id="aad9c-107">I fältet Plan, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="aad9c-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="aad9c-108">Välj plan 10 i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="aad9c-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="aad9c-109">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="aad9c-109">Click Run.</span></span>
4. <span data-ttu-id="aad9c-110">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="aad9c-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="aad9c-111">Detta representerar antalet parallella trådar parallella som ska användas för huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="aad9c-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="aad9c-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="aad9c-112">Click OK.</span></span>
    * <span data-ttu-id="aad9c-113">Detta kan ta ett tag.</span><span class="sxs-lookup"><span data-stu-id="aad9c-113">This may take a while.</span></span>  
6. <span data-ttu-id="aad9c-114">Klicka på Planned intercompany demand.</span><span class="sxs-lookup"><span data-stu-id="aad9c-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="aad9c-115">Klicka på Outbound planned intercompany demand.</span><span class="sxs-lookup"><span data-stu-id="aad9c-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="aad9c-116">På den här sidan finns en översikt över all planerad efterfrågan som ska uppfyllas av en intern leveranskedjeleverantör.</span><span class="sxs-lookup"><span data-stu-id="aad9c-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="aad9c-117">Expandera avsnittet Upstream demand details.</span><span class="sxs-lookup"><span data-stu-id="aad9c-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="aad9c-118">I det här avsnittet får du information om hur efterfrågan möts.</span><span class="sxs-lookup"><span data-stu-id="aad9c-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="aad9c-119">Du kan behöva vänta på att huvudplanering körs i leveransföretaget innan du kan se ytterligare information här.</span><span class="sxs-lookup"><span data-stu-id="aad9c-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

