---
title: "Registrera materialförbrukning med en mobil enhet"
description: "Det här avsnittet beskriver ett arbetsflöde som möjliggör registrering av förbrukningen av råmaterial i produktionen med hjälp av en bärbar enhet."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 460b98ff371c49ab3ec2aabb139d0244e6fd80f7
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="66c82-103">Registrera materialförbrukning med en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="66c82-103">Register material consumption using a mobile device</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="66c82-104">Det här avsnittet beskriver ett arbetsflöde som möjliggör registrering av förbrukningen av råmaterial i produktionen med hjälp av en bärbar enhet.</span><span class="sxs-lookup"><span data-stu-id="66c82-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="66c82-105">Introduktion</span><span class="sxs-lookup"><span data-stu-id="66c82-105">Introduction</span></span>
------------

<span data-ttu-id="66c82-106">Arbetsflödet är relevant om det finns strikta krav på att material ska kunna spåras.</span><span class="sxs-lookup"><span data-stu-id="66c82-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="66c82-107">Om du vill behålla spårbarheten för material måste exakt datum och exakt tid rapporteras för förbrukningen.</span><span class="sxs-lookup"><span data-stu-id="66c82-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="66c82-108">Den här processen kan ses i motsats till för- eller backflushing-arbete där det finns en avvikelse mellan registreringstiden och tiden då den faktiska förbrukningen sker.</span><span class="sxs-lookup"><span data-stu-id="66c82-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="66c82-109">Detta förklarar varför en strategi för automatisk förbrukning inte kan inte för vissa material med spårbarhetskrav.</span><span class="sxs-lookup"><span data-stu-id="66c82-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="66c82-110">Låt oss titta på ett enkelt scenario som beskriver hur du ställer in ett arbetsflöde för att aktivera registrering av förbrukningen av råmaterial med hjälp av en bärbar enhet.</span><span class="sxs-lookup"><span data-stu-id="66c82-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="66c82-111">[![Skapa ett arbetsflöde för att möjliggöra registrering av förbrukning av råmaterial med en bärbar enhet](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="66c82-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="66c82-112">Scenario-information</span><span class="sxs-lookup"><span data-stu-id="66c82-112">Scenario details</span></span>

<span data-ttu-id="66c82-113">En kontinuerlig produktionsprocess (5) använder batch-kontrollerat råmaterial RM-100.</span><span class="sxs-lookup"><span data-stu-id="66c82-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="66c82-114">Materialet som finns i lager på lagerstället Bulk-001 (1) vid registreringsskylt PL-1 med två batcher, B1 och B2, båda med en kvantitet på 100 kg.</span><span class="sxs-lookup"><span data-stu-id="66c82-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="66c82-115">Lagerställearbete (2) publiceras och bearbetas av RM 100 och materialet hämtas från Bulk-001 till platsen för produktionsinleverans PIL-01 (3), som definieras som icke-registreringsskyltkontrollerad.</span><span class="sxs-lookup"><span data-stu-id="66c82-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="66c82-116">Maskinoperatören väger ut material från platsen för produktionsinleverans (3) och registrerar vikten och batchnumret som förbrukade (4).</span><span class="sxs-lookup"><span data-stu-id="66c82-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="66c82-117">Från produktionsinleveransplatsen läggs en del av materialet till manuellt i produktionsprocessen i angivna tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="66c82-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="66c82-118">När maskinoperatören lägger till material, vägs det på en våg och batchnumret registreras.</span><span class="sxs-lookup"><span data-stu-id="66c82-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="66c82-119">Konfigurera arbetsflödet för att registrera förbrukning med hjälp av en bärbar enhet</span><span class="sxs-lookup"><span data-stu-id="66c82-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="66c82-120">Skapa en färdigvaruprodukt, FG 100, med en strukturlista med material som har batch-styrt råmaterial RM-100.</span><span class="sxs-lookup"><span data-stu-id="66c82-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="66c82-121">Lägg till två batcher B1 och B2 i RM-100 i en kvantitet på 100 till plats: Bulk-001 vid registreringsskylt: PL-1.</span><span class="sxs-lookup"><span data-stu-id="66c82-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="66c82-122">Avräkningsprincipen på strukturlisteraden för RM-100 anges till **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="66c82-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="66c82-123">Ställ in plats för produktionsinleverans på PIL-01.</span><span class="sxs-lookup"><span data-stu-id="66c82-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="66c82-124">Du kan du göra det genom att välja den här platsen som den standardinleveransplats för lagerställe 51.</span><span class="sxs-lookup"><span data-stu-id="66c82-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="66c82-125">Skapa en ny menyartikel för mobila enheter:</span><span class="sxs-lookup"><span data-stu-id="66c82-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="66c82-126">**Menyartikelnamn** – Registrera materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="66c82-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="66c82-127">**Rubrik** – Registrera materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="66c82-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="66c82-128">**Läge** – Indirekt.</span><span class="sxs-lookup"><span data-stu-id="66c82-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="66c82-129">**Aktivitetskod** – Registrera materialförbrukning.</span><span class="sxs-lookup"><span data-stu-id="66c82-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="66c82-130">Lägg till menyartikeln i enhetsmenyn **Mobil produktion**.</span><span class="sxs-lookup"><span data-stu-id="66c82-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="66c82-131">Skapa en produktionsorder för den färdiga produkten:</span><span class="sxs-lookup"><span data-stu-id="66c82-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="66c82-132">**Artikelnummer** – FG-100</span><span class="sxs-lookup"><span data-stu-id="66c82-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="66c82-133">**Plats** – 5</span><span class="sxs-lookup"><span data-stu-id="66c82-133">**Site** - 5</span></span> 
-    <span data-ttu-id="66c82-134">**Lagerställe** – 51</span><span class="sxs-lookup"><span data-stu-id="66c82-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="66c82-135">**Kvantitet** – 150</span><span class="sxs-lookup"><span data-stu-id="66c82-135">**Quantity** - 150</span></span>

<span data-ttu-id="66c82-136">Produktionsordern är **Uppskattad** och **Frisläppt** och lagerarbete har skapats.</span><span class="sxs-lookup"><span data-stu-id="66c82-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="66c82-137">Slutför arbetet med hjälp av arbetsflödet för råmaterialplockning för handhållen enhet.</span><span class="sxs-lookup"><span data-stu-id="66c82-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="66c82-138">Detta överför materialet från bulkplatsen till produktionsinleveransplatsen PIL-01.</span><span class="sxs-lookup"><span data-stu-id="66c82-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="66c82-139">När arbetet har slutförts har materialet statusen **Plockas på platsen för produktionsinleverans**.</span><span class="sxs-lookup"><span data-stu-id="66c82-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="66c82-140">Statusen efter att arbetet har bearbetats kan vara antingen **Plockad** eller **Fysiskt reserverat**.</span><span class="sxs-lookup"><span data-stu-id="66c82-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="66c82-141">Detta konfigureras med parametern **Utfärda status efter införandet i lagerställeformuläret**.</span><span class="sxs-lookup"><span data-stu-id="66c82-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="66c82-142">Starta tillverkningsordern från klienten eller från den handhållna enheten med hjälp av menyartikeln **Produktionsstart**.</span><span class="sxs-lookup"><span data-stu-id="66c82-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="66c82-143">När produktionsordern har startat kan du registrera materialförbrukning i arbetsflödet för handenheter.</span><span class="sxs-lookup"><span data-stu-id="66c82-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="66c82-144">Vi börjar med att registrera förbrukning på 25 kg från batch B1.</span><span class="sxs-lookup"><span data-stu-id="66c82-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="66c82-145">Välj menyartikeln **Registrera material** **förbrukning**. I menyn för handhållen enhet anger du följande information:</span><span class="sxs-lookup"><span data-stu-id="66c82-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="66c82-146">Tillverkningsordernumret.</span><span class="sxs-lookup"><span data-stu-id="66c82-146">The production order number.</span></span> 
-    <span data-ttu-id="66c82-147">Platsen där materialet ska förbrukas är i det här fallet PIL-01.</span><span class="sxs-lookup"><span data-stu-id="66c82-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="66c82-148">Artikelnummer RM-100.</span><span class="sxs-lookup"><span data-stu-id="66c82-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="66c82-149">Batchnummer B1.</span><span class="sxs-lookup"><span data-stu-id="66c82-149">Batch number B1.</span></span> 
-    <span data-ttu-id="66c82-150">Kvantitet: 25.</span><span class="sxs-lookup"><span data-stu-id="66c82-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="66c82-151">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="66c82-151">Select **OK**.</span></span>

<span data-ttu-id="66c82-152">Observera att meddelandet ”Journalrad har skapats” visas på skärmen.</span><span class="sxs-lookup"><span data-stu-id="66c82-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="66c82-153">På produktionsordern är en öppen journal av typen **Produktionsplocklista** för artikel nummer RM-100 och batch-nummer B1.</span><span class="sxs-lookup"><span data-stu-id="66c82-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="66c82-154">Du kan nu välja att fortsätta med registreringen, till exempel på batchnummer B2. Varje gång du väljer **OK** läggs en ny journalrad till i den öppna journalen.</span><span class="sxs-lookup"><span data-stu-id="66c82-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="66c82-155">När du har slutfört registreringen väljer du **Klart** för att bokföra journalen och avsluta arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="66c82-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="66c82-156">Ytterligare kommentarer</span><span class="sxs-lookup"><span data-stu-id="66c82-156">Additional comments</span></span> 

-   <span data-ttu-id="66c82-157">Om en användare avbryter arbetsflödet när en journalrad har skapats är journalen i ett ej bokfört tillstånd, men om användaren vid en senare tidpunkt använder arbetsflödet för samma produktionsorder, kommer raderna att läggas till i den öppna journalen i stället för i en ny journal.</span><span class="sxs-lookup"><span data-stu-id="66c82-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="66c82-158">Det nya arbetsflödet har även stöd för registrering av serienummer.</span><span class="sxs-lookup"><span data-stu-id="66c82-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="66c82-159">Det går bara att registrera ett artikelnummer som har definierats i strukturlistan eller formeln för vald produktionsorder eller batchorder.</span><span class="sxs-lookup"><span data-stu-id="66c82-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="66c82-160">Material kan vara överförbrukade.</span><span class="sxs-lookup"><span data-stu-id="66c82-160">Material can be overconsumed.</span></span> <span data-ttu-id="66c82-161">Exempelvis om materialet är beräknat att vara förbrukat med kvantiteten 100 kg kan det sedan vara överförbrukat med samma kvantitet, till exempel 105 kg.</span><span class="sxs-lookup"><span data-stu-id="66c82-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



