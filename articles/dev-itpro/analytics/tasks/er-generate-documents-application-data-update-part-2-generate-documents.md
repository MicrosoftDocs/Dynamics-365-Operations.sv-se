--- 
title: "Utforma konfigurationer för att skapa dokument som omfattar programdata"
description: "Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Skapa dokument med uppdatering av programdata (Del 1: Importera konfigurationer)."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 8376107a33dd83e04f82fcab6847e7f073f08dbc
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="35f02-103">Utforma konfigurationer för att skapa dokument som omfattar programdata</span><span class="sxs-lookup"><span data-stu-id="35f02-103">Design configurations to generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="35f02-104">Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Skapa dokument med uppdatering av programdata (Del 1: Importera konfigurationer).</span><span class="sxs-lookup"><span data-stu-id="35f02-104">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="35f02-105">Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument.</span><span class="sxs-lookup"><span data-stu-id="35f02-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="35f02-106">I den här proceduren ska du köra den importerade ER-formatkonfigurationen som har skapats för exempelföretaget Litware, Inc. för att skapa elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="35f02-106">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="35f02-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="35f02-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="35f02-108">Stegen kan utföras med hjälp av datauppsättningen DEMF.</span><span class="sxs-lookup"><span data-stu-id="35f02-108">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="35f02-109">Innan du börjar ska du ändra land för DEMF-företaget från DEU (Tyskland) till BEL (Belgien).</span><span class="sxs-lookup"><span data-stu-id="35f02-109">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="35f02-110">Klicka på Organisationsadministration > Organisationer > Juridiska personer för att uppdatera landskoden i den primära adressen för den juridiska personen DEMF.</span><span class="sxs-lookup"><span data-stu-id="35f02-110">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="35f02-111">Starta om programmet.</span><span class="sxs-lookup"><span data-stu-id="35f02-111">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="35f02-112">Kör det importerade ER-formatet</span><span class="sxs-lookup"><span data-stu-id="35f02-112">Run imported ER format</span></span>
1. <span data-ttu-id="35f02-113">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="35f02-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="35f02-114">Expandera Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="35f02-114">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="35f02-115">Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.</span><span class="sxs-lookup"><span data-stu-id="35f02-115">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="35f02-116">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="35f02-116">Click Run.</span></span>
    * <span data-ttu-id="35f02-117">Kör utkastversionen av ER-formatkonfigurationen för att skapa Intrastat-rapporten.</span><span class="sxs-lookup"><span data-stu-id="35f02-117">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="35f02-118">Skriv "intrastat.xml" i fältet Ange filnamn.</span><span class="sxs-lookup"><span data-stu-id="35f02-118">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="35f02-119">Ange namnet på filen.</span><span class="sxs-lookup"><span data-stu-id="35f02-119">Specify the name of the file.</span></span>  
6. <span data-ttu-id="35f02-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="35f02-120">Click OK.</span></span>
    * <span data-ttu-id="35f02-121">Granska den skapade XML-filen.</span><span class="sxs-lookup"><span data-stu-id="35f02-121">Review the generated XML file.</span></span>  
7. <span data-ttu-id="35f02-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="35f02-122">Close the page.</span></span>
8. <span data-ttu-id="35f02-123">Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="35f02-123">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="35f02-124">Öppna detta formulär när du vill visa Intrastat-transaktionerna som ingår i det skapade elektroniska dokumentet.</span><span class="sxs-lookup"><span data-stu-id="35f02-124">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="35f02-125">Klicka på Intrastat-arkiv.</span><span class="sxs-lookup"><span data-stu-id="35f02-125">Click Intrastat archive.</span></span>
    * <span data-ttu-id="35f02-126">Eftersom det ER-format som körts inte innehåller några inställningar för uppdatering av programdata, arkiverades inte informationen om den slutförda Intrastat-rapporten.</span><span class="sxs-lookup"><span data-stu-id="35f02-126">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="35f02-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="35f02-127">Close the page.</span></span>
11. <span data-ttu-id="35f02-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="35f02-128">Close the page.</span></span>


