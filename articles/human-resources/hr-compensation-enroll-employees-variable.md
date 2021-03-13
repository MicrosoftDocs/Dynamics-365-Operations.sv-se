---
title: Registrera en medarbetare i en variabel kompensationsplan
description: Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a173403e79212be5e4aac36d99f349da159e08
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114306"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="f5501-103">Registrera en medarbetare i en variabel kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="f5501-103">Enroll an employee in a variable compensation plan</span></span>

<span data-ttu-id="f5501-104">Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="f5501-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="f5501-105">I den här proceduren förutsätts att en variabel kompensationsplan har skapats med fältet Aktivera anmälan inställt på Ja, och att berättiganderegler har skapats för den variabla kompensationsplanen.</span><span class="sxs-lookup"><span data-stu-id="f5501-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="f5501-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="f5501-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f5501-107">Gå till Personal > Arbetare > Medarbetare > Kompensation > Registrering i variabel plan</span><span class="sxs-lookup"><span data-stu-id="f5501-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="f5501-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f5501-108">Click New.</span></span>
2. <span data-ttu-id="f5501-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="f5501-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f5501-110">Planuppslagningen filtreras för att visa endast de variabla kompensationsplaner som medarbetaren är berättigad till baserat på berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="f5501-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="f5501-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f5501-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f5501-112">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="f5501-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="f5501-113">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="f5501-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="f5501-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f5501-114">Click Save.</span></span>
7. <span data-ttu-id="f5501-115">Växla utökningen av avsnittet Åsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="f5501-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="f5501-116">Du kan också välja ett anställningsregeldatum för att åsidosätta anställningsdatumet för en medarbetare när anställningsregeln som har angetts för den valda variabla planen är Procent.</span><span class="sxs-lookup"><span data-stu-id="f5501-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="f5501-117">Om den variabla planen är en procentsats av basplanen kan ersättningsprocenten åsidosättas för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="f5501-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="f5501-118">Om den variabla kompensationsplanen är en plan med antal enheter kan antalet enheter åsidosättas för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="f5501-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="f5501-119">Om medarbetaren ska få ett fast belopp i belöning, kan beloppet anges här.</span><span class="sxs-lookup"><span data-stu-id="f5501-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="f5501-120">Växla utökningen av avsnittet Organisationsåsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="f5501-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="f5501-121">Om hänsyn ska tas till medarbetarens resultat, resultat för olika avdelningar eller för en annan avdelning än den som har tilldelats till medarbetarens befattning kan avdelningen åsidosättas.</span><span class="sxs-lookup"><span data-stu-id="f5501-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="f5501-122">Kolumnen Procent ska uppgå till 100.</span><span class="sxs-lookup"><span data-stu-id="f5501-122">The Percent column should total 100.</span></span>  

