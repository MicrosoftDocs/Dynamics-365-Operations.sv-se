---
title: Prognoser, arbetsorder och projekt
description: Det här avsnittet innehåller information om prognoser och arbetsorderintegration med modulen Projekthantering och redovisning i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886826"
---
# <a name="forecasts-work-orders-and-projects"></a><span data-ttu-id="1d650-103">Prognoser, arbetsorder och projekt</span><span class="sxs-lookup"><span data-stu-id="1d650-103">Forecasts, work orders, and projects</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="1d650-104">I Tillgångshantering görs integrering i modulen **Projekthantering och redovisning** för att optimera kostnadskontrollen, vilket gör att användarna kan spåra kostnader för underhållsjobb av typen prognoser och arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="1d650-104">In Asset Management, integration to the **Project management and accounting** module is done to optimize cost control, allowing users to track costs on maintenance job type forecasts and work order jobs.</span></span>

<span data-ttu-id="1d650-105">Om du vill spåra underhållsjobbtypen prognoser måste två inställningar göras:</span><span class="sxs-lookup"><span data-stu-id="1d650-105">To track maintenance job type forecasts, two settings must be made:</span></span>

1. <span data-ttu-id="1d650-106">Välj ett projekt i **Tillgångshantering** > **Inställningar** > **Parametrar för tillgångshantering** >  länken **Tillgångar** > snabbfliken **Projekt** > fältet **Underhållsprognosprojekt**.</span><span class="sxs-lookup"><span data-stu-id="1d650-106">Select a project in **Asset management** > **Setup** > **Asset management parameters** > **Assets** link > **Project** FastTab > **Maintenance forecast project** field.</span></span>

2. <span data-ttu-id="1d650-107">I **Standardvärden för underhållsjobbtyp**, när du skapar en standardrad för en underhållsjobbtyp, skapas ett aktivitetsnummer automatiskt för raden (**Tillgångshantering** > **Inställningar** > **Jobb** > **Standardvärden för underhållsjobbtyp**).</span><span class="sxs-lookup"><span data-stu-id="1d650-107">In **Maintenance job type defaults**, when you create a mainteance job type default line, an activity number is automatically created for the line (**Asset management** > **Setup** > **Jobs** > **Maintenance job type defaults**).</span></span>

<span data-ttu-id="1d650-108">Underhållsjobbtypen prognoser har två syfte: du kan spåra kostnader för underhållsjobbprognoser i modulen **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="1d650-108">Maintenance job type forecasts serve two purposes: You are able to track costs on maintenance job type forecasts in the **Project management and accounting** module.</span></span> <span data-ttu-id="1d650-109">Dessutom överförs prognoser automatiskt till ett jobbprojekt för arbetsorder när du väljer en underhållsjobbtyp för ett arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="1d650-109">Furthermore, forecasts are automatically transferred to a work order job project when you select a maintenance job type on a work order job.</span></span>

<span data-ttu-id="1d650-110">Om du vill spåra kostnader för arbetsorderjobb måste du först ställa in arbetsorderprojekt.</span><span class="sxs-lookup"><span data-stu-id="1d650-110">To track costs on work order jobs, you must first set up work order projects.</span></span> <span data-ttu-id="1d650-111">Se avsnittet [Projektinställningar för arbetsorder](../setup-for-work-orders/work-order-project-setup.md) för en beskrivning av proceduren.</span><span class="sxs-lookup"><span data-stu-id="1d650-111">Refer to the [Work order project setup](../setup-for-work-orders/work-order-project-setup.md) section for a description of the procedure.</span></span>

## <a name="work-order-job-projects"></a><span data-ttu-id="1d650-112">Jobbprojekt för arbetsorder</span><span class="sxs-lookup"><span data-stu-id="1d650-112">Work order job projects</span></span>

<span data-ttu-id="1d650-113">När du skapar ett arbetsorderjobb på en arbetsorder, bestäms arbetsorderprojektet av inställningen för det överordnade projektet för arbetsorder i **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställningar**.</span><span class="sxs-lookup"><span data-stu-id="1d650-113">When you create a work order job on a work order, the work order project is determined by the setup of the parent project for work orders in **Asset management** > **Setup** > **Work orders** > **Project setup**.</span></span>

<span data-ttu-id="1d650-114">Jobbprojekt för arbetsorder skapas genom att du använder en kombination av följande information om arbetsorder:</span><span class="sxs-lookup"><span data-stu-id="1d650-114">Work order job projects are created by using a combination of the following work order information:</span></span>

- <span data-ttu-id="1d650-115">Arbetsordertypen som har valts på arbetsordern</span><span class="sxs-lookup"><span data-stu-id="1d650-115">The Work order type selected on the work order</span></span> 
- <span data-ttu-id="1d650-116">Funktionsplatsen som är relaterad till tillgången i arbetsorderjobbet</span><span class="sxs-lookup"><span data-stu-id="1d650-116">The functional location related to the asset on the work order job</span></span>
- <span data-ttu-id="1d650-117">Tillgångstypen som är relaterad till tillgången i arbetsorderjobbet</span><span class="sxs-lookup"><span data-stu-id="1d650-117">The Asset type related to the asset on the work order job</span></span>  
- <span data-ttu-id="1d650-118">Den förväntade start- och sluttiden som angetts för arbetsordern</span><span class="sxs-lookup"><span data-stu-id="1d650-118">The Expected start and end time set on the work order</span></span>  

<span data-ttu-id="1d650-119">Det är möjligt att viss information som nämns ovan inte finns på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d650-119">It is possible that not all of the information mentioned above is found on a work order.</span></span> <span data-ttu-id="1d650-120">Därför görs sökningen efter ett överordnat arbetsorderprojekt genom att använda den tillgängliga kombinationen av data och välja det projekt-ID som motsvarar arbetsorderdata.</span><span class="sxs-lookup"><span data-stu-id="1d650-120">Therefore, the search for a work order parent project is done by using the available combination of data and selecting the project ID that corresponds with work order data.</span></span>

<span data-ttu-id="1d650-121">Exempel: inställningarna av tillgångstypen "Lastbilsmotor" i bilden nedan innebär att varje arbetsorderjobb som har skapats med denna tillgångstyp blir ett delprojekt med projekt-ID "000186".</span><span class="sxs-lookup"><span data-stu-id="1d650-121">Example: In the figure below, the setup of asset type "Truck Engine" means that every work order job created with that asset type will be a sub project of Project ID "000186".</span></span>

![Figur 1](media/01-integration-to-pma.png)

<span data-ttu-id="1d650-123">Syftet med projekt-ID: t för arbetsorderjobbet och det relaterade aktivitetsnumret (**Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** > välj arbetsorder i listan > snabbfliken **Radinformation** > fältet **Projekt-ID** och fältet **Aktivitetsnummer**) är att spåra kostnader som är relaterade till arbetsorderjobbet, och tillgången som valts i arbetsorderjobbet i modulen **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="1d650-123">The purpose of the project ID on the work order job, and the related activity number (**Asset management** > **Common** > **Work orders** > **All Work orders** > select work order in list > **Line details** FastTab > **Project ID** field and **Activity number** field), is to track costs related to the work order job, and the asset selected on the work order job, in the **Project management and accounting** module.</span></span> 

<span data-ttu-id="1d650-124">I bilden nedan visas en grafisk översikt över arbetsorderprojekt och relaterade projektaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="1d650-124">In the figure below, you see a graphic overview of work order projects and related project activities.</span></span>

![Figur 2](media/02-integration-to-pma.png)

<span data-ttu-id="1d650-126">När ett nytt arbetsorderjobb skapas på en arbetsorder skapas ett arbetsorderprojekt automatiskt för jobbet.</span><span class="sxs-lookup"><span data-stu-id="1d650-126">When a new work order job is created on a work order, a work order project is automatically created for the job.</span></span> <span data-ttu-id="1d650-127">De ekonomiska dimensionerna för tillgången relaterad till arbetsorderjobbet överförs automatiskt till arbetsorderprojektet.</span><span class="sxs-lookup"><span data-stu-id="1d650-127">The financial dimensions for the asset related to the work order job are automatically transferred to the work order project.</span></span> <span data-ttu-id="1d650-128">Projektaktiviteten som har skapats för ett arbetsorderjobb har relaterad information kopplad till sig om underhållsjobbtyp, variant av underhållsjobbtyp och yrkesgren.</span><span class="sxs-lookup"><span data-stu-id="1d650-128">The project activity created for a work order job has related information attached to it regarding maintenance job type, maintenance job type variant, and trade.</span></span> <span data-ttu-id="1d650-129">Dessa data är användbara om du t.ex. skapar en inköpsorder från en arbetsorder (se [Anskaffning](../work-orders/procurement.md)), eller om du använder modulen **Projekthantering och redovisning** för tidsregistrering.</span><span class="sxs-lookup"><span data-stu-id="1d650-129">Those data are useful if, for example, you create a purchase order from a work order (see [Procurement](../work-orders/procurement.md)), or if you use the **Project management and accounting** module for time registration.</span></span>  

<span data-ttu-id="1d650-130">Om tillgången har installerats på en funktionsplats och denna tillgång senare installeras på en annan funktionsplats, uppdateras de ekonomiska dimensionerna som hör till den nya funktionsplatsen automatiskt för tillgången.</span><span class="sxs-lookup"><span data-stu-id="1d650-130">If the asset was installed on a functional location, and that asset is later installed on another functional location, the financial dimensions related to the new functional location is automatically updated on the asset.</span></span> <span data-ttu-id="1d650-131">När du sedan skapar ett arbetsorderjobb för tillgången hämtar arbetsorderprojektet för arbetsorderjobbet automatiskt de ekonomiska dimensioner som nu är relaterade till tillgången.</span><span class="sxs-lookup"><span data-stu-id="1d650-131">Subsequently, when you create a work order job for the asset, the work order project for the work order job automatically gets the financial dimensions that are now related to the asset.</span></span> <span data-ttu-id="1d650-132">Det innebär att när du använder funktionsplatser kan kostnader alltid spåras på de funktionsplatser där en tillgång installerades vid en given tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="1d650-132">This means that when you use functional locations, costs can always be tracked on the functional locations on which an asset was installed at any given time.</span></span> <span data-ttu-id="1d650-133">Den automatiska uppdateringen av ekonomiska dimensioner säkerställer en fullständig spårning av kostnaderna för projektstyrning och rapportering.</span><span class="sxs-lookup"><span data-stu-id="1d650-133">The automatic update of financial dimensions ensures complete traceability of costs for project controlling and reporting.</span></span>  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a><span data-ttu-id="1d650-134">Arbetsorderprojekt, arbetsorders livscykeltillgång, projektfaser och projekttyper</span><span class="sxs-lookup"><span data-stu-id="1d650-134">Work order projects, work order lifecycle states, project stages, and project types</span></span>

<span data-ttu-id="1d650-135">För att säkerställa korrekt användning av livscykeltillstånd för arbetsorder och relaterade projektfaser på arbetsorder måste du ta hänsyn till beroendena i relation till modulen **Projekthantering och redovisning**:</span><span class="sxs-lookup"><span data-stu-id="1d650-135">To ensure correct use of work order lifecycle states and related project stages on work orders, consider the dependencies in relation to the **Project management and accounting** module:</span></span>

- <span data-ttu-id="1d650-136">I modulen **Projekthantering och redovisning** ställs projektfaser in för projekttyper i **Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="1d650-136">In the **Project management and accounting** module, project stages are set up on project types in **Project management and accounting parameters**.</span></span>  
- <span data-ttu-id="1d650-137">I **Parametrar för projekthantering och redovisning** måste du komma ihåg att markera relevanta kryssrutor för projektfaser för alla projekttyper som du ska använda.</span><span class="sxs-lookup"><span data-stu-id="1d650-137">In **Project management and accounting parameters**, remember to select relevant project stage check boxes for all the project types you are going to use.</span></span> <span data-ttu-id="1d650-138">I bilden nedan har fem faser **Skapat** - **Uppskattat** - **Tidsplanerat** - **Pågår** - **Slutfört** valts för projekttyperna "Tid och material" och "Internt".</span><span class="sxs-lookup"><span data-stu-id="1d650-138">In the figure below, five stages **Created** - **Estimated** - **Scheduled** - **In process** - **Finished** have been selected for the project types "Time and material" and "Internal".</span></span> <span data-ttu-id="1d650-139">De fem faserna är relevanta för både interna underhållsjobb och serviceunderhållsjobb.</span><span class="sxs-lookup"><span data-stu-id="1d650-139">Those five stages are relevant for both internal maintenance and service maintenance jobs.</span></span>  
- <span data-ttu-id="1d650-140">I **Tillgångshantering** definieras projekttyper av projektgrupperna som du ställer in i formuläret **Projektinställningar för arbetsorder** > länken **Projektgrupp**.</span><span class="sxs-lookup"><span data-stu-id="1d650-140">In **Asset Management**, project types are defined by the project groups you set up in the **Work order project setup** form > **Project group** link.</span></span>  
- <span data-ttu-id="1d650-141">Projektgrupperna som ställs in i **Projektinställningar för arbetsorder** används när du skapar arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d650-141">The project groups setup in **Work order project setup** are used when you create work orders.</span></span> <span data-ttu-id="1d650-142">När en arbetsorder skapas, skapas automatiskt ett arbetsorderprojekt för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="1d650-142">When a work order is created, a work order project is automatically created for the work order.</span></span>  
- <span data-ttu-id="1d650-143">Arbetsorderns livscykeltillstånd måste ha en relaterad projektfas.</span><span class="sxs-lookup"><span data-stu-id="1d650-143">Work order lifecycle states must each have a related project stage.</span></span>  
- <span data-ttu-id="1d650-144">Projektfasen som är relaterad till en arbetsorders livscykeltillstånd måste definieras som en aktiv fas för projektgruppen som definieras i arbetsorderprojektet.</span><span class="sxs-lookup"><span data-stu-id="1d650-144">The project stage related to a work order lifecycle state must be defined as an active stage for the project group defined in the work order project.</span></span> <span data-ttu-id="1d650-145">Arbetsorderprojektet skapas automatiskt på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d650-145">The work order project is automatically created on a work order.</span></span>  
- <span data-ttu-id="1d650-146">När du skapar en ny arbetsorder baseras den automatiska allokeringen av arbetsorderprojektet på inställningen i **Projektinställningar för arbetsorder** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställningar**).</span><span class="sxs-lookup"><span data-stu-id="1d650-146">When you create a new work order, the automatic allocation of a work order project is based on the setup in **Work order project setup** (**Asset management** > **Setup** > **Work orders** > **Project setup**).</span></span>  

<span data-ttu-id="1d650-147">Kopplingar mellan projektgrupper i arbetsorder, relaterade projekttyper, projektfaser och livscykeltillstånd för arbetsorder visas i bilderna nedan.</span><span class="sxs-lookup"><span data-stu-id="1d650-147">Associations between work order project groups, related project types, project stages, and work order lifecycle states are shown in the figures below.</span></span>  

![Figur 3](media/03-integration-to-pma.png)

![Figur 4](media/04-integration-to-pma.png)

![Figur 5](media/05-integration-to-pma.png)

<span data-ttu-id="1d650-151">Se [Projektinställningar för arbetsorder](../setup-for-work-orders/work-order-project-setup.md) för att ställa in arbetsorderprojekt samt [Livscykeltillstånd för arbetsorder](../setup-for-work-orders/work-order-lifecycle-states.md) för hur du skapar livscykeltillstånd för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d650-151">Refer to [Work order project setup](../setup-for-work-orders/work-order-project-setup.md) regarding how to set up work order projects, and to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) regarding how to create work order lifecycle states.</span></span>

<span data-ttu-id="1d650-152">I bilden nedan visas en grafisk översikt över de olika projekten som skapas i modulen **Tillgångshantering** för att möjliggöra integration med modulen **Projekthantering och redovisning**, samt de arbetsprocesser som projekten är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="1d650-152">The figure below shows a graphic overview of the various projects that are created in the **Asset management** module to allow integration with the **Project management and accounting** module, as well as the work processes to which the projects are related.</span></span>

![Figur 6](media/06-integration-to-pma.png)

