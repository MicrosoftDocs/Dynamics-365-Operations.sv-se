---
title: Registrera en medarbetare i en fast kompensationsplan
description: Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 843db6bc133382a701d4b25b164794e57df152c7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010674"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="e0cf8-103">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="e0cf8-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="e0cf8-104">Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="e0cf8-105">I den här proceduren förutsätts att en fast plan har skapats och är aktiv, och att berättiganderegler har angetts för planen.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="e0cf8-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e0cf8-107">Gå till Personal > Arbetare > Medarbetare > Kompensation > Fast plan för att starta proceduren</span><span class="sxs-lookup"><span data-stu-id="e0cf8-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="e0cf8-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-108">Click New.</span></span>
2. <span data-ttu-id="e0cf8-109">Välj en åtgärd för fast kompensation av typen Anställ/återanställ för att beskriva ändringen av en medarbetares kompensation.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="e0cf8-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e0cf8-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Befattning.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e0cf8-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e0cf8-113">Nivån som visas kommer från kompensationsnivån för jobbet på befattningen.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="e0cf8-114">Nivån måste anges för jobbet innan kompensation kan tilldelas till medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="e0cf8-115">Välj den fasta kompensationsplanen för medarbetaren i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="e0cf8-116">Planuppslagningen filtreras för att visa endast de planer som medarbetaren är berättigad till baserat på berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="e0cf8-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e0cf8-118">Giltighetsdatum och utgångsdatum för kompensationen hämtas som standard från start- och slutdatum för arbetarens befattningstilldelning.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="e0cf8-119">Du kan justera dessa datum efter behov.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="e0cf8-120">Om den fasta kompensationsplanen är en stegplan, väljer du det steg som innehåller korrekt lönesats för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="e0cf8-121">Om den fasta kompensationsplanen är en gradplan eller bandplan, anger du lönesatsen för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="e0cf8-122">Lönesatsen ska valideras mot toleransinställningarna för planen, och de lägsta och högsta referenspunkterna för jobbets kompensationsnivå.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="e0cf8-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0cf8-123">Click OK.</span></span>

