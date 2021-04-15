---
title: Skapa dokument som omfattar programdata
description: 'Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Generera dokument med uppdatering av programdata (Del 4: Ändra format)".'
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2591f5b32417dd7517f76fc237d2337af64b3f61
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745045"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="db533-103">Skapa dokument som omfattar programdata</span><span class="sxs-lookup"><span data-stu-id="db533-103">Generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db533-104">Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Generera dokument med uppdatering av programdata (Del 4: Ändra format)".</span><span class="sxs-lookup"><span data-stu-id="db533-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 4: Modify format)".</span></span>



<span data-ttu-id="db533-105">Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="db533-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="db533-106">I den här proceduren ska du köra ER-formatkonfigurationen för att generera Intrastat-rapporten och uppdatera programdata för arkivering av information om rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="db533-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="db533-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="db533-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="db533-108">Stegen kan utföras med hjälp av datauppsättningen DEMF.</span><span class="sxs-lookup"><span data-stu-id="db533-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="db533-109">Innan du börjar ska du se till att landet för företaget DEMF är BEL (Belgien).</span><span class="sxs-lookup"><span data-stu-id="db533-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="db533-110">Konfigurera utländska handelsparametrar</span><span class="sxs-lookup"><span data-stu-id="db533-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="db533-111">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="db533-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="db533-112">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="db533-112">Click the Number sequences tab.</span></span>

    <span data-ttu-id="db533-113">För att kunna arkivera information om Intrastat-rapporteringen måste vi identifiera poster för varje arkiv vi skapar.</span><span class="sxs-lookup"><span data-stu-id="db533-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="db533-114">För detta måste en särskild nummerserie konfigureras.</span><span class="sxs-lookup"><span data-stu-id="db533-114">A special number sequence must be configured for that.</span></span>  

3. <span data-ttu-id="db533-115">Välj referensen Arkiv-ID - Intrastat.</span><span class="sxs-lookup"><span data-stu-id="db533-115">Select the 'Intrastat archive ID' reference.</span></span>
4. <span data-ttu-id="db533-116">Skriv ett värde i fältet Nummerseriekod.</span><span class="sxs-lookup"><span data-stu-id="db533-116">In the Number sequence code field, type a value.</span></span>

    <span data-ttu-id="db533-117">Ange eller välj värdet Fore_2 i fältet Nummerseriekod.</span><span class="sxs-lookup"><span data-stu-id="db533-117">In the 'Number sequence code' field, enter or select the value 'Fore_2'.</span></span>  

5. <span data-ttu-id="db533-118">ResolveChanges nummerseriekoden.</span><span class="sxs-lookup"><span data-stu-id="db533-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="db533-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="db533-119">Click Save.</span></span>
7. <span data-ttu-id="db533-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db533-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="db533-121">Kör det ändrade ER-formatet</span><span class="sxs-lookup"><span data-stu-id="db533-121">Run modified ER format</span></span>
1. <span data-ttu-id="db533-122">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="db533-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="db533-123">Expandera Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="db533-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="db533-124">Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.</span><span class="sxs-lookup"><span data-stu-id="db533-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="db533-125">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="db533-125">Click Run.</span></span>
5. <span data-ttu-id="db533-126">Skriv "intrastat2.xml" i fältet Ange filnamn.</span><span class="sxs-lookup"><span data-stu-id="db533-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
6. <span data-ttu-id="db533-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="db533-127">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="db533-128">Granska resultatet från körningen av ER-formatet</span><span class="sxs-lookup"><span data-stu-id="db533-128">Review ER format execution's results</span></span>
<span data-ttu-id="db533-129">Granska den skapade XML-filen.</span><span class="sxs-lookup"><span data-stu-id="db533-129">Review the generated XML file.</span></span>  
1. <span data-ttu-id="db533-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db533-130">Close the page.</span></span>
2. <span data-ttu-id="db533-131">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="db533-131">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>

    <span data-ttu-id="db533-132">Öppna detta formulär som innehåller Intrastat-transaktionerna som har inkluderats i det genererade elektroniska dokumentet.</span><span class="sxs-lookup"><span data-stu-id="db533-132">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  

3. <span data-ttu-id="db533-133">Klicka på Intrastat-arkiv.</span><span class="sxs-lookup"><span data-stu-id="db533-133">Click Intrastat archive.</span></span>

    <span data-ttu-id="db533-134">Eftersom det ER-formatet nu innehåller inställningarna för uppdatering av programdata, har informationen om den slutförda Intrastat-rapporteringen arkiverats.</span><span class="sxs-lookup"><span data-stu-id="db533-134">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="db533-135">I det här formuläret visas rubrikposten för det skapade arkivet.</span><span class="sxs-lookup"><span data-stu-id="db533-135">In this form, you can see the header record of the created archive.</span></span>  

4. <span data-ttu-id="db533-136">Klicka på Detaljer.</span><span class="sxs-lookup"><span data-stu-id="db533-136">Click Details.</span></span>

    <span data-ttu-id="db533-137">I det här formuläret visas detaljerna för det skapade arkivet.</span><span class="sxs-lookup"><span data-stu-id="db533-137">In this form, you can see the details for the created archive.</span></span>  

5. <span data-ttu-id="db533-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db533-138">Close the page.</span></span>
6. <span data-ttu-id="db533-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db533-139">Close the page.</span></span>
7. <span data-ttu-id="db533-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="db533-140">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]