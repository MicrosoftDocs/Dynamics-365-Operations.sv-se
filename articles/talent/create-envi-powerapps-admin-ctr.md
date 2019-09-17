---
title: Det går inte att skapa en miljö i PowerApps administrationscenter
description: Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft PowerApps-administrationscenter.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742852"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a><span data-ttu-id="4dec3-103">Det går inte att skapa en miljö i administrationscentret för PowerApps</span><span class="sxs-lookup"><span data-stu-id="4dec3-103">Can't create an environment in the PowerApps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4dec3-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="4dec3-104">**Issue**</span></span>

- <span data-ttu-id="4dec3-105">Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft PowerApps Admin center.</span><span class="sxs-lookup"><span data-stu-id="4dec3-105">The tenant/environment admin can't create an environment in the Microsoft PowerApps Admin center.</span></span>
- <span data-ttu-id="4dec3-106">En licens som ger användaren rättigheter att utföra steget för att skapa miljö har inte tilldelats direkt till användaren som genomför detta steg.</span><span class="sxs-lookup"><span data-stu-id="4dec3-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="4dec3-107">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="4dec3-107">**Solution**</span></span>

<span data-ttu-id="4dec3-108">Se till att klientorganisationens administratör har tilldelats en giltig licens för PowerApps P2 direkt till den användare som ska utföra steget för att skapa miljö.</span><span class="sxs-lookup"><span data-stu-id="4dec3-108">Make sure that the tenant admin has assigned a valid PowerApps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="4dec3-109">Här är de Microsoft Dynamics serviceplaner som tillhandahåller denna rättighet.</span><span class="sxs-lookup"><span data-stu-id="4dec3-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="4dec3-110">Total lagerhållningsenhet för produkt (SKU)</span><span class="sxs-lookup"><span data-stu-id="4dec3-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="4dec3-111">PowerApps P2 serviceplan</span><span class="sxs-lookup"><span data-stu-id="4dec3-111">PowerApps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="4dec3-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="4dec3-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="4dec3-113">PowerApps för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4dec3-113">PowerApps for Dynamics 365</span></span> |
| <span data-ttu-id="4dec3-114">Microsoft Dynamics 365 planen Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4dec3-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="4dec3-115">PowerApps för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4dec3-115">PowerApps for Dynamics 365</span></span> |

<span data-ttu-id="4dec3-116">Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående PowerApps Plan 2 SKU:er.</span><span class="sxs-lookup"><span data-stu-id="4dec3-116">Note that various Microsoft Office SKUs also provide the right, together with standalone PowerApps Plan 2 SKUs.</span></span> <span data-ttu-id="4dec3-117">Det viktiga är att en av dessa SKU:er måste finnas.</span><span class="sxs-lookup"><span data-stu-id="4dec3-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="4dec3-118">Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="4dec3-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="4dec3-119">Skapa miljöerna genom att följa instruktionerna i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="4dec3-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
