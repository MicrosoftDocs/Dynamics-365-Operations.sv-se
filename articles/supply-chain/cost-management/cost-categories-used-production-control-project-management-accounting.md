---
title: Kostnadskategorier som används i produktionskontroll och projekthanteringsredovisning
description: Vissa typer av produktionsarbete kan gälla för projekttidsuppskattningar och rapportering. Den här artikeln innehåller information om de kostnadskategorier som du måste definiera för dessa typer av produktionsarbete för produktions- och projektändamål.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 59bf9c165af83aeb66586adc2d2bfc1bb5068601
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967868"
---
# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="66f97-104">Kostnadskategorier som används i produktionskontroll och projekthanteringsredovisning</span><span class="sxs-lookup"><span data-stu-id="66f97-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66f97-105">Vissa typer av produktionsarbete kan gälla för projekttidsuppskattningar och rapportering.</span><span class="sxs-lookup"><span data-stu-id="66f97-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="66f97-106">Den här artikeln innehåller information om de kostnadskategorier som du måste definiera för dessa typer av produktionsarbete för produktions- och projektändamål.</span><span class="sxs-lookup"><span data-stu-id="66f97-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="66f97-107">Vissa typer av produktionsarbete kan gälla för projekttidsuppskattningar och rapportering.</span><span class="sxs-lookup"><span data-stu-id="66f97-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="66f97-108">I det här fallet krävs en kostnadskategori för produktions- och projektandamål.</span><span class="sxs-lookup"><span data-stu-id="66f97-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="66f97-109">Mer projektrelaterad information måste definieras när en kostnadskategori används för produktion och projekt.</span><span class="sxs-lookup"><span data-stu-id="66f97-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="66f97-110">Timkostnaderna som är kopplade till projekt, skiljer sig t.ex. från timkostnaderna som är kopplade till produktion.</span><span class="sxs-lookup"><span data-stu-id="66f97-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="66f97-111">På **Kostnadskategorier**-sidan kan du definiera en kostnadskategori som används i redovisningen för produktionskontroll och projekthantering.</span><span class="sxs-lookup"><span data-stu-id="66f97-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="66f97-112">**Obs!** Kostnadsredovisning har en **Projektkategorier**-sida, men den här sidan har ingen koppling till funktionerna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="66f97-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="66f97-113">När du använder en kostnadskategori i projekt, sidan **Kostnadskategorier** har ytterligare flikar som visar ytterligare projektrelaterad information.</span><span class="sxs-lookup"><span data-stu-id="66f97-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="66f97-114">Den här informationen omfattar kategorigrupp, en radegenskap och huvudbokskonton som har tilldelats kostnadskategorin.</span><span class="sxs-lookup"><span data-stu-id="66f97-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="66f97-115">Kostnadskategorin måste tilldelas en kategorigrupp som stöder transaktionstypen **Timmar**.</span><span class="sxs-lookup"><span data-stu-id="66f97-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="66f97-116">Radegenskapen anger standardinformation för hur rapporterad tid kan debiteras för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="66f97-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="66f97-117">Vanligtvis definieras huvudbokskontona, som rör kostnader och försäljning, för kategorigruppen som har tilldelats kostnadskategorin.</span><span class="sxs-lookup"><span data-stu-id="66f97-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="66f97-118">Du kan dock definiera specifika konton för en enskild kostnadskategori.</span><span class="sxs-lookup"><span data-stu-id="66f97-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="66f97-119">Ytterligare knappar på **Kostnadskategorier**-sidan kan ge dig åtkomst till projektrelaterad information om en vald kostnadskategori.</span><span class="sxs-lookup"><span data-stu-id="66f97-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="66f97-120">Du kan till exempel visa projektrelaterade transaktioner, definiera medarbetare eller projekt, definiera timkostnader och försäljningspriser och visa rapporter.</span><span class="sxs-lookup"><span data-stu-id="66f97-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>



