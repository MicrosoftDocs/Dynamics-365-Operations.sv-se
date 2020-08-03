---
title: Övervaka och hantera IoT-information
description: I det här avsnittet beskrivs hur du övervakar och hanterar IoT-information.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 05aee9865dc90c97e026d5c05fa2032fc0625f7a
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597418"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="a8e48-103">Övervaka och hantera IoT-information</span><span class="sxs-lookup"><span data-stu-id="a8e48-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a8e48-104">I det här avsnittet beskrivs hur du övervakar och hanterar IoT-information.</span><span class="sxs-lookup"><span data-stu-id="a8e48-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="a8e48-105">Övervaka scenarier i Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a8e48-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="a8e48-106">Du kan övervaka IoT-information-bearbetningen från flera olika platser:</span><span class="sxs-lookup"><span data-stu-id="a8e48-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="a8e48-107">**Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Meddelanden** – Visa listan över olösta meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a8e48-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="a8e48-108">**Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Stängda meddelanden** – Visa listan över meddelanden som har lösts eller stängts.</span><span class="sxs-lookup"><span data-stu-id="a8e48-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="a8e48-109">**Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Metriska nycklar** – Visa måttnycklarna för **Resursstatus**-diagrammen för tidsserier.</span><span class="sxs-lookup"><span data-stu-id="a8e48-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="a8e48-110">**Moduler \> Tillverkningsstyrning \> Tillverkning \> Resursstatus** – Spåra specifika mått med hjälp av dialogrutan **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="a8e48-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="a8e48-111">Om ett scenario upptäcker ett undantag, visar ett meddelande information om undantaget.</span><span class="sxs-lookup"><span data-stu-id="a8e48-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="a8e48-112">**Arbetsytor \> Tillverkningsgolvsledning \> Meddelanden** – Visa listan över olösta meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a8e48-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="a8e48-113">Ändra ett IoT-information-scenario som körs</span><span class="sxs-lookup"><span data-stu-id="a8e48-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="a8e48-114">När ett scenario körs kan du göra följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="a8e48-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="a8e48-115">Lägg till nya definitioner för sensorschema.</span><span class="sxs-lookup"><span data-stu-id="a8e48-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="a8e48-116">Välj nya värden för signaldata.</span><span class="sxs-lookup"><span data-stu-id="a8e48-116">Select new signal data values.</span></span>
+ <span data-ttu-id="a8e48-117">Avbryt urvalet av befintliga signaldatavärden.</span><span class="sxs-lookup"><span data-stu-id="a8e48-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="a8e48-118">Lägg till och mappa nya värden för signaldata.</span><span class="sxs-lookup"><span data-stu-id="a8e48-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="a8e48-119">Uppdatera tröskelvärden.</span><span class="sxs-lookup"><span data-stu-id="a8e48-119">Update threshold values.</span></span>

<span data-ttu-id="a8e48-120">När ett scenario körs är följande ändringar förbjudna:</span><span class="sxs-lookup"><span data-stu-id="a8e48-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="a8e48-121">Ta bort eller ändra alla schemadefinitioner som för närvarande används av ett aktiverat scenario.</span><span class="sxs-lookup"><span data-stu-id="a8e48-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="a8e48-122">Ändra det aktiverade scenariots valda schemasökvägar.</span><span class="sxs-lookup"><span data-stu-id="a8e48-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="a8e48-123">Simuleringsalternativ</span><span class="sxs-lookup"><span data-stu-id="a8e48-123">Simulation options</span></span>

<span data-ttu-id="a8e48-124">Du kan simulera fabriksdatorsignaler.</span><span class="sxs-lookup"><span data-stu-id="a8e48-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="a8e48-125">Mer information finns i följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="a8e48-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="a8e48-126">Anslut IoT DevKit AZ3166 till Azure IoT Hub</span><span class="sxs-lookup"><span data-stu-id="a8e48-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="a8e48-127">Anslut Raspberryte PI online Simulator till Azure IoT-navet (Node.js)</span><span class="sxs-lookup"><span data-stu-id="a8e48-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="a8e48-128">Översikt över lösningsaccelerator för enhetssimulering</span><span class="sxs-lookup"><span data-stu-id="a8e48-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
