---
title: "Synkronisera projektkontrakt från Project Service Automation direkt till projektkontrakt i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektprojektkontrakt och projekt direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 8d8e3268ae8c612bad87c3c6416f223219149ee6
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-contracts-and-projects-from-project-service-automation-directly-to-project-contracts-and-projects-in-finance-and-operations"></a><span data-ttu-id="7ae3c-103">Synkronisera projektkontrakt och projekt från Project Service Automation direkt till projektkontrakt och projekt i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7ae3c-103">Synchronize project contracts and projects from Project Service Automation directly to project contracts and projects in Finance and Operations</span></span>

<span data-ttu-id="7ae3c-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektprojektkontrakt och projekt direkt från Microsoft Dynamics 365 for Project Service Automation till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-104">This topic describes the template and underlying tasks that are used to synchronize project contracts and projects directly from Microsoft Dynamics 365 for Project Service Automation to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="7ae3c-105">Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, 7.3.0, måste du installera KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-105">If you are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="7ae3c-106">Dataflöde för Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7ae3c-106">Data flow for Project Service Automation to Finance and Operations</span></span>

> [!NOTE]
> <span data-ttu-id="7ae3c-107">Innan du kan använda integrationslösningen Project Service Automation till Finance and Operations bör du känna till Dynamics 365 dataintegrationsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-107">Before you can use the Project Service Automation to Finance and Operations integration solution, you should be familiar with the Dynamics 365 Data integration feature.</span></span>

<span data-ttu-id="7ae3c-108">Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-108">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="7ae3c-109">Integrationsmallen som är tillgänglig med dataintegrationsfunktionen tillåter flöde av data om projektkontrakt, projekt, projektkontraktsrader och projektkontraktraders milstolpar från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-109">The integration template that is available with the Data integration feature enables the flow of data about project contracts, projects, project contract lines, and project contract line milestones from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="7ae3c-110">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="7ae3c-111">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-111">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7ae3c-112">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="7ae3c-112">Templates and tasks</span></span>

<span data-ttu-id="7ae3c-113">För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-113">To access the available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7ae3c-114">Följande mall och underliggande uppgift används för att synkronisera projektkontrakt och proojekt från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="7ae3c-114">The following template and underlying tasks are used to synchronize project contracts and projects from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="7ae3c-115">**Namnet på mallen i dataintegrering:** projektet och kontrakt (PSA till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-115">**Name of the template in Data integration:** Projects and contracts (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7ae3c-116">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="7ae3c-116">**Name of the tasks in the project:**</span></span>

  - <span data-ttu-id="7ae3c-117">Projektkontrakt PSA till Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="7ae3c-117">Project contracts PSA to Fin and Ops</span></span>
  - <span data-ttu-id="7ae3c-118">Projekt PSA till Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="7ae3c-118">Projects PSA to Fin and Ops</span></span>
  - <span data-ttu-id="7ae3c-119">Projektkontraktrader PSA till Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="7ae3c-119">Project contract lines PSA to Fin and Ops</span></span>
  - <span data-ttu-id="7ae3c-120">Projektkontraktraders milstolpar PSA till Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="7ae3c-120">Project contract line milestones PSA to Fin and Ops</span></span>

<span data-ttu-id="7ae3c-121">Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-121">Before synchronization of project contracts and projects can occur, you must synchronize accounts.</span></span>

## <a name="entity-set"></a><span data-ttu-id="7ae3c-122">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="7ae3c-122">Entity set</span></span>

| <span data-ttu-id="7ae3c-123">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7ae3c-123">Project Service Automation</span></span>       | <span data-ttu-id="7ae3c-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7ae3c-124">Finance and Operations</span></span>                                 |
|----------------------------------|--------------------------------------------------------|
| <span data-ttu-id="7ae3c-125">Order</span><span class="sxs-lookup"><span data-stu-id="7ae3c-125">Orders</span></span>                           | <span data-ttu-id="7ae3c-126">Integrationsenhet för projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-126">Integration entity for project contract.</span></span>                |
| <span data-ttu-id="7ae3c-127">Projekt</span><span class="sxs-lookup"><span data-stu-id="7ae3c-127">Projects</span></span>                         | <span data-ttu-id="7ae3c-128">Integrationsenhet för projekt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-128">Integration entity for project.</span></span>                         |
| <span data-ttu-id="7ae3c-129">Orderrader</span><span class="sxs-lookup"><span data-stu-id="7ae3c-129">Order lines</span></span>                      | <span data-ttu-id="7ae3c-130">Integrationsenhet för projektkontraktsrad.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-130">Integration entity for project contract line.</span></span>          |
| <span data-ttu-id="7ae3c-131">Milstolpar för projektkontraktsrad</span><span class="sxs-lookup"><span data-stu-id="7ae3c-131">Project contract line milestones</span></span> | <span data-ttu-id="7ae3c-132">Integrationsenhet för milstolpar för projektkontraktsrad</span><span class="sxs-lookup"><span data-stu-id="7ae3c-132">Integration entity for project contract line milestone.</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="7ae3c-133">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="7ae3c-133">Entity flow</span></span>

<span data-ttu-id="7ae3c-134">Projektkontrakt hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-134">Project contracts are managed in Project Service Automation, and they are synchronized to Finance and Operations as project contracts.</span></span> <span data-ttu-id="7ae3c-135">Du kan ange integrationsmallen som del av integrationskällan i Finance and Operations för projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-135">As part of the integration template, you can set the integration source in Finance and Operations for the project contract.</span></span>

<span data-ttu-id="7ae3c-136">Tids- och material- och fastprisprojekt hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projekt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-136">Time and material and fixed price projects are managed in Project Service Automation, and they are synchronized to Finance and Operations as projects.</span></span> <span data-ttu-id="7ae3c-137">Du kan ange integrationsmallen som del av integrationskällan i Finance and Operations för projektet.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-137">As part of the template integration, you can set the integration source in Finance and Operations for the project.</span></span>

<span data-ttu-id="7ae3c-138">Projektkontraktrader hanteras i Project Service Automation och de synkroniseras till Finance and Operations som faktureringsregler för projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-138">Project contract lines are managed in Project Service Automation, and they are synchronized to Finance and Operations as project contract billing rules.</span></span> <span data-ttu-id="7ae3c-139">Synkroniseringen uppdaterar projekttypen för kontraktradprojekt och projektgrupp om faktureringsmetoden är annorlunda än standardprojekttypen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-139">The synchronization will update the project type for the contract line project and project group if the billing method is different than the default project type.</span></span>

<span data-ttu-id="7ae3c-140">Milstolpar för projektkontraktsrad hanteras i Project Service Automation och de synkroniseras till Finance and Operations som milstolpar för faktureringsregler för projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-140">Project contract line milestones are managed in Project Service Automation, and they are synchronized to Finance and Operations as project contract billing rule milestones.</span></span>

## <a name="project-service-automation-to-finance-and-operations-integration-solution"></a><span data-ttu-id="7ae3c-141">Integegrationslösning för Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7ae3c-141">Project Service Automation to Finance and Operations integration solution</span></span>

<span data-ttu-id="7ae3c-142">Fältet **projektkontrakt-ID** är tillgängligt på sidan **projektkontrakt**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-142">The **Project contract ID** field is available on the **Project contracts** page.</span></span> <span data-ttu-id="7ae3c-143">Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-143">This field has been made a natural and unique key to support the integration.</span></span>

<span data-ttu-id="7ae3c-144">När ett nytt projektkontrakt skapas om ett **Projektkontrakt-ID**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-144">When a new project contract is created, if a **Project contract ID** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="7ae3c-145">Värdet består av **ORD** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-145">The value consists of **ORD** followed by an incrementing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="7ae3c-146">Här är ett exempel: **ORD-01022-Z4M9Q0**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-146">Here is an example: **ORD-01022-Z4M9Q0**.</span></span>

<span data-ttu-id="7ae3c-147">Fältet **Projektnummer** är tillgängligt på sidan **projekt**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-147">The **Project Number** field is available on the **Projects** page.</span></span> <span data-ttu-id="7ae3c-148">Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-148">This field has been made a natural and unique key to support the integration.</span></span>

<span data-ttu-id="7ae3c-149">När ett nytt projekt skapas om ett **projektnummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-149">When a new project is created, if a **Project Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="7ae3c-150">Värdet består av **PRJ** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-150">The value consists of **PRJ** followed by an incrementing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="7ae3c-151">Här är ett exempel: **PRJ-01049-CCNID0**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-151">Here is an example: **PRJ-01049-CCNID0**.</span></span>

<span data-ttu-id="7ae3c-152">När integrationslösningen för Project Service Automation till Finance and Operations tillämpas<TO DO: link in the top level document link where we will be adding the instructions for applying the PSA solution>, anger ett uppgraderingsskript fältet **projektkontrakt-ID** för befintliga projektkontrakt och **projektnummer** för befintliga projekt i Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-152">When the Project Service Automation to Finance and Operations integration solution is applied<TO DO: link in the top level document link where we will be adding the instructions for applying the PSA solution>, an upgrade script sets the **Project contract ID** field for existing project contracts and the **Project Number** field for existing projects in Project Service Automation.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="7ae3c-153">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="7ae3c-153">Prerequisites and mapping setup</span></span>

- <span data-ttu-id="7ae3c-154">Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-154">Before synchronization of project contracts and projects can occur, you must synchronize accounts.</span></span>
- <span data-ttu-id="7ae3c-155">I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_organizationalunits** till **msdyn\_namn \[Namn\]**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-155">In your connection set, add an integration key field mapping for **msdyn\_organizationalunits** to **msdyn\_name \[Name\]**.</span></span> <span data-ttu-id="7ae3c-156">Du kanske först måste lägga till ett projekt i anslutningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-156">You might first have to add a project to the connection set.</span></span> <span data-ttu-id="7ae3c-157">Mer information om integreringsnycklar finns i Dynamics 365 dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-157">For more information about integration keys, see Dynamics 365 Data integration.</span></span>
- <span data-ttu-id="7ae3c-158">I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_projekt** till **msdynce\_projektnummer \[Projektnummer\]**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-158">In your connection set, add an integration key field mapping for **msdyn\_projects** to **msdynce\_projectnumber \[Project Number\]**.</span></span> <span data-ttu-id="7ae3c-159">Du kanske först måste lägga till ett projekt i anslutningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-159">You might first have to add a project to the connection set.</span></span> <span data-ttu-id="7ae3c-160">Mer information om integreringsnycklar finns i Dynamics 365 dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-160">For more information about integration keys, see Dynamics 365 Data integration.</span></span>
- <span data-ttu-id="7ae3c-161">**SourceDataID** för projektkontrakt och projekt kan uppdateras till ett annat värde eller tas bort från mappningen.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-161">**SourceDataID** for project contracts and projects can be updated to a different value or removed from the mapping.</span></span> <span data-ttu-id="7ae3c-162">Standardmallvärdet är **Project Service Automation**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-162">The default template value is **Project Service Automation**.</span></span>
- <span data-ttu-id="7ae3c-163">Mappningen **PaymentTerms** måste uppdateras så att den motsvarar giltiga betalningsvillkor i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-163">The **PaymentTerms** mapping must be updated so that it reflects valid terms of payment in Finance and Operations.</span></span> <span data-ttu-id="7ae3c-164">Du kan också ta bort mappningen från projektuppgiften.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-164">You can also remove the mapping from the project task.</span></span> <span data-ttu-id="7ae3c-165">Den standardinställda värdemappningen har standardvärden för demodata.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-165">The default value map has default values for demo data.</span></span> <span data-ttu-id="7ae3c-166">Tabellen nedan visar värdena i Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-166">The following table shows the values in Project Service Automation.</span></span>

    | <span data-ttu-id="7ae3c-167">Värde</span><span class="sxs-lookup"><span data-stu-id="7ae3c-167">Value</span></span> | <span data-ttu-id="7ae3c-168">beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ae3c-168">Description</span></span>   |
    |-------|---------------|
    | <span data-ttu-id="7ae3c-169">1</span><span class="sxs-lookup"><span data-stu-id="7ae3c-169">1</span></span>     | <span data-ttu-id="7ae3c-170">Netto 30</span><span class="sxs-lookup"><span data-stu-id="7ae3c-170">Net 30</span></span>        |
    | <span data-ttu-id="7ae3c-171">2</span><span class="sxs-lookup"><span data-stu-id="7ae3c-171">2</span></span>     | <span data-ttu-id="7ae3c-172">2%10, Netto 30</span><span class="sxs-lookup"><span data-stu-id="7ae3c-172">2% 10, Net 30</span></span> |
    | <span data-ttu-id="7ae3c-173">3</span><span class="sxs-lookup"><span data-stu-id="7ae3c-173">3</span></span>     | <span data-ttu-id="7ae3c-174">Netto 45</span><span class="sxs-lookup"><span data-stu-id="7ae3c-174">Net 45</span></span>        |
    | <span data-ttu-id="7ae3c-175">4</span><span class="sxs-lookup"><span data-stu-id="7ae3c-175">4</span></span>     | <span data-ttu-id="7ae3c-176">Netto 60</span><span class="sxs-lookup"><span data-stu-id="7ae3c-176">Net 60</span></span>        |

## <a name="power-query"></a><span data-ttu-id="7ae3c-177">Power Query</span><span class="sxs-lookup"><span data-stu-id="7ae3c-177">Power Query</span></span>
<span data-ttu-id="7ae3c-178">Du måste använda  Microsoft Power Query för att filtrera data om följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="7ae3c-178">You must use Microsoft Power Query to filter data if the following conditions are met:</span></span>

- <span data-ttu-id="7ae3c-179">Det finns försäljningsorder i Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-179">You have sales orders in Microsoft Dynamics 365 for Sales.</span></span>
- <span data-ttu-id="7ae3c-180">Det finns flera organisationsenheter i Project Service Automation och organisationsenheterna mappas till flera juridiska personer i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-180">You have multiple organizational units in Project Service Automation, and these organizational units will be mapped to multiple legal entities in Finance and Operations.</span></span>

<span data-ttu-id="7ae3c-181">Om du måste använda Power Query enligt riktlinjerna nedan:</span><span class="sxs-lookup"><span data-stu-id="7ae3c-181">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="7ae3c-182">Mallen för projektkontraktet (PSA till Fin and Ops) har ett standardfilter som endast inkluderar försäljningsorder **arbetsuppgift (msdyn\_ordertype = 192350001)**.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-182">The Project contracts (PSA to Fin and Ops) template has a default filter that includes only sales orders of the **Work item (msdyn\_ordertype = 192350001)** type.</span></span> <span data-ttu-id="7ae3c-183">Det här filtret så att projektkontrakt inte skapas för försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-183">This filter ensures that project contracts aren't created for sales orders in Finance and Operations.</span></span> <span data-ttu-id="7ae3c-184">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-184">If you create your own template, you must add this filter.</span></span>
- <span data-ttu-id="7ae3c-185">Du måste skapa ett Power Query-filtret som endast inkluderar kontraktorganisationer som ska synkroniseras mot den juridiska personen av integrationens anslutningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-185">You must create a Power Query filter that includes only the contract organizations that should be synchronized to the legal entity of the integration connection set.</span></span> <span data-ttu-id="7ae3c-186">T.ex. ska projektkontrakt som du har med kontraktorganisationsenheten för Contoso US ska synkroniseras mot den juridiska personen USSI, men projektkontraktet som du har med kontraktorganisationsenhet för Contoso Global ska synkroniseras mot den juridiska personen för USMF.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-186">For example, project contracts that you have with the contract organizational unit of Contoso US should be synchronized to the USSI legal entity, but project contracts that you have with the contract organizational unit of Contoso Global should be synchronized to the USMF legal entity.</span></span> <span data-ttu-id="7ae3c-187">Om du inte lägger till det här filtret i din uppgiftsmappning kommer alla projektkontrakt att synkroniseras till den juridiska personen som har definierats för anslutningen, oavsett kontraktorganisationsenhet.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-187">If you don't add this filter to your task mapping, all project contracts will be synchronized to the legal entity that is defined for the connection set,  regardless of the contract organizational unit.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7ae3c-188">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="7ae3c-188">Template mapping in Data integration</span></span>

> [!NOTE] 
> <span data-ttu-id="7ae3c-189">Fälten **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** och **AddressZipCode** ingår inte i standardmappningen för projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-189">The **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState**, and **AddressZipCode** fields aren't included in the default mapping for project contracts.</span></span> <span data-ttu-id="7ae3c-190">Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-190">You can add the mappings if you require that this data be synchronized for project contracts.</span></span>
> <span data-ttu-id="7ae3c-191">Fälten **beskrivning**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, och **ProjectType** ingår inte i standardmappning för projekt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-191">The **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, and **ProjectType** fields aren't included in the default mapping for projects.</span></span> <span data-ttu-id="7ae3c-192">Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projekt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-192">You can add the mappings if you require that this data be synchronized for projects.</span></span>

<span data-ttu-id="7ae3c-193">I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-193">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="7ae3c-194">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-194">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="7ae3c-195">[![Mallmappning](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-195">[![Template mapping](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)</span></span>

<span data-ttu-id="7ae3c-196">[![Mallmappning](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-196">[![Template mapping](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)</span></span>

<span data-ttu-id="7ae3c-197">[![Mallmappning](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-197">[![Template mapping](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)</span></span>

<span data-ttu-id="7ae3c-198">[![Mallmappning](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)</span><span class="sxs-lookup"><span data-stu-id="7ae3c-198">[![Template mapping](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)</span></span>
