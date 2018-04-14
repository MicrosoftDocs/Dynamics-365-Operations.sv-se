--- 
title: "Skapa en konfigurationsleverantör och markera den som aktiv för elektronisk rapportering (ER)"
description: "I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9ed6f62318cd6806de1b4c9d6aa314c5f0a25500
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="b9312-103">Skapa en konfigurationsleverantör och markera den som aktiv för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="b9312-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9312-104">I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="b9312-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="b9312-105">Alla ER-konfigurationer refererar till leverantören som författare av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="b9312-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="b9312-106">I det här exemplet ska du skapa en konfigureringsleverantör för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringsleverantörer delas mellan alla företag.</span><span class="sxs-lookup"><span data-stu-id="b9312-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="b9312-107">Skapa en leverantör</span><span class="sxs-lookup"><span data-stu-id="b9312-107">Create a provider</span></span>
1. <span data-ttu-id="b9312-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="b9312-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b9312-109">Klicka på konfigurationsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="b9312-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="b9312-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b9312-110">Click New.</span></span>
    * <span data-ttu-id="b9312-111">En leverantörspost har ett unikt namn och en unik webbadress.</span><span class="sxs-lookup"><span data-stu-id="b9312-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="b9312-112">Granska innehållet på den här sidan och hoppa över den här proceduren om en post för Litware, Inc (`http://www.litware.com`) redan finns.</span><span class="sxs-lookup"><span data-stu-id="b9312-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="b9312-113">Skriv "Litware, Inc." i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b9312-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="b9312-114">Litware Inc.</span><span class="sxs-lookup"><span data-stu-id="b9312-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="b9312-115">Skriv in `http://www.litware.com` i fältet för Internetadress.</span><span class="sxs-lookup"><span data-stu-id="b9312-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="b9312-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b9312-116">Click Save.</span></span>
7. <span data-ttu-id="b9312-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b9312-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="b9312-118">Välj som en aktiv leverantör</span><span class="sxs-lookup"><span data-stu-id="b9312-118">Select as an active provider</span></span>
1. <span data-ttu-id="b9312-119">Välj leverantören "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="b9312-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="b9312-120">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="b9312-120">Click Set active.</span></span>


