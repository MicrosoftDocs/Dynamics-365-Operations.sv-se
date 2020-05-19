---
title: Inleverans av ID-nummer via lagerstyrningsappen
description: I det här avsnittet beskrivs hur du ställer in lagerstyrningsappen så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346386"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a><span data-ttu-id="5a98e-103">Inleverans av ID-nummer via lagerstyrningsappen</span><span class="sxs-lookup"><span data-stu-id="5a98e-103">License plate receiving via the warehousing app</span></span>

<span data-ttu-id="5a98e-104">I det här avsnittet beskrivs hur du ställer in lagerstyrningsappen så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.</span><span class="sxs-lookup"><span data-stu-id="5a98e-104">This topic explains how to set up the warehousing app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="5a98e-105">Du kan använda den här funktionen för att snabbt registrera inleveranser av ankommande lager som är relaterat till en leveransavisering (ASN).</span><span class="sxs-lookup"><span data-stu-id="5a98e-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="5a98e-106">Systemet skapar automatiskt ett ASN när lagerstyrningsprocesser används för att leverera en överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="5a98e-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="5a98e-107">För inköpsorderprocessen kan ett ASN registreras manuellt, eller importeras automatiskt med hjälp av en inkommande ASN-dataenhetsprocess.</span><span class="sxs-lookup"><span data-stu-id="5a98e-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="5a98e-108">ASN-data är kopplade till laster och försändelser via *förpackningsstrukturer*, där lastpallar (överordnade ID-nummerar) kan innehålla lådor (kapslade ID-nummer).</span><span class="sxs-lookup"><span data-stu-id="5a98e-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="5a98e-109">Om du vill minska antalet lagertransaktioner när förpackningsstrukturer som har kapslade ID-nummer används registrerar systemet den fysiska lagerbehållningen på den överordnade ID-numret.</span><span class="sxs-lookup"><span data-stu-id="5a98e-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="5a98e-110">För att den fysiska lagerbehållningen ska kunna initieras från den överordnade ID-numret till de kapslade ID-nummerna, baserat på förpackningsstrukturens data, måste den mobila enheten tillhandahålla ett menyobjekt som baseras på processen för att skapa arbete *paketet för att skapa kapslade ID-nummer*.</span><span class="sxs-lookup"><span data-stu-id="5a98e-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="5a98e-111">Visa eller hoppa över sidan för sammanfattning av inleveranser</span><span class="sxs-lookup"><span data-stu-id="5a98e-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="5a98e-112">Du kan använda funktionen *kontrollera om du vill visa en sida för sammanfattning av inleveranser* för att dra nytta av ett ytterligare detaljerat lagerstyrningsappflöde som del av inleveransprocessen med ID-numret.</span><span class="sxs-lookup"><span data-stu-id="5a98e-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed warehousing app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="5a98e-113">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="5a98e-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="5a98e-114">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="5a98e-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="5a98e-115">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="5a98e-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="5a98e-116">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="5a98e-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5a98e-117">**Funktionsnamn:** *ange om du ska visa sidan för sammanfattning av inleveranser på mobila enheter*</span><span class="sxs-lookup"><span data-stu-id="5a98e-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="5a98e-118">När den här funktionen är aktiverad visas ett menyalternativ för mobila enheter för inleverans av ID-nummer eller inleverans av ID-nummer och artikelinförsel ger inställningen **sidan för sammanfattning av inleveranser**.</span><span class="sxs-lookup"><span data-stu-id="5a98e-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="5a98e-119">Den här inställningen har följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="5a98e-119">This setting has the following options:</span></span>

- <span data-ttu-id="5a98e-120">**Visa en detaljerad sammanfattning** – under inleverans av ID-nummer ser arbetarna en extra sida med den fullständiga ASN-informationen.</span><span class="sxs-lookup"><span data-stu-id="5a98e-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="5a98e-121">**Hoppa över sammanfattningen** – arbetarna ser inte hela ASN-informationen.</span><span class="sxs-lookup"><span data-stu-id="5a98e-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="5a98e-122">Lagerarbetarna inte heller ange en dispositionskod eller lägga till undantag under inleveransprocessen.</span><span class="sxs-lookup"><span data-stu-id="5a98e-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="5a98e-123">Förhindra överföringsorder – de levererade ID-numren används inte på andra lagerställen än lagerstället vid destinationen</span><span class="sxs-lookup"><span data-stu-id="5a98e-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="5a98e-124">En inleveransprocess av ID-nummer kan inte användas om ett ASN innehåller ett ID-nummer som redan finns och som har fysiska behållningsdata på ett annat lagerställe än det där registrering av ID-numret.</span><span class="sxs-lookup"><span data-stu-id="5a98e-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="5a98e-125">För scenarion för överföringsorder där transportlager inte spårar ID-nummer (och därför inte heller spårar fysisk lagerbehållning per ID-nummer) kan du använda funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* för att förhindra att fysiska lageruppdateringar av ID-nummer som är under transport.</span><span class="sxs-lookup"><span data-stu-id="5a98e-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="5a98e-126">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="5a98e-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="5a98e-127">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="5a98e-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="5a98e-128">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="5a98e-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="5a98e-129">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="5a98e-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5a98e-130">**Funktionens namn:** *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen*</span><span class="sxs-lookup"><span data-stu-id="5a98e-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="5a98e-131">Om du vill hantera funktionerna när den här funktionen är tillgänglig följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="5a98e-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="5a98e-132">Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="5a98e-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="5a98e-133">På fliken **allmänt** i snabbfliken **ID-nummer** ställer du in fältet **ID-nummerpolicy för transitlager** till något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5a98e-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="5a98e-134">**Tillåt återanvändning av ej spårat ID-nummer** – systemet fungerar på samma sätt som när funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="5a98e-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="5a98e-135">Det här värdet är standardinställningen när du först aktiverar funktionen.</span><span class="sxs-lookup"><span data-stu-id="5a98e-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="5a98e-136">**Förhindra återanvändning av ej spårat ID-nummer** – endast uppdateringar av lager som är relaterade till ett levererat ID-nummer är tillåtna vid lagerstället på destinationen tills överföringsordern har inlevererats.</span><span class="sxs-lookup"><span data-stu-id="5a98e-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="5a98e-137">Mer information</span><span class="sxs-lookup"><span data-stu-id="5a98e-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="5a98e-138">Mer information om menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="5a98e-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
