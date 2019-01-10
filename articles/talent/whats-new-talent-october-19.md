---
title: "Nyheter och ändringar i Dynamics 365 for Talent Core HR (16 oktober 2018)"
description: "Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 2eb46f436305a4c81ea99553e4dc07288ee74008
ms.openlocfilehash: 7da597a682006cddb44ff9354813b07c15c1a449
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a><span data-ttu-id="eaffd-103">Nyheter och ändringar i Dynamics 365 for Talent Core HR (19 oktober 2018)</span><span class="sxs-lookup"><span data-stu-id="eaffd-103">What's new or changed in Dynamics 365 for Talent Core HR (October 19, 2018)</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="eaffd-104">**Skapa 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="eaffd-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="eaffd-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="eaffd-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="eaffd-106">Tillåt chefer att uppdatera ansökningar om ledig tid</span><span class="sxs-lookup"><span data-stu-id="eaffd-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="eaffd-107">Medarbetares ansökningar om ledig tid kan behöva uppdateras efter att de har godkänts i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="eaffd-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="eaffd-108">I många fall bör chefen göra uppdateringarna för den anställdes räkning.</span><span class="sxs-lookup"><span data-stu-id="eaffd-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="eaffd-109">Funktionen ger möjlighet för chefer att uppdatera ansökningar om ledig tid och avbryta ansökningar om ledig tid på uppdrag av deras anställda.</span><span class="sxs-lookup"><span data-stu-id="eaffd-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="eaffd-110">Funktionen styrs av parametern **Arbeta på uppdrag av** som kan ställas in på sidan **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="eaffd-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="eaffd-111">Tillåter HR att uppdatera ansökningar om ledig tid</span><span class="sxs-lookup"><span data-stu-id="eaffd-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="eaffd-112">Liknande funktionen ovan, kan medarbetares ansökningar om ledig tid behöva uppdateras av HR när de har godkänts tidigare i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="eaffd-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="eaffd-113">Den här funktionen ger möjligheten för HR-användare att uppdatera ansökningar om ledig tid.</span><span class="sxs-lookup"><span data-stu-id="eaffd-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="eaffd-114">Funktionen har aktiverats i arbetsytan **Personer** och på sidan **Arbetare** med hjälp av ett nytt alternativ som heter **Visa ledig tid**.</span><span class="sxs-lookup"><span data-stu-id="eaffd-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="eaffd-115">På dessa sidor kan HR-användare visa förfrågningar och uppdatera ledighetstransaktioner liknande hur chefer kan utföra dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="eaffd-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="eaffd-116">Säkerhetsprogrambehörigheten som styr åtkomsten till funktionen är:</span><span class="sxs-lookup"><span data-stu-id="eaffd-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="eaffd-117">Säkerhet: Underhåll processer för arbetarspecifik tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="eaffd-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="eaffd-118">Privilegium: Underhåll tjänstledighets- och frånvaroansökningar för alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="eaffd-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="eaffd-119">Andra ändringar</span><span class="sxs-lookup"><span data-stu-id="eaffd-119">Other changes</span></span>
<span data-ttu-id="eaffd-120">Följande uppdateringar har gjorts i den här versionen:</span><span class="sxs-lookup"><span data-stu-id="eaffd-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="eaffd-121">Ändringar av arbetares anställningsåtgärder så att de inte längre ”fastnat” i status **Arbetsflödet är slutfört**.</span><span class="sxs-lookup"><span data-stu-id="eaffd-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="eaffd-122">Nu kan medarbetarposter skapas utan anställningens startdatum.</span><span class="sxs-lookup"><span data-stu-id="eaffd-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="eaffd-123">Dynamics 365 Talent-registreringsdatum för en kurs som visas i Självbetjäning för medarbetare används nu på tidszonförskjutningen till datum.</span><span class="sxs-lookup"><span data-stu-id="eaffd-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="eaffd-124">Excel-filer kan importeras flera gånger utan fel med hjälp av **medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="eaffd-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="eaffd-125">Kända problem</span><span class="sxs-lookup"><span data-stu-id="eaffd-125">Known issue</span></span>

- <span data-ttu-id="eaffd-126">**Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade.</span><span class="sxs-lookup"><span data-stu-id="eaffd-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="eaffd-127">**Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda.</span><span class="sxs-lookup"><span data-stu-id="eaffd-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="eaffd-128">Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="eaffd-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="eaffd-129">(Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)</span><span class="sxs-lookup"><span data-stu-id="eaffd-129">(This issue will be fixed in the next platform update.)</span></span>
