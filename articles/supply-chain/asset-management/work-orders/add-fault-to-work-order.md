---
title: Lägg till fel i arbetsorder
description: I det här avsnittet beskrivs hur du lägger till felregistreringar i arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 489add5befe3660ad49e238b659bc8adbe1418a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263768"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="98f23-103">Lägg till fel i arbetsorder</span><span class="sxs-lookup"><span data-stu-id="98f23-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="98f23-104">Du kan lägga till fel som ställts in i feldesignern till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="98f23-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="98f23-105">Den tillgång som väljs i arbetsordern måste innehålla tillgångstyper som har en eller flera felposter kopplade till sig.</span><span class="sxs-lookup"><span data-stu-id="98f23-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="98f23-106">Mer information om hur du ställer in finns i [Felhantering](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="98f23-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="98f23-107">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="98f23-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="98f23-108">Välj den arbetsorder som du gör felregistreringen för och sedan i åtgärdsfönstret, på fliken **Arbetsorder** i gruppen **Tillgång**, välj **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="98f23-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="98f23-109">På snabbfliken **Symptom** klickar du på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="98f23-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="98f23-110">Ett sekventiellt felnummer infogas automatiskt i fältet **Fel**.</span><span class="sxs-lookup"><span data-stu-id="98f23-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="98f23-111">I fältet **Felsymptom**, välj relevant symptom.</span><span class="sxs-lookup"><span data-stu-id="98f23-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="98f23-112">I fälten **Felområde** och **Feltyp** välj lämpliga värden.</span><span class="sxs-lookup"><span data-stu-id="98f23-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="98f23-113">Fältet **Feldatum** ställs automatiskt in på aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="98f23-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="98f23-114">Du kan välja ett annat datum efter behov.</span><span class="sxs-lookup"><span data-stu-id="98f23-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="98f23-115">På snabbfliken **Orsaker till valda symptom** lägger du till en rad som beskriver orsaken till problemet.</span><span class="sxs-lookup"><span data-stu-id="98f23-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="98f23-116">På snabbfliken **Åtgärder för valda symptom** lägger du till en rad som beskriver möjliga lösningar på problemet.</span><span class="sxs-lookup"><span data-stu-id="98f23-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="98f23-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="98f23-117">Select **Save**.</span></span>

<span data-ttu-id="98f23-118">Bilden nedan visar ett exempel på en felregistrering.</span><span class="sxs-lookup"><span data-stu-id="98f23-118">The illustration below shows an example of a fault registration.</span></span>

![Figur 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="98f23-120">Visa tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="98f23-120">View asset faults</span></span>

<span data-ttu-id="98f23-121">I listan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="98f23-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="98f23-122">På listsidan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="98f23-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="98f23-123">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel** för att öppna listan.</span><span class="sxs-lookup"><span data-stu-id="98f23-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="98f23-124">Skriv ut rapport om tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="98f23-124">Print asset fault report</span></span>

<span data-ttu-id="98f23-125">Från listsidan **Alla tillgångar** kan du skriva ut en rapport över tillgångsfel som visar alla felregistreringar samt en grafisk översikt över felstatistik.</span><span class="sxs-lookup"><span data-stu-id="98f23-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="98f23-126">Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="98f23-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="98f23-127">Välj alla tillgångar för att skriva ut en felrapport för.</span><span class="sxs-lookup"><span data-stu-id="98f23-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="98f23-128">I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Rapporter**, klicka på **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="98f23-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="98f23-129">Ange en viss period eller välj en feltyp.</span><span class="sxs-lookup"><span data-stu-id="98f23-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="98f23-130">Klicka på **OK** om du vill skriva ut rapporten.</span><span class="sxs-lookup"><span data-stu-id="98f23-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="98f23-131">Du kan skriva ut en felrapport för flera tillgångar eller tillgångstyper genom att klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="98f23-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]