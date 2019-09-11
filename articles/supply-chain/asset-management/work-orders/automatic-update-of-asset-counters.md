---
title: Automatisk uppdatering av tillgångsräknare
description: Det här avsnittet beskriver automatisk uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875910"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="20c90-103">Automatisk uppdatering av tillgångsräknare</span><span class="sxs-lookup"><span data-stu-id="20c90-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="20c90-104">I föregående avsnitt beskrivs manuell registrering av tillgångsräknare.</span><span class="sxs-lookup"><span data-stu-id="20c90-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="20c90-105">Inställning av tillgångsräknare beskrivs i [Räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="20c90-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="20c90-106">Räknarvärden kan också uppdateras automatiskt från produktionsregistreringar, baserat på produktionstimmar eller produktionskvantitet.</span><span class="sxs-lookup"><span data-stu-id="20c90-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="20c90-107">Detta görs i **Uppdatera tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="20c90-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="20c90-108">Du kan uppdatera en eller flera tillgångar genom att infoga en parameter, **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="20c90-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="20c90-109">Den här parametern anger startdatum för produktionsregistreringar (timmar eller kvantitet producerad), dvs. startdatumet som räknarvärden ska uppdateras från.</span><span class="sxs-lookup"><span data-stu-id="20c90-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="20c90-110">Alla tillgångar som är relaterade till en resurs *och* har tillgångsräknare, som har ställts in för uppdatering baserad på producerad kvantitet eller produktionstimmar, tas med i en automatisk uppdatering och nya räknarvärden skapas.</span><span class="sxs-lookup"><span data-stu-id="20c90-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="20c90-111">För räknare som baseras på produktionskvantitet, ingår godkänd kvantitet och felregistrerad kvantitet i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="20c90-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="20c90-112">Om enheten som används för registrering av producerad kvantitet skiljer sig från den enhet som används på räknaren, konverteras kvantiteten till räknarenheten.</span><span class="sxs-lookup"><span data-stu-id="20c90-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="20c90-113">Som nämnts ovan kan automatiska räknare uppdateras från produktionsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="20c90-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="20c90-114">Därför måste den tillgång som du vill uppdatera räknare automatiskt för vara relaterad till en resurs (dator).</span><span class="sxs-lookup"><span data-stu-id="20c90-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="20c90-115">Följande beskrivningar ger en översikt över inställning och bearbetning av produktionsorder (i modulen **Produktionskontroll**), som används som grund för automatisk uppdatering av räknare på en till gång i modulen **Tillgångshantering**.</span><span class="sxs-lookup"><span data-stu-id="20c90-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="20c90-116">När producerade kvantiteter eller produktionstimmar har registrerats för resursen kan du uppdatera de relaterade räknarna för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="20c90-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="20c90-117">Klicka på **Tillgångshantering** > **Periodisk** > **Tillgångar** > **Uppdatera tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="20c90-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="20c90-118">Välj startdatum för den automatiska uppdateringen i fältet **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="20c90-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="20c90-119">Datumet i det här fältet är "pågående arbete"-datumet från **Flödestransaktioner** (**Produktionskontroll** > **Förfrågningar och rapporter** > **Produktion** > **Flödestransaktioner** >  fältet **Fysiskt datum**).</span><span class="sxs-lookup"><span data-stu-id="20c90-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="20c90-120">Om du vill välja vissa tillgångar, tillgångstyper eller resurser för den automatiska uppdateringen klickar du på **Filter** på snabbfliken **Poster som ska ingå** och gör de relevanta valen.</span><span class="sxs-lookup"><span data-stu-id="20c90-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="20c90-121">På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.</span><span class="sxs-lookup"><span data-stu-id="20c90-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Figur 1](media/12-work-orders.png)

5. <span data-ttu-id="20c90-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="20c90-123">Click **OK**.</span></span> <span data-ttu-id="20c90-124">När uppdateringen av tillgångsräknaren är färdig kan du se de räknarregistreringar relaterade till tillgången i **Tillgångsräknare** (**Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar** > välj tillgång > knappen **Räknare**).</span><span class="sxs-lookup"><span data-stu-id="20c90-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="20c90-125">I **Tillgångsräknarsummor** kan du få en översikt över den senaste registreringen som gjorts för alla räknartyper för alla tillgångar.</span><span class="sxs-lookup"><span data-stu-id="20c90-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="20c90-126">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Sammanlagt värde för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="20c90-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="20c90-127">Vyn liknar **Tillgångsräknare**, men du kan inte lägga till eller redigera registreringar i **Sammanlagt värde för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="20c90-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="20c90-128">Den är endast för översikt.</span><span class="sxs-lookup"><span data-stu-id="20c90-128">It is for overview only.</span></span>

![Figur 2](media/13-work-orders.png)


- <span data-ttu-id="20c90-130">Det går fortfarande att skapa manuella räknarvärderegistreringar för räknartyper som uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="20c90-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="20c90-131">Mer information finns i avsnittet "Manuell uppdatering av tillgångsräknare".</span><span class="sxs-lookup"><span data-stu-id="20c90-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="20c90-132">Du kan ställa in räknare som är relaterade till en annan räknare, vilket innebär att när en räknare uppdateras, uppdateras relaterade räknare automatiskt samtidigt.</span><span class="sxs-lookup"><span data-stu-id="20c90-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="20c90-133">Information om hur du ställer in relaterade räknare finns i [Räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="20c90-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
