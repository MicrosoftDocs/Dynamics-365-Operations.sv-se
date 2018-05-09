--- 
title: "Skapa format för inventering och summering"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c20f2190e6480b6586d8102c489633d748d85a95
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-format-for-counting-and-summing"></a><span data-ttu-id="0d079-103">Skapa format för inventering och summering</span><span class="sxs-lookup"><span data-stu-id="0d079-103">Create format for counting and summing</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d079-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="0d079-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="0d079-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="0d079-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="0d079-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="0d079-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="0d079-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="0d079-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="0d079-108">Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d079-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="0d079-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="0d079-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="0d079-110">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="0d079-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="0d079-111">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="0d079-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="0d079-112">Välj Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="0d079-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="0d079-113">leverantör.</span><span class="sxs-lookup"><span data-stu-id="0d079-113">provider.</span></span>
3. <span data-ttu-id="0d079-114">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="0d079-114">Click Repositories.</span></span>
    * <span data-ttu-id="0d079-115">Om en databas av typen "Operations resources" redan finns, hoppa då över återstående steg för den aktuella underuppgiften.</span><span class="sxs-lookup"><span data-stu-id="0d079-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="0d079-116">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0d079-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="0d079-117">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="0d079-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="0d079-118">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="0d079-118">Click Create repository.</span></span>
7. <span data-ttu-id="0d079-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0d079-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="0d079-120">Hämta Intrastat-konfigurationerna som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d079-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="0d079-121">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="0d079-121">Click Open.</span></span>
2. <span data-ttu-id="0d079-122">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="0d079-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="0d079-123">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="0d079-123">Click Import.</span></span>
    * <span data-ttu-id="0d079-124">Klicka på Import for version 1.1 för den valda konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0d079-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="0d079-125">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="0d079-125">Click Yes.</span></span>
5. <span data-ttu-id="0d079-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0d079-126">Close the page.</span></span>
6. <span data-ttu-id="0d079-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0d079-127">Close the page.</span></span>
7. <span data-ttu-id="0d079-128">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="0d079-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="0d079-129">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="0d079-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="0d079-130">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="0d079-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


