---
title: Ställa in en prioriterad tekniker
description: Du kan välja valfri anställd som en prioriterad tekniker för ett serviceavtal eller en serviceorder.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e904db7312563b8b7dc584c9fa4d40b947db4db5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341521"
---
# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="10f50-103">Ställa in en prioriterad tekniker</span><span class="sxs-lookup"><span data-stu-id="10f50-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="10f50-104">Du kan välja valfri anställd som en prioriterad tekniker för ett serviceavtal eller en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="10f50-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="10f50-105">Det är dock en bra idé att lägga till arbetare i en lämplig servicegrupp, så att arbetaren inkluderas på **Utförseltavla**.</span><span class="sxs-lookup"><span data-stu-id="10f50-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="10f50-106">Lägga till en medarbetare i en servicegrupp</span><span class="sxs-lookup"><span data-stu-id="10f50-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="10f50-107">Klicka på **Personal** \> **Gemensamt** \> **Arbetare** \> **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="10f50-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="10f50-108">Dubbelklicka på en anställd för att öppna arbetaredetaljsidan.</span><span class="sxs-lookup"><span data-stu-id="10f50-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="10f50-109">I **åtgärdsfönstret**, klickar du på **inställningar**\>**serviceteam** för att öppna formuläret **servicearbetare**.</span><span class="sxs-lookup"><span data-stu-id="10f50-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="10f50-110">I fältet **Serviceteam**, välj teamet som ska tilldelas arbetare i fältet </span><span class="sxs-lookup"><span data-stu-id="10f50-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="10f50-111">Tilldela en prioriterad tekniker till ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="10f50-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="10f50-112">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="10f50-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="10f50-113">Dubbelklicka på ett serviceavtal att öppna detaljformuläret.</span><span class="sxs-lookup"><span data-stu-id="10f50-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="10f50-114">På fliken **Allmänt**, välj fältet **Prioriterad tekniker** välj en medlem av en lämplig servicegrupp som den tekniker som föredras för serviceavtalet genom att använda listan.</span><span class="sxs-lookup"><span data-stu-id="10f50-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="10f50-115">Tilldela en prioriterad tekniker till en serviceorder</span><span class="sxs-lookup"><span data-stu-id="10f50-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="10f50-116">Klicka på **Servicehantering** \> **Periodisk** \> **Utförseltavla**.</span><span class="sxs-lookup"><span data-stu-id="10f50-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="10f50-117">I formuläret <STRONG>Utförseltavla</STRONG>, ange ett datumintervall för serviceaktiviteter som du vill se.</span><span class="sxs-lookup"><span data-stu-id="10f50-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="10f50-118">Ange dessutom om du vill se stängda aktiviteter och huruvida du vill begränsa aktivitetslistan till grupper som du tillhör eller är behörig att övervaka.</span><span class="sxs-lookup"><span data-stu-id="10f50-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="10f50-119">Klicka på <STRONG>OK</STRONG> för att öppna <STRONG>Utförseltavla</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10f50-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="10f50-120">Markera raden för den serviceaktivitet som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="10f50-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="10f50-121">På fliken **Relaterad**, använd listan **Arbetare** för att tilldela en medlem av en lämplig servicegrupp som den tekniker som föredras för servicetillfället.</span><span class="sxs-lookup"><span data-stu-id="10f50-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="10f50-122">Se även</span><span class="sxs-lookup"><span data-stu-id="10f50-122">See also</span></span>

[<span data-ttu-id="10f50-123">Serviceavtal </span><span class="sxs-lookup"><span data-stu-id="10f50-123">Service agreements</span></span>](service-agreements.md)

[<span data-ttu-id="10f50-124">Skapa en serviceorder manuellt</span><span class="sxs-lookup"><span data-stu-id="10f50-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="10f50-125">[Serviceavtal (formulär)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="10f50-125">[Service agreements (form)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))</span></span>
  


