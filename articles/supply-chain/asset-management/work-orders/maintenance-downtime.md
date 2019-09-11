---
title: Underhållsstopp
description: I det här avsnittet beskrivs underhållsstopp i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918254"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="8f692-103">Underhållsstopp</span><span class="sxs-lookup"><span data-stu-id="8f692-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="8f692-104">Du kan skapa registreringar av underhållsstopp för den valda tillgången på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8f692-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="8f692-105">Detta är användbart om du vill registrera underhållsstopp på en eller flera maskiner i produktionsområdet.</span><span class="sxs-lookup"><span data-stu-id="8f692-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="8f692-106">Först skapar du de orsakskoder för underhållsstopp som du vill använda, t.ex. uppdelning och planerad stopp.</span><span class="sxs-lookup"><span data-stu-id="8f692-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="8f692-107">Detta görs i **Orsakskoder för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="8f692-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="8f692-108">Sedan kan du skapa registreringar av underhållsstopp i **Underhållsstopp** och lägga till relevanta orsakskoder.</span><span class="sxs-lookup"><span data-stu-id="8f692-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="8f692-109">Skapa orsakskoder för underhållsstopp</span><span class="sxs-lookup"><span data-stu-id="8f692-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="8f692-110">Klicka på **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Orsakskoder för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="8f692-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="8f692-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8f692-111">Click **New**.</span></span>

3. <span data-ttu-id="8f692-112">Infoga ett ID i fältet **Orsakskod för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="8f692-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="8f692-113">Infoga ett namn för orsakskoden i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="8f692-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="8f692-114">Markera kryssrutan **Inkludera i KPI** om orsakskoden ska inkluderas i beräkningar av tillgångs-KPI.</span><span class="sxs-lookup"><span data-stu-id="8f692-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="8f692-115">I allmänhet ska planerade produktionsstopp inte inkluderas i KPI-beräkningar eftersom de inte påverkar förväntad prestanda.</span><span class="sxs-lookup"><span data-stu-id="8f692-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="8f692-116">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8f692-116">Click **Save**.</span></span>

![Figur 1](media/15-work-orders.png)


<span data-ttu-id="8f692-118">När du har skapat de orsakskoder för underhållsstopp som du vill använda kan du skapa registreringar av underhållsstopp för arbetsorder och tillgångar.</span><span class="sxs-lookup"><span data-stu-id="8f692-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="8f692-119">Skapa registreringar av underhållsstopp</span><span class="sxs-lookup"><span data-stu-id="8f692-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="8f692-120">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8f692-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8f692-121">Välj arbetsorder och klicka på **Underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="8f692-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="8f692-122">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8f692-122">Click **New**.</span></span>

4. <span data-ttu-id="8f692-123">Infoga datum- och tidsintervall för registreringen av underhållsstopp i fälten **Från** och **Till**.</span><span class="sxs-lookup"><span data-stu-id="8f692-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="8f692-124">När du lämnar fältet **Till** infogas varaktigheten i timmar automatiskt i fältet **Varaktighet**.</span><span class="sxs-lookup"><span data-stu-id="8f692-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="8f692-125">Välj en orsakskod i fältet **Orsakskod för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="8f692-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="8f692-126">Upprepa steg 3-6 om du vill lägga till fler registreringar.</span><span class="sxs-lookup"><span data-stu-id="8f692-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="8f692-127">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8f692-127">Click **Save**.</span></span>


![Figur 2](media/16-work-orders.png)


<span data-ttu-id="8f692-129">Den kalender som används för att beräkna en registrering av underhållsstopp beror på ditt val i inställningarna av tillgångar och parametrar.</span><span class="sxs-lookup"><span data-stu-id="8f692-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="8f692-130">Om en resurs väljs för en tillgång i **Alla tillgångar** >  snabbfliken **Anläggningstillgång** > fältet **Resurs**, används den kalender som har ställts in för den associerade resursgruppen, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="8f692-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Figur 3](media/17-work-orders.png)


<span data-ttu-id="8f692-132">Om ingen resurs väljs för tillgången används standardkalender som valts i fältet **Parametrar för tillgångshantering** som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="8f692-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Figur 4](media/18-work-orders.png)


<span data-ttu-id="8f692-134">Klicka på **Hantering av företagstillgångar** > **Förfrågningar** > **Underhållsstopp** för att se en översikt över alla registreringar av underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="8f692-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="8f692-135">Alla kalendrar som används i modulen **Tillgångshantering** ställs in i **Organisationsadministration** > **Inställningar** > **Kalendrar** > **Kalendrar**.</span><span class="sxs-lookup"><span data-stu-id="8f692-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

