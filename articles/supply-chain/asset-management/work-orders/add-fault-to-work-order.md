---
title: Lägg till fel i arbetsorder
description: I det här avsnittet beskrivs hur du lägger till felregistreringar i arbetsorder i Tillgångshantering.
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875908"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="8d064-103">Lägg till fel i arbetsorder</span><span class="sxs-lookup"><span data-stu-id="8d064-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="8d064-104">Du kan lägga till fel som ställts in i feldesignern till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8d064-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="8d064-105">Den tillgång som väljs i arbetsordern måste innehålla tillgångstyper som har en eller flera felposter kopplade till sig.</span><span class="sxs-lookup"><span data-stu-id="8d064-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="8d064-106">Mer information om inställningar finns i avsnittet [Felhantering](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="8d064-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="8d064-107">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8d064-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8d064-108">I listan väljer du den arbetsorder för vilken du vill göra en felregistrering och klickar på **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="8d064-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="8d064-109">På snabbfliken **Symptom** klickar du på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="8d064-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="8d064-110">Ett sekventiellt felnummer infogas automatiskt i fältet **Fel**.</span><span class="sxs-lookup"><span data-stu-id="8d064-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="8d064-111">Välj relevant symptom i fältet **Felsymptom**.</span><span class="sxs-lookup"><span data-stu-id="8d064-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="8d064-112">Välj **Felområde** och **Feltyp**.</span><span class="sxs-lookup"><span data-stu-id="8d064-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="8d064-113">Fältet **Feldatum** ställs automatiskt in på aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="8d064-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="8d064-114">Om det behövs kan du välja ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="8d064-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="8d064-115">På snabbfliken **Orsaker till valda symptom** lägger du till en rad som beskriver orsaken till problemet.</span><span class="sxs-lookup"><span data-stu-id="8d064-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="8d064-116">På snabbfliken **Åtgärder för valda symptom** lägger du till en rad som beskriver möjliga lösningar på problemet.</span><span class="sxs-lookup"><span data-stu-id="8d064-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="8d064-117">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8d064-117">Click **Save**.</span></span>

![Figur 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="8d064-119">Visa tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="8d064-119">View asset faults</span></span>

<span data-ttu-id="8d064-120">I listan **Tillgångsfel** kan du få en översikt över alla fel som registrerats för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="8d064-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="8d064-121">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel** för att öppna listan.</span><span class="sxs-lookup"><span data-stu-id="8d064-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="8d064-122">Skriv ut rapport om tillgångsfel</span><span class="sxs-lookup"><span data-stu-id="8d064-122">Print asset fault report</span></span>

<span data-ttu-id="8d064-123">Från listsidan **Alla tillgångar** kan du skriva ut en rapport över tillgångsfel som visar alla felregistreringar samt en grafisk översikt över felstatistik.</span><span class="sxs-lookup"><span data-stu-id="8d064-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="8d064-124">Klicka på **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="8d064-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="8d064-125">I listan **Tillgångar** väljer du den tillgång du vill skriva ut en felrapport för.</span><span class="sxs-lookup"><span data-stu-id="8d064-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="8d064-126">Klicka på fliken **Allmänt** > **avsnittet Rapporter**, klicka på **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="8d064-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="8d064-127">Infoga en viss period eller välj en feltyp.</span><span class="sxs-lookup"><span data-stu-id="8d064-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="8d064-128">Klicka på **OK** om du vill skriva ut rapporten.</span><span class="sxs-lookup"><span data-stu-id="8d064-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="8d064-129">Du kan också skriva ut en felrapport för flera tillgångar eller tillgångstyper genom att klicka på **Tillgångshantering** > **Rapporter** > **Tillgångar** > **Tillgångsfel**.</span><span class="sxs-lookup"><span data-stu-id="8d064-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

