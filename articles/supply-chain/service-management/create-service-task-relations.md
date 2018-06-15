---
title: Skapa serviceuppgiftsrelationer
description: "Du kan koppla serviceuppgifter till serviceavtal eller serviceorder för att beskriva serviceuppgiften som ska slutföras för avtalet eller serviceordern."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0892161605401420c0817b3b644271357446a99b
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-task-relations"></a><span data-ttu-id="60c24-103">Skapa serviceuppgiftsrelationer</span><span class="sxs-lookup"><span data-stu-id="60c24-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60c24-104">Du kan koppla serviceuppgifter till serviceavtal eller serviceorder för att beskriva serviceuppgiften som ska slutföras för avtalet eller serviceordern.</span><span class="sxs-lookup"><span data-stu-id="60c24-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="60c24-105">Den här informationen är tillgänglig för servicetekniker och kunder.</span><span class="sxs-lookup"><span data-stu-id="60c24-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="60c24-106">Skapa en relation med ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="60c24-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="60c24-107">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="60c24-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="60c24-108">Välj ett befintligt serviceavtal eller skapa ett nytt serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="60c24-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="60c24-109">Klicka på knappen **Serviceuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="60c24-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="60c24-110">I formuläret **serviceuppgifter** tryck på CTRL+N för att skapa en ny rad och välj sedan en serviceuppgift i listan **serviceuppgift** för att koppla serviceuppgiften till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="60c24-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="60c24-111">På fliken **Beskrivning** anger du eventuella interna eller externa anteckningar i fritextfälten.</span><span class="sxs-lookup"><span data-stu-id="60c24-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="60c24-112">Stäng formuläret om du vill spara posten.</span><span class="sxs-lookup"><span data-stu-id="60c24-112">Close the form to save the record.</span></span>

<span data-ttu-id="60c24-113">Upprepa proceduren tills du har skapat alla nödvändiga serviceuppgiftsrelationer för serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="60c24-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="60c24-114">Nu kan du specificera vilka serviceuppgifter som ska höra till vilka kopplade avtalsrader.</span><span class="sxs-lookup"><span data-stu-id="60c24-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="60c24-115">En serviceuppgiftsrelation som skapas i ett serviceavtal är tillgänligt från alla serviceorder som är kopplade till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="60c24-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="60c24-116">Skapa en relation med en serviceorder</span><span class="sxs-lookup"><span data-stu-id="60c24-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="60c24-117">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="60c24-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="60c24-118">Välj en befintlig serviceorder eller skapa en ny serviceorder.</span><span class="sxs-lookup"><span data-stu-id="60c24-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="60c24-119">Klicka på knappen **Serviceuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="60c24-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="60c24-120">Från formuläret **serviceuppgifter** tryck på CTRL+N för att skapa en ny rad och välj sedan en serviceuppgift i listan **serviceuppgift** för att koppla serviceuppgifterna till serviceordern.</span><span class="sxs-lookup"><span data-stu-id="60c24-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="60c24-121">På fliken **Beskrivning** anger du eventuella interna eller externa anteckningar i fritextfälten.</span><span class="sxs-lookup"><span data-stu-id="60c24-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="60c24-122">Stäng formuläret om du vill spara posten.</span><span class="sxs-lookup"><span data-stu-id="60c24-122">Close the form to save the record.</span></span>

<span data-ttu-id="60c24-123">Upprepa proceduren tills du har skapat alla nödvändiga serviceuppgiftsrelationer för serviceordern.</span><span class="sxs-lookup"><span data-stu-id="60c24-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="60c24-124">När du skapar serviceorderrader kan du välja den serviceuppgift för vilken du skapade relationen.</span><span class="sxs-lookup"><span data-stu-id="60c24-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="60c24-125">Serviceuppgiftsrelationer som skapas i en serviceorder är tillgängliga i den specifika serviceordern.</span><span class="sxs-lookup"><span data-stu-id="60c24-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="60c24-126">Se även</span><span class="sxs-lookup"><span data-stu-id="60c24-126">See also</span></span>

[<span data-ttu-id="60c24-127">Serviceuppgifter </span><span class="sxs-lookup"><span data-stu-id="60c24-127">Service tasks</span></span>](service-tasks.md)


  


