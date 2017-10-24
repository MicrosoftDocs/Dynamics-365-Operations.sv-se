--- 
title: Skapa en arbetsklass
description: "I den här proceduren visas hur du ställer in en arbetsklass."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9a775366bdaecb59a375f245f7a4d17a659cab11
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-work-class"></a><span data-ttu-id="059c7-103">Skapa en arbetsklass</span><span class="sxs-lookup"><span data-stu-id="059c7-103">Create a work class</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="059c7-104">I den här proceduren visas hur du ställer in en arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="059c7-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="059c7-105">Arbetsklasser används för att styra och/eller begränsa den typ av arbetsorderrader som en lagerarbetare kan bearbeta på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="059c7-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="059c7-106">De rader som en anställd kan bearbeta bestäms från de arbetsklasser på menyobjekten för mobil enhet som lagerarbetaren har tillgång till och den arbetsklass som anges i på arbetsraderna.</span><span class="sxs-lookup"><span data-stu-id="059c7-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that’s specified on the work lines.</span></span> <span data-ttu-id="059c7-107">Arbetsklasser kan också användas för att validera läggplatsen för en arbetsorderrad.</span><span class="sxs-lookup"><span data-stu-id="059c7-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="059c7-108">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="059c7-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="059c7-109">Den här proceduren är avsedd för lagerchefen.</span><span class="sxs-lookup"><span data-stu-id="059c7-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="059c7-110">Gå till Lagerstyrning > Inställningar > Arbete > Arbetsklasser.</span><span class="sxs-lookup"><span data-stu-id="059c7-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="059c7-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="059c7-111">Click New.</span></span>
3. <span data-ttu-id="059c7-112">Skriv ett värde i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="059c7-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="059c7-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="059c7-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="059c7-114">Välj ett alternativ i fältet Arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="059c7-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="059c7-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="059c7-115">Click New.</span></span>
7. <span data-ttu-id="059c7-116">Skriv ett värde i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="059c7-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="059c7-117">Om du väljer en platstyp anges en begränsning på var artiklar kan placeras efter att de har plockats.</span><span class="sxs-lookup"><span data-stu-id="059c7-117">If you select a location type, this sets a restriction on where items can be put after they’ve been picked.</span></span> <span data-ttu-id="059c7-118">Denna inställning används när ett platsdirektiv försöker lösa platsen, eller om en lagerarbetare manuellt anger platsen för menyobjektet för mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="059c7-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="059c7-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="059c7-119">Close the page.</span></span>


