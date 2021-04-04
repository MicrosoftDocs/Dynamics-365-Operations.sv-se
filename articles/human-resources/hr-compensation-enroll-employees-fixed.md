---
title: Registrera en medarbetare i en fast kompensationsplan
description: Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a129bf9a6cb6a3ef92597e2ff9d126e3e5ce973b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468261"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="df663-103">Registrera en medarbetare i en fast kompensationsplan</span><span class="sxs-lookup"><span data-stu-id="df663-103">Enroll an employee in a fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="df663-104">Chefen över kompensationer och förmåner kan tilldela medarbetare till fasta kompensationsplaner för att hantera deras grundlön.</span><span class="sxs-lookup"><span data-stu-id="df663-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="df663-105">I den här proceduren förutsätts att en fast plan har skapats och är aktiv, och att berättiganderegler har angetts för planen.</span><span class="sxs-lookup"><span data-stu-id="df663-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="df663-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="df663-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="df663-107">Gå till Personal > Arbetare > Medarbetare > Kompensation > Fast plan för att starta proceduren</span><span class="sxs-lookup"><span data-stu-id="df663-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="df663-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="df663-108">Click New.</span></span>
2. <span data-ttu-id="df663-109">Välj en åtgärd för fast kompensation av typen Anställ/återanställ för att beskriva ändringen av en medarbetares kompensation.</span><span class="sxs-lookup"><span data-stu-id="df663-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="df663-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="df663-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="df663-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Befattning.</span><span class="sxs-lookup"><span data-stu-id="df663-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="df663-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="df663-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="df663-113">Nivån som visas kommer från kompensationsnivån för jobbet på befattningen.</span><span class="sxs-lookup"><span data-stu-id="df663-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="df663-114">Nivån måste anges för jobbet innan kompensation kan tilldelas till medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="df663-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="df663-115">Välj den fasta kompensationsplanen för medarbetaren i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="df663-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="df663-116">Planuppslagningen filtreras för att visa endast de planer som medarbetaren är berättigad till baserat på berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="df663-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="df663-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="df663-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="df663-118">Giltighetsdatum och utgångsdatum för kompensationen hämtas som standard från start- och slutdatum för arbetarens befattningstilldelning.</span><span class="sxs-lookup"><span data-stu-id="df663-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="df663-119">Du kan justera dessa datum efter behov.</span><span class="sxs-lookup"><span data-stu-id="df663-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="df663-120">Om den fasta kompensationsplanen är en stegplan, väljer du det steg som innehåller korrekt lönesats för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="df663-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="df663-121">Om den fasta kompensationsplanen är en gradplan eller bandplan, anger du lönesatsen för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="df663-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="df663-122">Lönesatsen ska valideras mot toleransinställningarna för planen, och de lägsta och högsta referenspunkterna för jobbets kompensationsnivå.</span><span class="sxs-lookup"><span data-stu-id="df663-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="df663-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="df663-123">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]