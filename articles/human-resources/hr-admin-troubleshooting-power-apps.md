---
title: Det går inte att skapa en miljö i administrationscentret för Power Apps
description: Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft Power Apps-administrationscenter.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 26a228229a09e74809a048675a3ff90025f2a26c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892237"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="9cacf-103">Det går inte att skapa en miljö i administrationscentret för Power Apps</span><span class="sxs-lookup"><span data-stu-id="9cacf-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9cacf-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="9cacf-104">**Issue**</span></span>

- <span data-ttu-id="9cacf-105">Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft Power Apps Admin center.</span><span class="sxs-lookup"><span data-stu-id="9cacf-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="9cacf-106">Användaren har ingen licens som ger rätt att skapa miljöer.</span><span class="sxs-lookup"><span data-stu-id="9cacf-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="9cacf-107">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="9cacf-107">**Solution**</span></span>

<span data-ttu-id="9cacf-108">Kontrollera att klientorganisationens administratör ar tilldelat en giltig Power Apps P2-licens till användaren som skapar miljön.</span><span class="sxs-lookup"><span data-stu-id="9cacf-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="9cacf-109">Följande Microsoft Dynamics-serviceplaner ger behörigheter att skapa miljöer:</span><span class="sxs-lookup"><span data-stu-id="9cacf-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="9cacf-110">Total lagerhållningsenhet för produkt (SKU)</span><span class="sxs-lookup"><span data-stu-id="9cacf-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="9cacf-111">Power Apps P2 serviceplan</span><span class="sxs-lookup"><span data-stu-id="9cacf-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="9cacf-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="9cacf-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="9cacf-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9cacf-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="9cacf-114">Microsoft Dynamics 365 planen Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="9cacf-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="9cacf-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9cacf-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="9cacf-116">Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående Power Apps plan 2 SKU:er.</span><span class="sxs-lookup"><span data-stu-id="9cacf-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="9cacf-117">Det viktiga är att en av dessa SKU:er måste finnas.</span><span class="sxs-lookup"><span data-stu-id="9cacf-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="9cacf-118">Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="9cacf-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="9cacf-119">Skapa miljöerna genom att följa instruktionerna i [Etablera Personal](/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="9cacf-119">Create the environments by following the instructions in [Provision Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]