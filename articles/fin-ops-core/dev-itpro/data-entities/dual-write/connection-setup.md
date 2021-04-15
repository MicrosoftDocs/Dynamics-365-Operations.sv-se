---
title: Riktlinjer för att ställa in dubbelriktad skrivning
description: I det här avsnittet beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 999b37970be1c10fd5e78c3d8ac6c1fb25cad367
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751396"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="309eb-103">Riktlinjer för att ställa in dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="309eb-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="309eb-104">Du kan skapa en dubbelriktad anslutning mellan en Finance and Operations-miljö och en Dataverse-miljö.</span><span class="sxs-lookup"><span data-stu-id="309eb-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="309eb-105">En **Finance and Operations-miljö** tillhandahåller den underliggande plattformen för **Finance and Operations-appar** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="309eb-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="309eb-106">En **Dataverse-miljö** tillhandahåller den underliggande plattformen för **kundengagemangsappar** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="309eb-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="309eb-107">Personalmodulen i Dynamics 365 Finance har stöd för anslutningar för dubbelriktad skrivning men inte Dynamics 365 Human Resources-appen.</span><span class="sxs-lookup"><span data-stu-id="309eb-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="309eb-108">Installationsmekanismen varierar beroende på din prenumeration och miljön:</span><span class="sxs-lookup"><span data-stu-id="309eb-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="309eb-109">För nya instanser av Finance and Operations-appar börjar konfigurationen av en dubbelriktad anslutning i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="309eb-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="309eb-110">Om du har en licens för Microsoft Power Platform får du en ny Dataverse-miljö om ditt innehavare inte har någon.</span><span class="sxs-lookup"><span data-stu-id="309eb-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="309eb-111">När det gäller Finance and Operations-appar i befintliga instanser börjar konfigurationen av dubbelriktad anslutning i Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="309eb-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="309eb-112">Innan du startar dubbelriktad skrivning på en enhet kan du köra en inledande synkronisering för att hantera befintliga data på båda sidor av Finance and Operations-appar och kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="309eb-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="309eb-113">Du kan hoppa över den inledande synkroniseringen om du inte behöver synkronisera data mellan de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="309eb-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="309eb-114">Vid en inledande synkronisering kan du kopiera befintliga data från ett program till en annan dubbelriktat.</span><span class="sxs-lookup"><span data-stu-id="309eb-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="309eb-115">Det finns flera installationsscenarier beroende på vilka miljöer som du redan har och vilken typ av data som finns i dem.</span><span class="sxs-lookup"><span data-stu-id="309eb-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="309eb-116">Följande konfigurationsscenarier stöds:</span><span class="sxs-lookup"><span data-stu-id="309eb-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="309eb-117">En ny Finance and Operations-appinstans och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="309eb-118">En ny Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="309eb-119">En ny Finance and Operations-appinstans som har demodata och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="309eb-120">En ny Finance and Operations-appinstans som har demodata och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="309eb-121">En befintlig Finance and Operations-appinstans och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="309eb-122">En befintlig Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="309eb-123">En ny Finance and Operations-appinstans och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="309eb-124">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en ny instans av kundengagemangsapp följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="309eb-125">När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="309eb-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="309eb-126">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="309eb-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="309eb-127">En ny, tom instans av en kundengagemangsapp etableras, där den primtal som CRM är installerad.</span><span class="sxs-lookup"><span data-stu-id="309eb-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="309eb-128">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="309eb-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="309eb-129">Tabellmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="309eb-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="309eb-130">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="309eb-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="309eb-131">En ny Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="309eb-132">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en befintlig instans av kundengagemangsapp följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="309eb-133">När anslutningsinstallationen har slutförts sker följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="309eb-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="309eb-134">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="309eb-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="309eb-135">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="309eb-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="309eb-136">Tabellmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="309eb-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="309eb-137">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="309eb-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="309eb-138">Om du vill synkronisera befintliga Dataverse data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="309eb-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="309eb-139">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="309eb-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="309eb-140">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="309eb-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="309eb-141">[Starta](bootstrap-company-data.md) Dataverse data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="309eb-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="309eb-142">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-143">Länkar till ett exempel och en alternativ metod finns i [Exempel](#example) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="309eb-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="309eb-144">En ny Finance and Operations-appinstans som har demodata och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="309eb-145">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har data och en ny instans av en kundengagemangsapp, följ stegen i [En ny Finance and Operations-appinstans och en ny kundengagemangsapp](#new-new) tidigare i detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="309eb-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="309eb-146">När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="309eb-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="309eb-147">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="309eb-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="309eb-148">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-149">Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).</span><span class="sxs-lookup"><span data-stu-id="309eb-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="309eb-150">En ny Finance and Operations-appinstans som har demodata och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="309eb-151">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har data och en befintlig instans av en kundengagemangsapp, följ stegen i [En ny Finance and Operations-appinstans och en befintlig kundengagemangsapp](#new-existing) tidigare i detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="309eb-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="309eb-152">När anslutningskonfigurationen har slutförts, och du vill synkronisera data med kundengagemangsappen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="309eb-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="309eb-153">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="309eb-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="309eb-154">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-155">Om du vill synkronisera befintliga Dataverse data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="309eb-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="309eb-156">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="309eb-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="309eb-157">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="309eb-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="309eb-158">[Starta](bootstrap-company-data.md) Dataverse-data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="309eb-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="309eb-159">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-160">Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).</span><span class="sxs-lookup"><span data-stu-id="309eb-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="309eb-161">En befintlig Finance and Operations-appinstans och en ny instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="309eb-162">Inställningen dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en ny instans av en kundengagemangsapp förekommer i Finance and Operation-miljön.</span><span class="sxs-lookup"><span data-stu-id="309eb-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="309eb-163">[Ställ in anslutningen från Finance and Operations-appen](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="309eb-164">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-165">Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).</span><span class="sxs-lookup"><span data-stu-id="309eb-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="309eb-166">En befintlig Finance and Operations-appinstans och en befintlig instans av kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="309eb-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="309eb-167">Inställning av dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en befintlig instans av en kundengagemangsapp sker i Finance and Operation-miljön.</span><span class="sxs-lookup"><span data-stu-id="309eb-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="309eb-168">[Ställ in anslutningen från Finance and Operations-appen](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="309eb-169">Om du vill synkronisera befintlig Dataverse data till Finance and Operations-app, [starta](bootstrap-company-data.md) Dataverse data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="309eb-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="309eb-170">Kör funktionen **Initial synkronisering** för de tabeller som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="309eb-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="309eb-171">Länkar till ett exempel och en alternativ metod finns i avsnittet [Exempel](#example).</span><span class="sxs-lookup"><span data-stu-id="309eb-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="309eb-172">Exempel</span><span class="sxs-lookup"><span data-stu-id="309eb-172">Example</span></span>

<span data-ttu-id="309eb-173">Ett exempel finns i [Aktivera Customers V3 – kontakter tabellmappning](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="309eb-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="309eb-174">Om du vill ha en alternativ metod baserad på datavolymer i varje enhet som måste köra en inledande synkronisering, se [Att tänka på vid första synkroniseringen](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]