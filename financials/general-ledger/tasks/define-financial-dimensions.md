--- 
title: Definiera ekonomiska dimensioner
description: "Den här uppgiften vägleder dig genom stegen för att skapa en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0b72acf763f0f6dbc64c3e00986bc9eb0e366bb5
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="define-financial-dimensions"></a><span data-ttu-id="ad98d-103">Definiera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="ad98d-103">Define financial dimensions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ad98d-104">Den här uppgiften vägleder dig genom stegen för att skapa en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="ad98d-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="ad98d-105">Guiden använder demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ad98d-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="ad98d-106">Skapa en enhetsbaserad ekonomisk dimension</span><span class="sxs-lookup"><span data-stu-id="ad98d-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="ad98d-107">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="ad98d-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="ad98d-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ad98d-108">Click New.</span></span>
3. <span data-ttu-id="ad98d-109">Välj en systemdefinierad enhet som den ekonomiska dimensionen ska baseras på i fältet Användarvärden från.</span><span class="sxs-lookup"><span data-stu-id="ad98d-109">In the User values from field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="ad98d-110">Skriv ett värde som beskriver den ekonomiska dimensionen i fältet Dimensionsnamn.</span><span class="sxs-lookup"><span data-stu-id="ad98d-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="ad98d-111">Namnet kan vara ett annat än den systemdefinierade entiteten men får inte innehålla blanksteg eller specialtecken.</span><span class="sxs-lookup"><span data-stu-id="ad98d-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="ad98d-112">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ad98d-112">Click Activate.</span></span>
    * <span data-ttu-id="ad98d-113">Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort.</span><span class="sxs-lookup"><span data-stu-id="ad98d-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="ad98d-114">Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="ad98d-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="ad98d-115">Klicka på Stäng i aktiveringsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ad98d-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="ad98d-116">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ad98d-116">Click Activate.</span></span>
    * <span data-ttu-id="ad98d-117">Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.</span><span class="sxs-lookup"><span data-stu-id="ad98d-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="ad98d-118">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="ad98d-118">Click Dimension values.</span></span>
    * <span data-ttu-id="ad98d-119">Vissa dimensionsvärden är företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="ad98d-119">Some dimension values are company specific.</span></span> <span data-ttu-id="ad98d-120">Du kan kontrollera om de är företagsspecifika genom att se efter om företagsnamnet visas i dimensionsvärdelistan.</span><span class="sxs-lookup"><span data-stu-id="ad98d-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="ad98d-121">Skapa en anpassad ekonomisk dimension</span><span class="sxs-lookup"><span data-stu-id="ad98d-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="ad98d-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ad98d-122">Close the page.</span></span>
2. <span data-ttu-id="ad98d-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ad98d-123">Click New.</span></span>
3. <span data-ttu-id="ad98d-124">Välj <Custom dimension> ett alternativ i fältet Använd värden från.</span><span class="sxs-lookup"><span data-stu-id="ad98d-124">In the Use values from field, select <Custom dimension>.</span></span>
4. <span data-ttu-id="ad98d-125">Skriv ett värde som beskriver den ekonomiska dimensionen i fältet Dimensionsnamn.</span><span class="sxs-lookup"><span data-stu-id="ad98d-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="ad98d-126">Namnet kan inte innehålla blanksteg eller specialtecken.</span><span class="sxs-lookup"><span data-stu-id="ad98d-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="ad98d-127">Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="ad98d-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="ad98d-128">Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck.</span><span class="sxs-lookup"><span data-stu-id="ad98d-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="ad98d-129">Du kan även ange nummertecken (#.) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång som dimensionsvärdet skapas.</span><span class="sxs-lookup"><span data-stu-id="ad98d-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="ad98d-130">Använd ett nummertecken (#.) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav.</span><span class="sxs-lookup"><span data-stu-id="ad98d-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="ad98d-131">Exempel: Om du vill begränsa dimensionsvärdet till bokstäverna CC och tre siffror anger du CC-### i formatmasken.</span><span class="sxs-lookup"><span data-stu-id="ad98d-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="ad98d-132">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ad98d-132">Click Activate.</span></span>
    * <span data-ttu-id="ad98d-133">Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort.</span><span class="sxs-lookup"><span data-stu-id="ad98d-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="ad98d-134">Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="ad98d-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="ad98d-135">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ad98d-135">Click Activate.</span></span>
    * <span data-ttu-id="ad98d-136">Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.</span><span class="sxs-lookup"><span data-stu-id="ad98d-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="ad98d-137">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="ad98d-137">Click Dimension values.</span></span>
8. <span data-ttu-id="ad98d-138">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ad98d-138">Click New.</span></span>
9. <span data-ttu-id="ad98d-139">Skriv ett namn som beskriver det ekonomiska dimensionsvärdet i fältet Dimensionsvärde.</span><span class="sxs-lookup"><span data-stu-id="ad98d-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="ad98d-140">Skriv en beskrivning som beskriver den ekonomiska dimensionens värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ad98d-140">In the Description field, type a description that describes your financial dimension value.</span></span>


