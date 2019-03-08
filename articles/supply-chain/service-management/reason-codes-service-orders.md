---
title: Orsakskoder för serviceorder
description: Använd orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdade89d07fec6a01926015a8c73bacce015fd7a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "363555"
---
# <a name="reason-codes-for-service-orders"></a><span data-ttu-id="a8bd7-103">Orsakskoder för serviceorder</span><span class="sxs-lookup"><span data-stu-id="a8bd7-103">Reason codes for service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a8bd7-104">Du kan använda orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-104">You can use reason codes to help explain the status of a service order when the stage of a service order is updated.</span></span> <span data-ttu-id="a8bd7-105">Om du till exempel annullerar en serviceorder kan du välja en orsakskod för annulleringen.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-105">For example, if you cancel a service order, you can select a reason code for the cancellation.</span></span>

<span data-ttu-id="a8bd7-106">Kör rapporten Serviceorderförlopp om du vill visa information om orsakskoder som används för att följa serviceorderförlopp.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-106">To view information about reason codes that are used to track the progress of service orders, run the Service order progress report.</span></span> <span data-ttu-id="a8bd7-107">Rapporten listar alla serviceorder, oavsett vilken fas de befinner sig i, samt de orsakskoder som specificeras när en serviceorderfas uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-107">This report lists all service orders, regardless of their stage, and the reason codes that are specified when a service order stage is updated.</span></span>

## <a name="turn-reason-codes-on-or-off"></a><span data-ttu-id="a8bd7-108">Aktivera eller inaktivera orsakskoder</span><span class="sxs-lookup"><span data-stu-id="a8bd7-108">Turn reason codes on or off</span></span>

<span data-ttu-id="a8bd7-109">Orsakskoder är valfria.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-109">Reason codes are optional.</span></span> <span data-ttu-id="a8bd7-110">Du kan välja om det ska krävas en orsakskod när du uppdaterar en serviceorder från en viss servicefas.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-110">You can decide whether to require a reason code when you update a service order to a specific service stage.</span></span>

1.  <span data-ttu-id="a8bd7-111">Klicka på **servicehantering**\>**inställningar**\>**serviceorder**\>**Servicefaser**.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-111">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="a8bd7-112">I formuläret **Servicefaser** väljer du en servicefas och markerar sedan kryssrutan **Orsaker** för servicefasen.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-112">In the **Service stages** form, select a service stage, and then select the **Reason** check box for the service stage.</span></span>

3.  <span data-ttu-id="a8bd7-113">Stäng formuläret så att ändringarna sparas.</span><span class="sxs-lookup"><span data-stu-id="a8bd7-113">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8bd7-114">Se även</span><span class="sxs-lookup"><span data-stu-id="a8bd7-114">See also</span></span>

[<span data-ttu-id="a8bd7-115">Ställ in serviceorderfaser</span><span class="sxs-lookup"><span data-stu-id="a8bd7-115">Set up service order stages</span></span>](set-up-service-order-stages.md)



