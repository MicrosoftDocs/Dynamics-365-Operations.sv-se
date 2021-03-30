---
title: Tilldela användarroller för leasing
description: Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar. Det innehåller även information om hur du tilldelar användare till dessa roller.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 09d80e9629b60144665441989d9d63d7f6be3c60
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207289"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="3b8ef-104">Tilldela användarroller för leasing</span><span class="sxs-lookup"><span data-stu-id="3b8ef-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b8ef-105">Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="3b8ef-106">Det innehåller även information om hur du tilldelar användare till dessa roller.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="3b8ef-107">Tre användarroller differentierar åtkomsten till Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="3b8ef-108">En roll är lämplig för att underhålla leasing, en är lämplig för att visa leasing och en är lämplig att för att utföra en leasinghandläggares uppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="3b8ef-109">Varje roll har specifika behörigheter för alla leasingsidor, och varje användare kan visa, skapa, redigera och ta bort leasingar enligt sina arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="3b8ef-110">Roll</span><span class="sxs-lookup"><span data-stu-id="3b8ef-110">Role</span></span>           | <span data-ttu-id="3b8ef-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="3b8ef-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="3b8ef-112">Upprätthålla leasing</span><span class="sxs-lookup"><span data-stu-id="3b8ef-112">Maintain Lease</span></span> | <span data-ttu-id="3b8ef-113">Användare med den här rollen kan lägga till, redigera, ta bort och visa leasing.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="3b8ef-114">Den här rollen är utformad för dagliga användare vars uppgifter omfattar att skapa och bokföra månatliga journalposter och lägga till nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="3b8ef-115">Den här rollen ger till gång till alla funktioner i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="3b8ef-116">Visa leasing</span><span class="sxs-lookup"><span data-stu-id="3b8ef-116">View Lease</span></span>     | <span data-ttu-id="3b8ef-117">Användare med den här rollen kan bara visa leasingposter, planer och köra rapporter.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="3b8ef-118">De kan inte skapa nya leasingar, redigera befintliga leasingar eller skapa journalposter mot leasingar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="3b8ef-119">Rollen är utformad för användare som bara behöver visa leasingar, leasingplaner och de transaktioner som inträffar mot dessa leasingar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="3b8ef-120">Leasinghandläggare</span><span class="sxs-lookup"><span data-stu-id="3b8ef-120">Lease Clerk</span></span>    | <span data-ttu-id="3b8ef-121">Användare med den här rollen kan bara skapa nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="3b8ef-122">De kan inte redigera eller ta bort befintliga leasingar, visa leasingplaner eller bokföra leasingjournalposter.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="3b8ef-123">Den här rollen är avsedd för användare som arbetar i en datainmatningskapacitet.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="3b8ef-124">Följ dessa steg om du vill tilldela användarna roller som används i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="3b8ef-125">Gå till **Systemadministration \> Säkerhet \> Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="3b8ef-126">Välj rollen **Upprätthålla leasing**, **Leasinghandläggare** eller **Visa leasing** och välj sedan **Tilldela/exkludera användare manuellt**.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="3b8ef-127">Välj användaren som du vill tilldela rollen och välj sedan **Tilldela till roll**.</span><span class="sxs-lookup"><span data-stu-id="3b8ef-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]