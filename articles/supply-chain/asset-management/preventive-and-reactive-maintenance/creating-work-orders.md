---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875898"
---
# <a name="creating-work-orders"></a><span data-ttu-id="804b4-103">Skapa arbetsorder</span><span class="sxs-lookup"><span data-stu-id="804b4-103">Creating work orders</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="804b4-104">När du har schemalagt förebyggande underhållsjobb är nästa steg att skapa arbetsorder för jobben.</span><span class="sxs-lookup"><span data-stu-id="804b4-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="804b4-105">Det gör du i ett av underhållsschemana.</span><span class="sxs-lookup"><span data-stu-id="804b4-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="804b4-106">De schemalagda jobben i ett underhållsschema kan ha olika referenstyper:</span><span class="sxs-lookup"><span data-stu-id="804b4-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="804b4-107">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="804b4-107">Reference type</span></span> | <span data-ttu-id="804b4-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="804b4-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="804b4-109">Underhållsplaner</span><span class="sxs-lookup"><span data-stu-id="804b4-109">Maintenance plans</span></span>     | <span data-ttu-id="804b4-110">Förebyggande underhållsjobb baserade på underhållsplanens typer "Tid" eller "Räknare".</span><span class="sxs-lookup"><span data-stu-id="804b4-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="804b4-111">Underhållsomgångar</span><span class="sxs-lookup"><span data-stu-id="804b4-111">Maintenance rounds</span></span>    | <span data-ttu-id="804b4-112">Förebyggande underhållsjobb som innehåller flera tillgångar som kräver en liknande typ av underhåll.</span><span class="sxs-lookup"><span data-stu-id="804b4-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="804b4-113">Underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="804b4-113">Maintenance request</span></span>   | <span data-ttu-id="804b4-114">Manuellt skapad begäran om underhåll eller reparation av en tillgång, som kan konverteras till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="804b4-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="804b4-115">Klicka på **Tillgångshantering** > **Allmänt** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="804b4-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="804b4-116">Välj de schemalagda underhållsjobb som du vill skapa en arbetsorder för och klicka på **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="804b4-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="804b4-117">Det totala antalet prognostimmar för de valda raderna visas i fältet **Prognostimmar för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="804b4-117">The total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="804b4-118">I avsnittet **Parametrar** väljer du hur många arbetsorder du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="804b4-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="804b4-119">Du kan skapa en arbetsorder per underhållsschemarad eller ett antal arbetsorder utifrån dina val i avsnittet **En arbetsorder per**.</span><span class="sxs-lookup"><span data-stu-id="804b4-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="804b4-120">Välj en **arbetsordertyp** som ska användas på alla arbetsorder som du skapar.</span><span class="sxs-lookup"><span data-stu-id="804b4-120">Select a **Work order type** that will be used on all the work orders you create.</span></span>

5. <span data-ttu-id="804b4-121">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="804b4-121">Click **OK**.</span></span> <span data-ttu-id="804b4-122">En eller flera arbetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="804b4-122">One or more work orders are created.</span></span>

![Figur 1](media/18-preventive-maintenance.png)

