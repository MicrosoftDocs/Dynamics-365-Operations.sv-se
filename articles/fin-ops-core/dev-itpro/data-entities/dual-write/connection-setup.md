---
title: Scenarier som stöds för inställningen dubbelriktad skrivning
description: I det här avsnittet beskrivs scenarier som stöds för inställningen dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 1319f1228b635e207754f7c2516cb2b5353a9edd
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112521"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="8b1b4-103">Scenarier som stöds för inställningen dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="8b1b4-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="8b1b4-104">Du kan skapa en dubbelriktad anslutning mellan en Finance and Operations-miljö och en Common Data Service-miljö.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="8b1b4-105">En **Finance and Operations-miljö** tillhandahåller den underliggande plattformen för **Finance and Operations-appar** (till exempel Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail och Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="8b1b4-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="8b1b4-106">En **Common Data Service-miljö** tillhandahåller den underliggande plattformen för **modellstyrda appar i Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing och Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="8b1b4-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="8b1b4-107">Installationsmekanismen varierar beroende på din prenumeration och miljön.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="8b1b4-108">För nya instanser av Finance and Operations-appar börjar konfigurationen av en dubbelriktad anslutning i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8b1b4-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="8b1b4-109">Om du har en licens för Microsoft Power Platform får du en ny Common Data Service-miljö om ditt innehavare inte har någon.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="8b1b4-110">När det gäller Finance and Operations-appar i befintliga instanser börjar konfigurationen av dubbelriktad anslutning i Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="8b1b4-111">Följande konfigurationsscenarier stöds:</span><span class="sxs-lookup"><span data-stu-id="8b1b4-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="8b1b4-112">En ny Finance and Operations-appinstans och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="8b1b4-113">En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="8b1b4-114">En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="8b1b4-115">En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="8b1b4-116">En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="8b1b4-117">En ny Finance and Operations-appinstans och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="8b1b4-118">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en ny instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="8b1b4-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="8b1b4-119">När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="8b1b4-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="8b1b4-120">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="8b1b4-121">En ny, tom instans av en modellstyrd app etableras, där den primtal som CRM är installerad.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="8b1b4-122">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="8b1b4-123">Entitetsmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="8b1b4-124">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="8b1b4-125">En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="8b1b4-126">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av Finance and Operations-app som inte har några data och en befintlig instans av en modellstyrd app i Dynamics 365 följer du stegen i [inställningen dubbelriktad skrivning från Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="8b1b4-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="8b1b4-127">När anslutningsinställningarna har slutförts utförs följande åtgärder automatiskt:</span><span class="sxs-lookup"><span data-stu-id="8b1b4-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="8b1b4-128">En ny, tom Finance and Operations-miljö etableras.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="8b1b4-129">En dubbelriktad anslutning har upprättats för DAT företagsdata.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="8b1b4-130">Entitetsmappningar aktiveras för direkt synkronisering.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="8b1b4-131">De båda miljöerna är sedan klara för synkronisering av realtidsdata.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="8b1b4-132">Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="8b1b4-133">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="8b1b4-134">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="8b1b4-135">[Starta](bootstrap-company-data.md) Common Data Service data med en ISO-kod (Internationella standardiseringsorganisationen) med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="8b1b4-136">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="8b1b4-137">En ny Finance and Operations-appinstans som har demodata och en ny modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="8b1b4-138">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en ny instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en ny modellstyrd appinstans](#new-new) tidigare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="8b1b4-139">När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="8b1b4-140">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="8b1b4-141">Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="8b1b4-142">En ny Finance and Operations-appinstans som har demodata och en befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="8b1b4-143">Om du vill ställa in en dubbelriktad anslutning mellan en ny instans av en Finance and Operations-app som har demodata och en befintlig instans av en modellstyrd app i Dynamics 365, följ stegen i avsnittet [En ny Finance and Operations-appinstans och en befintlig modellstyrd appinstans](#new-existing) tidigare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="8b1b4-144">När anslutningskonfigurationen har slutförts, och du vill synkronisera demonstrationsdata med den modellstyrda appen, följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="8b1b4-145">Öppna Finance and Operations-appen från sidan LCS, logga in och gå sedan till **datahantering \> dubbelriktadskrivning**.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="8b1b4-146">Kör funktionen **Initial synkronisering** för de entiteter som du vill synkronisera data för.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="8b1b4-147">Om du vill synkronisera befintliga Common Data Service data till Finance and Operations-appen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="8b1b4-148">Skapa ett nytt företag i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="8b1b4-149">Lägg till företaget i konfigurationen av dubbelriktad anslutning.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="8b1b4-150">[Starta](bootstrap-company-data.md) Common Data Service-data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="8b1b4-151">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="8b1b4-152">En befintlig Finance and Operations-appinstans och en ny eller befintlig modellstyrd appinstans</span><span class="sxs-lookup"><span data-stu-id="8b1b4-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="8b1b4-153">Inställningen dubbelriktad anslutning mellan en befintlig instans av en Finance and Operations-app och en ny eller befintlig instans av en modellstyrd app i Dynamics 365 inträffar i Finance and Operation-miljön.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="8b1b4-154">Ställ in anslutningen från Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="8b1b4-155">Om du vill synkronisera befintlig Common Data Service data till Finance and Operations-app, [starta](bootstrap-company-data.md) Common Data Service data med en ISO-företagskod med tre bokstäver.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="8b1b4-156">Eftersom dubbelriktad skrivning är i realtidssynkroniseringsläge, startar data från Common Data Service automatiskt för att flöda till Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="8b1b4-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
