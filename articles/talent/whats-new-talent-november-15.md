---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (15 november 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "857325"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="f2248-103">Nyheter och ändringar i Dynamics 365 for Talent Core HR (15 november 2018)</span><span class="sxs-lookup"><span data-stu-id="f2248-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2248-104">**Skapa 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="f2248-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="f2248-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="f2248-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="f2248-106">Andra ändringar/korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f2248-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="f2248-107">Det går inte att ändra medarbetarens nuvarande befattning till en framtida ledig befattning</span><span class="sxs-lookup"><span data-stu-id="f2248-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="f2248-108">En ändring har gjorts för att aktivera befattningsöverföringar när befattningen bara finns i framtiden.</span><span class="sxs-lookup"><span data-stu-id="f2248-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="f2248-109">Befattningen visas inte när du skapar en ny medarbetare</span><span class="sxs-lookup"><span data-stu-id="f2248-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="f2248-110">En ändring har gjorts för att visa alla lediga befattningar som är tillgängliga för tilldelning när du anställer en ny medarbetare i Talent.</span><span class="sxs-lookup"><span data-stu-id="f2248-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="f2248-111">Detta inkluderar historiska befattningar eller om befattningarna har framtida datum.</span><span class="sxs-lookup"><span data-stu-id="f2248-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="f2248-112">Befattningar visas nu på rätt sätt, baserat på anställningens startdatum.</span><span class="sxs-lookup"><span data-stu-id="f2248-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="f2248-113">Uppsägningsdatum visas baserat på användarinställningar</span><span class="sxs-lookup"><span data-stu-id="f2248-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="f2248-114">En ändring har gjorts i listan över tidigare anställda för att ta hänsyn till de tidszonsförskjutningar för den prioriterade medarbetarens tidszon när de visade uppsägningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="f2248-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="f2248-115">Arbetsuppgifter som tilldelats till mig visar inte korrekt information</span><span class="sxs-lookup"><span data-stu-id="f2248-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="f2248-116">Med denna ändring, om du navigerar till detaljerad information om enskilda arbetsuppgifter i listan kommer korrekt information för den valda artikeln att visas.</span><span class="sxs-lookup"><span data-stu-id="f2248-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="f2248-117">Det här problemet uppstod endast med avancerade säkerhetsalternativ.</span><span class="sxs-lookup"><span data-stu-id="f2248-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="f2248-118">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f2248-118">Known issue</span></span>

- <span data-ttu-id="f2248-119">**Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade.</span><span class="sxs-lookup"><span data-stu-id="f2248-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="f2248-120">**Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda.</span><span class="sxs-lookup"><span data-stu-id="f2248-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="f2248-121">Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f2248-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="f2248-122">(Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)</span><span class="sxs-lookup"><span data-stu-id="f2248-122">(This issue will be fixed in the next platform update.)</span></span>
