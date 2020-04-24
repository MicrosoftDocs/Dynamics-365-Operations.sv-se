---
title: Projektförsäljningsorder för tid- och materialprojekt
description: Det här avsnittet beskriver hur du skapar projektbaserade försäljningsorder för tids- och materialprojekt.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249103"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="e8366-103">Projektförsäljningsorder för tid- och materialprojekt</span><span class="sxs-lookup"><span data-stu-id="e8366-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e8366-104">I det här avsnittet beskriver hur du skapar en försäljningsorder för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="e8366-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="e8366-105">Försäljningsorder kan endast skapas för projekt av typen **tid och material**.</span><span class="sxs-lookup"><span data-stu-id="e8366-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="e8366-106">Om ett tids- och materialprojekt har flera finansieringskällor för projektkontraktet, måste du aktivera parametern **Tillåt försäljningsorder för projekt som har flera finansieringskällor** på sidan **Projekthantering och redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="e8366-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="e8366-107">Stöd för projektförsäljningsorder med flera finansieringskällor är tillgänglig från och med programutgåva 10.0.2 och högre.</span><span class="sxs-lookup"><span data-stu-id="e8366-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="e8366-108">Parametern för att aktivera stöd för projektförsäljningsorder med flera finansieringskällor tas bort i versionen april 2020 och sedn är funktionen alltid aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e8366-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="e8366-109">Du kan skapa projektbaserade försäljningsorder på två sätt:</span><span class="sxs-lookup"><span data-stu-id="e8366-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="e8366-110">Gå till själva projektet.</span><span class="sxs-lookup"><span data-stu-id="e8366-110">Go to the project itself.</span></span> <span data-ttu-id="e8366-111">I åtgärdsfönstret, välj **Hantera > artikeluppgifter > försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="e8366-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="e8366-112">Projektinformationen används som standard till försäljningsordern från projektet.</span><span class="sxs-lookup"><span data-stu-id="e8366-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="e8366-113">Projektkontraktet har mer än en finansieringskälla, du behöver välja finansieringskälla för att ange kunden för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="e8366-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="e8366-114">Om det bara finns en finansieringskälla för projektet, anges kunden automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e8366-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="e8366-115">Gå till listsidan **Alla försäljningsorder** och skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="e8366-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="e8366-116">Du måste välja projektet för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="e8366-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="e8366-117">När projektet väljs anges kunden från finansieringskällan eller så behöver du välja finansieringskälla om projektkontraktet som har flera finansieringskällor.</span><span class="sxs-lookup"><span data-stu-id="e8366-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

