---
title: ER Konfigurera format för inventering och summering (Del 1 - Skapa format)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2a3b3997b8d366f92192ff765dbcff9b68844ba
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182403"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1-create-format"></a><span data-ttu-id="8ba65-103">ER Konfigurera format för inventering och summering (Del 1: Skapa format)</span><span class="sxs-lookup"><span data-stu-id="8ba65-103">ER Configure format to do counting and summing (Part 1: Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8ba65-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="8ba65-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="8ba65-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="8ba65-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="8ba65-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="8ba65-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="8ba65-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="8ba65-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="8ba65-108">Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ba65-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="8ba65-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="8ba65-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="8ba65-110">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="8ba65-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="8ba65-111">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="8ba65-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="8ba65-112">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="8ba65-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="8ba65-113">leverantör.</span><span class="sxs-lookup"><span data-stu-id="8ba65-113">provider.</span></span>
3. <span data-ttu-id="8ba65-114">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="8ba65-114">Click Repositories.</span></span>
    * <span data-ttu-id="8ba65-115">Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="8ba65-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="8ba65-116">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8ba65-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="8ba65-117">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="8ba65-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="8ba65-118">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="8ba65-118">Click Create repository.</span></span>
7. <span data-ttu-id="8ba65-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8ba65-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="8ba65-120">Hämta Intrastat-konfigurationerna som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ba65-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="8ba65-121">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="8ba65-121">Click Open.</span></span>
2. <span data-ttu-id="8ba65-122">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8ba65-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="8ba65-123">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="8ba65-123">Click Import.</span></span>
    * <span data-ttu-id="8ba65-124">Klicka på Import for version 1.1 för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="8ba65-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="8ba65-125">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="8ba65-125">Click Yes.</span></span>
5. <span data-ttu-id="8ba65-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8ba65-126">Close the page.</span></span>
6. <span data-ttu-id="8ba65-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8ba65-127">Close the page.</span></span>
7. <span data-ttu-id="8ba65-128">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="8ba65-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="8ba65-129">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8ba65-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="8ba65-130">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8ba65-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

