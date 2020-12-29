---
title: Använd fasorsakskoder
description: Med en orsakskod kan du ange varför ett serviceavtal har annullerats eller varför en serviceorder har överskridigt tidsgränsen som du angav i avtalet.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74594871e9eeed86ae2914d1e5a08c0af28ab643
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437822"
---
# <a name="use-stage-reason-codes"></a><span data-ttu-id="2251b-103">Använd fasorsakskoder</span><span class="sxs-lookup"><span data-stu-id="2251b-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2251b-104">Med en orsakskod kan du ange varför ett serviceavtal har annullerats eller varför en serviceorder har överskridigt tidsgränsen som du angav i avtalet.</span><span class="sxs-lookup"><span data-stu-id="2251b-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="2251b-105">Du kan även ange att en orsakskod krävs när ett serviceavtal annulleras, eller när tidsgränsen som har angetts i servicenivåavtalet för serviceordern överskrids.</span><span class="sxs-lookup"><span data-stu-id="2251b-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="2251b-106">Om du har angett att en orsakskod krävs måste du ange en orsakskod i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="2251b-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="2251b-107">När en serviceordern flyttas till en fas som stoppar tidsregistreringen enligt serviceavtalet för serviceordern.</span><span class="sxs-lookup"><span data-stu-id="2251b-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="2251b-108">När serviceordern kvitteras.</span><span class="sxs-lookup"><span data-stu-id="2251b-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="2251b-109">När tidsregistreringen stoppas manuellt.</span><span class="sxs-lookup"><span data-stu-id="2251b-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="2251b-110">Ställ in orsakskoder</span><span class="sxs-lookup"><span data-stu-id="2251b-110">Set up reason codes</span></span>

1.  <span data-ttu-id="2251b-111">Klicka på **servicehantering**\>**inställningar**\>**serviceorder**\>**Ange orsakskoder**.</span><span class="sxs-lookup"><span data-stu-id="2251b-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="2251b-112">I formuläret **Fasorsakskoder**, klicka på **Ny** för att skapa en ny orsakskod.</span><span class="sxs-lookup"><span data-stu-id="2251b-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="2251b-113">Ange en unik orsakskod för fas i fältet **Fasorsakskod**.</span><span class="sxs-lookup"><span data-stu-id="2251b-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="2251b-114">Ange en orsakskod för fas i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="2251b-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="2251b-115">Stäng formuläret så att ändringarna sparas.</span><span class="sxs-lookup"><span data-stu-id="2251b-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="2251b-116">Kräv orsakskoder när ett serviceavtal annulleras</span><span class="sxs-lookup"><span data-stu-id="2251b-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="2251b-117">Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="2251b-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="2251b-118">I formuläret **Serviceparametrar** klickar du på länken **allmänt** och markerar sedan kryssrutan **orsakskod vid annullering**.</span><span class="sxs-lookup"><span data-stu-id="2251b-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="2251b-119">Kräv orsakskoder när en serviceorder överskrider tidsgränsen som anges i serviceavtalet</span><span class="sxs-lookup"><span data-stu-id="2251b-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="2251b-120">Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="2251b-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="2251b-121">I formuläret **Serviceparametrar** klickar du på länken **allmänt** och markerar sedan kryssrutan **Orsakskod för överskriden tidsgräns**.</span><span class="sxs-lookup"><span data-stu-id="2251b-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="2251b-122">Se även</span><span class="sxs-lookup"><span data-stu-id="2251b-122">See also</span></span>

[<span data-ttu-id="2251b-123">Registrering av start- och stopptid för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="2251b-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  


