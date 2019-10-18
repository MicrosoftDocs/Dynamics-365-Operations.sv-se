---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (8 oktober 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 330ffebf73c8948a1bbab2ee57acba7b97a93b6f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008883"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-8-2018"></a><span data-ttu-id="254cf-103">Nyheter och ändringar i Dynamics 365 Talent - Core HR (8 oktober 2018)</span><span class="sxs-lookup"><span data-stu-id="254cf-103">What's new or changed in Dynamics 365 Talent - Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="254cf-104">**Skapa 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="254cf-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="254cf-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="254cf-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="254cf-106">Tillåta andra datum att användas för underlag för tjänstledighetsnivå (Hantering av tjänstledighet)</span><span class="sxs-lookup"><span data-stu-id="254cf-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="254cf-107">När medarbetare beviljas tjänstledighet bestämmer underlag för tjänstledighetsnivå hur mycket ledig tid som tillfaller medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="254cf-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="254cf-108">För närvarande baseras dessa nivåer på medarbetarens startdatum och tjänsteålder.</span><span class="sxs-lookup"><span data-stu-id="254cf-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="254cf-109">I vissa fall måste företagen basera dessa nivåer på andra datum såsom jubileumsdatum eller ursprungligt anställningsdatum.</span><span class="sxs-lookup"><span data-stu-id="254cf-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="254cf-110">Datumen används redan på tjänstledighetsplanen för att bestämma när periodiseringar sker, att dessa samma datum ska användas när medarbetaren är anmäld till en plan har lagts till för att fastställa det upplupna beloppet.</span><span class="sxs-lookup"><span data-stu-id="254cf-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="254cf-111">Andra ändringar</span><span class="sxs-lookup"><span data-stu-id="254cf-111">Other changes</span></span>
<span data-ttu-id="254cf-112">Diverse korrigeringar finns i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="254cf-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="254cf-113">Kända problem</span><span class="sxs-lookup"><span data-stu-id="254cf-113">Known issue</span></span>

<span data-ttu-id="254cf-114">**Problem:** när du lägger till en ny bilaga till en arbetare är knapparna **Ny** och **Redigera** nedtonade. **Lösning:** innan du öppnar bilagesidan, se till att faktarutorna på sidan **arbetare** är stängda.</span><span class="sxs-lookup"><span data-stu-id="254cf-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="254cf-115">Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="254cf-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="254cf-116">(Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)</span><span class="sxs-lookup"><span data-stu-id="254cf-116">(This issue will be fixed in the next platform update.)</span></span>
