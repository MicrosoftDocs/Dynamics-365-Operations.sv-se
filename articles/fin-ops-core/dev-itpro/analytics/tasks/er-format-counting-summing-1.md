---
title: ER Konfigurera format för inventering och summering (Del 1 - Skapa format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 64bf9f48319029e835f9e3fe2b888625100cc408
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565153"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="433fb-104">ER Konfigurera format för inventering och summering (Del 1 - Skapa format)</span><span class="sxs-lookup"><span data-stu-id="433fb-104">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="433fb-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="433fb-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="433fb-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="433fb-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="433fb-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="433fb-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="433fb-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="433fb-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="433fb-109">Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="433fb-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="433fb-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="433fb-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="433fb-111">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="433fb-111">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="433fb-112">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="433fb-112">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="433fb-113">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="433fb-113">Select the "Litware, Inc."</span></span> <span data-ttu-id="433fb-114">leverantör.</span><span class="sxs-lookup"><span data-stu-id="433fb-114">provider.</span></span>
3. <span data-ttu-id="433fb-115">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="433fb-115">Click Repositories.</span></span>
    * <span data-ttu-id="433fb-116">Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="433fb-116">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="433fb-117">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="433fb-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="433fb-118">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="433fb-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="433fb-119">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="433fb-119">Click Create repository.</span></span>
7. <span data-ttu-id="433fb-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="433fb-120">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="433fb-121">Hämta Intrastat-konfigurationerna som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="433fb-121">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="433fb-122">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="433fb-122">Click Open.</span></span>
2. <span data-ttu-id="433fb-123">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="433fb-123">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="433fb-124">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="433fb-124">Click Import.</span></span>
    * <span data-ttu-id="433fb-125">Klicka på Import for version 1.1 för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="433fb-125">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="433fb-126">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="433fb-126">Click Yes.</span></span>
5. <span data-ttu-id="433fb-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="433fb-127">Close the page.</span></span>
6. <span data-ttu-id="433fb-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="433fb-128">Close the page.</span></span>
7. <span data-ttu-id="433fb-129">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="433fb-129">Click Reporting configurations.</span></span>
8. <span data-ttu-id="433fb-130">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="433fb-130">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="433fb-131">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="433fb-131">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]