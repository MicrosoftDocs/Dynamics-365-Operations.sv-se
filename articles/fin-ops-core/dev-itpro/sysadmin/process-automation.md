---
title: Processautomatisering
description: Det här avsnittet innehåller information om hur processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: e3babed18caefff16105f70a0b15b8b8cf0f08eb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568220"
---
# <a name="process-automation"></a><span data-ttu-id="3c3c2-103">Processautomatisering</span><span class="sxs-lookup"><span data-stu-id="3c3c2-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3c3c2-104">Processautomatisering tillåter enkel schemaläggning av processer som ska köras av batchservern.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="3c3c2-105">Med den uppdaterade kalendervyn av det schemalagda arbetet kan slutanvändare visa och vidta åtgärder för schemalagt och slutfört arbete.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="3c3c2-106">Administration</span><span class="sxs-lookup"><span data-stu-id="3c3c2-106">Administration</span></span>

<span data-ttu-id="3c3c2-107">Sidan Central administration för alla automatiseringar av processer finns i modulen systemadministration på menyn **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="3c3c2-108">Den här sidan visar alla automatiserade processer (serier) som är inställda i systemet.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="3c3c2-109">Du kan också lägga till nya processautomatiseringar direkt från den här sidan.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="3c3c2-110">När en serie har ställts in kan du hantera varje serie från den här listan.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="3c3c2-111">Du kan välja att redigera hela serien, ta bort den, visa alla förekomster i en listvy eller inaktivera serien om du vill pausa det schemalagda arbetet under en tid.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-111">You can choose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a while.</span></span> 

<span data-ttu-id="3c3c2-112">Alla processer som inaktiveras i funktionshanteringen visas inte när funktionen är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-112">Any processes that are disabled in feature management won't show when the feature is disabled.</span></span> <span data-ttu-id="3c3c2-113">Dessutom kommer schemaläggningsmotorn för processautomation inte att schemalägga några händelser eller bakgrundsprocesser för en inaktiverad funktion.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-113">Additionally, the process automation scheduling engine won't schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="3c3c2-114">Om du aktiverar funktionen igen kommer schemalagda förekomster eller bakgrundsprocesser tidigare att kunna köras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span>

## <a name="calendar-view"></a><span data-ttu-id="3c3c2-115">Kalendervy</span><span class="sxs-lookup"><span data-stu-id="3c3c2-115">Calendar view</span></span>

<span data-ttu-id="3c3c2-116">En av huvudfördelarna med processautomatisering är möjligheten att se det schemalagda arbetet i en enkel kalendervy.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-116">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="3c3c2-117">I den här vyn kan du se arbetet för en vecka i taget.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-117">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="3c3c2-118">Den här vyn visas till höger på sidan **Processautomatisering**.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-118">You'll see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="3c3c2-119">Den kommer att fyllas i med det schemalagda arbetet för den valda serien.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-119">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="3c3c2-120">[![Kalender för processautomatisering](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-120">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="3c3c2-121">Förekomständringar</span><span class="sxs-lookup"><span data-stu-id="3c3c2-121">Occurrence changes</span></span>

<span data-ttu-id="3c3c2-122">Varje förekomst kan ändras utan att påverka andra förekomster som har definierats i serien.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-122">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="3c3c2-123">Förekomster av schemalagt arbete kan redigeras i kalendervyn genom att du väljer knappen **Visa/redigera** och väljer **Förekomst**.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-123">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="3c3c2-124">Denna sida gör att du kan komma åt alla inställningar som ursprungligen visades i guiden för serieinställningar och du kan göra en enstaka ändring för den valda förekomsten.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-124">This page allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="3c3c2-125">Du kan också stänga av en förekomst av schemalagt arbete genom att välja knappen **Inaktivera** i kalendervyn.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-125">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span>

## <a name="developer-documentation"></a><span data-ttu-id="3c3c2-126">Dokumentation för utvecklare</span><span class="sxs-lookup"><span data-stu-id="3c3c2-126">Developer documentation</span></span>

<span data-ttu-id="3c3c2-127">Med processens automatiseringsramverk kan utvecklare utöka processens automatiseringsramverk.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-127">The process automation framework allows developers to extend the process automation framework.</span></span> <span data-ttu-id="3c3c2-128">[Ramverket för processautomatisering](../process-automation/process-automation-framework.md) dokumentationen får du information om hur du kan skapa anpassade processer som du behöver köra av den batchservern som är schemalagd med guiden bearbeta automatisering och visas automatiskt i kalendervyn.</span><span class="sxs-lookup"><span data-stu-id="3c3c2-128">The [Process automation framework](../process-automation/process-automation-framework.md) documentation provides information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]