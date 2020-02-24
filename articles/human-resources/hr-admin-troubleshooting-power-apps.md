---
title: Det går inte att skapa en miljö i administrationscentret för Power Apps
description: Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft Power Apps-administrationscenter.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f4c75706183a3d6c961852395e464d46ba3ec1f2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010566"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="c0a2c-103">Det går inte att skapa en miljö i administrationscentret för Power Apps</span><span class="sxs-lookup"><span data-stu-id="c0a2c-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="c0a2c-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="c0a2c-104">**Issue**</span></span>

- <span data-ttu-id="c0a2c-105">Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft Power Apps Admin center.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="c0a2c-106">En licens som ger användaren rättigheter att utföra steget för att skapa miljö har inte tilldelats direkt till användaren som genomför detta steg.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="c0a2c-107">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="c0a2c-107">**Solution**</span></span>

<span data-ttu-id="c0a2c-108">Se till att klientorganisationens administratör har tilldelats en giltig licens för Power Apps P2 direkt till den användare som ska utföra steget för att skapa miljö.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="c0a2c-109">Här är de Microsoft Dynamics serviceplaner som tillhandahåller denna rättighet.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="c0a2c-110">Total lagerhållningsenhet för produkt (SKU)</span><span class="sxs-lookup"><span data-stu-id="c0a2c-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="c0a2c-111">Power Apps P2 serviceplan</span><span class="sxs-lookup"><span data-stu-id="c0a2c-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="c0a2c-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="c0a2c-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="c0a2c-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c0a2c-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="c0a2c-114">Microsoft Dynamics 365 planen Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c0a2c-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="c0a2c-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c0a2c-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="c0a2c-116">Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående Power Apps plan 2 SKU:er.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="c0a2c-117">Det viktiga är att en av dessa SKU:er måste finnas.</span><span class="sxs-lookup"><span data-stu-id="c0a2c-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="c0a2c-118">Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="c0a2c-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="c0a2c-119">Skapa miljöerna genom att följa instruktionerna i [Etablera Personal](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="c0a2c-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
