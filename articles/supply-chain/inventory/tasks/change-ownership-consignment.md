---
title: Ändra ägarskapet för försändelselagret baserat på produktionsbegäran
description: I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1324da6996230eb383e2f37d3a133ec35cb0f41
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "319027"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="1fcf7-103">Ändra ägarskapet för försändelselagret baserat på produktionsbegäran</span><span class="sxs-lookup"><span data-stu-id="1fcf7-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1fcf7-104">I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="1fcf7-105">Den här ändringen i ägarskap görs genom att skapa och bokföra en ändringsjournal för lagerägarskap.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="1fcf7-106">Ändringsjournalraderna för ägarskap kan skapas manuellt eller, som visas i denna registrering, baseras på befintliga produktionsbegäran.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="1fcf7-107">Vanligtvis utför en produktionslagerarbetsledare denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="1fcf7-108">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="1fcf7-109">Om du använder dina egna data, kontrollera då att du har följande förutsättningar: ett journalnamn för lager som har skapats för lageräganderättsändring, fysiskt registrerade leverantörsägda behållningsartiklar, samt en eller flera produktionsorderrader för materialet.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="1fcf7-110">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="1fcf7-111">Skapa en journal över lagerägarskap</span><span class="sxs-lookup"><span data-stu-id="1fcf7-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="1fcf7-112">Gå till Lagerhantering > Journalposter > Artiklar > Lagerägarskapsändring.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="1fcf7-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-113">Click New.</span></span>
    * <span data-ttu-id="1fcf7-114">Ändringsjournalen för lageräganderätt används för att byta ägaren till försändelselager från leverantören till nuvarande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="1fcf7-115">Denna ändring i ägarskap görs genom att frisläppa det behållningslager som ägs av leverantören och seden ta emot det lagret i nuvarande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="1fcf7-116">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="1fcf7-117">Du kan bara välja lagerjournalnamn som har en journal av typen Ownership change (ägarskapsändring).</span><span class="sxs-lookup"><span data-stu-id="1fcf7-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="1fcf7-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-118">Click OK.</span></span>
5. <span data-ttu-id="1fcf7-119">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-119">Click Functions.</span></span>
6. <span data-ttu-id="1fcf7-120">Klicka på Create journal lines from production orders.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="1fcf7-121">Du kan starta en ändring av ägarskapsprocessen genom att skicka en fråga till samtliga produktionslinor med krav på förbrukning av råmaterial.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="1fcf7-122">Välj ett alternativ i fältet Inventory issue statuses to include.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="1fcf7-123">Detta alternativ låter dig filtrera efter utleveransstatusen för lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="1fcf7-124">Du kan till exempel skapa journalrader för lager som har fysisk status Picked eller Reserved.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="1fcf7-125">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="1fcf7-126">I det här avsnittet kan du använda ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="1fcf7-127">Du kan till exempel välja ett specifikt råmaterialdatum.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="1fcf7-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="1fcf7-129">Bokför journalen över lagerägarskapsändringar</span><span class="sxs-lookup"><span data-stu-id="1fcf7-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="1fcf7-130">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-130">Click Post.</span></span>
    * <span data-ttu-id="1fcf7-131">När journalen bokförs frisläpps det leverantörsägda lagret genom att använda referensen ”Ownership change".</span><span class="sxs-lookup"><span data-stu-id="1fcf7-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="1fcf7-132">Lagret tas sedan emot som behållning genom att använda en lagertransaktion som uppdateras med en produktinleverans för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="1fcf7-133">Observera att endast transaktioner kopplade till den bokförda journalen skapas.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="1fcf7-134">Inga förväntade lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="1fcf7-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-135">Click OK.</span></span>
3. <span data-ttu-id="1fcf7-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1fcf7-136">Close the page.</span></span>

