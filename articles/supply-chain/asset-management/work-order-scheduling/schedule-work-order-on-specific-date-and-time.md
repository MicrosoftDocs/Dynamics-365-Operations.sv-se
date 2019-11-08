---
title: Planera arbetsorder på specifikt datum och tid
description: I det här avsnittet beskrivs hur du planerar en arbetsorder på ett visst datum och tid i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 634bbb4326d560848d36f579a1179187d8369087
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652044"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="9ad50-103">Planera arbetsorder på specifikt datum och tid</span><span class="sxs-lookup"><span data-stu-id="9ad50-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9ad50-104">Om en arbetsorder måste tidsplaneras på ett visst datum *och* en viss tid, kan du åsidosätta standardtidsplaneringsprocessen i Tillgångshantering och skapa ett specifikt schema för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9ad50-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="9ad50-105">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="9ad50-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="9ad50-106">Klicka på arbets orderns ID i kolumnen **Arbetsorder** i listan med arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9ad50-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="9ad50-107">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9ad50-107">Click **Edit**.</span></span>

4. <span data-ttu-id="9ad50-108">På snabbfliken **Arbetsorderhuvud** infogar du start-och slutdatum och -tider i fälten **Förväntad start** och **Förväntat slut**.</span><span class="sxs-lookup"><span data-stu-id="9ad50-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

    ![Figur 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="9ad50-110">På fliken **Allmänt**, klicka på **Schema** om du vill använda standardplaneringsprocessen, eller klicka på **Skicka ut** om du vill tilldela arbetsordern till en särskild arbetare.</span><span class="sxs-lookup"><span data-stu-id="9ad50-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to assign the work order to a specific worker.</span></span>

6. <span data-ttu-id="9ad50-111">Om du vill åsidosätta befintliga kapacitetsreservationer för att se till att arbetsordern planeras i förväntad period, gör du valen enligt bilden nedan i dialogrutan **Schemalägg arbetsorder** > avsnittet **Begränsad kapacitet**.</span><span class="sxs-lookup"><span data-stu-id="9ad50-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="9ad50-112">Detta innebär att planeringsprocessen ignorerar befintliga kapacitetsreservationer eftersom arbetsordern måste starta på den förväntade starttiden.</span><span class="sxs-lookup"><span data-stu-id="9ad50-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

    ![Figur 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="9ad50-114">Klicka på **OK** för att starta planeringen.</span><span class="sxs-lookup"><span data-stu-id="9ad50-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="9ad50-115">Om tidsplaneringsprocessen leder till dubbel bokföring visas ett meddelande på skärmen och du kan justera relaterade arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="9ad50-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="9ad50-116">För att kunna tidsplanera en underhållsarbetare för arbetsordern måste underhållsarbetare vara tillgängliga på det förväntade startdatumet och starttiden.</span><span class="sxs-lookup"><span data-stu-id="9ad50-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="9ad50-117">Arbetarens tillgänglighet ställs in i [arbetarkalendern](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="9ad50-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

