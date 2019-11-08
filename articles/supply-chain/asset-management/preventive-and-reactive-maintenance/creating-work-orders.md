---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e910b2400106baf9f9dc06f6bc0d3daee8e4a43
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570086"
---
# <a name="creating-work-orders"></a><span data-ttu-id="75b28-103">Skapa arbetsorder</span><span class="sxs-lookup"><span data-stu-id="75b28-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="75b28-104">När du har schemalagt förebyggande underhållsjobb är nästa steg att skapa arbetsorder för jobben.</span><span class="sxs-lookup"><span data-stu-id="75b28-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="75b28-105">Det gör du i ett av underhållsschemana.</span><span class="sxs-lookup"><span data-stu-id="75b28-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="75b28-106">De schemalagda jobben i ett underhållsschema kan ha olika referenstyper:</span><span class="sxs-lookup"><span data-stu-id="75b28-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="75b28-107">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="75b28-107">Reference type</span></span> | <span data-ttu-id="75b28-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="75b28-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="75b28-109">Underhållsplaner</span><span class="sxs-lookup"><span data-stu-id="75b28-109">Maintenance plans</span></span>     | <span data-ttu-id="75b28-110">Förebyggande underhållsjobb baserade på underhållsplanens typer "Tid" eller "Räknare".</span><span class="sxs-lookup"><span data-stu-id="75b28-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="75b28-111">Underhållsomgångar</span><span class="sxs-lookup"><span data-stu-id="75b28-111">Maintenance rounds</span></span>    | <span data-ttu-id="75b28-112">Förebyggande underhållsjobb som innehåller flera tillgångar som kräver en liknande typ av underhåll.</span><span class="sxs-lookup"><span data-stu-id="75b28-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="75b28-113">Underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="75b28-113">Maintenance request</span></span>   | <span data-ttu-id="75b28-114">Manuellt skapad begäran om underhåll eller reparation av en tillgång, som kan konverteras till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="75b28-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="75b28-115">Klicka på **Tillgångshantering** > **Allmänt** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="75b28-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="75b28-116">Välj de schemalagda underhållsjobb som du vill skapa en arbetsorder för och klicka på **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="75b28-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="75b28-117">I dialogrutan **Skapa arbetsorder** visas det totala antalet prognostimmar för de valda raderna i fältet **Prognostimmar för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="75b28-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="75b28-118">I avsnittet **Parametrar** väljer du hur många arbetsorder du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="75b28-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="75b28-119">Du kan skapa en arbetsorder per underhållsschemarad eller ett antal arbetsorder utifrån dina val i avsnittet **En arbetsorder per**.</span><span class="sxs-lookup"><span data-stu-id="75b28-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="75b28-120">Välj en **arbetsordertyp** som ska användas på alla arbetsorder som du skapar.</span><span class="sxs-lookup"><span data-stu-id="75b28-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="75b28-121">Illustrationen nedan visar ett exempel på dialogrutan **Skapa arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="75b28-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Figur 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="75b28-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="75b28-123">Click **OK**.</span></span> <span data-ttu-id="75b28-124">En eller flera arbetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="75b28-124">One or more work orders are created.</span></span>

