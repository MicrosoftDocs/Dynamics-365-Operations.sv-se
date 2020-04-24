---
title: Schemalägg underhållsplaner
description: I det här avsnittet beskrivs schemaläggning av underhållsplaner i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: df5bcd57c611ed5f77a417a28f28fca84057d734
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205999"
---
# <a name="schedule-maintenance-plans"></a><span data-ttu-id="47ae7-103">Schemalägg underhållsplaner</span><span class="sxs-lookup"><span data-stu-id="47ae7-103">Schedule maintenance plans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="47ae7-104">Vid planering av förebyggande underhåll skapas kalenderposter på tillgångar utifrån underhållsplaner som angetts för tillgångarna.</span><span class="sxs-lookup"><span data-stu-id="47ae7-104">Preventive maintenance scheduling generates calendar entries on assets, based on the maintenance plans set up on the assets.</span></span> <span data-ttu-id="47ae7-105">Du kan schemalägga kalenderposter baserat på valda underhållsplaner, tillgångstyper och tillgångar.</span><span class="sxs-lookup"><span data-stu-id="47ae7-105">You can schedule calendar entries based on selected maintenance plans, asset types, and assets.</span></span>

1. <span data-ttu-id="47ae7-106">Klicka på **Tillgångshantering** > **Periodiskt** > **Förebyggande underhåll** > **Schemalägg underhållsplaner**.</span><span class="sxs-lookup"><span data-stu-id="47ae7-106">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance plans**.</span></span>

2. <span data-ttu-id="47ae7-107">Du kan välja ett tidsintervall i fälten **Period** och **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="47ae7-107">You can select a time interval in the **Period** and **Period frequency** fields.</span></span>

>[!NOTE]
><span data-ttu-id="47ae7-108">Fälten **Period** och **Periodfrekvens** anger hur långt fram i tiden du vill att underhållsschemarader ska skapas, baserat på de underhållsplaner som du har skapat (tidsbaserad eller räknarbaserad).</span><span class="sxs-lookup"><span data-stu-id="47ae7-108">The **Period** and **Period frequencey** fields indicate how far ahead in time you want maintenance schedule lines to be created, based on the maintenance plans you have created (time-based or counter-based).</span></span> <span data-ttu-id="47ae7-109">I bilden nedan skapas rader för underhållsplaner (= arbetsorderförslag) från det aktuella datumet och tre månader framåt.</span><span class="sxs-lookup"><span data-stu-id="47ae7-109">In the figure below, maintenance schedule lines (= work order proposals) are created from the current date and three months onwards.</span></span>

3. <span data-ttu-id="47ae7-110">Välj "Ja" på växlingsknappen **Autoskapa om angivet på raden** om arbetsorder automatiskt ska skapas enligt underhållsplanraden.</span><span class="sxs-lookup"><span data-stu-id="47ae7-110">Select "Yes" on the **Auto create if specified in the line** toggle button if work orders should automatically be created according to the maintenance plan line.</span></span>

>[!NOTE]
><span data-ttu-id="47ae7-111">Om den här växlingsknappen är inställd på "Ja" *och* kryssrutan **Autoskapa** också har markerats på underhållsplanrader i **Underhållsplaner**, skapas arbetsorder baserade på underhållsplanraderna, och underhållsschemarader med statusen "Arbetsorder skapad" skapas också.</span><span class="sxs-lookup"><span data-stu-id="47ae7-111">If this toggle button is set to "Yes", *and* the **Auto create** check box is also selected on maintenance plan lines in **Maintenance plans**, work orders are created based on the maintenance plan lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="47ae7-112">Om endast ett alternativ har valts (växlingsknappen **Autoskapa om angivet på raden** i den här dialogrutan eller kryssrutan **Autoskapa** i formuläret **Underhållsplaner**) skapas endast rader för underhållsplaner med status "Skapad".</span><span class="sxs-lookup"><span data-stu-id="47ae7-112">If only one option is selected (**Auto create if specified in the line** toggle button in this dialog or **Auto create** check box in **Maintenance plans** form), only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="47ae7-113">I så fall skapas inga arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="47ae7-113">In that case, no work orders are created.</span></span>

4. <span data-ttu-id="47ae7-114">Det går att generera kalenderposter baserat på underhållsplaner (tid eller räknare), tillgångar, tillgångstyper, funktionsplatser och funktionsplatstyper.</span><span class="sxs-lookup"><span data-stu-id="47ae7-114">It is possible to generate calendar entries based on maintenance plans (time or counter), assets, asset types, functional locations, and functional location types.</span></span> <span data-ttu-id="47ae7-115">Klicka på knappen **Filter** och gör dina val om det behövs.</span><span class="sxs-lookup"><span data-stu-id="47ae7-115">Click the **Filter** button and make your selections, if required.</span></span>

- <span data-ttu-id="47ae7-116">När det gäller tidsplanering av underhållsplaner på funktionsplatser: Om du uppdaterar inställningarna för tillgångstyper, tillverkare och modeller på underhållsplaner på snabbfliken **Alla funktionsplatser** > **Underhållsplaner** när du har planerat underhållsplaner, kommer befintliga underhållsschemaposter som är relaterade till funktionsplatsen att raderas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="47ae7-116">Regarding scheduling of maintenance plans on functional locations: If you update the setup of asset types, manufacturers, and models on maintenance plans in **All functional locations** > **Maintenance plans** FastTab after you have scheduled maintenance plans, existing maintenance schedule entries related to that functional location are automatically deleted.</span></span> <span data-ttu-id="47ae7-117">Om du vill skapa nya kalenderposter, som motsvarar den uppdaterade underhållsplaninställningen på den funktionsplatsen, måste du köra ett nytt schema för underhållsplanen för den funktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="47ae7-117">In order to create new calendar entries, which correspond with the updated maintenance plan setup on the functional location, you must run a new maintenance plan schedule for that functional location.</span></span> <span data-ttu-id="47ae7-118">Läs mer om inställningarna av tillgångstyper, tillverkare och modeller på funktionsplatser i [Skapa funktionsplatser](../functional-locations/create-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="47ae7-118">Read more about the setup of asset types, manufacturers, and models on functional locations in [Create functional locations](../functional-locations/create-functional-locations.md).</span></span>

><span data-ttu-id="47ae7-119">*Exempel:* Du vill skapa en underhållsplan för en specifik funktionsplats, vilket innebär att alla tillgångar som ställs in på den funktionsplatsen vid en given tidpunkt inkluderas när du planerar underhållsplanen.</span><span class="sxs-lookup"><span data-stu-id="47ae7-119">*Example:* You want to create a maintenance plan for a specific functional location, meaning all assets set up on that functional location at any given time will be included when you schedule the maintenance plan.</span></span> <span data-ttu-id="47ae7-120">I så fall skapar du en underhållsplan och väljer en viss funktionsplats, men du lägger INTE till några tillgångar i underhållsplanen.</span><span class="sxs-lookup"><span data-stu-id="47ae7-120">In that case, you create a maintenance plan and select the specific functional location, but you do NOT add any assets in the maintenance plan.</span></span> <span data-ttu-id="47ae7-121">Resultatet blir att när du planerar underhållsplanen skapas underhållsschemarader för alla till gångar som är relaterade till funktionsplatsen vid den tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="47ae7-121">The result is that when you schedule that maintenance plan, maintenance schedule lines will be created for all the assets related to the functional location at that time.</span></span>

- <span data-ttu-id="47ae7-122">Om du gör ändringar i tillgångstyper, tillverkare och modeller i **Tillgångstyper** påverkar dessa ändringar bara nya tillgångar som använder den uppdaterade tillgångstypen.</span><span class="sxs-lookup"><span data-stu-id="47ae7-122">If you make changes to asset types, manufacturers and models in **Asset types**, those changes only affect new assets that use the updated asset type.</span></span> <span data-ttu-id="47ae7-123">Läs mer om inställning av tillgångstyp i [Tillgångstyper](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="47ae7-123">Read more about asset type setup in [Asset types](../setup-for-objects/object-types.md).</span></span>  

5. <span data-ttu-id="47ae7-124">Klicka på **OK** för att påbörja genereringen av underhållsschemaposter för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="47ae7-124">Click **OK** to start the generation of maintenance schedule entries on assets.</span></span> <span data-ttu-id="47ae7-125">De genererade posterna visas på listsidan **Alla underhållsscheman**.</span><span class="sxs-lookup"><span data-stu-id="47ae7-125">The generated entries will be shown in the **All maintenance schedule** list page.</span></span> <span data-ttu-id="47ae7-126">Följande illustration visar ett exempel på dialogrutan **Schemalägg underhållsplaner**.</span><span class="sxs-lookup"><span data-stu-id="47ae7-126">The following illustration shows an example of the **Schedule maintenance plans** dialog.</span></span>

![Figur 1](media/09-preventive-maintenance.png)

- <span data-ttu-id="47ae7-128">I dialogrutan **Schemalägg underhållsplaner** kan du ställa in batchjobb för snabbfliken **Kör i bakgrunden** för att automatiskt generera kalenderposter med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="47ae7-128">In the **Schedule maintenance plans** dialog, you can set up batch jobs on the **Run in the background** FastTab to automatically generate calendar entries at regular intervals.</span></span>  
- <span data-ttu-id="47ae7-129">När du planerar förebyggande underhåll skapas inte rader för underhållsplanering med förväntat startdatum och starttid före systemdatumet och systemtiden.</span><span class="sxs-lookup"><span data-stu-id="47ae7-129">When you schedule preventive maintenance, maintenance schedule lines with expected start date and time earlier than the system date and time will not be created.</span></span>  

<span data-ttu-id="47ae7-130">Bilden nedan visar en grafisk illustration av en beräkning av tidsbaserad underhållsplan.</span><span class="sxs-lookup"><span data-stu-id="47ae7-130">The figure below provides a graphic illustration of a time-based maintenance plan calculation.</span></span>  

![Figur 2](media/10-preventive-maintenance.jpg)

<span data-ttu-id="47ae7-132">Beträffande räknarbaserade underhållsplaner: I bilderna nedan visas två olika cykler för räknarregistrering.</span><span class="sxs-lookup"><span data-stu-id="47ae7-132">Regarding counter-based maintenance plans: In the figures below, two different counter registration cycles are shown.</span></span> <span data-ttu-id="47ae7-133">De är baserade på en underhållsplan som ställts in för tillgång "V0001", vilket förväntar tillgången (en bil) att köra cirka 2 000 km varje månad.</span><span class="sxs-lookup"><span data-stu-id="47ae7-133">They are based on a maintenance plan set up for asset "V0001", expecting the asset (a car) to run approx. 2,000 km every month.</span></span>

<span data-ttu-id="47ae7-134">I det första exemplet uppnås inte de förväntade 2 000 km varje månad.</span><span class="sxs-lookup"><span data-stu-id="47ae7-134">In the first example, the expected 2,000 km are not reached every month.</span></span> <span data-ttu-id="47ae7-135">Enligt den räknarbaserade underhållsplanen är tröskelvärdet 2 000 km, vilket innebär att när du kör en planering av underhållsplan ska en underhållsschemarad skapas varje gång som tröskelvärdet 2 000 km uppnås.</span><span class="sxs-lookup"><span data-stu-id="47ae7-135">According to the counter-based maintenance plan, the threshold is 2,000 km, meaning when you run a maintenance plan scheduling, a maintenance schedule line should be created each time the 2,000-kilometer threshold is reached.</span></span> <span data-ttu-id="47ae7-136">I exempel 1 finns 4 registreringsrader, men tröskelvärdet på 2 000 km uppnås bara en gång.</span><span class="sxs-lookup"><span data-stu-id="47ae7-136">In example 1, there are 4 registration lines, but the 2,000-kilometer threshold is only reached once.</span></span> <span data-ttu-id="47ae7-137">Det innebär att när du kör schemaläggning av underhållsplaner för tillgången, till exempel för en period på tre månader, skapas bara underhållsschemarad.</span><span class="sxs-lookup"><span data-stu-id="47ae7-137">This means that when you run schedule maintenance plans this asset, for example for a 3-month period, only one maintenance schedule line will be created.</span></span>

<span data-ttu-id="47ae7-138">I nästa bild registreras 2 000 km eller mer varje månad.</span><span class="sxs-lookup"><span data-stu-id="47ae7-138">In the next figure, 2,000 km or more are registered every month.</span></span> <span data-ttu-id="47ae7-139">Därför skapas tre underhållsrader om du schemalägger underhållsplaner för den här tillgången under en tremånadersperiod.</span><span class="sxs-lookup"><span data-stu-id="47ae7-139">Therefore, three maintenance lines would be created if you schedule maintenance plans for this asset for a 3-month period.</span></span> 

<span data-ttu-id="47ae7-140">I exemplen som beskrivs här visas att alla räknarregistreringar som görs på en tillgång visar en tendens som beskriver slitage på tillgången.</span><span class="sxs-lookup"><span data-stu-id="47ae7-140">The examples described here show that all counter registrations made on an asset show a trend describing wear and tear on the asset.</span></span> <span data-ttu-id="47ae7-141">Denna trend används som beräkningsbas vid tidsplanering av underhållsplanen.</span><span class="sxs-lookup"><span data-stu-id="47ae7-141">That trend is used as calculation basis at the time of maintenance plan scheduling.</span></span>

![Figur 3](media/11-preventive-maintenance.png)

![Figur 4](media/12-preventive-maintenance.png)

