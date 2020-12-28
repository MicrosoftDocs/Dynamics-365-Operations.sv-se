---
title: Skapa ett massanställningsprojekt
description: I den här proceduren beskrivs processen för att ställa in ett massanställningsprojekt.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ddcfd531e7b5c76ac4b15cee54880f6868a73f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420527"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="3a480-103">Skapa ett massanställningsprojekt</span><span class="sxs-lookup"><span data-stu-id="3a480-103">Create a mass hire project</span></span>



<span data-ttu-id="3a480-104">I den här proceduren beskrivs processen för att ställa in ett massanställningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="3a480-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="3a480-105">En rekryterare kan använda massanställningsprojekt för att skapa flera befattningar och anställa ett antal arbetare till dessa befattningar på ett enkelt sätt.</span><span class="sxs-lookup"><span data-stu-id="3a480-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="3a480-106">Gå till Personal > Rekrytering > Massanställningsprojekt för att starta proceduren.</span><span class="sxs-lookup"><span data-stu-id="3a480-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="3a480-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="3a480-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="3a480-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3a480-108">Click New.</span></span>
2. <span data-ttu-id="3a480-109">Skriv ett värde i fältet Massanställningsprojekt.</span><span class="sxs-lookup"><span data-stu-id="3a480-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="3a480-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="3a480-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="3a480-111">Ange ett datum i fältet Projekt.</span><span class="sxs-lookup"><span data-stu-id="3a480-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="3a480-112">Ange ett datum i fältet Projektslut.</span><span class="sxs-lookup"><span data-stu-id="3a480-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="3a480-113">Klicka på Öppet projekt.</span><span class="sxs-lookup"><span data-stu-id="3a480-113">Click Open project.</span></span>
7. <span data-ttu-id="3a480-114">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="3a480-114">Click Yes.</span></span>
8. <span data-ttu-id="3a480-115">Klicka på Skapa befattningar.</span><span class="sxs-lookup"><span data-stu-id="3a480-115">Click Create positions.</span></span>
9. <span data-ttu-id="3a480-116">I fältet Kvantitet anger du det antal befattningar som du vill skapa</span><span class="sxs-lookup"><span data-stu-id="3a480-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="3a480-117">Startdatumet kommer att bli anställningsdatumet för de nya arbetarna.</span><span class="sxs-lookup"><span data-stu-id="3a480-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="3a480-118">Slutdatumet kommer att bli uppsägningsdatumet för de nya arbetarna.</span><span class="sxs-lookup"><span data-stu-id="3a480-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="3a480-119">Ange om de nya arbetarna ska vara medarbetare eller leverantörer.</span><span class="sxs-lookup"><span data-stu-id="3a480-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="3a480-120">Klicka på den nedrullningsbara knappen för att välja det jobb som du vill skapa befattningarna för.</span><span class="sxs-lookup"><span data-stu-id="3a480-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="3a480-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3a480-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="3a480-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="3a480-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3a480-123">Heltidsvärdet ska hämtas från det jobb som har valts.</span><span class="sxs-lookup"><span data-stu-id="3a480-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="3a480-124">Du kan ändra detta om det behövs.</span><span class="sxs-lookup"><span data-stu-id="3a480-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="3a480-125">Du kan välja avdelning för de nya befattningarna.</span><span class="sxs-lookup"><span data-stu-id="3a480-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="3a480-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3a480-126">Click OK.</span></span>

