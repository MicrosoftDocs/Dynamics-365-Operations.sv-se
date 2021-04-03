---
title: Registrering av start- och stopptid för en serviceorder
description: Registrering av start- och stopptid för en serviceorder
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcec3cfde34959de73132c8d764df25fb676d140
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242359"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a><span data-ttu-id="62692-103">Registrering av start- och stopptid för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="62692-103">Start and stop time recording on a service order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="62692-104">Använd den här proceduren om du vill starta och stoppa tidsregistrering för en serviceorder som har ett definierat serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="62692-104">Use this procedure to start and stop time recording for a service order for which a service level agreement is defined.</span></span>

## <a name="start-time-recording"></a><span data-ttu-id="62692-105">Starta tidsregistrering</span><span class="sxs-lookup"><span data-stu-id="62692-105">Start time recording</span></span>

1.  <span data-ttu-id="62692-106">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="62692-106">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="62692-107">Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **starta**.</span><span class="sxs-lookup"><span data-stu-id="62692-107">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Start**.</span></span>

3.  <span data-ttu-id="62692-108">Ange datum och tid då tidsregistreringen ska startas.</span><span class="sxs-lookup"><span data-stu-id="62692-108">Enter the date and time that the time recording should be started.</span></span>

## <a name="stop-time-recording"></a><span data-ttu-id="62692-109">Stoppa tidsregistrering</span><span class="sxs-lookup"><span data-stu-id="62692-109">Stop time recording</span></span>

1.  <span data-ttu-id="62692-110">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="62692-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="62692-111">Klicka på fliken **serviceorder**. På **åtgärdsfönstret** i gruppen **Servicenivåavtal** genom att klicka på **stopp**.</span><span class="sxs-lookup"><span data-stu-id="62692-111">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Stop**.</span></span>

3.  <span data-ttu-id="62692-112">Ange datum och tid då tidsregistreringen ska stoppas.</span><span class="sxs-lookup"><span data-stu-id="62692-112">Enter the date and time that the time recording should be stopped.</span></span>

4.  <span data-ttu-id="62692-113">Välj **Lägg till en återkallningsorsak**, och välj en orsakskod i **Fasorsakskod** om du vill ange en orsak till varför tidsregistreringen stoppas.</span><span class="sxs-lookup"><span data-stu-id="62692-113">Select **Add a revocation reason**, and select a reason code in the **Stage reason code** list to provide a reason for stopping the time recording.</span></span>


> [!NOTE]
> <P><span data-ttu-id="62692-114">Om <STRONG>Orsakskod för överskriden tidsgräns</STRONG> väljs i formuläret <STRONG>Serviceparametrar</STRONG> måste du ange en orsakskod innan du kan stoppa tidsregistreringen.</span><span class="sxs-lookup"><span data-stu-id="62692-114">If <STRONG>Reason code on exceeding time</STRONG> is selected in the <STRONG>Service management parameters</STRONG> form, you must provide a reason code before you can stop the time recording.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="62692-115">Se även</span><span class="sxs-lookup"><span data-stu-id="62692-115">See also</span></span>

<span data-ttu-id="62692-116">[Starta tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/library/hh242297\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="62692-116">[Start SLA time recording (form)](https://technet.microsoft.com/library/hh242297\(v=ax.60\))</span></span>

<span data-ttu-id="62692-117">[Stoppa tidsregistrering för servicenivåavtalet (formulär)](https://technet.microsoft.com/library/hh242241\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="62692-117">[Stop SLA time recording (form)](https://technet.microsoft.com/library/hh242241\(v=ax.60\))</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]