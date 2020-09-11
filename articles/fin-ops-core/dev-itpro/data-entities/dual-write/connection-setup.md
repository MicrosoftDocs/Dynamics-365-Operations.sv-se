---
title: Scenarier som stöds för inställningen dubbelriktad skrivning
description: I det här avsnittet beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 275d24d8f32fd1d2d15356d14c5c6591e8503c65
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706262"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="4ba2e-103">Scenarier som stöds för inställningen dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="4ba2e-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="4ba2e-104">Du kan skapa en dubbelriktad anslutning mellan en Finance and Operations-miljö och en Common Data Service-miljö.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="4ba2e-105">En **Finance and Operations-miljö** tillhandahåller den underliggande plattformen för **Finance and Operations-appar** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management och Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="4ba2e-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="4ba2e-106">En **Common Data Service-miljö** tillhandahåller den underliggande plattformen för **modellstyrda appar i Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="4ba2e-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="4ba2e-107">Personal i Finance and Operations stöder anslutningar med dubbla skrivfunktioner med inte Dynamics 365 Human Resources-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="4ba2e-108">Installationsmekanismen varierar beroende på din prenumeration och miljön.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="4ba2e-109">För nya instanser av Finance and Operations-appar börjar konfigurationen av en dubbelriktad anslutning i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4ba2e-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="4ba2e-110">Om du har en licens för Microsoft Power Platform får du en ny Common Data Service-miljö om ditt innehavare inte har någon.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-110">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="4ba2e-111">När det gäller Finance and Operations-appar i befintliga instanser börjar konfigurationen av dubbelriktad anslutning i Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="4ba2e-112">Följande konfigurationsscenarier stöds:</span><span class="sxs-lookup"><span data-stu-id="4ba2e-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="4ba2e-113">En ny Finance and Operations-appinstans och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="4ba2e-114">En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="4ba2e-115">En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="4ba2e-116">En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="4ba2e-117">En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="4ba2e-118">En ny Finance and Operations-appinstans och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="4ba2e-119">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en ny instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="4ba2e-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="4ba2e-120">När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="4ba2e-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="4ba2e-121">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="4ba2e-122">En ny, tom instans av en modellstyrd app etableras, där den primtal som CRM är installerad.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="4ba2e-123">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="4ba2e-124">Entitetsmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="4ba2e-125">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="4ba2e-126">En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="4ba2e-127">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en befintlig instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="4ba2e-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="4ba2e-128">När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="4ba2e-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="4ba2e-129">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="4ba2e-130">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="4ba2e-131">Entitetsmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="4ba2e-132">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="4ba2e-133">Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="4ba2e-134">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="4ba2e-135">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="4ba2e-136">[Starta](bootstrap-company-data.md) Common Data Service data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="4ba2e-137">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="4ba2e-138">En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="4ba2e-139">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en ny instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en ny modellstyrd appinstans](#new-new) tidigare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="4ba2e-140">När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="4ba2e-141">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="4ba2e-142">Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="4ba2e-143">En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="4ba2e-144">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en befintlig instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans](#new-existing) tidigare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="4ba2e-145">När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="4ba2e-146">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="4ba2e-147">Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="4ba2e-148">Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="4ba2e-149">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="4ba2e-150">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="4ba2e-151">[Starta](bootstrap-company-data.md) Common Data Service-data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="4ba2e-152">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="4ba2e-153">En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="4ba2e-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="4ba2e-154">Inställningen dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en ny eller befintlig instans av en modellstyrd app i Dynamics 365 inträffar i Finance and Operation-miljön.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="4ba2e-155">Ställ in anslutningen från Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="4ba2e-156">Om du vill synkronisera befintlig Common Data Service data till Finance and Operations-app, [starta](bootstrap-company-data.md) Common Data Service data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="4ba2e-157">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="4ba2e-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
