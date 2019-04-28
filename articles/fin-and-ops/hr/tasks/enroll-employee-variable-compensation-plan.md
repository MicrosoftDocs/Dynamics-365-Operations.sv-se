---
title: Registrera en medarbetare i en variabel kompensationsplan
description: Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d120f8bb52252956d75178d2ffac6ab632385e00
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "856403"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="ca8d5-103">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="ca8d5-103">Enroll an employee in a variable compensation plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca8d5-104">Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="ca8d5-105">I den här proceduren förutsätts att en variabel kompensationsplan har skapats med fältet Aktivera anmälan inställt på Ja, och att berättiganderegler har skapats för den variabla kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="ca8d5-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ca8d5-107">Gå till Personal > Arbetare > Medarbetare > Kompensation > Registrering i variabel plan</span><span class="sxs-lookup"><span data-stu-id="ca8d5-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="ca8d5-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-108">Click New.</span></span>
2. <span data-ttu-id="ca8d5-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ca8d5-110">Planuppslagningen filtreras för att visa endast de variabla kompensationsplaner som medarbetaren är berättigad till baserat på berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="ca8d5-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ca8d5-112">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="ca8d5-113">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="ca8d5-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-114">Click Save.</span></span>
7. <span data-ttu-id="ca8d5-115">Växla utökningen av avsnittet Åsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="ca8d5-116">Du kan också välja ett anställningsregeldatum för att åsidosätta anställningsdatumet för en medarbetare när anställningsregeln som har angetts för den valda variabla planen är Procent.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="ca8d5-117">Om den variabla planen är en procentsats av basplanen kan ersättningsprocenten åsidosättas för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="ca8d5-118">Om den variabla kompensationsplanen är en plan med antal enheter kan antalet enheter åsidosättas för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="ca8d5-119">Om medarbetaren ska få ett fast belopp i belöning, kan beloppet anges här.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="ca8d5-120">Växla utökningen av avsnittet Organisationsåsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="ca8d5-121">Om hänsyn ska tas till medarbetarens resultat, resultat för olika avdelningar eller för en annan avdelning än den som har tilldelats till medarbetarens befattning kan avdelningen åsidosättas.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="ca8d5-122">Kolumnen Procent ska uppgå till 100.</span><span class="sxs-lookup"><span data-stu-id="ca8d5-122">The Percent column should total 100.</span></span>  

