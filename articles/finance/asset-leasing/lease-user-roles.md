---
title: Tilldela användarroller för leasing
description: Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar. Det innehåller även information om hur du tilldelar användare till dessa roller.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 05728f5027dc079dd413dde1c3aa78cddcea136b
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881070"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="48dc4-104">Tilldela användarroller för leasing</span><span class="sxs-lookup"><span data-stu-id="48dc4-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48dc4-105">Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="48dc4-106">Det innehåller även information om hur du tilldelar användare till dessa roller.</span><span class="sxs-lookup"><span data-stu-id="48dc4-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="48dc4-107">Tre användarroller differentierar åtkomsten till Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="48dc4-108">En roll är lämplig för att underhålla leasing, en är lämplig för att visa leasing och en är lämplig att för att utföra en leasinghandläggares uppgifter.</span><span class="sxs-lookup"><span data-stu-id="48dc4-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="48dc4-109">Varje roll har specifika behörigheter för alla leasingsidor, och varje användare kan visa, skapa, redigera och ta bort leasingar enligt sina arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="48dc4-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="48dc4-110">Roll</span><span class="sxs-lookup"><span data-stu-id="48dc4-110">Role</span></span>           | <span data-ttu-id="48dc4-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="48dc4-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="48dc4-112">Upprätthålla leasing</span><span class="sxs-lookup"><span data-stu-id="48dc4-112">Maintain Lease</span></span> | <span data-ttu-id="48dc4-113">Användare med den här rollen kan lägga till, redigera, ta bort och visa leasing.</span><span class="sxs-lookup"><span data-stu-id="48dc4-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="48dc4-114">Den här rollen är utformad för dagliga användare vars uppgifter omfattar att skapa och bokföra månatliga journalposter och lägga till nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="48dc4-115">Den här rollen ger till gång till alla funktioner i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="48dc4-116">Visa leasing</span><span class="sxs-lookup"><span data-stu-id="48dc4-116">View Lease</span></span>     | <span data-ttu-id="48dc4-117">Användare med den här rollen kan bara visa leasingposter, planer och köra rapporter.</span><span class="sxs-lookup"><span data-stu-id="48dc4-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="48dc4-118">De kan inte skapa nya leasingar, redigera befintliga leasingar eller skapa journalposter mot leasingar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="48dc4-119">Rollen är utformad för användare som bara behöver visa leasingar, leasingplaner och de transaktioner som inträffar mot dessa leasingar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="48dc4-120">Leasinghandläggare</span><span class="sxs-lookup"><span data-stu-id="48dc4-120">Lease Clerk</span></span>    | <span data-ttu-id="48dc4-121">Användare med den här rollen kan bara skapa nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="48dc4-122">De kan inte redigera eller ta bort befintliga leasingar, visa leasingplaner eller bokföra leasingjournalposter.</span><span class="sxs-lookup"><span data-stu-id="48dc4-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="48dc4-123">Den här rollen är avsedd för användare som arbetar i en datainmatningskapacitet.</span><span class="sxs-lookup"><span data-stu-id="48dc4-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="48dc4-124">Följ dessa steg om du vill tilldela användarna roller som används i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="48dc4-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="48dc4-125">Gå till **Systemadministration \> Säkerhet \> Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="48dc4-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="48dc4-126">Välj rollen **Upprätthålla leasing**, **Leasinghandläggare** eller **Visa leasing** och välj sedan **Tilldela/exkludera användare manuellt**.</span><span class="sxs-lookup"><span data-stu-id="48dc4-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="48dc4-127">Välj användaren som du vill tilldela rollen och välj sedan **Tilldela till roll**.</span><span class="sxs-lookup"><span data-stu-id="48dc4-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
