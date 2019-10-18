---
title: Underhållsomgångar
description: I det här avsnittet beskrivs underhållsomgångar i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: eca732f245650c8e1f3dc976454536a0ab1ee117
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922032"
---
# <a name="maintenance-rounds"></a><span data-ttu-id="792ff-103">Underhållsomgångar</span><span class="sxs-lookup"><span data-stu-id="792ff-103">Maintenance rounds</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="792ff-104">In **Tillgångshantering** kan du skapa underhållsomgångar för olika tillgångar, där du måste utföra en liknande uppgift med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="792ff-104">In **Asset Management**, you can create maintenance rounds for various assets, on which you need to carry out a similar task at regular intervals.</span></span> <span data-ttu-id="792ff-105">Exempelvis smörjmedelsjobb eller säkerhetsinspektionsjobb som måste utföras på ett antal maskiner inom samma intervall.</span><span class="sxs-lookup"><span data-stu-id="792ff-105">For example, lubrication jobs or safety inspection jobs that need to be carried out on a number of machines within the same intervals.</span></span> <span data-ttu-id="792ff-106">Första steget är att skapa en underhållsomgång, inklusive tillgångar som kräver samma typ av underhållsjobb.</span><span class="sxs-lookup"><span data-stu-id="792ff-106">First step is to create a maintenance round, including assets that require the same form of maintenance job.</span></span> <span data-ttu-id="792ff-107">Därefter schemalägger du underhållsomgångarna.</span><span class="sxs-lookup"><span data-stu-id="792ff-107">Next, you schedule the maintenance rounds.</span></span> <span data-ttu-id="792ff-108">När du har avslutat schemat för underhållsomgångar kan du se alla jobbposter som är relaterade till omgången i **Alla underhållsscheman** och **Öppna rader för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="792ff-108">When you have completed the maintenance rounds schedule, you can see all the job records relating to the round in the **All maintenance schedule** and **Open maintenance schedule lines**.</span></span>

>[!NOTE]
><span data-ttu-id="792ff-109">Underhållsomgångar kan också ställas in på de funktionsplatser som ska slutföras på de tillgångar som är installerade på funktionsplatsen vid tidpunkten för skapandet av den omgångsbaserade arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="792ff-109">Maintenance rounds can also be set up on functional locations to be completed on the assets installed on the functional location at the time of creation of the round-based work order.</span></span> <span data-ttu-id="792ff-110">I [Skapa funktionsplatser](../functional-locations/create-functional-locations.md) finns mer information om inställningen av underhållsomgångar och funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="792ff-110">Refer to [Create functional locations](../functional-locations/create-functional-locations.md) for more information on the setup of maintenance rounds on functional locations.</span></span>

## <a name="set-up-a-maintenance-round"></a><span data-ttu-id="792ff-111">Ställa in en underhållsomgång</span><span class="sxs-lookup"><span data-stu-id="792ff-111">Set up a maintenance round</span></span>

1. <span data-ttu-id="792ff-112">Klicka på **Tillgångshantering** > **Inställning** > **Förebyggande underhåll** > **Underhållsomgångar**.</span><span class="sxs-lookup"><span data-stu-id="792ff-112">Click **Asset management** > **Setup** > **Preventive maintenance** > **Maintenance rounds**.</span></span>

2. <span data-ttu-id="792ff-113">Klicka på **Nytt** om du vill skapa en ny underhållsomgång.</span><span class="sxs-lookup"><span data-stu-id="792ff-113">Click **New** to create a new maintenance round.</span></span>

3. <span data-ttu-id="792ff-114">Infoga ett ID i fältet **Underhållsomgång** och ett namn på det underhållsomgången i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="792ff-114">Insert and ID in the **Maintenance round** field, and a name for the maintenance round in the **Name** field.</span></span>

4. <span data-ttu-id="792ff-115">Välj ett startdatum för omgången i fältet **Startdatum**.</span><span class="sxs-lookup"><span data-stu-id="792ff-115">Select a start date for the round in the **Start date** field.</span></span>

5. <span data-ttu-id="792ff-116">I fälten **Slutför inom dagar** och **Slutför inom timmar** kan du infoga förväntat slutdatum i dagar eller timmar.</span><span class="sxs-lookup"><span data-stu-id="792ff-116">In the **Finish within days** and **Finish within hours** fields, you can insert expected end date in days or hours.</span></span> <span data-ttu-id="792ff-117">Det förväntade slutdatumet beräknas i förhållande till startdatumet, som beräknas när underhållsschemarader skapas.</span><span class="sxs-lookup"><span data-stu-id="792ff-117">The expected end date is calculated relative to the start date, which is calculated when maintenance schedule lines are created.</span></span> <span data-ttu-id="792ff-118">Du kan till exempel infoga "7" i fältet **Slutför inom dagar** för att ange att det relaterade jobbet ska slutföras inom en vecka från startdatumet.</span><span class="sxs-lookup"><span data-stu-id="792ff-118">For example, you can insert "7" in the **Finish within days** field to indicate that the related job should be completed within a week from the start date.</span></span>

6. <span data-ttu-id="792ff-119">Välj "Ja" på växlingsknappen **Autoskapa** om arbetsorder automatiskt ska skapas från rader för underhållsschemarader som skapas från den här underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-119">Select "Yes" on the **Auto create** toggle button if work orders should automatically be created from maintenance schedule lines that are created from this maintenance round.</span></span>

7. <span data-ttu-id="792ff-120">I fältet **Arbetsordertyp** väljer du den arbetsordertyp som ska användas på arbetsorder som skapas från den här underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-120">In the **Work order type** field, select the work order type to be used on work orders created from this maintenance round.</span></span>

8. <span data-ttu-id="792ff-121">I fältet **Servicenivå** väljer du den servicenivå för arbetsorder som ska användas på arbetsorder som skapas från den här underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-121">In the **Service level** field, select the work order service level to be used on work orders created from this maintenance round.</span></span>

9. <span data-ttu-id="792ff-122">På snabbfliken **Tillgångsrader**, klicka på **Lägg till** för att lägga till en tillgång i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-122">On the **Asset lines** FastTab, click **Add** to add an asset to the maintenance round.</span></span>

10. <span data-ttu-id="792ff-123">Ett radnummer anges automatiskt i fältet **Radnummer** för att visa ordningsföljden på tillgångarna i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-123">A line number is automatically inserted in the **Line number** field to indicate the sequence of the assets in maintenance round.</span></span>

11. <span data-ttu-id="792ff-124">Välj tillgången i fältet **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="792ff-124">Select the asset in the **Asset** field.</span></span>

12. <span data-ttu-id="792ff-125">Välj underhållsjobbtypen för tillgången i fältet **Underhållsjobbtyp**.</span><span class="sxs-lookup"><span data-stu-id="792ff-125">Select the maintenance job type for the asset in the **Maintenance job type** field.</span></span>

13. <span data-ttu-id="792ff-126">Om det behövs väljer du **Variant av underhållsjobbtyp** och **Yrkesgren** relaterad till underhållsjobbtypen.</span><span class="sxs-lookup"><span data-stu-id="792ff-126">If required, select **Maintenance job typ variant** and **Trade** related to the maintenance job type.</span></span>

14. <span data-ttu-id="792ff-127">Välj återkommande (dag, vecka, osv.) i fältet **Periodtyp**.</span><span class="sxs-lookup"><span data-stu-id="792ff-127">Select the recurrence (day, week, etc.) in the **Period type** field.</span></span>

15. <span data-ttu-id="792ff-128">I fältet **Periodfrekvens** anger du antalet upprepningar för underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-128">In the **Period frequency** field, insert the number of recurrences for the maintenance round.</span></span> <span data-ttu-id="792ff-129">Exempel: om du har valt "Dag" i fältet **Periodtyp** och infogar siffran "7" i det här fältet, skapas nya underhållsomgångsrader under planering av förebyggande underhåll en gång i veckan.</span><span class="sxs-lookup"><span data-stu-id="792ff-129">Example: If you have selected "Day" in the **Period type** field, and you insert the number "7" in this field, new maintenance round lines are created during preventive maintenance scheduling once a week.</span></span>

16. <span data-ttu-id="792ff-130">Välj ett startdatum för tillgången som ska tas med i underhållsomgången i fältet **Startdatum**.</span><span class="sxs-lookup"><span data-stu-id="792ff-130">Select a start date for the asset to be included in the maintenance round in the **Start date** field.</span></span> <span data-ttu-id="792ff-131">Datumet kan skilja sig från det startdatum som ställts in för underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-131">This date may differ from the start date set on the maintenance round.</span></span>

17. <span data-ttu-id="792ff-132">Upprepa steg 9 till 16 om du vill lägga till fler tillgångar i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-132">Repeat steps 9-16 to add more assets to the maintenance round.</span></span>

18. <span data-ttu-id="792ff-133">På snabbfliken **Funktionsplatsrader**, klicka på **Lägg** för att lägga till en funktionsplats i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-133">On the **Functional location lines** FastTab, click **Add** to add a functional location to the maintenance round.</span></span> <span data-ttu-id="792ff-134">Se beskrivningen av de relaterade fälten ovan.</span><span class="sxs-lookup"><span data-stu-id="792ff-134">Refer to the description of the related fields above.</span></span> <span data-ttu-id="792ff-135">Samma fält är tillgängliga för att skapa en tillgångsrad, men du kan också välja **Tillverkare** och **Modell** för en funktionsplats, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="792ff-135">The same fields are available as for creating an asset line, but you can also select **Manufacturer** and **Model** for a functional location, if required.</span></span> <span data-ttu-id="792ff-136">Om du bara väljer en funktionsplats på en rad men inte gör några val i **Tillgångstyp**, **Tillverkare**, **Modell**, **Underhållsjobbtyp**, **Variant av underhållsjobbtyp** och **Yrkesgren** inkluderas alla tillgångar relaterade till den funktionsplatsen vid tidpunkten för underhållsplaneringen i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-136">If you only select a functional location on a line, but make no selections in **Asset type**, **Manufacturer**, **Model**, **Maintenance job type**, **Maintenance job type variant** and **Trade**, all assets related to that functional location at the time of maintenance scheduling will be included in the maintenance round.</span></span>

19. <span data-ttu-id="792ff-137">Klicka på **Lägg till** på snabbfliken **Pooler** om du vill välja en arbetsorderpool som ska inkluderas i underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-137">On the **Pools** FastTab, click **Add** to select a work order pool to be included in the maintenance round.</span></span> <span data-ttu-id="792ff-138">Flera arbetsorderpooler kan kopplas till en underhållsomgång.</span><span class="sxs-lookup"><span data-stu-id="792ff-138">Several work order pools can be connected to one maintenance round.</span></span>

20. <span data-ttu-id="792ff-139">Spara dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="792ff-139">Save your setup.</span></span>

>[!NOTE]
><span data-ttu-id="792ff-140">Fälten **Tillgångar** och **Rader** i gruppen **Information** på snabbfliken **Sidhuvud** visar det totala antalet tillgångar och rader som är relaterade till den valda underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-140">The **Assets** and **Lines** fields located in the **Details** group on the **Header** FastTab show the total number of assets and lines related to the selected maintenance round.</span></span>

<span data-ttu-id="792ff-141">Bilden nedan visar och exempel på en underhållsrunda som innehåller tre tillgångar.</span><span class="sxs-lookup"><span data-stu-id="792ff-141">The illustration below shows and example of a maintenance round containing three assets.</span></span>

![Figur 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a><span data-ttu-id="792ff-143">Schemalägg underhållsomgångar</span><span class="sxs-lookup"><span data-stu-id="792ff-143">Schedule maintenance rounds</span></span>

<span data-ttu-id="792ff-144">När du har ställt in en underhållsomgång kör du ett schemajobb för att tidsplanera alla jobb som relaterar till underhållsomgången.</span><span class="sxs-lookup"><span data-stu-id="792ff-144">When you've set up a maintenance round, you run a schedule job to schedule all the jobs related to the maintenance round.</span></span>

1. <span data-ttu-id="792ff-145">Klicka på **Tillgångshantering** > **Periodiskt** > **Förebyggande underhåll** > **Schemalägg underhållsomgångar** eller **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema** > välj underhållsschemaraden i listan > knappen **Underhållsomgångar**.</span><span class="sxs-lookup"><span data-stu-id="792ff-145">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance rounds**, or **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** > select maintenance schedule line in the list > **Maintenance rounds** button.</span></span>

2. <span data-ttu-id="792ff-146">I fältet **period** väljer du den periodtyp som ska användas för planeringsjobbet.</span><span class="sxs-lookup"><span data-stu-id="792ff-146">In the **Period** field, select the period type to be used for the scheduling job.</span></span>

3. <span data-ttu-id="792ff-147">I fältet **Periodfrekvens** anger du antalet perioder som ska inkluderas i planeringsjobbet.</span><span class="sxs-lookup"><span data-stu-id="792ff-147">In the **Period frequency** field, insert the number of periods to be included in the scheduling job.</span></span> <span data-ttu-id="792ff-148">Början på planeringen är det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="792ff-148">The start of the scheduling is the current date.</span></span>

4. <span data-ttu-id="792ff-149">Välj "Ja" på växlingsknappen **Autoskapa** om en arbetsorder automatiskt ska skapas baserat på en underhållsomgång.</span><span class="sxs-lookup"><span data-stu-id="792ff-149">Select "Yes" on the **Auto create** toggle button if a work order should automatically be created on the basis of a maintenance round.</span></span>

>[!NOTE]
><span data-ttu-id="792ff-150">Om den här växlingsknappen är inställd på "Ja" och växlingsknappen **Autoskapa** även är inställd på "Ja" i formuläret **Underhållsomgångar**, skapas arbetsorder baserade på underhållsomgångsraderna, och underhållsschemarader med statusen "Arbetsorder skapad" skapas också.</span><span class="sxs-lookup"><span data-stu-id="792ff-150">If this toggle button is set to "Yes", and the **Auto create** toggle button is also set to "Yes" on the maintenance round in **Maintenance rounds** form, work orders are created based on the maintenance round lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="792ff-151">Om endast en av växlingsknapparna **Autoskapa** är inställd på "Ja", i den här nedrullningsbara eller i **Underhållsomgångar**, skapas bara underhållsschemarader med statusen "Skapad".</span><span class="sxs-lookup"><span data-stu-id="792ff-151">If only one of the **Auto create** toggle buttons is set to "Yes", in this drop-down or in **Maintenance rounds**, only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="792ff-152">I så fall skapas inga arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="792ff-152">In that case, no work orders are created.</span></span>

5. <span data-ttu-id="792ff-153">Vid behov kan du välja specifika omgångar eller ett annat startdatum för schemajobbet.</span><span class="sxs-lookup"><span data-stu-id="792ff-153">If required, you can select specific rounds or another start date for the schedule job.</span></span> <span data-ttu-id="792ff-154">Klicka på **Filter** och lägg till omgångarna som ska inkluderas.</span><span class="sxs-lookup"><span data-stu-id="792ff-154">Click **Filter**, and add the rounds to be included.</span></span>

6. <span data-ttu-id="792ff-155">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="792ff-155">Click **OK**.</span></span>

7. <span data-ttu-id="792ff-156">Du kan nu se underhållsomgångsjobben i **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="792ff-156">You are now able to see the maintenance rounds jobs in **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines**.</span></span> <span data-ttu-id="792ff-157">Om schemalagda omgångar är kopplade till en pool för arbetsorder visas även underhållsschemarader i **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="792ff-157">If the scheduled rounds are connected to a work order pool, you also see maintenance schedule lines in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="792ff-158">Underhållsschemarader som skapas från en omgång av har referenstypen "Underhållsomgångar".</span><span class="sxs-lookup"><span data-stu-id="792ff-158">Maintenance schedule lines created from a round have the reference type "Maintenance rounds".</span></span>

<span data-ttu-id="792ff-159">De två bilderna nedan visar ett schemajobb i dialogrutan **Schemalägg underhållsomgångar** och de rader för underhållsschema som skapats i **Alla underhållsscheman** baserat på det schemajobbet.</span><span class="sxs-lookup"><span data-stu-id="792ff-159">The two illustrations below show a schedule job in the **Schedule maintenance rounds** dialog, and the maintenance schedule lines created in **All maintenance schedule** based on that schedule job.</span></span>

![Figur 2](media/14-preventive-maintenance.png)

![Figur 3](media/15-preventive-maintenance.png)

- <span data-ttu-id="792ff-162">När arbetsorder skapas manuellt på tillgångar som täcks av en leverantörsgaranti visas en dialogruta som gör användaren medveten om garantin.</span><span class="sxs-lookup"><span data-stu-id="792ff-162">When work orders are manually created on assets that are covered by a vendor warranty, a dialog box is shown to make the user aware of the warranty.</span></span> <span data-ttu-id="792ff-163">Skapandet av arbetsordern kan sedan annulleras.</span><span class="sxs-lookup"><span data-stu-id="792ff-163">The creation of the work order can then be canceled.</span></span> <span data-ttu-id="792ff-164">Kontrollen av en garantirelation utelämnas för arbetsorder som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="792ff-164">The check for a warranty relation is omitted for work orders that are automatically created.</span></span>  
- <span data-ttu-id="792ff-165">Du kan ställa in ett batchjobb på snabbfliken **Kör i bakgrunden** för att schemalägga omgångar med regelbundna intervall.</span><span class="sxs-lookup"><span data-stu-id="792ff-165">You can set up a batch job on the **Run in the background** FastTab to schedule rounds at regular intervals.</span></span>  
- <span data-ttu-id="792ff-166">Om en omgång ingår i flera arbetsorderpooler (se [Arbetsorderpooler](../work-orders/work-order-pools.md)) visas en post för varje pool i **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="792ff-166">If a round is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="792ff-167">Detta görs för att optimera filtreringsalternativen för arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="792ff-167">This is done to optimize the filtering options for work order pools.</span></span>

