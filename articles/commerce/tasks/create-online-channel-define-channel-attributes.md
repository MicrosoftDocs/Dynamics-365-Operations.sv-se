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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f85a74e44be28452f5d892f1875d74261f9dbe3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215446"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="f27b2-103">Skapa online-kanal och definiera kanalattribut</span><span class="sxs-lookup"><span data-stu-id="f27b2-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f27b2-104">I den här proceduren skapar du en ny onlinekanal och lägger till den i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f27b2-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="f27b2-105">Du måste skapa organisationshierarkin innan du kan skapa en ny onlinekanal.</span><span class="sxs-lookup"><span data-stu-id="f27b2-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="f27b2-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="f27b2-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="f27b2-107">Skapa en ny onlinekanal</span><span class="sxs-lookup"><span data-stu-id="f27b2-107">Create a new online channel</span></span>
1. <span data-ttu-id="f27b2-108">Gå till Butik och handel > Kanaler > Onlinebutiker.</span><span class="sxs-lookup"><span data-stu-id="f27b2-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="f27b2-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f27b2-109">Click New.</span></span>
3. <span data-ttu-id="f27b2-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f27b2-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="f27b2-111">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="f27b2-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="f27b2-112">Markera ett alternativ i fältet Tidszon för butik.</span><span class="sxs-lookup"><span data-stu-id="f27b2-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="f27b2-113">Ange eller välj ett värde i fältet Standardkund.</span><span class="sxs-lookup"><span data-stu-id="f27b2-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="f27b2-114">Ange eller välj ett värde i fältet Kundens adressbok.</span><span class="sxs-lookup"><span data-stu-id="f27b2-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="f27b2-115">Ange eller välj ett värde i fältet Betalningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="f27b2-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="f27b2-116">Ange eller välj ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="f27b2-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="f27b2-117">I fältet Meddelandeprofil för e-post, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="f27b2-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="f27b2-118">Expandera avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="f27b2-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="f27b2-119">Ange eller välj ett värde i fältet BusinessUnit.</span><span class="sxs-lookup"><span data-stu-id="f27b2-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="f27b2-120">Ange värdet på samma sätt för alla andra standarddimensioner.</span><span class="sxs-lookup"><span data-stu-id="f27b2-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="f27b2-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f27b2-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="f27b2-122">Lägg till onlinekanalen i organisationshierarkin</span><span class="sxs-lookup"><span data-stu-id="f27b2-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="f27b2-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f27b2-123">Close the page.</span></span>
2. <span data-ttu-id="f27b2-124">Gå till Organisationsadministration > Organisationer > Organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="f27b2-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="f27b2-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f27b2-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f27b2-126">Klicka på Visa.</span><span class="sxs-lookup"><span data-stu-id="f27b2-126">Click View.</span></span>
5. <span data-ttu-id="f27b2-127">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f27b2-127">Click Edit.</span></span>
    * <span data-ttu-id="f27b2-128">Du kan välja en hierarkinod som du vill infoga den nya kanalen under.</span><span class="sxs-lookup"><span data-stu-id="f27b2-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="f27b2-129">Klicka på Infoga.</span><span class="sxs-lookup"><span data-stu-id="f27b2-129">Click Insert.</span></span>
7. <span data-ttu-id="f27b2-130">Klicka på handelskanal.</span><span class="sxs-lookup"><span data-stu-id="f27b2-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="f27b2-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f27b2-131">Click OK.</span></span>
9. <span data-ttu-id="f27b2-132">Klicka på Publicera om du vill öppna formuläret med listrutan för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f27b2-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="f27b2-133">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="f27b2-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="f27b2-134">Klicka på Publicera.</span><span class="sxs-lookup"><span data-stu-id="f27b2-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="f27b2-135">Konfigurera order för nära realtidsmeddelande</span><span class="sxs-lookup"><span data-stu-id="f27b2-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="f27b2-136">Gå till Butik och handel > Administrationsinställning > Parametrar > Commerceparametrar.</span><span class="sxs-lookup"><span data-stu-id="f27b2-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="f27b2-137">Ange Använd realtidstjänst för skapande av näthandelsorder till "Ja".</span><span class="sxs-lookup"><span data-stu-id="f27b2-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="f27b2-138">Kör distributionsschema 1070 för att synkronisera ändringar i databasen för kanalen.</span><span class="sxs-lookup"><span data-stu-id="f27b2-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]