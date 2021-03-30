---
title: Ändra ägarskapet för försändelselagret baserat på produktionsbegäran
description: I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen.
author: perlynne
manager: tfehr
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 508226a3b5693b123af639cf6f130be07811c3c2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209525"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="b104f-103">Ändra ägarskapet för försändelselagret baserat på produktionsbegäran</span><span class="sxs-lookup"><span data-stu-id="b104f-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b104f-104">I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen.</span><span class="sxs-lookup"><span data-stu-id="b104f-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="b104f-105">Den här ändringen i ägarskap görs genom att skapa och bokföra en ändringsjournal för lagerägarskap.</span><span class="sxs-lookup"><span data-stu-id="b104f-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="b104f-106">Ändringsjournalraderna för ägarskap kan skapas manuellt eller, som visas i denna registrering, baseras på befintliga produktionsbegäran.</span><span class="sxs-lookup"><span data-stu-id="b104f-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="b104f-107">Vanligtvis utför en produktionslagerarbetsledare denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="b104f-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="b104f-108">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="b104f-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="b104f-109">Om du använder dina egna data, kontrollera då att du har följande förutsättningar: ett journalnamn för lager som har skapats för lageräganderättsändring, fysiskt registrerade leverantörsägda behållningsartiklar, samt en eller flera produktionsorderrader för materialet.</span><span class="sxs-lookup"><span data-stu-id="b104f-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="b104f-110">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="b104f-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="b104f-111">Utgående försändelseprocesser stöds inte omedelbart och automatisk ägarskapsjournalbearbetning stöds inte.</span><span class="sxs-lookup"><span data-stu-id="b104f-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="b104f-112">Skapa en journal över lagerägarskap</span><span class="sxs-lookup"><span data-stu-id="b104f-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="b104f-113">Gå till Lagerhantering > Journalposter > Artiklar > Lagerägarskapsändring.</span><span class="sxs-lookup"><span data-stu-id="b104f-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="b104f-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b104f-114">Click New.</span></span>
    * <span data-ttu-id="b104f-115">Ändringsjournalen för lageräganderätt används för att byta ägaren till försändelselager från leverantören till nuvarande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="b104f-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="b104f-116">Denna ändring i ägarskap görs genom att frisläppa det behållningslager som ägs av leverantören och seden ta emot det lagret i nuvarande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="b104f-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="b104f-117">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b104f-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="b104f-118">Du kan bara välja lagerjournalnamn som har en journal av typen Ownership change (ägarskapsändring).</span><span class="sxs-lookup"><span data-stu-id="b104f-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="b104f-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b104f-119">Click OK.</span></span>
5. <span data-ttu-id="b104f-120">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="b104f-120">Click Functions.</span></span>
6. <span data-ttu-id="b104f-121">Klicka på Create journal lines from production orders.</span><span class="sxs-lookup"><span data-stu-id="b104f-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="b104f-122">Du kan starta en ändring av ägarskapsprocessen genom att skicka en fråga till samtliga produktionslinor med krav på förbrukning av råmaterial.</span><span class="sxs-lookup"><span data-stu-id="b104f-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="b104f-123">Välj ett alternativ i fältet Inventory issue statuses to include.</span><span class="sxs-lookup"><span data-stu-id="b104f-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="b104f-124">Detta alternativ låter dig filtrera efter utleveransstatusen för lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="b104f-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="b104f-125">Du kan till exempel skapa journalrader för lager som har fysisk status Picked eller Reserved.</span><span class="sxs-lookup"><span data-stu-id="b104f-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="b104f-126">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="b104f-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="b104f-127">I det här avsnittet kan du använda ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="b104f-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="b104f-128">Du kan till exempel välja ett specifikt råmaterialdatum.</span><span class="sxs-lookup"><span data-stu-id="b104f-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="b104f-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b104f-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="b104f-130">Bokför journalen över lagerägarskapsändringar</span><span class="sxs-lookup"><span data-stu-id="b104f-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="b104f-131">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="b104f-131">Click Post.</span></span>
    * <span data-ttu-id="b104f-132">När journalen bokförs frisläpps det leverantörsägda lagret genom att använda referensen ”Ownership change".</span><span class="sxs-lookup"><span data-stu-id="b104f-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="b104f-133">Lagret tas sedan emot som behållning genom att använda en lagertransaktion som uppdateras med en produktinleverans för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b104f-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="b104f-134">Observera att endast transaktioner kopplade till den bokförda journalen skapas.</span><span class="sxs-lookup"><span data-stu-id="b104f-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="b104f-135">Inga förväntade lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="b104f-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="b104f-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b104f-136">Click OK.</span></span>
3. <span data-ttu-id="b104f-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b104f-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]