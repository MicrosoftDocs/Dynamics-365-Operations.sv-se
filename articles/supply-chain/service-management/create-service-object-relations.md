---
title: Skapa serviceobjektrelationer
description: Det här avsnittet beskriver hur du kan skapa serviceobjektrelationer för ett serviceavtal och en serviceorder.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05d770234beb486eb3a8181b160967c802c15e8f
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813165"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="c05e1-103">Skapa serviceobjektrelationer</span><span class="sxs-lookup"><span data-stu-id="c05e1-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c05e1-104">Det här avsnittet beskriver hur du kan skapa serviceobjektrelationer för ett serviceavtal och en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="c05e1-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="c05e1-105">När du skapar en serviceobjektrelation kopplar du serviceobjektet till serviceavtalet eller serviceordern.</span><span class="sxs-lookup"><span data-stu-id="c05e1-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="c05e1-106">När en kund begär service för en artikel som är ett serviceobjekt, kan du välja serviceobjektet från listan med serviceobjektrelationer.</span><span class="sxs-lookup"><span data-stu-id="c05e1-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="c05e1-107">Skapa en serviceobjektrelation för ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="c05e1-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="c05e1-108">Använd följande steg för att skapa en ny serviceobjektrelation för ett serviceavtal:</span><span class="sxs-lookup"><span data-stu-id="c05e1-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="c05e1-109">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="c05e1-110">I listan **Serviceavtal** markera ett befintligt serviceavtal eller klicka på **Ny** för att skapa ett nytt serviceavtal i listan.</span><span class="sxs-lookup"><span data-stu-id="c05e1-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="c05e1-111">I formuläret **Serviceavtal** på **åtgärdsfönstret**, på fliken **serviceavtal** i gruppen **Relationer**, klicka på **Serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="c05e1-112">I formuläret **Serviceobjekt**, klicka på **Ny** och välj sedan ett serviceobjekt för det här serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="c05e1-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="c05e1-113">Om du vill tilldela en strukturlista till ett serviceavtal klickar du på **Funktioner** och väljer sedan **Bifoga mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="c05e1-114">I formuläret **Välj strukturlistemall** i fältet **Mallstrukturlista**, välj en mall.</span><span class="sxs-lookup"><span data-stu-id="c05e1-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="c05e1-115">Skapa en serviceobjektrelation för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="c05e1-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="c05e1-116">Använd följande steg för att skapa en ny serviceobjektrelation för ett serviceorder:</span><span class="sxs-lookup"><span data-stu-id="c05e1-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="c05e1-117">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="c05e1-118">I listan **Serviceorder** väljer du en befintlig serviceorder eller skapar en ny serviceorder.</span><span class="sxs-lookup"><span data-stu-id="c05e1-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="c05e1-119">I formuläret **Serviceorder** på **åtgärdsfönstret**, på fliken **serviceorder** i gruppen **Relationer**, klicka på **Serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="c05e1-120">I formuläret **Serviceobjekt**, klicka på **Ny** och välj sedan ett serviceobjekt för det här serviceordern.</span><span class="sxs-lookup"><span data-stu-id="c05e1-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="c05e1-121">Om du vill tilldela en strukturlista till ett serviceavtal klickar du på **Funktioner** och väljer sedan **Bifoga mallstrukturlista**.</span><span class="sxs-lookup"><span data-stu-id="c05e1-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="c05e1-122">I formuläret **Välj strukturlistemall** i fältet **Mallstrukturlista**, välj en mall.</span><span class="sxs-lookup"><span data-stu-id="c05e1-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="c05e1-123">Se även</span><span class="sxs-lookup"><span data-stu-id="c05e1-123">See also</span></span>

[<span data-ttu-id="c05e1-124">Serviceobjekt – översikt</span><span class="sxs-lookup"><span data-stu-id="c05e1-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="c05e1-125">Serviceobjektrelationer</span><span class="sxs-lookup"><span data-stu-id="c05e1-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="c05e1-126">Strukturlistemallar</span><span class="sxs-lookup"><span data-stu-id="c05e1-126">Template BOMs</span></span>](template-boms.md)

  


