---
title: Synkronisering av resurskapacitet
description: I det här avsnittet finns information om hur du synkroniserar en resurskapacitet för kalendrar och projekt.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760662"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="75285-103">Synkronisering av resurskapacitet</span><span class="sxs-lookup"><span data-stu-id="75285-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75285-104">Processerna för synkronisering av resurser hjälper till att garantera att information till kalendern och baskalendern sipprar ned i tidsplaneringen av projektresurser.</span><span class="sxs-lookup"><span data-stu-id="75285-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="75285-105">Om kalendern ändras gör processerna de nödvändiga uppdateringarna av planeringen av projektresurser.</span><span class="sxs-lookup"><span data-stu-id="75285-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="75285-106">Processerna kan även förbättra prestanda, detta eftersom resursinformationen i kalendern synkroniseras i förväg.</span><span class="sxs-lookup"><span data-stu-id="75285-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="75285-107">Därför sker uppdateringar för resursplaneringsinformation snabbare.</span><span class="sxs-lookup"><span data-stu-id="75285-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="75285-108">Vi rekommenderar att du planerar processer som en batch i stället för en i taget.</span><span class="sxs-lookup"><span data-stu-id="75285-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="75285-109">Annars finns det en risk att någon glömmer inklusive datum när informationen synkroniserades senast.</span><span class="sxs-lookup"><span data-stu-id="75285-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="75285-110">Om inklusive datum inte används, luckor kan inträffa under datumsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="75285-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Kalendersynkronisering](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="75285-112">Synkronisera kapacitetsuppföljningar för resurs</span><span class="sxs-lookup"><span data-stu-id="75285-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="75285-113">Synkroniseringsprocessen har utformats för att synkronisera all information om resurskalendrarna.</span><span class="sxs-lookup"><span data-stu-id="75285-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="75285-114">Informationen omfattar baskalenderinformation om alla ändringar i kapacitetsregistret för projektets resurskalender.</span><span class="sxs-lookup"><span data-stu-id="75285-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="75285-115">Om nya resurser läggs till i projektet, synkroniseringen hjälper till att garantera att den uppdaterade kalenderinformationen är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="75285-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="75285-116">Den här synkroniseringen kan göras när som helst.</span><span class="sxs-lookup"><span data-stu-id="75285-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="75285-117">Vi rekommenderar att du använder en batch.</span><span class="sxs-lookup"><span data-stu-id="75285-117">We recommend that you use a batch.</span></span> <span data-ttu-id="75285-118">Alternativen är tillgängliga i samband med synkronisering av kapacitetsreservationer.</span><span class="sxs-lookup"><span data-stu-id="75285-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="75285-119">Markera **Projekthantering och redovisning** &gt; **Periodisk** &gt; **Kapacitetssynkronisering** &gt; **Synkronisera kapacitetsuppföljningar för resurs**.</span><span class="sxs-lookup"><span data-stu-id="75285-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="75285-120">I följande tabell ställer du in alternativen.</span><span class="sxs-lookup"><span data-stu-id="75285-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="75285-121">Alternativ</span><span class="sxs-lookup"><span data-stu-id="75285-121">Option</span></span>      | <span data-ttu-id="75285-122">beskrivning</span><span class="sxs-lookup"><span data-stu-id="75285-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="75285-123">Periodkod</span><span class="sxs-lookup"><span data-stu-id="75285-123">Period code</span></span> | <span data-ttu-id="75285-124">Markera vid behov datumintervallkod Redovisning för att ange start- och slutdatum för synkroniseringen av resurskapacitetssummeringen.</span><span class="sxs-lookup"><span data-stu-id="75285-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="75285-125">Startdatum</span><span class="sxs-lookup"><span data-stu-id="75285-125">Start date</span></span>  | <span data-ttu-id="75285-126">Ange startdatum för synkroniseringen för resurskapacitetssummeringen.</span><span class="sxs-lookup"><span data-stu-id="75285-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="75285-127">Slutdatum</span><span class="sxs-lookup"><span data-stu-id="75285-127">End date</span></span>    | <span data-ttu-id="75285-128">Ange slutdatum för synkroniseringen för resurskapacitetssummeringen.</span><span class="sxs-lookup"><span data-stu-id="75285-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="75285-129">[![Synkroniseringsprocess](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="75285-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
