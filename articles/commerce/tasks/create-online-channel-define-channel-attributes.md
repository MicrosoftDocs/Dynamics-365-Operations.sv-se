---
title: Skapa online-kanal och definiera kanalattribut
description: I den här proceduren skapar du en ny onlinekanal och lägger till den i organisationshierarkin.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f15b035c01801041d637a2d315d8a3ddcc9d6540
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415885"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="35371-103">Skapa online-kanal och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="35371-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35371-104">I den här proceduren skapar du en ny onlinekanal och lägger till den i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="35371-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="35371-105">Du måste skapa organisationshierarkin innan du kan skapa en ny onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="35371-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="35371-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="35371-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="35371-107">Skapa en ny onlinekanal</span><span class="sxs-lookup"><span data-stu-id="35371-107">Create a new online channel</span></span>
1. <span data-ttu-id="35371-108">Gå till Butik och handel > Kanaler > Onlinebutiker.</span><span class="sxs-lookup"><span data-stu-id="35371-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="35371-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="35371-109">Click New.</span></span>
3. <span data-ttu-id="35371-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="35371-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="35371-111">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="35371-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="35371-112">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="35371-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="35371-113">Ange eller välj ett värde i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="35371-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="35371-114">Ange eller välj ett värde i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="35371-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="35371-115">Ange eller välj ett värde i fältet Betalningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="35371-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="35371-116">Ange eller välj ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="35371-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="35371-117">I fältet Meddelandeprofil för e-post, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="35371-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="35371-118">Expandera avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="35371-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="35371-119">Ange eller välj ett värde i fältet BusinessUnit.</span><span class="sxs-lookup"><span data-stu-id="35371-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="35371-120">Ange värdet på samma sätt för alla andra standarddimensioner.</span><span class="sxs-lookup"><span data-stu-id="35371-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="35371-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="35371-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="35371-122">Lägg till onlinekanalen i organisationshierarkin</span><span class="sxs-lookup"><span data-stu-id="35371-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="35371-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="35371-123">Close the page.</span></span>
2. <span data-ttu-id="35371-124">Gå till Organisationsadministration > Organisationer > Organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="35371-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="35371-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="35371-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="35371-126">Klicka på Visa.</span><span class="sxs-lookup"><span data-stu-id="35371-126">Click View.</span></span>
5. <span data-ttu-id="35371-127">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="35371-127">Click Edit.</span></span>
    * <span data-ttu-id="35371-128">Du kan välja en hierarkinod som du vill infoga den nya kanalen under.</span><span class="sxs-lookup"><span data-stu-id="35371-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="35371-129">Klicka på Infoga.</span><span class="sxs-lookup"><span data-stu-id="35371-129">Click Insert.</span></span>
7. <span data-ttu-id="35371-130">Klicka på handelskanal.</span><span class="sxs-lookup"><span data-stu-id="35371-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="35371-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="35371-131">Click OK.</span></span>
9. <span data-ttu-id="35371-132">Klicka på Publicera om du vill öppna formuläret med listrutan för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="35371-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="35371-133">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="35371-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="35371-134">Klicka på Publicera.</span><span class="sxs-lookup"><span data-stu-id="35371-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="35371-135">Konfigurera order för nära realtidsmeddelande</span><span class="sxs-lookup"><span data-stu-id="35371-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="35371-136">Gå till Butik och handel > Administrationsinställning > Parametrar > Handelparametrar.</span><span class="sxs-lookup"><span data-stu-id="35371-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="35371-137">Ange Använd realtidstjänst för skapande av näthandelsorder till "Ja".</span><span class="sxs-lookup"><span data-stu-id="35371-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="35371-138">Kör distributionsschema 1070 för att synkronisera ändringar i databasen för kanalen.</span><span class="sxs-lookup"><span data-stu-id="35371-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


