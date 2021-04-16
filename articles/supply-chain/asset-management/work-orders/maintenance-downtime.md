---
title: Underhållsstopp för arbetsorder
description: Detta ämne förklarar hur du skapar registreringar av underhållsstopp för den valda tillgången på en arbetsorder.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5c0c584ed53dc4ec8a761065838127dc67cbc41e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813735"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="6a574-103">Underhållsstopp för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="6a574-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="6a574-104">Du kan skapa registreringar av underhållsstopp för den valda tillgången på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6a574-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="6a574-105">Denna funktion är användbar om du vill registrera underhållsstopp på en eller flera maskiner i produktionsområdet.</span><span class="sxs-lookup"><span data-stu-id="6a574-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="6a574-106">Först skapar du de orsakskoder för underhållsstopp som du vill använda, t.ex. **uppdelning** och **planerat stopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="6a574-107">Detta steg görs på sidan **Orsakskoder för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="6a574-108">Sedan kan du skapa registreringar av underhållsstopp på sidan **Underhållsstopp** och lägga till relevanta orsakskoder för underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="6a574-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="6a574-109">Skapa orsakskoder för underhållsstopp</span><span class="sxs-lookup"><span data-stu-id="6a574-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="6a574-110">Välj **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Orsakskoder för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="6a574-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6a574-111">Select **New**.</span></span>

3. <span data-ttu-id="6a574-112">I fältet **Orsakskod för underhållsstopp** anger du ett ID för orsakskoden för underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="6a574-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="6a574-113">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6a574-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="6a574-114">Markera kryssrutan **KPI inkludera** om orsakskoden ska inkluderas i beräkningen av tillgångens nyckeltal (KPI:er).</span><span class="sxs-lookup"><span data-stu-id="6a574-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="6a574-115">I allmänhet ska planerade produktionsstopp inte inkluderas i KPI-beräkningar eftersom de inte påverkar förväntad prestanda.</span><span class="sxs-lookup"><span data-stu-id="6a574-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="6a574-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6a574-116">Select **Save**.</span></span>

<span data-ttu-id="6a574-117">Bilden nedan visar ett exempel på sidan **Orsakskoder för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Figur 1](media/15-work-orders.png)

<span data-ttu-id="6a574-119">När du har skapat de orsakskoder för underhållsstopp som du vill använda kan du skapa registreringar av underhållsstopp för arbetsorder och tillgångar.</span><span class="sxs-lookup"><span data-stu-id="6a574-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="6a574-120">Skapa registreringar av underhållsstopp</span><span class="sxs-lookup"><span data-stu-id="6a574-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="6a574-121">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6a574-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6a574-122">Välj en arbetsorder och sedan på fliken **Arbetsorder**, i gruppen **Tillgång**, välj **Underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="6a574-123">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6a574-123">Select **New**.</span></span>

4. <span data-ttu-id="6a574-124">I fälten **Från** och **Till** definierar du datum- och tidsintervall för registreringen av underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="6a574-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="6a574-125">När du lämnar fältet **Till** infogas varaktigheten i timmar automatiskt i fältet **Varaktighet**.</span><span class="sxs-lookup"><span data-stu-id="6a574-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="6a574-126">Välj en orsakskod i fältet **Orsakskod för underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="6a574-127">Upprepa steg 3 till och med 5 om du vill lägga till fler registreringar.</span><span class="sxs-lookup"><span data-stu-id="6a574-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="6a574-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6a574-128">Select **Save**.</span></span>

<span data-ttu-id="6a574-129">Bilden nedan visar ett exempel på listan Registrering för underhållsstopp.</span><span class="sxs-lookup"><span data-stu-id="6a574-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Figur 2](media/16-work-orders.png)

<span data-ttu-id="6a574-131">Den kalender som används för att beräkna en registrering av underhållsstopp beror på ditt val i inställningarna av tillgångar och parametrar.</span><span class="sxs-lookup"><span data-stu-id="6a574-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="6a574-132">Om en resurs väljs för en tillgång i fältet **Resurs** på snabbfliken **Anläggningstillgång** på sidan **Alla tillgångar** används den kalender som har ställts in för den associerade resursgruppen, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="6a574-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Figur 3](media/17-work-orders.png)

<span data-ttu-id="6a574-134">Om ingen resurs väljs för tillgången används standardkalender som valts på sidan **Parametrar för tillgångshantering** som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="6a574-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Figur 4](media/18-work-orders.png)

<span data-ttu-id="6a574-136">Om du vill se en översikt över alla underhållsstoppregistreringar, klicka på **Tillgångshantering** > **Förfrågningar** > **Underhållsstopp**.</span><span class="sxs-lookup"><span data-stu-id="6a574-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="6a574-137">Alla kalendrar som används i modulen **Tillgångshantering** ställs in i **Organisationsadministration** > **Inställningar** > **Kalendrar** > **Kalendrar**.</span><span class="sxs-lookup"><span data-stu-id="6a574-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]