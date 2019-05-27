---
title: Skapa konfigurationsleverantörer och markera dem som aktiva
description: I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544919"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="c38d3-103">Skapa konfigurationsleverantörer och markera dem som aktiva</span><span class="sxs-lookup"><span data-stu-id="c38d3-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c38d3-104">I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="c38d3-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="c38d3-105">Alla ER-konfigurationer refererar till leverantören som författare av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c38d3-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="c38d3-106">I det här exemplet ska du skapa en konfigureringsleverantör för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringsleverantörer delas mellan alla företag.</span><span class="sxs-lookup"><span data-stu-id="c38d3-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="c38d3-107">Skapa en leverantör</span><span class="sxs-lookup"><span data-stu-id="c38d3-107">Create a provider</span></span>
1. <span data-ttu-id="c38d3-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="c38d3-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c38d3-109">Klicka på konfigurationsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="c38d3-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="c38d3-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c38d3-110">Click New.</span></span>
    * <span data-ttu-id="c38d3-111">En leverantörspost har ett unikt namn och en unik webbadress.</span><span class="sxs-lookup"><span data-stu-id="c38d3-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="c38d3-112">Granska innehållet på den här sidan och hoppa över den här proceduren om en post för Litware, Inc (http://www.litware.com) redan finns.</span><span class="sxs-lookup"><span data-stu-id="c38d3-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="c38d3-113">Skriv "Litware, Inc." i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="c38d3-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="c38d3-114">Litware Inc.</span><span class="sxs-lookup"><span data-stu-id="c38d3-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="c38d3-115">Skriv in "http://www.litware.com" i fältet för Internetadress.</span><span class="sxs-lookup"><span data-stu-id="c38d3-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * http://www.litware.com  
6. <span data-ttu-id="c38d3-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c38d3-116">Click Save.</span></span>
7. <span data-ttu-id="c38d3-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c38d3-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="c38d3-118">Välj som en aktiv leverantör</span><span class="sxs-lookup"><span data-stu-id="c38d3-118">Select as an active provider</span></span>
1. <span data-ttu-id="c38d3-119">Välj leverantören "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="c38d3-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="c38d3-120">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="c38d3-120">Click Set active.</span></span>

